




# November 06, 2026
Focus: TryHackMe SOC Level 1 — Active Reconnaissance & Web Transport Mechanics

-What I did (TryHackMe): Investigated active web reconnaissance fundamentals using standard web browsers in TryHackMe's SOC Level 1 path. Evaluated transport-level communication mechanics across plain HTTP (TCP/80), HTTPS (TCP/443), and modern HTTP/3 utilizing the QUIC protocol over UDP/443 (identifiable via `h3` in browser Network developer tools). Analyzed non-standard port probing via explicit URL addressing (e.g., `:8443`, `:8080`) and assessed why standard browser traffic poses low-noise reconnaissance detection challenges for perimeter defenders.
-Takeaway (TryHackMe): Web browsers blend naturally with legitimate user traffic, making them stealthy active recon instruments; identifying transport variations like HTTP/3 (`QUIC` over UDP/443) and targeting non-standard web ports (`8080`, `8443`) are essential steps in uncovering unindexed administrative or development interfaces.

-Daily Outcome: Completed Web Browser Active Reconnaissance & Transport-Level Basics task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 05, 2026
Focus: TryHackMe SOC Level 1 — Shodan & Passive Exposure Analytics

-What I did (TryHackMe): Evaluated passive device exposure and service banner reconnaissance using Shodan in TryHackMe's SOC Level 1 path[cite: 1]. Practiced search query filters including `hostname:`, `org:`, `port:`, `country:`, and technology stack tags like `http.component:`[cite: 1]. Investigated target host exposure profiles (Cloudflare infrastructure, open ports, banners) and cross-referenced results using Censys.io[cite: 1]. Performed global product searches (e.g., `product:Apache`, `product:nginx`) to analyze host aggregation distributions across Top Countries and Top Ports panels[cite: 1].
-Takeaway (TryHackMe): Shodan and Censys provide granular, zero-traffic visibility into external infrastructure, service banners, and technology stacks, allowing SOC defenders to analyze perimeter exposures without sending packets to target networks[cite: 1].

-Daily Outcome: Completed Shodan search query fundamentals and global telemetry exercises[cite: 1]. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 04, 2026
Focus: TryHackMe SOC Level 1 — Passive Subdomain Discovery & CT Log Analysis

-What I did (TryHackMe): Evaluated passive subdomain enumeration techniques and OSINT tools in TryHackMe's SOC Level 1 path. Investigated DNSDumpster for public DNS record aggregation, host IP geolocation mapping, and domain relationship graphing without active scanning. Deep-dived into Certificate Transparency (CT) logs using `crt.sh` (`%.tryhackme.com` wildcard queries) to extract Subject Alternative Name (SAN) fields across issued SSL/TLS certificates. Examined defensive applications including dangling DNS record monitoring and subdomain takeover prevention.
-Takeaway (TryHackMe): Certificate Transparency logs (`crt.sh`) provide real-time, zero-traffic subdomain discovery that significantly outpaces passive DNS databases; identifying unadvertised development panels and staging environments (`dev`, `app`, `blog`) is vital for mapping an organization's true attack surface.

-Daily Outcome: Completed Passive Subdomain Discovery task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 03, 2026
Focus: TryHackMe SOC Level 1 — Passive Reconnaissance & DNS Querying

-What I did (TryHackMe): Investigated DNS record enumeration techniques in TryHackMe's SOC Level 1 path. Evaluated DNS query tools, contrasting legacy interactive lookup (`nslookup`) with modern, scriptable query tools (`dig`). Mapped standard DNS record types (A, AAAA, CNAME, MX, SOA, TXT) and analyzed how querying public/open resolvers (e.g., Cloudflare `1.1.1.1`) maintains a passive reconnaissance posture without generating target server log events.
-Takeaway (TryHackMe): `dig` is the preferred tool for DNS intelligence due to default TTL output, clean Unix output formatting, and precise flag control; querying open resolvers yields essential asset telemetry (SPF/DMARC, mail routing, IP mapping) while keeping recon 100% passive.

-Daily Outcome: Completed DNS record querying and passive DNS analysis module. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 02, 2026
Focus: TryHackMe SOC Level 1 — Reconnaissance Methodologies (Passive vs. Active)

-What I did (TryHackMe): Evaluated core reconnaissance methodologies in TryHackMe's SOC Level 1 path. Contrasted Passive Reconnaissance (OSINT, DNS resolvers, crt.sh transparency logs, job posting tech stacks, public repositories) with Active Reconnaissance (ICMP/ARP host discovery, Nmap/masscan port scanning, web fuzzing, direct social engineering). Analyzed detection profiles (IDS/IPS, WAF alerts) and answered exercise questions categorizing specific scenarios (Facebook employee mapping = Passive, Webserver ICMP pinging = Active, Party-based IT Admin social engineering = Active).
-Takeaway (TryHackMe): Passive recon provides stealthy, zero-footprint OSINT without generating target log telemetry, whereas any direct host interaction (packet sending) or human engagement (social engineering/vishing) constitutes active reconnaissance.

-Daily Outcome: Completed Reconnaissance taxonomy analysis and exercise questions. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 01, 2026
Focus: TryHackMe SOC Level 1 — Penetration Testing Reporting & Documentation Standards

-What I did (TryHackMe): Evaluated penetration test reporting fundamentals and documentation methodologies in TryHackMe's SOC Level 1 path. Analyzed essential report structure components (Cover Page, Executive Summary for non-technical stakeholders, Technical Summary for engineering leads, Prioritized Vulnerability Severity Matrix, and Detailed Exploitation/Remediation sections). Examined standardized vulnerability documentation formats using a concrete finding report (Title, Severity, Description, Step-by-Step Proof of Concept, and Defense-in-Depth Recommendations).
-Takeaway (TryHackMe): High-quality penetration testing reporting translates technical risk into business context; findings must feature reproducible exploitation steps alongside actionable remediation guidance (e.g., secrets management and least privilege enforcement).

-Daily Outcome: Completed Penetration Testing Reporting & Documentation Standards module milestone. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.