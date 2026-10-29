









# October 28, 2026
Focus: TryHackMe SOC Level 1 - Web Security Attack Chain & Remediation

-What I did (TryHackMe): Completed the comprehensive exploit chain analysis for the RecruitX web application in TryHackMe's SOC Level 1 path. Synthesized the end-to-end intrusion kill chain: 
 1. Enumeration: Mapped technology stack (Apache, PHP, MySQL) and directory paths (`/admin`, `/api`, `/uploads`, `/reset.php`).
 2. IDOR Exploitation: Leveraged broken object-level authorization (`/profile.php?id=` and `/api/user?id=`) to enumerate user accounts and extract administrative email details.
 3. Weak Password Reset: Exploited HTTP response token disclosures at `/reset.php` to take over the administrator account.
 4. Authenticated Upload Bypass: Bypassed client-side `accept` attributes and incomplete extension blocklists using `.phtml` file uploads at `/admin/upload.php`.
 5. Remote Code Execution (RCE): Triggered PHP web shell execution within `/uploads/documents/` to establish interactive system-level shell access.
 Evaluated defensive remediations across each severity tier (server-side authorization checks, out-of-band email reset tokens, strict extension allowlisting/non-executable upload storage, and API access controls).
-Takeaway (TryHackMe): Cyber intrusions rarely rely on a single critical vulnerability; combining low/medium informational flaws (IDOR + API leaks) with logic flaws (token exposure) creates high-impact compromise paths to full system takeover.

-Daily Outcome: Completed full exploit chain breakdown and defensive remediation matrix for the RecruitX lab target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 28, 2026
Focus: TryHackMe SOC Level 1 - Web Security Attack Chain & Remediation

-What I did (TryHackMe): Completed the comprehensive exploit chain analysis for the RecruitX web application in TryHackMe's SOC Level 1 path. Synthesized the end-to-end intrusion kill chain: 
 1. Enumeration: Mapped technology stack (Apache, PHP, MySQL) and directory paths (`/admin`, `/api`, `/uploads`, `/reset.php`).
 2. IDOR Exploitation: Leveraged broken object-level authorization (`/profile.php?id=` and `/api/user?id=`) to enumerate user accounts and extract administrative email details.
 3. Weak Password Reset: Exploited HTTP response token disclosures at `/reset.php` to take over the administrator account.
 4. Authenticated Upload Bypass: Bypassed client-side `accept` attributes and incomplete extension blocklists using `.phtml` file uploads at `/admin/upload.php`.
 5. Remote Code Execution (RCE): Triggered PHP web shell execution within `/uploads/documents/` to establish interactive system-level shell access.
 Evaluated defensive remediations across each severity tier (server-side authorization checks, out-of-band email reset tokens, strict extension allowlisting/non-executable upload storage, and API access controls).
-Takeaway (TryHackMe): Cyber intrusions rarely rely on a single critical vulnerability; combining low/medium informational flaws (IDOR + API leaks) with logic flaws (token exposure) creates high-impact compromise paths to full system takeover.

-Daily Outcome: Completed full exploit chain breakdown and defensive remediation matrix for the RecruitX lab target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 27, 2026
Focus: TryHackMe SOC Level 1 - Web Security & File Upload Security

-What I did (TryHackMe): Investigated file upload validation controls on the RecruitX web application (`/admin/upload.php`) in TryHackMe's SOC Level 1 path. Inspected client-side HTML controls (`accept` attribute on file input elements) and demonstrated client-side restriction bypasses. Evaluated server-side extension validation mechanics, testing blocklist bypasses using alternative PHP extensions (`.phtml`) to confirm code execution within the `/uploads/documents/` directory.
-Takeaway (TryHackMe): Relying on client-side controls (`accept` attribute) or incomplete server-side extension blocklists fails to prevent arbitrary file execution; secure upload implementations require strict allowlisting, extension re-naming, and disabling execution permissions in upload storage paths.

-Daily Outcome: Completed File Upload vulnerability analysis and client/server validation assessment on the RecruitX lab target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 26, 2026
Focus: Logbook Sync — Networking & Linux Operational Tracks

-What I did (Networking): Updated progress across Network Fundamentals (hosts, interfaces, encapsulation), IP Addressing & Routing (IPv4, CIDR, ARP, NAT, DHCP), and Transport Layer Protocols (TCP/UDP, port mappings, handshakes). Marked TCP reliability mechanics as the immediate pending item.
-What I did (Linux): Completed foundational CLI execution chunks across Filesystem Navigation, User/Group Permissions (`chmod`, `chown`), Process & Service Management (`systemctl`, `journalctl`), and Bash I/O Redirection (`>`, `2>`, `|`). Flagged text processing tools (`grep`, `awk`, `cut`, `sort`, `uniq`) for continued practice.

-Daily Outcome: Synced progression logs across `tracks/networking.md` and `tracks/linux.md`. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 26, 2026
Focus: TryHackMe SOC Level 1 - Web Security & IDOR Analysis

-What I did (TryHackMe): Investigated IDOR mechanics on the RecruitX web application in TryHackMe's SOC Level 1 path. Analyzed predictable object referencing via URL parameters (`/profile.php?id=6`), evaluating authorization flaws where server-side validation is absent. Formulated testing methodology to test object-level authorization by incrementing/decrementing numeric object identifiers (`id` parameter) to test for unauthorized data access.
-Takeaway (TryHackMe): IDOR vulnerabilities occur when applications rely on user-supplied parameters to fetch internal objects without enforcing server-side authorization checks; testing sequential numeric parameters reveals broken object-level authorization flaws instantly.

-Daily Outcome: Completed IDOR theoretical analysis and URL parameter structure assessment on the RecruitX lab target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 25, 2026
Focus: TryHackMe SOC Level 1 - Web Security & API Exploration

-What I did (TryHackMe): Logged into the RecruitX web application via `/login.php` using test credentials (`testuser@fake.thm` / `Password123`) to establish an active session (`PHPSESSID`) and reach `/dashboard.php`. Navigated through the authenticated user interface (Open Positions, Applications, Browse Jobs, and user profile views). Initiated targeted exploration of the previously enumerated `/api` endpoint to analyze accessible REST routes and unauthenticated data exposure vectors.
-Takeaway (TryHackMe): Authenticated session state reveals dynamic application behavior (`/dashboard.php`, `/profile.php`), while probing exposed API structures (`/api`) often highlights broken object-level authorization (BOLA) or hidden data endpoints not present in the primary UI.

-Daily Outcome: Completed authentication setup and initiated API endpoint exploration on the RecruitX lab target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 24, 2026
Focus: TryHackMe SOC Level 1 - Web Security & Target Reconnaissance

-What I did (TryHackMe): Conducted reconnaissance on the RecruitX web application target. Analyzed full Nmap port scans (`-sV -sC -p-`), identifying open services on TCP ports 22 (OpenSSH 9.6p1), 80 (Apache 2.4.58), 3306 (MySQL), and 8080 (Apache default page). Inspected HTTP headers (`PHPSESSID`) to map out a classic LAMP stack (Linux + Apache + MySQL + PHP). Performed directory enumeration via Gobuster using `directory-list-2.3-small.txt`, mapping critical operational paths including `/admin`, `/api`, `/uploads`, `/reset.php`, `/profile.php`, `/dashboard.php`, and `/config`.
-Takeaway (TryHackMe): Combining layer-4 service detection with web directory enumeration reveals attack vectors early—particularly exposed API endpoints (`/api`), file upload directories (`/uploads`), and unauthenticated reset mechanisms (`/reset.php`).

-Daily Outcome: Completed target reconnaissance and directory enumeration task for RecruitX target. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 23, 2026
Focus: TryHackMe SOC Level 1 - Endpoint Security & Malware Categories

-What I did (TryHackMe): Analyzed core malware classifications and behavioral signatures in TryHackMe's SOC Level 1 path. Evaluated primary intent, execution mechanics, and real-world specimens across nine categories: Adware (Fireball), Spyware (Hermit), Ransomware (WannaCry), Wiper (PathWiper), Command & Control (Emotet), Data Stealer (Lumma Stealer), Keylogger (Zeus), and Cryptominer (Coinhive). Examined realistic operational scenarios for SOC detection across host telemetry (e.g., unauthorized process CPU spikes, anomalous TLS out-of-band traffic, and persistent keystroke logging).
-Takeaway (TryHackMe): Endpoint security triage relies on matching host indicators (high CPU usage, file encryption/overwriting, keystroke hooks) and network signatures (C2 beaconing, external data exfiltration) to specific malware archetypes to quickly contain threats.

-Daily Outcome: Analyzed Malware Categories & Behavioral Scenarios task in Endpoint Security module. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 22, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Completed Tasks 4, 5, and 6 in TryHackMe's "Linux Logs" room, finishing the module (100%). Investigated root account SSH intrusion indicators (successful password login from IP `91.224.92.79`), command injection in web applications (`/opt/trypingme/main.py`), and process tree construction via `auditd` telemetry (`ausearch -i -x whoami` -> PPID `1018` -> PID `577` Python application execution spawning a Python reverse shell). Analyzed supply chain compromise patterns and process tree analysis as a universal detection control.
-Takeaway (TryHackMe): Tracing execution chains via `auditd` process tree construction (`ausearch -i --pid`/`--ppid`) bridges web-layer command injection (e.g., ping forms) with endpoint post-exploitation binaries, providing deterministic evidence of service compromise.

-Daily Outcome: Completed Linux Logs room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 21, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Evaluated process tree analysis techniques in TryHackMe's "Linux Logs" room to trace initial access and post-exploitation service breaches. Used `auditd` commands (`ausearch -i -x command` to locate execution, `ausearch -i --pid <PPID>` to walk up parent processes to PID 1, and `ausearch -i --ppid <PID>` to enumerate child processes). Reconstructed an exploitation chain demonstrating how an web application (`/opt/mywebapp/app.py`, PID 3898) spawned `/bin/sh` child processes to execute reconnaissance (`whoami`, `ls -la`) and secondary payloads (`curl ... | sh`). Applied process tree walking to investigate the TryPingMe breach scenario.
-Takeaway (TryHackMe): When application logs are absent or sanitized, process tree analysis via audit telemetry provides a reliable, universal approach to trace command lineage back to compromised parent services.

-Daily Outcome: Completed Process Tree Construction & Auditd Service Breach Analysis task in Linux Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 20, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Investigated Linux Initial Access mechanisms focusing on exposed SSH services in TryHackMe's "Linux Logs" room. Analyzed MITRE ATT&CK T1133 (External Remote Services) attack vectors, contrasting key-based compromise risks (leaked private keys in repositories/automation servers, credential stealers) with password-based vulnerability vectors (weak temporary passwords, exposed legacy instances, automated botnet brute-forcing). Reviewed real-world threat group campaigns (e.g., Outlaw group) and advanced exposure risks (SSH server CVEs and session hijacking).
-Takeaway: SSH is the dominant perimeter exposure vector on Linux infrastructure; detecting SSH-based Initial Access requires monitoring authentication logs for high-frequency password brute-force patterns and key-based session origin anomalies.

-Daily Outcome: Analyzed SSH Initial Access & External Remote Services task in Linux Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 19, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Explored kernel-level runtime auditing using `auditd` in TryHackMe's "Linux Logs" room. Analyzed ruleset configuration (`/etc/audit/rules.d/`), investigated real-time audit logs via `ausearch -i`, and dissected multi-line syscall event structures (`PROCTITLE`, `CWD`, `PATH`, and `SYSCALL`). Processed key identification fields including process tree identifiers (`pid`, `ppid`), session tracking (`tty`), executable paths (`exe`), rule keys (`key`), and user privilege escalation indicators (`auid` audit user vs `uid` effective execution user). Compared `auditd` with alternative Linux endpoint detection tools (Sysmon for Linux, Falco for container workloads, Osquery, and commercial EDRs).
-Takeaway (TryHackMe): `auditd` provides granular syscall visibility into process creation (`execve`) and critical file modification (`openat`/`write`), making `auid` vs `uid` tracking vital for detecting privilege escalation and post-exploitation activity on Linux endpoints.

-Daily Outcome: Completed Audit Daemon (auditd) runtime monitoring task in Linux Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 18, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Deepened analysis of system and application log structures in TryHackMe's "Linux Logs" room. Evaluated generic Linux system logs (`/var/log/kern.log`, `/var/log/syslog` / `messages`, Debian package logs `/var/log/dpkg.log` / `apt`, and RHEL package logs `/var/log/dnf.log` / `yum.log`). Examined application-specific logging telemetry with a focus on Nginx web server access logs (`/var/log/nginx/access.log`), mapping HTTP request lines, status codes (e.g., 200, 302 redirect, 403 forbidden), response sizes, and client source IPs.
-Takeaway (TryHackMe): Combining generic system telemetry with application-specific logs (e.g., Nginx, database, mail, container) allows SOC analysts to correlate web-based intrusion attempts with underlying host and kernel activity.

-Daily Outcome: Completed Generic System Logs & App-Specific Logs analysis task in Linux Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 17, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Investigated Linux system logging mechanisms in TryHackMe's "Linux Logs" room. Evaluated plain-text file storage in `/var/log/` (e.g., `/var/log/syslog`, `/var/log/auth.log`, `/var/log/kern.log`), analyzed log structure differences compared to binary Windows EVTX logs, and practiced command-line log discovery/filtering techniques using `grep` (including recursive search `grep -R -E "auth|login|session" /var/log`).
-Takeaway (TryHackMe): Unlike structured Windows Event logs, default Linux logs are plain-text and distribution-dependent; mastering CLI tools (`grep`, `awk`, `cat`, `less`) across `/var/log` enables rapid identification of system events, cron jobs, and authentication attempts.

-Daily Outcome: Completed Log Format, Working With Logs, & Filtering task in Linux Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 16, 2026
Focus: TryHackMe SOC Level 1 - Linux Logs

-What I did (TryHackMe): Started the "Linux Logs" room in TryHackMe's SOC Level 1 path. Reviewed core learning objectives covering Linux authentication, runtime, and system logs, log analysis CLI tools/commands, and `auditd` event monitoring across on-premises and cloud-native containerized workloads. Initialized the target lab machine environment.
-Takeaway (TryHackMe): Linux log analysis requires familiarity with both traditional file-based logs (`/var/log`) and systemd journal telemetry, alongside audit daemon (`auditd`) rules to trace root activities, authentication events, and process execution.

-Daily Outcome: Initiated Linux Logs room and initialized target lab machine. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 15, 2026
Focus: TryHackMe SOC Level 1 - Windows Initial Access

-What I did (TryHackMe): Completed the remaining tasks and wrapped up the "Windows Initial Access" room in TryHackMe's SOC Level 1 path (100% completion). Analyzed Initial Access via Phishing (T1566) and Removable Media/USB (T1091), alongside process execution signatures (e.g., LNK payload execution).
-Takeaway (TryHackMe): Detecting early-stage Windows breaches requires dual-pivot telemetry: exposed service intrusions (RDP/SMB) map directly to Event IDs 4624/4625, while user-driven vectors (Phishing/USB) rely on Sysmon Event ID 1 process trees to trace malicious child process execution.

-Daily Outcome: Completed Windows Initial Access room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 14, 2026
Focus: TryHackMe SOC Level 1 - Windows Initial Access

-What I did (TryHackMe): Deepened analysis of user-driven Windows Initial Access vectors in TryHackMe's "Windows Initial Access" room. Evaluated MITRE ATT&CK techniques T1566 (Phishing via malicious links/attachments) and T1091 (Replication Through Removable Media via USB drop attacks). Reviewed modern Initial Access tendencies and real-world campaign telemetry across major ransomware groups (e.g., Medusa, Akira) leveraging both edge-exposed service exploitation and user-driven execution vectors.
-Takeaway (TryHackMe): Even isolated workstations remain vulnerable to Initial Access via social engineering and physical vectors; SOC monitoring strategies must account for multi-stage threat actor TTPs across both perimeter boundaries and endpoint user execution.

-Daily Outcome: Analyzed Phishing, Removable Media, & Threat Actor TTPs task in Windows Initial Access room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 13, 2026
Focus: TryHackMe SOC Level 1 - Windows Event Logs

-What I did (TryHackMe): Completed the "Windows Event Logs" room in TryHackMe's SOC Level 1 path. Consolidated key analytical takeaways across Windows authentication telemetry (4624/4625), Logon ID and PID correlation for attack chain reconstruction, advanced endpoint visibility via Sysmon process creation monitoring (Event ID 1), and PowerShell script-block logging.
-Takeaway (TryHackMe): Correlating authentication IDs with endpoint process trees and PowerShell command-line logs provides the necessary context to map out initial access execution and lateral movement.

-Daily Outcome: Completed Windows Event Logs room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 12, 2026
Focus: TryHackMe SOC Level 1 - Windows Event Logs

-What I did (TryHackMe): Investigated process creation monitoring in TryHackMe's "Windows Event Logs" room. Compared Security Log Event ID 4688 with Sysmon Event ID 1 (Process Creation), evaluating critical telemetry fields: Process Info (PID, Image Path, Command Line), Parent Process Context (building process trees/attack chains), Binary Metadata (PE hashes, signatures), and User Context (Logon ID linkage). Located Sysmon logs in Event Viewer under `Applications and Services Logs -> Microsoft -> Windows -> Sysmon -> Operational`.
-Takeaway (TryHackMe): Process creation logs bridge the gap between authentication alerts and endpoint execution; analyzing parent-child process relationships (e.g., MS Office spawning PowerShell) provides immediate visibility into post-exploitation initial access vectors.

-Daily Outcome: Completed Sysmon Event ID 1 & Process Monitoring analysis task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 11, 2026
Focus: TryHackMe SOC Level 1 - Windows Initial Access

-What I did (TryHackMe): Initiated the Windows Initial Access module in TryHackMe's SOC Level 1 path. Evaluated the core taxonomies of Initial Access mechanisms across Exposed Services (MITRE ATT&CK T1133: External Remote Services via RDP/SSH/VNC; T1190: Exploit Public-Facing Application) and User-Driven Vectors (MITRE ATT&CK T1566: Phishing attachments/links; T1091: Replication Through Removable Media).
-Takeaway (TryHackMe): Initial Access strategies divide cleanly into active exploitation of perimeter-exposed listening ports and social-engineering vectors targeting internal workstations; defenders must monitor both perimeter edge logs and endpoint execution indicators to detect early entry.

-Daily Outcome: Completed Initial Access recap & vector classification task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 10, 2026
Focus: TryHackMe SOC Level 1 - Windows Event Logs

-What I did (TryHackMe): Deepened analysis of Windows Security logs in TryHackMe's "Windows Event Logs" room, evaluating Event ID 4624 (Successful Logon) and Event ID 4625 (Failed Logon). Examined key logon types (Type 3 Network via NLA, Type 10 RemoteInteractive/RDP), logon parameters (Logon ID, Subject/Target User, Workstation Name, Source IP), and RDP brute force detection indicators. Analyzed the `Practice-Security.evtx` dataset to investigate an active RDP brute force attack targeting `THM-PC`.
-Takeaway (TryHackMe): Detecting RDP compromise requires correlating high-frequency Event ID 4625 brute-force failures from an untrusted source IP with a subsequent Event ID 4624/Type 10 success event sharing the same source IP and target account.

-Daily Outcome: Analyzed authentication logs (4624/4625) in `Practice-Security.evtx`. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 9, 2026
Focus: TryHackMe SOC Level 1 - Windows Event Logs

-What I did (TryHackMe): Initiated the Windows Event Logs module in TryHackMe's SOC Level 1 path. Studied the fundamentals of Windows logging architectures, examining binary `.evtx` log structures (`C:\Windows\System32\winevt\Logs`), Event Viewer navigation (`eventvwr`), log sources (Application vs. Security), key log attributes (System Timestamp, Event IDs like 4625 for failed logins, Keywords), and filtering controls.
-Takeaway (TryHackMe): Windows logs are stored in binary EVTX format and rely on structured Event IDs; mastering log categories and Event Viewer XML/plaintext filtering is essential for triage, threat hunting, and incident response timelines.

-Daily Outcome: Completed Logging Overview & Anatomy of a Log Entry task in Windows Event Logs room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 8, 2026
Focus: TryHackMe SOC Level 1 - Detecting Web Attacks

-What I did (TryHackMe): Successfully wrapped up the "Detecting Web Attacks" room in TryHackMe's SOC Level 1 path (100% completion). Summarized core detection strategies spanning client-side/server-side attack vectors, log-based access analysis, network traffic packet capture inspection, and Web Application Firewall (WAF) rule sets.
-Takeaway (TryHackMe): Correlating indicators across web access logs, raw packet captures, and WAF alert feeds eliminates alert silos, enabling SOC analysts to reconstruct complete web attack timelines from initial scanning to exploitation and exfiltration.

-Daily Outcome: Completed Detecting Web Attacks room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 7, 2026
Focus: TryHackMe SOC Level 1 - Detecting Web Attacks

-What I did (TryHackMe): Analyzed Web Application Firewall (WAF) mitigation mechanisms in TryHackMe's "Detecting Web Attacks" room. Evaluated WAF rule categories (Signature/Payload Blocking, Known Malicious IP/Threat Intel Reputation, Custom URI Rules, and Rate-Limiting), challenge-response mechanisms (CAPTCHA for bot traffic mitigation), and automated threat intelligence feed integrations (OWASP Top 10 rule sets, CVE protection, and botnet/VPN IP curation).
-Takeaway (TryHackMe): WAFs serve as layer-7 gatekeepers capable of inspecting full TLS-decrypted HTTP payloads; combining automated signature feeds with custom heuristic rules blocks malicious tools (e.g., SQLMap User-Agents) without impacting legitimate web traffic.

-Daily Outcome: Completed Web Application Firewalls task in Detecting Web Attacks room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 6, 2026
Focus: TryHackMe SOC Level 1 - Detecting Web Attacks

-What I did (TryHackMe): Analyzed log-based detection fundamentals in TryHackMe's "Detecting Web Attacks" room. Evaluated access log formats (Client IP, Timestamp, HTTP Status Codes, Response Size, Referrer, User-Agent), studied log signatures across directory fuzzing, HTTP POST brute-forcing, and SQL injection (SQLi), and noted structural log limitations (omission of POST request bodies/payloads). Initialized investigation of the `access.log` dataset for the TryBankMe incident on the Desktop.
-Takeaway (TryHackMe): Web access logs provide critical forensic timelines (mapping directory enumeration and authentication redirects), but full request payload visibility—especially HTTP POST parameters—requires layer-7 packet captures or WAF logs.

-Daily Outcome: Completed Log-Based Detection task and initialized TryBankMe forensic investigation. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 5, 2026
Focus: TryHackMe SOC Level 1 - Detecting Web Attacks

-What I did (TryHackMe): Started the "Detecting Web Attacks" room in TryHackMe's SOC Level 1 path (Web Security Monitoring module). Reviewed core learning objectives focusing on client-side/server-side web attack vectors, log-based vs. network traffic-based detection methods, and Web Application Firewall (WAF) rule analysis.
-Takeaway (TryHackMe): Detecting web attacks requires combining log analysis (HTTP request/response status, URI parameters) and packet capture inspection (Wireshark layer-7 analysis) to accurately identify OWASP Top 10 web exploit attempts.

-Daily Outcome: Initiated Detecting Web Attacks room and reviewed core module prerequisites. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 4, 2026
Focus: TryHackMe SOC Level 1 - Web Security Essentials

-What I did (TryHackMe): Wrapped up the "Web Security Essentials" room (SOC Level 1 > Web Security Monitoring), reviewing the shift from legacy desktop applications to web-based architectures, core web request/server dynamics, high-risk exposure vectors targeting sensitive data/databases, and perimeter/host defense-in-depth strategies.
-Takeaway (TryHackMe): Web security monitoring demands end-to-end visibility across layer-7 application payloads, server-side infrastructure behavior, and endpoint security controls to detect initial exploitation attempts before they escalate into wider infrastructure breaches.

-Daily Outcome: Completed Web Security Essentials room conclusion and module wrap-up. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 3, 2026
Focus: TryHackMe SOC Level 1 - Web Security Essentials

-What I did (TryHackMe): Successfully completed the practical hands-on scenario for securing "Secure-A-Site" across three critical architectural tiers in TryHackMe's "Web Security Essentials" room: Web Application (THM{APPLICATION_SECURED_8371}), Web Server (THM{SERVER_PROTECTED_9120}), and Host Machine (THM{HOST_HARDENED_4059}). Reached 100% completion for the room.
-Takeaway (TryHackMe): Effective web security demands a defense-in-depth approach where application-level controls (HTTPS, secure cookies, input validation), server perimeter protections (WAF rules, directory restrictions, rate limiting), and host-level hardening (firewalls, AV endpoints, minimal service exposure) work in unison.

-Daily Outcome: Completed Web Security Essentials room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 2, 2026
Focus: TryHackMe SOC Level 1 - Web Security Essentials

-What I did (TryHackMe): Examined core perimeter and endpoint defense systems in TryHackMe's "Web Security Essentials" room (Task 5). Analyzed Content Delivery Network (CDN) security architectures (IP masking, DDoS mitigation, TLS enforcement, WAF integration), Web Application Firewall (WAF) deployment modes (Cloud Reverse Proxy, Host-based, Network-based) and detection mechanisms (Signature, Heuristic, Anomaly/Behavioral, IP Reputation), and endpoint Antivirus (AV) controls for mitigating malicious web file uploads.
-Takeaway (TryHackMe): Robust web application security requires a defense-in-depth model where CDNs buffer origin servers from volumetric attacks, WAFs filter malicious layer-7 payloads, and AV endpoints catch post-exploitation tools or web shells that bypass perimeter inspection.

-Daily Outcome: Completed Task 5 Defense Systems analysis in Web Security Essentials room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# October 1, 2026
Focus: TryHackMe SOC Level 1 - Web Security Essentials

-What I did (TryHackMe): Reached 71% progress in TryHackMe's "Web Security Essentials" room (SOC Level 1 > Web Security Monitoring). Completed core tasks covering web application fundamentals, web infrastructure components, defensive architectures, and security controls for protecting web environments.
-Takeaway (TryHackMe): Securing modern web architectures requires defense-in-depth across client-server infrastructure, web application firewalls (WAFs), transport-layer encryption, and secure session management to safeguard against public-facing attack vectors.

-Daily Outcome: Reached 71% completion in Web Security Essentials room upon finishing Task 5. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.