# 🛡️ Cybersecurity Project: Phishing, ARP Spoofing & NTLMv2 Hash Attacks

This repository presents a practical cybersecurity lab project focused on **Phishing Attacks**, **ARP Spoofing**, and **NTLMv2 Hash Stealing and Cracking** using a fully virtualized LAN environment. The lab simulates real-world attack vectors using industry-standard tools to explore and understand vulnerabilities, attack mechanics, and defense strategies.

---

## 📚 Project Overview

**Team Members:** Mark Dakroub, Mohamed Amine Belkhalifa, Saibou Keita  
**Course:** Fundamentals of Cyber Security Practices  
**Instructor:** Prof. Adel Khaldi  
**Institution:** DSTI School of Engineering – Applied MSc in Data Engineering for AI

---

## 🎯 Objectives

- 🧠 Understand how phishing, spoofing, and credential theft attacks work.
- 🔧 Gain hands-on experience with the Social Engineering Toolkit (SET), Ettercap, Responder, and John the Ripper.
- 🧪 Simulate credential harvesting in a controlled lab setup.
- 🔐 Learn methods for identifying and mitigating these attacks.
- 📈 Analyze the success and impact of each attack and propose defense strategies.

---

## 💻 Lab Environment

| Component           | Description                           |
|---------------------|---------------------------------------|
| **Virtualization**  | VMware Workstation Pro                |
| **Attacker VM**     | Kali Linux                            |
| **Victim VM**       | Windows 7                             |
| **Network**         | Local Area Network (LAN)              |

---

## 🧪 Methodology & Setup

### 1. **Environment Setup**
- Installed VMware Workstation Pro
- Created and configured VM directories
- Imported Kali Linux and Windows 7 VMs
- Assigned both VMs to the same LAN

### 2. **Phishing Attack Simulation (SET)**
- Tool: Social-Engineer Toolkit (SET)
- Method: Credential Harvester + Site Cloner
- Target: Facebook Login Page (for demonstration only)
- Steps:
  1. Cloned target site
  2. Hosted local phishing server
  3. Captured victim credentials (username, password)
  4. Generated XML report of session

### 3. **ARP Spoofing Attack (Ettercap)**
- Tool: Ettercap
- Method: ARP cache poisoning between victim and gateway
- Steps:
  1. Scanned local network and identified hosts
  2. Launched MITM attack via Ettercap
  3. Sniffed unencrypted traffic (HTTP)
  4. Captured credentials from demo login site

### 4. **NTLMv2 Hash Stealing and Cracking**
- Tools: Responder + John the Ripper
- Method: LLMNR/NBT-NS spoofing and password hash cracking
- Steps:
  1. Ran `responder` on Kali to impersonate server
  2. Triggered SMB authentication request on Windows
  3. Captured NTLMv2 hash
  4. Cracked the hash using John the Ripper

---

## 📊 Results

- ✅ **Phishing Attack:** Successfully cloned Facebook login and captured test credentials via SET.
- ✅ **ARP Spoofing:** Ettercap redirected traffic and intercepted HTTP login credentials.
- ✅ **NTLMv2 Hash Capture:** Responder captured encrypted hashes, which were cracked successfully.

---

## 🔍 Key Findings

- **User Trust:** Users tend to trust familiar interfaces — a major vulnerability in phishing.
- **LAN Exposure:** Local network weaknesses allow for MITM attacks like ARP spoofing.
- **Legacy Protocols:** NTLMv2 and SMB authentication can be easily exploited if not secured.

---

## 🔐 Defense Recommendations

| Technique                  | Description                                                                 |
|----------------------------|-----------------------------------------------------------------------------|
| **User Awareness Training** | Conduct phishing simulations and educate users on social engineering tactics |
| **MFA (Multi-Factor Auth)** | Adds a second layer of defense even if credentials are compromised          |
| **Email Filtering**         | Use ML-based filtering tools to block phishing emails                       |
| **Secure Browsing**         | Enforce HTTPS and browser plugin protections                               |
| **Traffic Monitoring**      | Deploy IDS/IPS systems like Snort or Suricata to monitor network anomalies  |
| **Disable LLMNR & NBT-NS**  | Prevent responder-based hash capturing                                     |

---

## 📁 Repository Structure


