Lab 03: Log Analysis & Threat Identification
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
