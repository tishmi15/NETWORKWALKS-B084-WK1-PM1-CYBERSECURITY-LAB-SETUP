# Week 1 – Cybersecurity Lab Setup

## Project Overview
This project focuses on creating a virtual cybersecurity testing lab using Oracle VirtualBox and Kali Linux.

## Objectives
- Install and configure Oracle VirtualBox.
- Set up Kali Linux as an attacking machine.
- Configure a NAT Network.
- Configure the network subnet as `10.0.0.0/24`.
- Assign a static IP address to Kali Linux.
- Configure shared folders, clipboard, and drag-and-drop.
- Test network connectivity and Internet access.
- Create a Virtual Machine snapshot.

## Lab Configuration

| Component | Configuration |
|---|---|
| Virtualization Platform | Oracle VirtualBox |
| Operating System | Kali Linux |
| Network Mode | NAT Network |
| Network Subnet | 10.0.0.0/24 |
| Kali IP Address | 10.0.0.2/24 |
| Default Gateway | 10.0.0.1 |
| Network Interface | eth0 |
| Shared Folder | downloads |
| Snapshot | WK1-PM1-Kali-Setup-Completed |

## Tasks Completed
1. Installed and configured VirtualBox.
2. Created a Kali Linux virtual machine.
3. Configured the NAT Network.
4. Configured the Kali network interface.
5. Assigned the static IP address.
6. Configured the shared folder.
7. Enabled Shared Clipboard and Drag and Drop.
8. Tested gateway connectivity.
9. Tested Internet and DNS connectivity.
10. Created a VM snapshot.

## Troubleshooting Experience

### Issue 1: Network Interface Was Down
**Problem:** The Kali network interface `eth0` was initially down.

**Solution:**
```bash
sudo ip link set eth0 up
```

### Issue 2: NetworkManager Command Not Found
**Problem:** The `nmcli` command was unavailable in the minimal Kali installation.

**Solution:** Used the Linux `ip` command to enable the network interface.

### Issue 3: Internet Connection Was Unavailable
**Problem:** The default gateway route was missing.

**Solution:**
```bash
sudo ip route replace default via 10.0.0.1 dev eth0
```

DNS was configured using:
```bash
sudo sh -c 'echo "nameserver 8.8.8.8" > /etc/resolv.conf'
```

## Connectivity Testing
- Gateway connectivity: Successful.
- Internet connectivity: Successful.
- DNS resolution: Successful.

## Snapshot
Created a VirtualBox snapshot named:

`WK1-PM1-Kali-Setup-Completed`

## Learning Outcomes
Through this project, I gained practical experience in virtualization, Kali Linux configuration, network interfaces, IP addressing, NAT networking, troubleshooting, and basic network connectivity testing.

## Disclaimer
This lab was created for educational purposes in my own authorized virtual environment.
