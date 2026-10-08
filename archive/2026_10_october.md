















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