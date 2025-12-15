# Firewall Rules + IDS (Snort) Simulation Lab

## Author: **Ayan Dhokle**  

##  Project Overview
This lab demonstrates how firewall rules and an Intrusion Detection System (IDS) work together to secure a network. The project focuses on configuring firewall rules, installing and running Snort IDS, simulating basic attacks, and analyzing alerts.

This project is aligned with **CompTIA Network+ security objectives**.

---

## Objectives
- Configure firewall rules to allow and deny traffic
- Understand port-based traffic filtering
- Install and configure Snort IDS
- Simulate network reconnaissance attacks
- Observe and analyze IDS alerts and logs

---

## Lab Environment

### Virtual Machines

 Attacker : Kali Linux <br>
 Defender : Ubuntu Server

### Network Configuration
- **VirtualBox Network Mode:** Host-Only Adapter
- Isolated and safe lab environment

---

## Firewall Configuration (UFW)

### Enable Firewall
```bash
sudo ufw enable
```

### Allow SSH (Port 22)
```bash
sudo ufw allow 22
```

### Deny HTTP Traffic (Port 80)
```bash
sudo ufw deny 80
```

### Verify Rules
```bash
sudo ufw status numbered
```

**Concepts Learned:**
- Firewall rules
- Allow vs deny policies
- Port-based filtering

---

## IDS Setup (Snort)

### Install Snort
```bash
sudo apt update
sudo apt install snort -y
```

### Start Snort in IDS Mode
```bash
sudo snort -A console -q -c /etc/snort/snort.conf -i enp0s3
```

**Expected Output:**
```
Commencing packet processing
```
(This indicates Snort is running and monitoring traffic.)

---

## Attack Simulation (From Kali Linux)

### ICMP Test
```bash
ping <Ubuntu-IP>
```

### Nmap Port Scan
```bash
nmap -sS <Ubuntu-IP>
```

### Result
- Snort detects reconnaissance activity
- Alerts displayed on the console

---

## Alert & Log Analysis

### View Alert Logs
```bash
sudo cat /var/log/snort/alert
```

**Concepts Learned:**
- IDS alerts
- Log analysis
- Indicators of compromise

---

## Network+ Concepts Covered
- Firewalls and ACLs
- Ports and protocols
- IDS vs IPS
- Network reconnaissance
- Security monitoring and logging

---

## Key Takeaways
- Firewalls **prevent** unauthorized access
- IDS **detects and alerts** on suspicious activity
- Logs are critical for investigation and forensics

---

## Disclaimer
This project was performed in an isolated lab environment for educational purposes only.

---
