# 🔥 Firewall Rule Configuration Project

## 📌 Objective
This project demonstrates how to configure, test, and remove a firewall rule on a Windows system using Command Prompt. The main goal is to block Telnet traffic (TCP Port 23) and verify that the rule is correctly applied and removed.

---

## 🛠️ Tools & Environment
- Windows 10 / 11
- Command Prompt (Run as Administrator)
- Windows Defender Firewall
- Telnet Client

---

## 📋 Steps Performed

### ✅ Step 1: Open Command Prompt as Administrator
- Press `Windows` key → Type `cmd`
- Right-click **Command Prompt** → Select **"Run as administrator"**

### ✅ Step 2: Add Firewall Rule to Block Port 23 (Telnet)
```bash
netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23
```

### ✅ Step 3: Enable Telnet Client (if not already enabled)
- Run `optionalfeatures` → Enable **Telnet Client**
OR  
- Run this command in elevated CMD:
```bash
dism /online /Enable-Feature /FeatureName:TelnetClient
```

### ✅ Step 4: Test the Rule with Telnet
```bash
telnet 127.0.0.1 23
```
- Expected output: **"Could not open connection..."** (indicates port is blocked)

### ✅ Step 5: Delete the Firewall Rule
```bash
netsh advfirewall firewall delete rule name="Block Telnet"
```

---

## 🔍 How a Firewall Filters Traffic
- Firewalls inspect incoming/outgoing packets based on rules.
- They can block or allow traffic by protocol, port, direction, IP, etc.
- Stateful inspection tracks the state of connections.
- Default policies (e.g., deny all) improve security posture.
- Blocking unused ports (e.g., Telnet) reduces attack surface.

---

## 📸 Screenshots to Include (for Report)
- Opening CMD as Administrator
- Adding the firewall rule
- Telnet connection failure (test)
- Deleting the firewall rule

---

## ✅ Outcome
By the end of this task, the user understands:
- Basic firewall operations on Windows
- How to create, test, and delete firewall rules
- The significance of filtering traffic by ports and protocols


