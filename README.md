## 🔐Cybersecurity Lab Environment Setup

Building an isolated virtual lab for penetration testing and ethical hacking practice.

Cybersecurity VirtualBox Kali Linux Networking 10.0.0.0/24 Penetration Testing Virtualization Ethical Hacking


## 📌Project Overview

This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.

The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.

## 🧩Lab Configuration

The cybersecurity lab is configured in a virtualized environment using VirtualBox and Kali Linux. The setup is designed for controlled security testing and practical cybersecurity exercises.

Component| Configuration
Host OS| Windows 10
Host RAM| 8 GB
Processor| Intel Core i7
Hypervisor| VirtualBox 7.2
Security OS| Kali Linux 2026.2
Kali Linux RAM| 2048 MB (2 GB)
Virtual Network| NAT Network
Network Address| "10.0.0.0/24"
Kali Linux IP Address| "10.0.0.2/24"
Default Gateway| "10.0.0.1"
DNS Server| "8.8.8.8"
Future VM IP Range| "10.0.0.3–10.0.0.99"

## 🎯Setup Steps

1. Installed 7-Zip for file extraction
2. Installed the latest version of VirtualBox
3. Created a custom NAT Network (NatNetwork) with subnet 10.0.0.0/24, DHCP enabled
4. Downloaded and imported the Kali Linux VirtualBox image
5. Assigned Kali Linux a static IP: 10.0.0.2/24, gateway 10.0.0.1
6. Enabled Bidirectional Clipboard and Drag & Drop in VM settings
7. Enabled Shared Folders, mapping the host's Downloads folder with Auto-mount
8. Verified internet connectivity from Kali Linux
9. Took a snapshot of the clean, working VM state

## 🔗Tools Used

1. Oracle VisualBox
2. Kali Linux
3. 7-zip

## 💡Lessons Learned

Through this lab setup, I gained practical experience in preparing a virtualized environment for cybersecurity practice.

## 🧠Troubleshooting Experience

*Problem:* After configuring a static IP on Kali Linux, internet connectivity was lost.

*Solution:* This is a known issue on newer VirtualBox/Kali versions. Fixed it by running:
```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"

