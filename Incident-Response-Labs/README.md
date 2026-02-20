# Lab: Analyzing a Brute Force Attack

### 🛡️ Scenario
An alert was triggered for 50+ failed SSH login attempts within a 2-minute window on a Linux-based web server. This lab demonstrates the process of identifying, analyzing, and suggesting mitigation for a brute-force attack.

### 🛠️ Tools Used
* **Linux Terminal (CLI):** For log parsing and filtering.
* **Log File:** `/var/log/auth.log`
* **OSINT Tools:** AbuseIPDB (for IP reputation checking).

### 🔍 Investigative Steps
1. **Identification:** Used the `grep` command to filter for "Failed password" entries in the system authentication logs.
2. **Analysis:** Extracted the source IP address and performed a reputation check.
3. **Findings:** The source IP was identified as a known malicious botnet hosting site.
4. **Resolution:** Recommended a temporary firewall block (IPTables) and the implementation of **Fail2Ban** to automate the blocking of repeated failed attempts.

### 📜 Key Command Used
`grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c`
*(This command counts the unique IP addresses attempting to log in.)*
