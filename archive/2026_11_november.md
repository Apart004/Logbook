












# November 11, 2026
* Completed **Active Reconnaissance (Tasks 2 & 3 — ARP Broadcast & Subnet Boundary Simulation)** on TryHackMe, verifying link-layer packet isolation across default gateways. Logged in [`tracks/tryhackme.md`](../tracks/tryhackme.md#active-reconnaissance--tryhackme-writeup).
* Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, Codelivly SOC Path, and LeetCode tracks on hold.

# November 10, 2026
* Completed **Active Reconnaissance (Task 6 — Netcat Banner Grabbing)** on TryHackMe, grabbing the FTP service banner on port 21 via `nc` and reviewing listener flags (`-vnlp`). Logged in [`tracks/tryhackme.md`](../tracks/tryhackme.md#active-reconnaissance--tryhackme-writeup).
* Started **Brutus (Sherlock — DFIR)** on Hack The Box and solved Tasks 1–3 (identified SSH brute-force IP `65.2.161.68`, `root` compromise in `auth.log`, and manual PTY login at `2024-03-06 06:32:45 UTC` in `wtmp` via `utmp.py`). Logged in [`tracks/hackthebox.md`](../tracks/hackthebox.md#brutus-sherlock--dfir).
* Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 09, 2026
Focus: TryHackMe SOC Level 1 & Codelivly SOC Path Initialization

-What I did (TryHackMe): Analyzed multi-run `traceroute` output variations against `tryhackme.com` in TryHackMe's SOC Level 1 path. Examined hop counts (14 vs. 26 hops), per-hop three-packet probe round-trip times, load balancing path divergence across intermediate routers, and CDN anycast routing effects (Cloudflare/Akamai). Evaluated suppressed ICMP responses (`*` hops due to rate limiting/firewall filtering) alongside advanced variants (`mtr` continuous packet loss/latency tracking, TCP `-T` and ICMP `-I` filter-evasion probes, and `traceroute6`).
-Takeaway (TryHackMe): Consecutive `traceroute` runs rarely take identical paths across external networks due to dynamic routing, load balancing, and CDN anycast; combining `traceroute` with `mtr` and TCP/ICMP probe flags provides accurate network topology and filtering visibility.

-What I did (Codelivly): Initialized `tracks/codelivly.md` for the Codelivly SOC Learning Path. Started "Computer Fundamentals" (Lesson 1: "What is a Computer?"), completing IPOS cycle theory questions and Brightwater embedded device inventory CTF tasks (3/7 tasks completed, 43%)[cite: 2, 3].
-Takeaway (Codelivly): Grounding security fundamentals in the IPOS cycle and asset inventory principles reinforces visibility across both enterprise endpoints and embedded network devices[cite: 2, 3].

-Daily Outcome: Completed `traceroute` output analysis on TryHackMe and launched the Codelivly SOC track (`tracks/codelivly.md`). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 08, 2026
Focus: TryHackMe SOC Level 1 — Active Reconnaissance & Traceroute Mechanics

-What I did (TryHackMe): Investigated network topology mapping and hop discovery using `traceroute` in TryHackMe's SOC Level 1 path. Analyzed IP header Time-to-Live (TTL) decrement mechanics, evaluating how incremental TTL probes (`TTL=1`, `2`, `3`...) trigger ICMP Time-to-Live Exceeded messages from intermediate routers to enumerate network paths. Contrasted cross-platform CLI execution (`traceroute` on Linux/macOS vs. `tracert` on Windows, plus `-6`/`traceroute6` for IPv6) and protocol variants on Linux (default UDP probes vs. TCP `-T` and ICMP `-I` flags for firewall filter evasion). Examined dynamic routing impacts (BGP, OSPF, anycast, load balancing) and interpreted filtered hops (`*`).
-Takeaway (TryHackMe): `traceroute` maps intermediate routing infrastructure and perimeter filtering boundaries by manipulating IP TTL fields; switching between UDP, TCP (`-T`), and ICMP (`-I`) probes allows analysts to bypass restrictive firewall rules during active network discovery.

-Daily Outcome: Completed `traceroute` network path discovery and protocol variant analysis task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# November 07, 2026
Focus: TryHackMe SOC Level 1 — Active Reconnaissance & ICMP Ping Mechanics

-What I did (TryHackMe): Investigated active host reachability testing using `ping` in TryHackMe's SOC Level 1 path. Analyzed underlying ICMP protocol mechanics, mapping ICMP Echo Request (Type 8) and ICMP Echo Reply (Type 0) exchanges. Contrasted cross-platform CLI execution flags (`ping -c` on Linux/macOS vs. `ping -n` on Windows), DNS name resolution dependencies prior to ICMP transmission, and dual-stack protocol forcing (`-4` and `-6` flags / `ping6`).
-Takeaway (TryHackMe): `ping` provides a lightweight layer-3 reachability verification step prior to deep port scanning, though perimeter firewalls frequently drop ICMP Type 8 packets—requiring secondary TCP/UDP probing techniques when ICMP replies are blocked.

-Daily Outcome: Completed ICMP `ping` active reconnaissance mechanics task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

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