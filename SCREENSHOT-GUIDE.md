# Screenshot guide — Snort-only evidence

Original source: `Cyber Home Lab Doc 1.docx` (embedded `word/media/imageN.png`).

These screenshots were selected specifically for the Ubuntu/Snort intrusion-detection exercise. The first image is Kali's network configuration relevant to the Snort tests; the remainder are the contiguous Snort/Ubuntu sequence. **pfSense begins at the original `image49.png` and was deliberately excluded.**

| Source image | Renamed file | What it actually shows |
|---|---|---|
| `image8.png` | `screenshots/01-kali-network-interfaces.png` | Kali `ip address` output: eth1 on 172.30.1.20/24; eth0 on a separate subnet. |
| `image26.png` | `screenshots/02-snortvm-virtualbox-overview.png` | VirtualBox configuration of SnortVM(IDS), its Ubuntu guest OS and allocated resources. |
| `image25.png` | `screenshots/03-ubuntu-server-download.png` | Ubuntu Server download page consulted during lab preparation. |
| `image27.png` | `screenshots/04-ubuntu-server-install-options.png` | Ubuntu Server installation-option screen. |
| `image28.png` | `screenshots/05-ubuntu-installer-network-configuration.png` | Ubuntu installer showing available virtual network interfaces. |
| `image31.png` | `screenshots/06-ubuntu-installation-progress.png` | Ubuntu Server installation/progress screen. |
| `image29.png` | `screenshots/07-ubuntu-server-post-install-setup.png` | Ubuntu Server console following installation. |
| `image30.png` | `screenshots/08-kali-ping-test.png` | Kali successfully pinging 172.30.1.26 with five replies and zero packet loss. |
| `image32.png` | `screenshots/09-snort-conf-edit-in-nano.png` | Editing /etc/snort/snort.conf with GNU nano. |
| `image33.png` | `screenshots/10-snort-home-net-settings.png` | Snort HOME_NET set to 172.30.1.0/24 in snort.conf. |
| `image34.png` | `screenshots/11-snort-configuration-validation.png` | Snort 2.9.20 output reporting successful configuration validation. |
| `image35.png` | `screenshots/12-snort-rule-engine-initialization.png` | Snort rule engine/initialization output from the validation workflow. |
| `image36.png` | `screenshots/13-custom-rule-icmp-initial.png` | First custom local.rules signature: ICMP detection, SID 1000001. |
| `image37.png` | `screenshots/14-local-rules-and-monitor-command.png` | ICMP rule in local.rules and Snort live-monitoring command visible in terminal. |
| `image38.png` | `screenshots/15-initial-icmp-console-alerts.png` | Snort console monitoring alongside Kali ping traffic. |
| `image39.png` | `screenshots/16-snort-saved-log-command.png` | Command for reading a saved Snort packet log with less. |
| `image40.png` | `screenshots/17-snort-replayed-icmp-packets.png` | Saved-log review showing ICMP Echo and Echo Reply packet data. |
| `image41.png` | `screenshots/18-icmp-and-large-icmp-rules.png` | Custom ICMP and large-payload ICMP rules, SIDs 1000001 and 1000002. |
| `image42.png` | `screenshots/19-kali-standard-and-large-ping.png` | Standard ping and ping -s 501 tests from Kali. |
| `image43.png` | `screenshots/20-large-icmp-alert-results.png` | Snort alerts for standard and large ICMP packets, including the SID 1000002 rule. |
| `image44.png` | `screenshots/21-five-custom-snort-rules.png` | All five custom local.rules signatures for ICMP, large ICMP, FTP, SSH and a protected HTTP path. |
| `image45.png` | `screenshots/22-ssh-connection-test.png` | Kali SSH connection attempt to 172.30.1.26 and initial host-key verification prompt. |
| `image46.png` | `screenshots/23-ssh-custom-rule-alerts.png` | Snort SSH connection detected events with custom SID 1000004. |
| `image47.png` | `screenshots/24-nmap-syn-scan-test.png` | Kali nmap -sS against 172.30.1.26 showing 22/tcp open. |
| `image48.png` | `screenshots/25-follow-up-snort-alerts.png` | Follow-up Snort console showing custom SSH events and built-in SNMP-related signatures. |

## Custom-rule evidence

- `image36.png`: first ICMP rule (SID 1000001).
- `image41.png`: added size-aware ICMP rule (SID 1000002).
- `image44.png`: the full five-rule set (SIDs 1000001–1000005).
- `image43.png`: console matches for ICMP SIDs 1000001 and 1000002.
- `image46.png`: console matches for SSH SID 1000004.

The screenshot set does **not** independently demonstrate a successful FTP or protected-HTTP-path rule match. Their definitions are included as authored rules, with this limitation noted in the README.
