# Honeypot-Lab-PenTBox-Intrusion-Detection
Deployed a honeypot on Kali Linux using PenTBox to simulate a vulnerable service and capture intrusion attempts from a remote Windows machine.


# Honeypot Lab — PenTBox Intrusion Detection

Deployed a honeypot on Kali Linux using PenTBox to simulate a vulnerable service and capture intrusion attempts from a remote Windows machine.

---

## Setup & Installation

**Step 1 — Update Kali and install dependencies:**
```bash
sudo apt update && sudo apt upgrade
```

**Step 2 — Clone PenTBox from GitHub:**
```bash
git clone https://github.com/technicaldada/pentbox
```

**Step 3 — Navigate and extract:**
```bash
cd pentbox
tar -zxvf pentbox.tar.gz
cd pentbox-1.8
```

**Step 4 — Run PenTBox with root privileges:**
```bash
sudo ./pentbox.rb
```

---

## Honeypot Configuration

**From the PenTBox menu:**
1. Select `2` → Network Tools
2. Select `3` → Honeypot
3. Select `1` → Fast Auto Configuration
4. Honeypot activates on **Port 80**

---

## Testing the Honeypot

**Step 1 — Get your Kali IP:**
```bash
hostname -I
```

**Step 2 — From Windows Server, open Chrome and enter:**
```
http://[your-kali-ip]
```

**Step 3 — Observe honeypot response:**
- Browser shows **"Access denied"** and "IP Address login failed"
- Timestamp of access attempt logged

**Step 4 — Check honeypot terminal:**
Intrusion attempts appear with:
- Source IP and port
- HTTP request method (GET)
- Timestamp
- User-Agent and full HTTP headers
- Request path

---

## Lab Results

| Component | Result |
|-----------|--------|
| Honeypot activation | Port 80 running successfully |
| Windows access attempt | Access denied response returned |
| Intrusion logging | Multiple attempts captured with full headers |
| Detection accuracy | 100% — all access attempts logged |
---

## What I Learned

- How honeypots work as deception-based security tools to detect intrusions
- How to deploy and configure PenTBox on Kali Linux
- How to capture and analyze intrusion attempt data (IP, port, HTTP headers, user-agent)
- How honeypots log attacker behavior without harming the real network

---

## PenTBox Features Used

**PenTBox** is an open-source security toolkit with:
- Network Tools (port scanner, banner grabbing, DNS enumeration, **honeypot**)
- Cryptography Tools (hashing, Base64, password generator)
- Web Tools (HTTP brute force, DoS simulator)
- Other utilities (system info gathering)

---

## Tools & Environment

- Kali Linux (RDP: kali)
- PenTBox 1.8 (Ruby-based penetration testing framework)
- Windows Server 2019 (RDP: target) — attacker machine
- LCPS Cyber Virtual Environment

---

## Author

Mofolorunsho Adeleke — [github.com/Mo200909](https://github.com/Mo200909)
