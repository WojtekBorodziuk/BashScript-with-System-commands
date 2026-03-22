# Linux System Security & Enumeration Tool

## Overview
This repository contains a comprehensive Bash script designed to automate system enumeration, security auditing, and baseline documentation for Linux environments. Originally tailored for Debian/Kali-based systems, it executes a series of core commands to gather deep insights into the host's current state, running services, network configuration, and security posture.

## Features
The script automates the collection of critical system data, outputting it into a neatly formatted, timestamped text file. Key enumeration areas include:
* **Process & Resource Monitoring:** Identifies high-memory processes, root-owned processes, and specific user activities.
* **Package & Service Auditing:** Verifies installed packages (e.g., `openssh-server`, `vsftpd`), recent package modifications, and systemctl service states.
* **Network Posture:** Dumps active listening ports (`ss -tulnp`), routing tables, DNS configurations, and performs local port scanning (`nmap`).
* **User & Permissions:** Extracts user accounts from `/etc/passwd` with shell access and lists `sudo` group members.
* **Security Configurations:** Audits `iptables` rules, `AppArmor` status, and root's scheduled tasks (`crontab`).
* **Hardware & OS Specs:** Gathers kernel version, CPU info, memory availability, and disk space usage.

## Usage
1. Clone this repository to your target machine.
2. Grant execution permissions to the script:
```bash
chmod +x gather_info.sh
3. Run the script (running as root or with sudo is recommended to capture complete data, such as iptables and root crontab)
sudo ./gather_info.sh
4. A report file will be generated in the current working directory in the format: report_<hostname>_<YYYYMMDD_HHMMSS>.txt
```
