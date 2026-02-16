# 🛡️ Vulnerability Assessment using Nessus Essentials (Kali Linux)

## 📌 Project Overview

This project demonstrates the complete installation, configuration, execution, and analysis of a vulnerability scan using **Tenable Nessus Essentials** on **Kali Linux**.

The scan was performed against:

```
Target: 127.0.0.1 (Localhost)
Scan Type: Basic Network Scan
Scanner: Local Scanner
Duration: 41 Minutes
```

---

# 📑 Table of Contents

* [Environment Details](#environment-details)
* [Installation Process](#installation-process)
* [Service Verification](#service-verification)
* [Plugin Update Process](#plugin-update-process)
* [Scan Configuration](#scan-configuration)
* [Scan Execution](#scan-execution)
* [Scan Results](#scan-results)
* [High Severity Analysis](#high-severity-analysis)
* [Remediation Actions](#remediation-actions)
* [Conclusion](#conclusion)

---

# 🖥️ Environment Details

| Component      | Value               |
| -------------- | ------------------- |
| OS             | Kali Linux          |
| Nessus Version | 10.11.2 (#42) Linux |
| License        | Nessus Essentials   |
| Scan Target    | 127.0.0.1           |
| Policy         | Basic Network Scan  |

---

# ⚙️ Installation Process

## Step 1: Download Nessus

Download the Debian package from Tenable:

```
Nessus-10.11.2-debian10_amd64.deb
```

## Step 2: Install Package

```bash
sudo dpkg -i Nessus-10.11.2-debian10_amd64.deb
```

Successful installation message:

```
INSTALL PASSED
You can start Nessus Scanner by typing:
systemctl start nessusd.service
```


# 🔄 Service Verification

Start and verify Nessus service:

```bash
sudo systemctl start nessusd
sudo systemctl status nessusd
```

Expected Status:

```
Active (running)
```


# 🔌 Plugin Update Process

Initially, plugin download failed due to DNS/network issues.

After resolving:

```bash
sudo /opt/nessus/sbin/nessuscli update
```

Final Status:

```
Nessus Plugins: Complete
Nessus Core Components: Complete
```


# 🧪 Scan Configuration

## Step 1: Open Web Interface

```
https://127.0.0.1:8834
```

## Step 2: Create New Scan

Template Selected:

```
Basic Network Scan
```

## Step 3: Configure Scan

| Field  | Value          |
| ------ | -------------- |
| Name   | Localhost Scan |
| Target | 127.0.0.1      |
| Folder | My Scans       |


# 🚀 Scan Execution

Launch scan from dashboard.

Scan Details:

* Status: Completed
* Start Time: 6:13 AM
* End Time: 6:54 AM
* Duration: 41 Minutes



# 📊 Scan Results

Total Vulnerabilities Detected:

```
60
```

Severity Breakdown:

* 🔴 High: 3
* 🟠 Medium: 2
* 🔵 Info: Remaining


# 🔥 High Severity Analysis

## Vulnerability: Python Library Brotli <= 1.1.0 DoS

| Field             | Value         |
| ----------------- | ------------- |
| Severity          | High          |
| CVSS v3.0         | 7.5           |
| CVE               | CVE-2025-6176 |
| Installed Version | 1.1.0         |
| Fixed Version     | 1.2.0         |

Affected Path:

```
/usr/lib/python3/dist-packages/Brotli-1.1.0.egg-info
```


# 📌 Key Findings

* Nessus successfully installed and configured.
* Plugin updates completed after network troubleshooting.
* Localhost scan executed successfully.
* 60 vulnerabilities detected.
* 3 High severity vulnerabilities identified.
* Immediate update required for Brotli package.

---

# 🧠 Lessons Learned

* Proper DNS configuration is critical for plugin updates.
* Nessus Essentials supports up to 5 hosts.
* Localhost scanning reveals installed package vulnerabilities.
* Regular patch management is essential.

---

# 📅 License Information

* Nessus Essentials
* Licensed Hosts: 0 of 5 used
* Expiration: March 17, 2026

---

# 📚 References

* [https://www.tenable.com/products/nessus](https://www.tenable.com/products/nessus)
* [https://www.cve.org/](https://www.cve.org/)

---

# 🏁 Conclusion

This project demonstrates a full vulnerability assessment lifecycle using Nessus Essentials:

* Installation
* Configuration
* Scanning
* Analysis
* Remediation planning

The identified vulnerabilities highlight the importance of maintaining updated system libraries to prevent denial-of-service and exploitation risks.

