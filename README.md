# 🔐 12th Project - Network Security (TLS, SSH, Snort)

## 📚 Overview

This repository documents the implementation of three major components in network security using virtual machines:

1. **TLS Configuration** between client and server.
2. **SSH Key-Based Authentication**.
3. **Snort IDS Integration** with a custom network setup.

All tasks were executed using **Linux Mint** and **Metasploitable2** VMs, configured and monitored through **pfSense** and **Wireshark**.

---

## 🧑‍🏫 Project Details

- **Lecturer**: Dr. Ayman Adel Abdelhamid  
- **T.A.**: Abdelrhman Solyman  
- **Students**:
  - Mohamed Elsayed Mohamed (ID: 221010750)
  - Omar Sherif Hosny (ID: 221010339)

---

## 📁 Contents

### 🔐 Part 1: TLS Implementation

- Created Root Certificate Authority (CA) with RSA 2048-bit encryption.
- Generated server and client keys and certificates.
- Implemented SAN (Subject Alternative Name) using `san.cnf`.
- Verified certificate integrity using `openssl` and `grep`.
- Built a basic TLS server using Python.
- Captured and decrypted TLS traffic using Wireshark by setting the `SSLKEYLOGFILE`.

### 🔒 Part 2: SSH Key-Based Authentication

- Installed OpenSSH server/client on both Linux Mint VMs.
- Created a user (`omar221010339`) on the server.
- Connected initially using password, then switched to key-based login.
- Generated and copied ed25519 key pair.
- Disabled password login to enforce key-only authentication.
- Used `ssh -v` for verbose connection logging.
- Verified access through PuTTY (Windows).

### 📶 Bonus: Snort + Network Configuration

- Network topology setup using **pfSense**:
  - Linux Mint IP: `10.0.0.100`
  - Metasploitable2 IP: `10.6.6.2`
- Configured routing and rules in pfSense to allow traffic between the two subnets.
- Installed and configured **Snort** to monitor unusual traffic.

---

## 🛠️ Tools & Technologies

- Linux Mint
- Metasploitable2
- pfSense Firewall
- Snort IDS
- OpenSSL
- OpenSSH
- Python 3 (TLS server)
- Wireshark
- PuTTY (Windows)

---

## 📡 Network Diagram (Conceptual)

```text
[Linux Mint Client] <--TLS/SSH--> [Linux Mint Server]
        |                                 |
     10.0.0.100                       10.6.6.2
        |                                 |
      [pfSense Firewall / Router with Snort]
