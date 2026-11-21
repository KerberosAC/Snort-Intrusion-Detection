# Screenshot Identification Guide

All screenshots below were sourced from `Cyber Home Lab Doc 1.docx` and reviewed against the content of each image. The source images had already been curated in the Cybersecurity Virtual Lab project; the first column is the source-extraction filename.

| Source screenshot | GitHub screenshot | Visible evidence |
|---|---|---|
| `49-snort-vm-virtualbox-settings.png` | `screenshots/01-snort-vm-virtualbox-settings.png` | SnortVM virtual hardware: Ubuntu 64-bit, 4096 MB RAM, two CPUs, 45 GB virtual disk and mounted Ubuntu installer image. |
| `02-kali-internal-network-vulnlabs.png` | `screenshots/02-kali-internal-lab-network.png` | Kali adapter set to an internal network named VulnLabs during one configuration stage; does not establish SnortVM adapter membership. |
| `18-ubuntu-server-installation-snortvm.png` | `screenshots/03-snortvm-ubuntu-installation.png` | Ubuntu installer running in the VM named SnortVM(IDS). |
| `19-ubuntu-server-terminal-setup.png` | `screenshots/04-snortvm-installer-network-settings.png` | Ubuntu installer shows enp0s3 at 192.168.100.216/24 and enp0s8 at 172.30.1.23/24 at this point in setup. |
| `20-ubuntu-server-post-install-console.png` | `screenshots/05-ubuntu-post-install-update.png` | Later booted console reports Ubuntu 24.04.5 LTS, enp0s3 address 192.168.100.216, and sudo apt-get update. |
| `05-kali-network-interface-configuration.png` | `screenshots/06-kali-network-interface-ip.png` | ip address on Kali: eth0 192.168.100.207/24 and eth1 172.30.1.20/24 in a recorded lab stage. |
| `21-kali-ubuntu-reachability-validation.png` | `screenshots/07-kali-ping-172-30-1-26.png` | Kali ping 172.30.1.26 returns five successful replies and zero packet loss. |
| `22-snort-installation-workflow.png` | `screenshots/08-snort-config-validation.png` | Snort 2.9.20 prints configuration validation success; the shell shows the -T config test command. |
| `24-snort-monitoring-output.png` | `screenshots/09-snort-console-icmp-alerts.png` | Snort console events include ICMP PING speedera, Large ICMP Detected Alex, and ICMP has been Detected between 172.30.1.20 and 172.30.1.26. |
| `23-snort-test-traffic-or-logs.png` | `screenshots/10-snort-saved-log-review-command.png` | Terminal shows sudo snort -v -r /var/log/snort/snort.log.1792625255 | less; no resulting listing is visible. |
| `25-nmap-scan-during-ids-testing.png` | `screenshots/11-kali-nmap-syn-scan.png` | nmap -sS 172.30.1.26 reports host up, port 22/tcp SSH open, and 999 scanned ports closed. |

## Notes

- The Ubuntu ISO shown in the VirtualBox VM details is not the same version as the later booted Ubuntu screen; both are presented as separate stages.
- `172.30.1.23` appears on the SnortVM installer screen. `172.30.1.26` appears in later ping, Snort, and Nmap evidence; a precise address-change history was not provided.
- The Snort alerts demonstrate detection and logging, not traffic prevention.
- The source does not include raw Snort rules or a full PCAP; do not add reconstructed rules to the README as though they were original evidence.
