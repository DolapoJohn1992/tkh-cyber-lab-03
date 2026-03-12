# 🛡️ Lab 03: Log Analysis & Threat Identification
**Theme: "The Holy Trinity—Grep, Sed, and Awk"**

## 🕵️ Project Overview
In this session, I acted as a "Shell Plumber," using Linux streams and redirection to perform data surgery on web server logs. The objective was to identify and isolate Indicators of Compromise (IoCs) from a simulated SQL Injection attack.

---

## 🛠️ The Holy Trinity (Data Surgery)
To extract the threat actors, I utilized the following "surgical" tools:

* **`grep` (The Scalpel):** Sliced out only the lines containing the attack signature.
* **`awk` (The Formatter):** Grabbed the specific column containing the source IP addresses.
* **`sort | uniq`:** Cleaned the data to provide a list of unique attackers.

### The Forensic Pipeline
I constructed a command-line "pipe" to transform raw log data into actionable intelligence:

```bash
grep "UNION SELECT" access.log | awk '{print $1}' | sort | uniq > threat_ips.txt
🚩 Identified Artifacts: threat_ips.txt
The final list of malicious IP addresses recovered during this investigation is stored here:

threat_ips.txt — This serves as the evidence provided to the security team for blacklisting.

📚 Technical Concepts Applied
Redirection (>): Diverting output to overwrite the threat log.

Piping (|): Passing "dirty water" (raw data) through multiple filters to get a clean result.

Log Interrogation: Identifying SQL Injection patterns (UNION SELECT).

Source: The Knowledge House Cybersecurity Curriculum (2026)
Author: Dolapo John


---

### 🚀 Step 3: Push it to GitHub
Now, save the file (`Ctrl+O`, `Enter`, `Ctrl+X`) and run these commands:

1.  `git add README.md`
2.  `git commit -m "feat: add professional stream editing forensic report"`
3.  `git push origin master`

---

### 🧠 Quick Knowledge Check (From your Guide)
* **The Diverter (`>`):** If you ran your command again with `>`, would it add to the bottom or erase the old list? 
    * *Answer:* It would **overwrite** (erase) everything. 
* **The Extender (`>>`):** If you wanted to keep adding new IPs to the same file without deleting the old ones, you would use `>>`.



**Now that this lab is done, do you want to create that "Master Portfolio" page to show off all three projects (Scavenger Hunt, Access Control, and Threat ID) together?**Lab 03: Log Analysis & Threat Identification
Project Overview
This project involved a forensic investigation of server access logs to identify a targeted SQL Injection attack. The goal was to filter through raw log data, identify malicious patterns (specifically UNION SELECT statements), and isolate the unique IP addresses of the attackers.

Methodology
To extract the threat actors from the access.log, I utilized a Linux stream editing pipeline:

grep: To search for the specific attack signature (UNION SELECT).

awk: To isolate the first column of the log (the IP addresses).

sort & uniq: To remove duplicates and create a clean list of unique attackers.

Identified Artifacts
The final list of malicious IP addresses found during this session is stored in:

threat_ips.txt

Tools Used
Linux Command Line (Bash)

Git/GitHub for version control and artifact submission




## APA References

DigitalOcean. (2023, April 14). *How to use journalctl to view and manipulate systemd logs*. https://www.digitalocean.com/community/tutorials/how-to-use-journalctl-to-view-and-manipulate-systemd-logs

OWASP Foundation. (2021). *A03:2021 – Injection*. OWASP Top 10:2021. https://owasp.org/Top10/A03_2021-Injection/

PortSwigger. (n.d.). *SQL injection UNION attacks*. PortSwigger Web Security Academy. https://portswigger.net/web-security/sql-injection/union-attacks

The Knowledge House. (2026). *Night 3: Stream editing & automation* [Lab instructions]. Cybersecurity Phase 1.
