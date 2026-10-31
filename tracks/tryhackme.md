









# October 31, 2026
Focus: Metasploit Exploitation — UnrealIRCd Backdoor & Reverse Shell

-What I did: Navigated the Metasploit Framework (`msfconsole`) workflow targeting the UnrealIRCd 3.2.8.1 backdoor vulnerability (`exploit/unix/irc/unreal_ircd_3281_backdoor`). Configured target parameters (`RHOSTS`, target port), selected the generic Unix double reverse TCP payload (`cmd/unix/reverse`), configured local listener parameters (`LHOST`, `LPORT`), and executed the exploit. Obtained an unprivileged command shell as `webmaster` and retrieved `/home/webmaster/flag.txt`. Reviewed the theoretical requirement and mechanics of upgrading basic dumb shells to interactive TTYs for commands like `su`/`sudo`.
-Takeaway: Exploiting backdoored services via Metasploit requires precise alignment of exploit module options and payload listener settings; recognizing shell interactive constraints (dumb shell vs. interactive TTY) is critical for subsequent post-exploitation operations.

# October 30, 2026
Focus: Vulnerability Analysis & Service Enumeration Workflows

-What I did: Evaluated vulnerability analysis methodologies following network scanning and service enumeration in TryHackMe's SOC Level 1 path. Practiced mapping raw Nmap service banner data to potential exploit vectors, assessing version-specific vulnerability databases, and analyzing command-line exploit lookup workflows via tools like `searchsploit` (Exploit-DB offline repository) versus OS-specific patch backporting verification (e.g., evaluating OpenSSH 9.6p1 banners).
-Takeaway: Vulnerability analysis bridges raw enumeration and risk prioritization; cross-referencing service banners with known CVE databases or offline repositories (`searchsploit`) helps distinguish theoretical or backported vendor versions from actionable exposure risks.

# October 28, 2026
Focus: Web Security - Full Attack Chain Analysis & Remediation Synthesis

-What I did: Completed the comprehensive exploit chain analysis for the RecruitX web application in TryHackMe's SOC Level 1 path. Synthesized the end-to-end intrusion kill chain: 
 1. Enumeration: Mapped technology stack (Apache, PHP, MySQL) and directory paths (`/admin`, `/api`, `/uploads`, `/reset.php`).
 2. IDOR Exploitation: Leveraged broken object-level authorization (`/profile.php?id=` and `/api/user?id=`) to enumerate user accounts and extract administrative email details.
 3. Weak Password Reset: Exploited HTTP response token disclosures at `/reset.php` to take over the administrator account.
 4. Authenticated Upload Bypass: Bypassed client-side `accept` attributes and incomplete extension blocklists using `.phtml` file uploads at `/admin/upload.php`.
 5. Remote Code Execution (RCE): Triggered PHP web shell execution within `/uploads/documents/` to establish interactive system-level shell access.
 Evaluated defensive remediations across each severity tier (server-side authorization checks, out-of-band email reset tokens, strict extension allowlisting/non-executable upload storage, and API access controls).
-Takeaway: Cyber intrusions rarely rely on a single critical vulnerability; combining low/medium informational flaws (IDOR + API leaks) with logic flaws (token exposure) creates high-impact compromise paths to full system takeover.

# October 28, 2026
Focus: Web Security - Full Attack Chain Analysis & Remediation Synthesis

-What I did: Completed the comprehensive exploit chain analysis for the RecruitX web application in TryHackMe's SOC Level 1 path. Synthesized the end-to-end intrusion kill chain: 
 1. Enumeration: Mapped technology stack (Apache, PHP, MySQL) and directory paths (`/admin`, `/api`, `/uploads`, `/reset.php`).
 2. IDOR Exploitation: Leveraged broken object-level authorization (`/profile.php?id=` and `/api/user?id=`) to enumerate user accounts and extract administrative email details.
 3. Weak Password Reset: Exploited HTTP response token disclosures at `/reset.php` to take over the administrator account.
 4. Authenticated Upload Bypass: Bypassed client-side `accept` attributes and incomplete extension blocklists using `.phtml` file uploads at `/admin/upload.php`.
 5. Remote Code Execution (RCE): Triggered PHP web shell execution within `/uploads/documents/` to establish interactive system-level shell access.
 Evaluated defensive remediations across each severity tier (server-side authorization checks, out-of-band email reset tokens, strict extension allowlisting/non-executable upload storage, and API access controls).
-Takeaway: Cyber intrusions rarely rely on a single critical vulnerability; combining low/medium informational flaws (IDOR + API leaks) with logic flaws (token exposure) creates high-impact compromise paths to full system takeover.

# October 27, 2026
Focus: Web Security - Unrestricted File Upload & Client-Side Bypass Analysis

-What I did: Investigated file upload validation controls on the RecruitX web application (`/admin/upload.php`) in TryHackMe's SOC Level 1 path. Inspected client-side HTML controls (`accept` attribute on file input elements) and demonstrated client-side restriction bypasses. Evaluated server-side extension validation mechanics, testing blocklist bypasses using alternative PHP extensions (`.phtml`) to confirm code execution within the `/uploads/documents/` directory.
-Takeaway: Relying on client-side controls (`accept` attribute) or incomplete server-side extension blocklists fails to prevent arbitrary file execution; secure upload implementations require strict allowlisting, extension re-naming, and disabling execution permissions in upload storage paths.

# October 26, 2026
Focus: Web Security - Insecure Direct Object Reference (IDOR) Analysis

-What I did: Investigated IDOR mechanics on the RecruitX web application in TryHackMe's SOC Level 1 path. Analyzed predictable object referencing via URL parameters (`/profile.php?id=6`), evaluating authorization flaws where server-side validation is absent. Formulated testing methodology to test object-level authorization by incrementing/decrementing numeric object identifiers (`id` parameter) to test for unauthorized data access.
-Takeaway: IDOR vulnerabilities occur when applications rely on user-supplied parameters to fetch internal objects without enforcing server-side authorization checks; testing sequential numeric parameters reveals broken object-level authorization flaws instantly.

# October 25, 2026
Focus: Web Security - Authentication & API Endpoint Enumeration

-What I did: Logged into the RecruitX web application via `/login.php` using test credentials (`testuser@fake.thm` / `Password123`) to establish an active session (`PHPSESSID`) and reach `/dashboard.php`. Navigated through the authenticated user interface (Open Positions, Applications, Browse Jobs, and user profile views). Initiated targeted exploration of the previously enumerated `/api` endpoint to analyze accessible REST routes and unauthenticated data exposure vectors.
-Takeaway: Authenticated session state reveals dynamic application behavior (`/dashboard.php`, `/profile.php`), while probing exposed API structures (`/api`) often highlights broken object-level authorization (BOLA) or hidden data endpoints not present in the primary UI.

# October 24, 2026
Focus: Web Security & Application Reconnaissance - RecruitX Target Assessment

-What I did: Conducted reconnaissance on the RecruitX web application target. Analyzed full Nmap port scans (`-sV -sC -p-`), identifying open services on TCP ports 22 (OpenSSH 9.6p1), 80 (Apache 2.4.58), 3306 (MySQL), and 8080 (Apache default page). Inspected HTTP headers (`PHPSESSID`) to map out a classic LAMP stack (Linux + Apache + MySQL + PHP). Performed directory enumeration via Gobuster using `directory-list-2.3-small.txt`, mapping critical operational paths including `/admin`, `/api`, `/uploads`, `/reset.php`, `/profile.php`, `/dashboard.php`, and `/config`.
-Takeaway: Combining layer-4 service detection with web directory enumeration reveals attack vectors early—particularly exposed API endpoints (`/api`), file upload directories (`/uploads`), and unauthenticated reset mechanisms (`/reset.php`).

# October 23, 2026
Focus: Endpoint Security - Malware Categories & Behavioral Scenarios

-What I did: Analyzed core malware classifications and behavioral signatures in TryHackMe's SOC Level 1 path. Evaluated primary intent, execution mechanics, and real-world specimens across nine categories: Adware (Fireball), Spyware (Hermit), Ransomware (WannaCry), Wiper (PathWiper), Command & Control (Emotet), Data Stealer (Lumma Stealer), Keylogger (Zeus), and Cryptominer (Coinhive). Examined realistic operational scenarios for SOC detection across host telemetry (e.g., unauthorized process CPU spikes, anomalous TLS out-of-band traffic, and persistent keystroke logging).
-Takeaway: Endpoint security triage relies on matching host indicators (high CPU usage, file encryption/overwriting, keystroke hooks) and network signatures (C2 beaconing, external data exfiltration) to specific malware archetypes to quickly contain threats.

# October 22, 2026
Focus: Linux Logs - Service Breaches, Auditd Process Trees, & Room Completion (100%)

-What I did: Completed Tasks 4, 5, and 6 in TryHackMe's "Linux Logs" room, finishing the module (100%). Investigated root account SSH intrusion indicators (successful password login from IP `91.224.92.79`), command injection in web applications (`/opt/trypingme/main.py`), and process tree construction via `auditd` telemetry (`ausearch -i -x whoami` -> PPID `1018` -> PID `577` Python application execution spawning a Python reverse shell). Analyzed supply chain compromise patterns and process tree analysis as a universal detection control.
-Takeaway: Tracing execution chains via `auditd` process tree construction (`ausearch -i --pid`/`--ppid`) bridges web-layer command injection (e.g., ping forms) with endpoint post-exploitation binaries, providing deterministic evidence of service compromise.

# October 21, 2026
Focus: Linux Logs - Process Tree Construction & Service Breach Tracing (`auditd`)

-What I did: Evaluated process tree analysis techniques in TryHackMe's "Linux Logs" room to trace initial access and post-exploitation service breaches. Used `auditd` commands (`ausearch -i -x command` to locate execution, `ausearch -i --pid <PPID>` to walk up parent processes to PID 1, and `ausearch -i --ppid <PID>` to enumerate child processes). Reconstructed an exploitation chain demonstrating how an web application (`/opt/mywebapp/app.py`, PID 3898) spawned `/bin/sh` child processes to execute reconnaissance (`whoami`, `ls -la`) and secondary payloads (`curl ... | sh`). Applied process tree walking to investigate the TryPingMe breach scenario.
-Takeaway: When application logs are absent or sanitized, process tree analysis via audit telemetry provides a reliable, universal approach to trace command lineage back to compromised parent services.

# October 20, 2026
Focus: Linux Logs - SSH Initial Access & External Remote Services (T1133)

-What I did: Investigated Linux Initial Access mechanisms focusing on exposed SSH services in TryHackMe's "Linux Logs" room. Analyzed MITRE ATT&CK T1133 (External Remote Services) attack vectors, contrasting key-based compromise risks (leaked private keys in repositories/automation servers, credential stealers) with password-based vulnerability vectors (weak temporary passwords, exposed legacy instances, automated botnet brute-forcing). Reviewed real-world threat group campaigns (e.g., Outlaw group) and advanced exposure risks (SSH server CVEs and session hijacking).
-Takeaway: SSH is the dominant perimeter exposure vector on Linux infrastructure; detecting SSH-based Initial Access requires monitoring authentication logs for high-frequency password brute-force patterns and key-based session origin anomalies.

# October 19, 2026
Focus: Linux Logs - Audit Daemon (auditd) & Runtime System Call Monitoring

-What I did: Explored kernel-level runtime auditing using `auditd` in TryHackMe's "Linux Logs" room. Analyzed ruleset configuration (`/etc/audit/rules.d/`), investigated real-time audit logs via `ausearch -i`, and dissected multi-line syscall event structures (`PROCTITLE`, `CWD`, `PATH`, and `SYSCALL`). Processed key identification fields including process tree identifiers (`pid`, `ppid`), session tracking (`tty`), executable paths (`exe`), rule keys (`key`), and user privilege escalation indicators (`auid` audit user vs `uid` effective execution user). Compared `auditd` with alternative Linux endpoint detection tools (Sysmon for Linux, Falco for container workloads, Osquery, and commercial EDRs).
-Takeaway: `auditd` provides granular syscall visibility into process creation (`execve`) and critical file modification (`openat`/`write`), making `auid` vs `uid` tracking vital for detecting privilege escalation and post-exploitation activity on Linux endpoints.

# October 18, 2026
Focus: Linux Logs - Generic System Logs & App-Specific Logging

-What I did: Deepened analysis of system and application log structures in TryHackMe's "Linux Logs" room. Evaluated generic Linux system logs (`/var/log/kern.log`, `/var/log/syslog` / `messages`, Debian package logs `/var/log/dpkg.log` / `apt`, and RHEL package logs `/var/log/dnf.log` / `yum.log`). Examined application-specific logging telemetry with a focus on Nginx web server access logs (`/var/log/nginx/access.log`), mapping HTTP request lines, status codes (e.g., 200, 302 redirect, 403 forbidden), response sizes, and client source IPs.
-Takeaway: Combining generic system telemetry with application-specific logs (e.g., Nginx, database, mail, container) allows SOC analysts to correlate web-based intrusion attempts with underlying host and kernel activity.

# October 17, 2026
Focus: Linux Logs - Log Format, `/var/log` Architecture, & Filtering

-What I did: Investigated Linux system logging mechanisms in TryHackMe's "Linux Logs" room. Evaluated plain-text file storage in `/var/log/` (e.g., `/var/log/syslog`, `/var/log/auth.log`, `/var/log/kern.log`), analyzed log structure differences compared to binary Windows EVTX logs, and practiced command-line log discovery/filtering techniques using `grep` (including recursive search `grep -R -E "auth|login|session" /var/log`).
-Takeaway: Unlike structured Windows Event logs, default Linux logs are plain-text and distribution-dependent; mastering CLI tools (`grep`, `awk`, `cat`, `less`) across `/var/log` enables rapid identification of system events, cron jobs, and authentication attempts.

# October 16, 2026
Focus: Linux Logs - Introduction & Environment Setup

-What I did: Started the "Linux Logs" room in TryHackMe's SOC Level 1 path. Reviewed core learning objectives covering Linux authentication, runtime, and system logs, log analysis CLI tools/commands, and `auditd` event monitoring across on-premises and cloud-native containerized workloads. Initialized the target lab machine environment.
-Takeaway: Linux log analysis requires familiarity with both traditional file-based logs (`/var/log`) and systemd journal telemetry, alongside audit daemon (`auditd`) rules to trace root activities, authentication events, and process execution.

# October 15, 2026
Focus: Windows Initial Access - Phishing, USB Vectors, & Room Conclusion (100%)

-What I did: Completed the remaining tasks and wrapped up the "Windows Initial Access" room in TryHackMe's SOC Level 1 path (100% completion). Analyzed Initial Access via Phishing (T1566) and Removable Media/USB (T1091), alongside process execution signatures (e.g., LNK payload execution).
-Takeaway: Detecting early-stage Windows breaches requires dual-pivot telemetry: exposed service intrusions (RDP/SMB) map directly to Event IDs 4624/4625, while user-driven vectors (Phishing/USB) rely on Sysmon Event ID 1 process trees to trace malicious child process execution.

# October 14, 2026
Focus: Windows Initial Access - Phishing, Removable Media, & Threat Actor TTPs

-What I did: Deepened analysis of user-driven Windows Initial Access vectors in TryHackMe's "Windows Initial Access" room. Evaluated MITRE ATT&CK techniques T1566 (Phishing via malicious links/attachments) and T1091 (Replication Through Removable Media via USB drop attacks). Reviewed modern Initial Access tendencies and real-world campaign telemetry across major ransomware groups (e.g., Medusa, Akira) leveraging both edge-exposed service exploitation and user-driven execution vectors.
-Takeaway: Even isolated workstations remain vulnerable to Initial Access via social engineering and physical vectors; SOC monitoring strategies must account for multi-stage threat actor TTPs across both perimeter boundaries and endpoint user execution.

# October 13, 2026
Focus: Windows Event Logs - Room Completion & Module Wrap-Up (100%)

-What I did: Completed the "Windows Event Logs" room in TryHackMe's SOC Level 1 path. Consolidated key analytical takeaways across Windows authentication telemetry (4624/4625), Logon ID and PID correlation for attack chain reconstruction, advanced endpoint visibility via Sysmon process creation monitoring (Event ID 1), and PowerShell script-block logging.
-Takeaway: Correlating authentication IDs with endpoint process trees and PowerShell command-line logs provides the necessary context to map out initial access execution and lateral movement.

# October 12, 2026
Focus: Windows Event Logs - Process Monitoring (Sysmon Event ID 1 & 4688)

-What I did: Investigated process creation monitoring in TryHackMe's "Windows Event Logs" room. Compared Security Log Event ID 4688 with Sysmon Event ID 1 (Process Creation), evaluating critical telemetry fields: Process Info (PID, Image Path, Command Line), Parent Process Context (building process trees/attack chains), Binary Metadata (PE hashes, signatures), and User Context (Logon ID linkage). Located Sysmon logs in Event Viewer under `Applications and Services Logs -> Microsoft -> Windows -> Sysmon -> Operational`.
-Takeaway: Process creation logs bridge the gap between authentication alerts and endpoint execution; analyzing parent-child process relationships (e.g., MS Office spawning PowerShell) provides immediate visibility into post-exploitation initial access vectors.

# October 11, 2026
Focus: Windows Initial Access - Exposed Services vs. User-Driven Vectors

-What I did: Initiated the Windows Initial Access module in TryHackMe's SOC Level 1 path. Evaluated the core taxonomies of Initial Access mechanisms across Exposed Services (MITRE ATT&CK T1133: External Remote Services via RDP/SSH/VNC; T1190: Exploit Public-Facing Application) and User-Driven Vectors (MITRE ATT&CK T1566: Phishing attachments/links; T1091: Replication Through Removable Media).
-Takeaway: Initial Access strategies divide cleanly into active exploitation of perimeter-exposed listening ports and social-engineering vectors targeting internal workstations; defenders must monitor both perimeter edge logs and endpoint execution indicators to detect early entry.

# October 10, 2026
Focus: Windows Event Logs - Authentication Logs (4624 & 4625) & Practical Analysis

-What I did: Deepened analysis of Windows Security logs in TryHackMe's "Windows Event Logs" room, evaluating Event ID 4624 (Successful Logon) and Event ID 4625 (Failed Logon). Examined key logon types (Type 3 Network via NLA, Type 10 RemoteInteractive/RDP), logon parameters (Logon ID, Subject/Target User, Workstation Name, Source IP), and RDP brute force detection indicators. Analyzed the `Practice-Security.evtx` dataset to investigate an active RDP brute force attack targeting `THM-PC`.
-Takeaway: Detecting RDP compromise requires correlating high-frequency Event ID 4625 brute-force failures from an untrusted source IP with a subsequent Event ID 4624/Type 10 success event sharing the same source IP and target account.

# October 9, 2026
Focus: Windows Event Logs - Logging Overview & Event Viewer Anatomy

-What I did: Initiated the Windows Event Logs module in TryHackMe's SOC Level 1 path. Studied the fundamentals of Windows logging architectures, examining binary `.evtx` log structures (`C:\Windows\System32\winevt\Logs`), Event Viewer navigation (`eventvwr`), log sources (Application vs. Security), key log attributes (System Timestamp, Event IDs like 4625 for failed logins, Keywords), and filtering controls.
-Takeaway: Windows logs are stored in binary EVTX format and rely on structured Event IDs; mastering log categories and Event Viewer XML/plaintext filtering is essential for triage, threat hunting, and incident response timelines.

# October 8, 2026
Focus: Detecting Web Attacks - Room Completion & Module Wrap-Up (100%)

-What I did: Successfully wrapped up the "Detecting Web Attacks" room in TryHackMe's SOC Level 1 path (100% completion). Summarized core detection strategies spanning client-side/server-side attack vectors, log-based access analysis, network traffic packet capture inspection, and Web Application Firewall (WAF) rule sets.
-Takeaway: Correlating indicators across web access logs, raw packet captures, and WAF alert feeds eliminates alert silos, enabling SOC analysts to reconstruct complete web attack timelines from initial scanning to exploitation and exfiltration.

# October 7, 2026
Focus: Detecting Web Attacks - Web Application Firewalls (WAFs) & Mitigation Rules

-What I did: Analyzed Web Application Firewall (WAF) mitigation mechanisms in TryHackMe's "Detecting Web Attacks" room. Evaluated WAF rule categories (Signature/Payload Blocking, Known Malicious IP/Threat Intel Reputation, Custom URI Rules, and Rate-Limiting), challenge-response mechanisms (CAPTCHA for bot traffic mitigation), and automated threat intelligence feed integrations (OWASP Top 10 rule sets, CVE protection, and botnet/VPN IP curation).
-Takeaway: WAFs serve as layer-7 gatekeepers capable of inspecting full TLS-decrypted HTTP payloads; combining automated signature feeds with custom heuristic rules blocks malicious tools (e.g., SQLMap User-Agents) without impacting legitimate web traffic.

# October 6, 2026
Focus: Detecting Web Attacks - Log-Based Detection & TryBankMe Investigation

-What I did: Analyzed log-based detection fundamentals in TryHackMe's "Detecting Web Attacks" room. Evaluated access log formats (Client IP, Timestamp, HTTP Status Codes, Response Size, Referrer, User-Agent), studied log signatures across directory fuzzing, HTTP POST brute-forcing, and SQL injection (SQLi), and noted structural log limitations (omission of POST request bodies/payloads). Initialized investigation of the `access.log` dataset for the TryBankMe incident on the Desktop.
-Takeaway: Web access logs provide critical forensic timelines (mapping directory enumeration and authentication redirects), but full request payload visibility—especially HTTP POST parameters—requires layer-7 packet captures or WAF logs.

# October 5, 2026
Focus: Web Security Monitoring - Detecting Web Attacks (Introduction & Setup)

-What I did: Started the "Detecting Web Attacks" room in TryHackMe's SOC Level 1 path (Web Security Monitoring module). Reviewed core learning objectives focusing on client-side/server-side web attack vectors, log-based vs. network traffic-based detection methods, and Web Application Firewall (WAF) rule analysis.
-Takeaway: Detecting web attacks requires combining log analysis (HTTP request/response status, URI parameters) and packet capture inspection (Wireshark layer-7 analysis) to accurately identify OWASP Top 10 web exploit attempts.

# October 4, 2026
Focus: Web Security Essentials - Room Conclusion & Module Wrap-Up (100%)

-What I did: Wrapped up the "Web Security Essentials" room (SOC Level 1 > Web Security Monitoring), reviewing the shift from legacy desktop applications to web-based architectures, core web request/server dynamics, high-risk exposure vectors targeting sensitive data/databases, and perimeter/host defense-in-depth strategies.
-Takeaway: Web security monitoring demands end-to-end visibility across layer-7 application payloads, server-side infrastructure behavior, and endpoint security controls to detect initial exploitation attempts before they escalate into wider infrastructure breaches.

# October 3, 2026
Focus: Web Security Essentials - Practical Hands-On Scenario (100%)

-What I did: Successfully completed the practical hands-on scenario for securing "Secure-A-Site" across three critical architectural tiers in TryHackMe's "Web Security Essentials" room: Web Application (THM{APPLICATION_SECURED_8371}), Web Server (THM{SERVER_PROTECTED_9120}), and Host Machine (THM{HOST_HARDENED_4059}). Reached 100% completion for the room.
-Takeaway: Effective web security demands a defense-in-depth approach where application-level controls (HTTPS, secure cookies, input validation), server perimeter protections (WAF rules, directory restrictions, rate limiting), and host-level hardening (firewalls, AV endpoints, minimal service exposure) work in unison.

# October 2, 2026
Focus: Web Security Essentials - Defense Systems (CDNs, WAFs, & Antivirus)

-What I did: Examined core perimeter and endpoint defense systems in TryHackMe's "Web Security Essentials" room (Task 5). Analyzed Content Delivery Network (CDN) security architectures (IP masking, DDoS mitigation, TLS enforcement, WAF integration), Web Application Firewall (WAF) deployment modes (Cloud Reverse Proxy, Host-based, Network-based) and detection mechanisms (Signature, Heuristic, Anomaly/Behavioral, IP Reputation), and endpoint Antivirus (AV) controls for mitigating malicious web file uploads.
-Takeaway: Robust web application security requires a defense-in-depth model where CDNs buffer origin servers from volumetric attacks, WAFs filter malicious layer-7 payloads, and AV endpoints catch post-exploitation tools or web shells that bypass perimeter inspection.

# October 1, 2026
Focus: Web Security Essentials - Milestone Progress (71%)

-What I did: Reached 71% progress in TryHackMe's "Web Security Essentials" room (SOC Level 1 > Web Security Monitoring). Completed core tasks covering web application fundamentals, web infrastructure components, defensive architectures, and security controls for protecting web environments.
-Takeaway: Securing modern web architectures requires defense-in-depth across client-server infrastructure, web application firewalls (WAFs), transport-layer encryption, and secure session management to safeguard against public-facing attack vectors.

# September 30, 2026
Focus: Web Application Security - Desktop-to-Web Paradigm Shift & Risk Vectors

-What I did: Investigated the security tradeoffs associated with the historical evolution from desktop to web-based applications, SaaS, and cloud architectures. Evaluated web app exposure vectors from both owner perspectives (24/7 exposure, database connectivity) and user perspectives (credential exposure, browser compromise), analyzing real-world breaches (Equifax 2017 Apache Struts vulnerability, Capital One 2019 WAF SSRF/cloud misconfiguration).
-Takeaway: Web applications serve as primary attack surfaces because they are continuously exposed to public networks and bridge external client interactions with critical back-end infrastructure and cloud databases.

# September 29, 2026
Focus: Network Discovery - Scan Types & Kibana Log Analysis

-What I did: Evaluated fundamental host/port scanning mechanics in TryHackMe's Network Discovery room, covering Ping Sweeps (ICMP Echo Request/Reply), TCP SYN Scans (stealth half-open handshake), and UDP Scans (relying on ICMP Port Unreachable or timeout heuristics). Configured Kibana (`http://MACHINE_IP:5601`) to index `All logs` for query-based scan type identification.
-Takeaway: Understanding transport and network layer scan signatures—such as incomplete TCP handshakes or ICMP unreachable cascades—enables precise query filtering in SIEM dashboards like Kibana to isolate scanning behavior from authorized vulnerability assessments.

# September 28, 2026
Focus: Network Discovery - Horizontal, Vertical, & Mixed Scanning Detection

-What I did: Deepened analysis of network discovery techniques in TryHackMe's Network Discovery room, focusing on log detection criteria for Horizontal Scans (same SRC IP, single DST port, multiple DST IPs), Vertical Scans (same SRC IP, single DST IP, multiple DST ports), and hybrid Mixed Scanning strategies.
-Takeaway: Detecting mixed horizontal and vertical scanning requires multi-dimensional log grouping—filtering on source IP while tracking distinct counts for both destination IP addresses and destination ports over specific time windows.

# September 27, 2026

Focus: Network Discovery - Horizontal vs. Vertical Port Scanning

-What I did: Investigated port scanning methodologies in TryHackMe's Network Discovery room, distinguishing between Horizontal Scanning (single port across multiple destination IPs, e.g., WannaCry SMB/445 sweeps) and Vertical Scanning (multiple ports on a single destination IP for host footprinting).
-Takeaway: Correlating log event cardinality identifies scan tactics—fixed destination port with varying destination IPs indicates a horizontal attack sweep, while fixed destination IP with varying destination ports indicates targeted vertical host reconnaissance.
# September 26, 2026
Focus: Network Discovery - External vs. Internal Log Analysis

-What I did: Completed the hands-on log analysis task in TryHackMe's Network Discovery room, analyzing exported SIEM CSV datasets (`log-session-1.csv` & `log-session-2.csv`). Filtered network sessions to identify external scanning probes from public IP `203.0.113.25` and counted `100` distinct internal scanning log entries from a compromised host.
-Takeaway: Analyzing session counts and traffic directionality (external-to-internal vs. internal-to-internal) provides immediate contextual visibility to separate low-severity perimeter probing from high-severity internal discovery.

# September 25, 2026
Focus: Network Discovery - External vs. Internal Scanning Analysis

-What I did: Analyzed external vs. internal network discovery vectors in TryHackMe's Network Discovery room using exported SIEM CSV log files (`log-session-1.csv`). Mapped external scanning to MITRE ATT&CK Reconnaissance (low severity, perimeter defense/blocking) and internal scanning to MITRE ATT&CK Discovery (high severity, active host compromise/incident escalation).
-Takeaway: Differentiating source/destination IP scopes (public vs. private) establishes alert severity—internal-to-internal port scanning signals post-compromise lateral movement preparation requiring immediate host containment and incident response.

# September 24, 2026
Focus: Network Discovery - Introduction & Core Mechanics

-What I did: Initiated the Network Discovery room in TryHackMe's SOC Level 1 path. Examined the core principles of target reconnaissance, studying why adversaries perform network discovery and how SOC analysts identify early-stage scanning, host discovery, and port enumeration across enterprise networks.
-Takeaway: Network discovery is one of the earliest visible indicators of adversary activity; detecting reconnaissance patterns allows defenders to implement proactive perimeter blocks before initial exploitation takes place.

# September 23, 2026
Focus: Network Traffic Basics - Room Completion (100%)

-What I did: Completed the "Network Traffic Basics" room on TryHackMe (100%), wrapping up foundational concepts on enterprise network architecture, perimeter security boundaries, traffic baselining, and SOC triage workflows.
-Takeaway: Enterprise defense relies on monitoring the network perimeter boundary across firewalls, Active Directory, application servers, and endpoints to detect early-stage scanning, brute-forcing, and unauthorized traffic before lateral movement occurs.

# September 22, 2026
Focus: Network Traffic Analysis - Incident Scenario Log Analysis

-What I did: Analyzed a full month of perimeter logs (`firewall.log`, `ids_alerts.log`, `vpn_auth.log`) for Initech Corp in TryHackMe's Network Traffic Analysis challenge. Traced the complete intrusion lifecycle: external reconnaissance (`198.51.100.92`), VPN credential brute-forcing against service accounts (`svc_vpn`), initial access with assigned ephemeral IP (`10.8.0.62`), internal SMB lateral movement to `10.0.0.20` (`FINANCE-SRV1`), persistent C2 beaconing on port 4444, and HTTP POST data exfiltration on ports 80/8080.
-Takeaway: Correlating log sources across firewall, IDS, and VPN auth logs allows SOC analysts to reconstruct full attack chains from initial probing to lateral movement and exfiltration.

# September 21, 2026
Focus: Network Traffic Basics - Perimeter Log Analysis & Attack Patterns

-What I did: Analyzed perimeter log samples (`firewall.log`, `waf.log`, `vpn.log`) in Task 6 of TryHackMe's "Network Traffic Basics" room. Identified key attack patterns: port scanning (`203.0.113.10`), web application attacks via WAF rule blocks (`198.51.100.200`), and VPN credential brute-forcing (`203.0.113.50`).
-Takeaway: Correlating event patterns across perimeter devices differentiates benign noise from active threats—scanning exhibits 1-to-many port connections, brute-forcing shows high-volume authentication failures, and C2 exhibits fixed-interval beaconing.

# September 20, 2026
Focus: Network Traffic Basics - Splunk Integration & Perimeter Log Investigation

-What I did: Initialized the TryHackMe practical lab environment for Network Traffic Basics. Configured local VM access to inspect ingested perimeter log sources within the Splunk Web interface (`http://MACHINE_IP:8000`) and the `Perimeter_logs` desktop directory for Task 7 incident investigation.
-Takeaway: Ingesting raw network and perimeter logs into a SIEM like Splunk allows rapid indexing, cross-protocol correlation, and efficient query-based threat hunting during network traffic analysis.

# September 19, 2026
Focus: Network Traffic Basics - Milestone Progress (90%)

-What I did: Reached 90% completion in TryHackMe's "Network Traffic Basics" room (SOC Level 1 > Network Traffic Analysis). Completed core tasks covering NTA fundamentals, primary motives for traffic analysis, layer-by-layer packet observation, network traffic sources/flows, and traffic capture mechanisms.
-Takeaway: Mastered foundational network monitoring mechanisms across TAP/SPAN access methods, flow log generation, and full packet inspection strategies to establish baseline traffic behavioral profiles in SOC environments.

# September 18, 2026
Focus: Network Traffic Analysis - TCP/IP Layer Encapsulation & Inspection

-What I did: Analyzed protocol headers across the four TCP/IP stack layers (Application, Transport, Internet, Link) in TryHackMe's Network Traffic Analysis room. Inspected HTTP application payloads (`Content-Length: 10485760`), detected TCP session hijacking via abnormal sequence number jumps, identified IP fragmentation overlaps, and analyzed MAC spoofing in gratuitous ARP poisoning attacks.
-Takeaway: Full packet captures (PCAP) provide deep header and payload visibility—such as sequence numbers, fragment offsets, and raw application bytes—that high-level log outputs sanitize or omit.

# September 17, 2026
Focus: Network Traffic Analysis - DNS Tunneling & C2 Inspection

-What I did: Analyzed the fundamental necessity of Network Traffic Analysis (NTA) in SOC operations on TryHackMe. Inspected raw DNS packet captures for host `192.168.1.16` (`WIN-016`), identifying C2 beaconing via high-frequency subdomain generation and base64-encoded command extraction within TXT record responses (`SSBsb3ZlIHlvdXIgY3VyaW91c2l0eQ==` -> `I love your curiosity`).
-Takeaway: Standard firewall and DNS logs only capture high-level metadata (query/QTYPE); full packet analysis is required to inspect payload contents and uncover covert channels like DNS tunneling and C2 instruction streams.

# September 16, 2026
Focus: Phishing Emails in Action - Room Completion (88% -> 100%)

-What I did: Completed all practical investigation tasks (Tasks 1 through 7) in TryHackMe's "Phishing Emails in Action" room, reaching 88% overall room progress prior to the final conclusion task. Analyzed phishing scenarios covering order cancellations, package tracking, multi-stage document downloads, account holds, recent purchase lures, and scheduled shipment notifications.
-Takeaway: Analyzing diverse phishing scenarios reinforces key threat patterns—such as spoofed sender domains, artificial urgency, hidden redirects, and credential harvesting landing pages—improving rapid triage capabilities for SOC analysis.


# September 15, 2026
Focus: Phishing Analysis - Multi-Stage Redirection & Credential Harvesting

-What I did: Investigated multi-stage redirection phishing campaigns within TryHackMe's Email Analysis room. Analyzed tactics including artificial urgency (same-day expiration), multi-brand impersonation (OneDrive/Adobe/Microsoft), URL redirection chains to bypass secure email gateways (SEGs), and fake authentication portals designed for credential harvesting.
-Takeaway: Attackers chain trusted document-sharing platforms with multi-stage redirects to bypass static email filters; security controls must evaluate post-click redirection paths and domain reputation beyond the initial email link.



# September 14, 2026
Focus: Phishing Emails in Action - Package Tracking Analysis (33%)

-What I did: Reached 33% progress in TryHackMe's Phishing Emails in Action room by analyzing Task 3 (Track Your Package). Examined shipping notification phishing vectors including spoofed distribution center sender addresses, tracking pixel deployment for recipient validation, and malicious link manipulation.
-Takeaway: Attackers combine tracking pixels with domain spoofing to confirm active mailboxes and lure users into payload delivery via fake package updates.

# September 14, 2026
Focus: Phishing Emails in Action - Package Tracking Analysis (33%)

-What I did: Reached 33% progress in TryHackMe's Phishing Emails in Action room by analyzing Task 3 (Track Your Package). Examined shipping notification phishing vectors including spoofed distribution center sender addresses, tracking pixel deployment for recipient validation, and malicious link manipulation.
-Takeaway: Attackers combine tracking pixels with domain spoofing to confirm active mailboxes and lure users into payload delivery via fake package updates.

# September 13, 2026
Focus: Email Analysis - Malicious Email Types & Phishing Anatomy

-What I did: Evaluated malicious email categories within TryHackMe's Email Analysis module, distinguishing between Spam, Malspam, Phishing, Spear Phishing, Whaling, Smishing, and Vishing. Analyzed social engineering indicators including sender address spoofing, artificial urgency, brand impersonation, generic greetings, hidden/shortened links, and executable payload attachments.
-Takeaway: Identifying structural phishing indicators—such as display name vs. envelope address mismatches and obfuscated URLs—enables rapid triage of incoming email security alerts.

# September 12, 2026
Focus: Email Analysis - Email Body & HTML Source Inspection

-What I did: Investigated email body structures, HTML formatting, and embedded media handling in TryHackMe's Email Analysis room. Inspected raw message code to uncover hidden HTML links, blocked remote image tags, and base64-encoded file attachments identified via `Content-Type`, `Content-Disposition`, and `Content-Transfer-Encoding` headers.
-Takeaway: Inspecting raw HTML sources and attachment encoding headers enables analysts to extract obfuscated URLs and safely reconstruct suspicious attachments without relying on client-side rendering.

# September 11, 2026
Focus: Email Analysis - Email Headers & Raw Message Inspection

-What I did: Investigated email metadata structures in TryHackMe's Email Analysis room using Thunderbird to analyze raw `.eml` samples (`email1.eml`). Inspected raw message sources (`Ctrl + U`) to extract critical header fields including From, To, Reply-To, Subject, Date, and originating IP addresses.
-Takeaway: Analyzing raw message headers reveals hidden delivery metadata and originating IP addresses that standard email client interfaces obscure, enabling SOC analysts to verify true sender identity during phishing triage.

# September 10, 2026
Focus: Email Analysis - Email Protocols & Transport Journey

-What I did: Analyzed core email transfer and retrieval protocols on TryHackMe, examining SMTP for mail transmission alongside POP3 (local download/deletion) and IMAP (server synchronization). Mapped end-to-end email routing, covering DNS MX record lookups, mail server delivery, and client mailbox retrieval.
-Takeaway: Distinguishing between transmission (SMTP) and retrieval (POP3/IMAP) protocols is critical when tracing mail header hops and auditing email logs during phishing incident response.

# September 9, 2026
Focus: Email Analysis - Anatomy of an Email Address

-What I did: Started the Email Analysis module on TryHackMe, studying the core structure and RFC-standard components of email addresses (Username, @ delimiter, and Domain Name). Evaluated how basic parsing of mailbox identification and destination mail server routing forms the baseline for phishing investigations.
-Takeaway: Understanding recipient routing fundamentals is essential for identifying spoofing anomalies, display name deceptions, and domain typosquatting during initial phishing triage.

# September 8, 2026
Focus: Unified Kill Chain - Room Completion (100%)

-What I did: Completed the Unified Kill Chain room on TryHackMe (100%), finalizing the study of all 18 phases across Initial Access, Foothold, and Action on Objectives ("Out" goals). Evaluated how the UKC framework complements Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK in identifying risk and reconstructing attack paths.
-Takeaway: Mastered the UKC framework to systematically model end-to-end adversary behavior, improving SOC alert reconstruction and threat modeling across modern, non-linear intrusion scenarios.

# September 5, 2026
Focus: Unified Kill Chain (UKC) - Phase Identification Questions

-What I did: Answered comprehension questions covering Unified Kill Chain (UKC) phases on TryHackMe. Correctly mapped tactics including email phishing, social engineering password resets, C2 infrastructure setup during Weaponization, Exploitation, Pivoting between targets, and maintaining access via Persistence.
-Takeaway: Categorizing individual adversary actions into standardized UKC phases reinforces rapid incident response triage and aids in mapping detection rules to specific threat behaviors.

# September 5, 2026
Focus: Unified Kill Chain (UKC) - Phase Identification Questions

-What I did: Answered comprehension questions covering Unified Kill Chain (UKC) phases on TryHackMe. Correctly mapped tactics including email phishing, social engineering password resets, C2 infrastructure setup during Weaponization, Exploitation, Pivoting between targets, and maintaining access via Persistence.
-Takeaway: Categorizing individual adversary actions into standardized UKC phases reinforces rapid incident response triage and aids in mapping detection rules to specific threat behaviors.

# September 4, 2026
Focus: Unified Kill Chain (UKC) - Initial Access & Foothold Phases

-What I did: Analyzed the Initial Access phase group of the Unified Kill Chain framework on TryHackMe, spanning Reconnaissance, Weaponization, Social Engineering, Exploitation, Persistence, Defense Evasion, Command & Control, and Pivoting. Mapped each operational phase to corresponding MITRE ATT&CK Tactics (TA0043, TA0001, TA0002, TA0003, TA0005, TA0011, TA0008).
-Takeaway: Analyzing initial foothold phases through the UKC model highlights how adversaries layer defense evasion and persistence alongside C2 and pivoting, allowing blue teams to disrupt intrusion paths before lateral movement occurs.

# September 3, 2026
Focus: Unified Kill Chain (UKC) - Framework Overview

-What I did: Analyzed Paul Pols' Unified Kill Chain (UKC) framework and its 18 phases, comparing its modern scope against traditional models like Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK. Evaluated the model's non-linear, iterative approach to post-exploitation, pivoting, and adversary intent.
-Takeaway: The UKC accurately reflects real-world operational threats by modeling iterative attack loops—such as post-exploitation pivoting and secondary reconnaissance—where static, linear frameworks fail.

# September 2, 2026
Focus: Threat Modeling Concepts & Frameworks

-What I did: Studied threat modeling principles within cybersecurity environments, focusing on asset identification, vulnerability assessment, remediation planning, and SDLC policy implementation. Evaluated risk frameworks such as STRIDE, DREAD, and CVSS to map attack surfaces alongside the Unified Kill Chain (UKC).
-Takeaway: Proactive threat modeling translates technical vulnerabilities into operational risk, enabling security teams to implement preventative SDLC controls and prioritize defensive engineering effort before exploitation occurs.

# September 1, 2026
Focus: Cyber Kill Chain - Introduction & Fundamental Concepts

-What I did: Reviewed the core foundational concepts of the Cyber Kill Chain framework on TryHackMe. Analyzed how military intrusion models translate to offensive cybersecurity methodologies and defensive strategy alignment to disrupt adversary operations.
-Takeaway: Understanding the sequential stages of an adversary's intrusion path allows blue teams to map defensive controls at each layer, enabling early detection and active disruption before attackers achieve their primary objectives.

# August 31, 2026
Focus: Cyber Kill Chain - Practical Scenario Analysis (Target Breach)

-What I did: Applied Cyber Kill Chain framework mapping to the historical 2013 Target data breach practical scenario on TryHackMe. Mapped attack vectors across stages including spearphishing attachments, public-facing exploits, dynamic linker hijacking, PowerShell execution, fallback C2 channels, and local system data collection.
-Takeaway: Mapping complex real-world breaches into specific Kill Chain phases enables SOC analysts to identify defensive gaps, understand adversary progression, and implement layered controls across the intrusion lifecycle.

# August 30, 2026
Focus: Cyber Kill Chain - Actions on Objectives

-What I did: Analyzed Phase 7 (Actions on Objectives) of the Cyber Kill Chain room on TryHackMe. Evaluated post-exploitation activities including credential harvesting, privilege escalation, lateral movement, data exfiltration, and adversary tactics like destroying Windows Shadow Copies to prevent system recovery.
-Takeaway: The final phase of the Cyber Kill Chain represents impact; monitoring for volume shadow copy deletion (`vssadmin delete shadows`) is critical to early detection of ransomware or destruction attempts before data loss occurs.

# August 29, 2026
Focus: Cyber Kill Chain - Command & Control (C2)

-What I did: Analyzed Phase 6 (Command and Control / C2) of the Cyber Kill Chain room on TryHackMe. Evaluated modern beaconing mechanisms across common egress channels including HTTP/HTTPS (ports 80/443) and DNS Tunneling, comparing them to legacy detection vectors like IRC.
-Takeaway: Adversaries leverage high-volume legitimate protocols (HTTP/S, DNS) for C2 beaconing to blend with regular network noise; detecting C2 requires identifying subtle periodicity and anomalous payload patterns in outbound traffic.

# August 28, 2026
Focus: Git Detached HEAD & Aborted Rebase Recovery

-What I did: Recovered from a stuck `rebase-merge` state and detached HEAD state in `~/VS Code/Github/Logbook`. Aborted the interrupted rebase session (`git rebase --abort`), checked back into the `main` branch, and successfully rebased and pushed local commits to the remote repository.
-Takeaway: When Git enters a stuck rebase state or detached HEAD, aborting the active rebase (`git rebase --abort`) before pulling allows a safe return to the target tracking branch.
