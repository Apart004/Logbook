















# September 23, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Basics

-What I did (TryHackMe): Completed the "Network Traffic Basics" room on TryHackMe (100%), wrapping up foundational concepts on enterprise network architecture, perimeter security boundaries, traffic baselining, and SOC triage workflows.
-Takeaway (TryHackMe): Enterprise defense relies on monitoring the network perimeter boundary across firewalls, Active Directory, application servers, and endpoints to detect early-stage scanning, brute-forcing, and unauthorized traffic before lateral movement occurs.

-Daily Outcome: Completed Network Traffic Basics room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 22, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Analysis

-What I did (TryHackMe): Analyzed a full month of perimeter logs (`firewall.log`, `ids_alerts.log`, `vpn_auth.log`) for Initech Corp in TryHackMe's Network Traffic Analysis challenge. Traced the complete intrusion lifecycle: external reconnaissance (`198.51.100.92`), VPN credential brute-forcing against service accounts (`svc_vpn`), initial access with assigned ephemeral IP (`10.8.0.62`), internal SMB lateral movement to `10.0.0.20` (`FINANCE-SRV1`), persistent C2 beaconing on port 4444, and HTTP POST data exfiltration on ports 80/8080.
-Takeaway (TryHackMe): Correlating log sources across firewall, IDS, and VPN auth logs allows SOC analysts to reconstruct full attack chains from initial probing to lateral movement and exfiltration.

-Daily Outcome: Completed Incident Scenario Log Analysis in Network Traffic Analysis room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 21, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Basics

-What I did (TryHackMe): Analyzed perimeter log samples (`firewall.log`, `waf.log`, `vpn.log`) in Task 6 of TryHackMe's "Network Traffic Basics" room. Identified key attack patterns: port scanning (`203.0.113.10`), web application attacks via WAF rule blocks (`198.51.100.200`), and VPN credential brute-forcing (`203.0.113.50`).
-Takeaway (TryHackMe): Correlating event patterns across perimeter devices differentiates benign noise from active threats—scanning exhibits 1-to-many port connections, brute-forcing shows high-volume authentication failures, and C2 exhibits fixed-interval beaconing.

-Daily Outcome: Completed Task 6 Perimeter Log Analysis scenario. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 20, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Basics

-What I did (TryHackMe): Initialized the TryHackMe practical lab environment for Network Traffic Basics. Configured local VM access to inspect ingested perimeter log sources within the Splunk Web interface (`http://MACHINE_IP:8000`) and the `Perimeter_logs` desktop directory for Task 7 incident investigation.
-Takeaway (TryHackMe): Ingesting raw network and perimeter logs into a SIEM like Splunk allows rapid indexing, cross-protocol correlation, and efficient query-based threat hunting during network traffic analysis.

-Daily Outcome: Deployed lab machine and initiated Splunk perimeter log investigation. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 19, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Basics

-What I did (TryHackMe): Reached 90% completion in TryHackMe's "Network Traffic Basics" room (SOC Level 1 > Network Traffic Analysis). Completed core tasks covering NTA fundamentals, primary motives for traffic analysis, layer-by-layer packet observation, network traffic sources/flows, and traffic capture mechanisms.
-Takeaway (TryHackMe): Mastered foundational network monitoring mechanisms across TAP/SPAN access methods, flow log generation, and full packet inspection strategies to establish baseline traffic behavioral profiles in SOC environments.

-Daily Outcome: Reached 90% completion in Network Traffic Basics room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 18, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Analysis

-What I did (TryHackMe): Analyzed protocol headers across the four TCP/IP stack layers (Application, Transport, Internet, Link) in TryHackMe's Network Traffic Analysis room. Inspected HTTP application payloads (`Content-Length: 10485760`), detected TCP session hijacking via abnormal sequence number jumps, identified IP fragmentation overlaps, and analyzed MAC spoofing in gratuitous ARP poisoning attacks.
-Takeaway (TryHackMe): Full packet captures (PCAP) provide deep header and payload visibility—such as sequence numbers, fragment offsets, and raw application bytes—that high-level log outputs sanitize or omit.

-Daily Outcome: Completed TCP/IP Stack Encapsulation and Layered Inspection task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 17, 2026
Focus: TryHackMe SOC Level 1 - Network Traffic Analysis

-What I did (TryHackMe): Analyzed the fundamental necessity of Network Traffic Analysis (NTA) in SOC operations on TryHackMe. Inspected raw DNS packet captures for host `192.168.1.16` (`WIN-016`), identifying C2 beaconing via high-frequency subdomain generation and base64-encoded command extraction within TXT record responses (`SSBsb3ZlIHlvdXIgY3VyaW91c2l0eQ==` -> `I love your curiosity`).
-Takeaway (TryHackMe): Standard firewall and DNS logs only capture high-level metadata (query/QTYPE); full packet analysis is required to inspect payload contents and uncover covert channels like DNS tunneling and C2 instruction streams.

-Daily Outcome: Completed Introduction to Network Traffic Analysis and DNS Tunneling practical scenario. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 16, 2026
Focus: TryHackMe SOC Level 1 - Phishing Emails in Action

-What I did (TryHackMe): Completed all practical investigation tasks (Tasks 1 through 7) in TryHackMe's "Phishing Emails in Action" room, reaching 88% overall room progress prior to the final conclusion task. Analyzed phishing scenarios covering order cancellations, package tracking, multi-stage document downloads, account holds, recent purchase lures, and scheduled shipment notifications.
-Takeaway (TryHackMe): Analyzing diverse phishing scenarios reinforces key threat patterns—such as spoofed sender domains, artificial urgency, hidden redirects, and credential harvesting landing pages—improving rapid triage capabilities for SOC analysis.

-Daily Outcome: Reached 88% progress on Phishing Emails in Action upon completing Task 7. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 14, 2026
Focus: TryHackMe SOC Level 1 - Phishing Emails in Action

-What I did (TryHackMe): Reached 33% progress in TryHackMe's Phishing Emails in Action room by analyzing Task 3 (Track Your Package). Examined shipping notification phishing vectors including spoofed distribution center sender addresses, tracking pixel deployment for recipient validation, and malicious link manipulation.
-Takeaway (TryHackMe): Attackers combine tracking pixels with domain spoofing to confirm active mailboxes and lure users into payload delivery via fake package updates.

-Daily Outcome: Reached 33% completion in Phishing Emails in Action. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 13, 2026
Focus: TryHackMe SOC Level 1 - Email Analysis

-What I did (TryHackMe): Evaluated malicious email categories within TryHackMe's Email Analysis module, distinguishing between Spam, Malspam, Phishing, Spear Phishing, Whaling, Smishing, and Vishing. Analyzed social engineering indicators including sender address spoofing, artificial urgency, brand impersonation, generic greetings, hidden/shortened links, and executable payload attachments.
-Takeaway (TryHackMe): Identifying structural phishing indicators—such as display name vs. envelope address mismatches and obfuscated URLs—enables rapid triage of incoming email security alerts.

-Daily Outcome: Completed Malicious Email Types & Phishing Anatomy task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 12, 2026
Focus: TryHackMe SOC Level 1 - Email Analysis

-What I did (TryHackMe): Investigated email body structures, HTML formatting, and embedded media handling in TryHackMe's Email Analysis room. Inspected raw message code to uncover hidden HTML links, blocked remote image tags, and base64-encoded file attachments identified via `Content-Type`, `Content-Disposition`, and `Content-Transfer-Encoding` headers.
-Takeaway (TryHackMe): Inspecting raw HTML sources and attachment encoding headers enables analysts to extract obfuscated URLs and safely reconstruct suspicious attachments without relying on client-side rendering.

-Daily Outcome: Completed Email Body & HTML Source Inspection task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 11, 2026
Focus: TryHackMe SOC Level 1 - Email Analysis

-What I did (TryHackMe): Investigated email metadata structures in TryHackMe's Email Analysis room using Thunderbird to analyze raw `.eml` samples (`email1.eml`). Inspected raw message sources (`Ctrl + U`) to extract critical header fields including From, To, Reply-To, Subject, Date, and originating IP addresses.
-Takeaway (TryHackMe): Analyzing raw message headers reveals hidden delivery metadata and originating IP addresses that standard email client interfaces obscure, enabling SOC analysts to verify true sender identity during phishing triage.

-Daily Outcome: Completed Email Headers & Raw Message Inspection task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 10, 2026
Focus: TryHackMe SOC Level 1 - Email Analysis

-What I did (TryHackMe): Analyzed core email transfer and retrieval protocols on TryHackMe, examining SMTP for mail transmission alongside POP3 (local download/deletion) and IMAP (server synchronization). Mapped end-to-end email routing, covering DNS MX record lookups, mail server delivery, and client mailbox retrieval.
-Takeaway (TryHackMe): Distinguishing between transmission (SMTP) and retrieval (POP3/IMAP) protocols is critical when tracing mail header hops and auditing email logs during phishing incident response.

-Daily Outcome: Completed Email Protocols & Transport Journey task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 9, 2026
Focus: TryHackMe SOC Level 1 - Email Analysis

-What I did (TryHackMe): Started the Email Analysis module on TryHackMe, studying the core structure and RFC-standard components of email addresses (Username, @ delimiter, and Domain Name). Evaluated how basic parsing of mailbox identification and destination mail server routing forms the baseline for phishing investigations.
-Takeaway (TryHackMe): Understanding recipient routing fundamentals is essential for identifying spoofing anomalies, display name deceptions, and domain typosquatting during initial phishing triage.

-Daily Outcome: Completed Anatomy of an Email Address introductory task. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 8, 2026
Focus: TryHackMe SOC Level 1 - Unified Kill Chain

-What I did (TryHackMe): Completed the Unified Kill Chain room on TryHackMe (100%), finalizing the study of all 18 phases across Initial Access, Foothold, and Action on Objectives ("Out" goals). Evaluated how the UKC framework complements Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK in identifying risk and reconstructing attack paths.
-Takeaway (TryHackMe): Mastered the UKC framework to systematically model end-to-end adversary behavior, improving SOC alert reconstruction and threat modeling across modern, non-linear intrusion scenarios.

-Daily Outcome: Completed Unified Kill Chain room (100%). Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 5, 2026
Focus: TryHackMe SOC Level 1 - Unified Kill Chain

-What I did (TryHackMe): Answered comprehension questions covering Unified Kill Chain (UKC) phases on TryHackMe. Correctly mapped tactics including email phishing, social engineering password resets, C2 infrastructure setup during Weaponization, Exploitation, Pivoting between targets, and maintaining access via Persistence.
-Takeaway (TryHackMe): Categorizing individual adversary actions into standardized UKC phases reinforces rapid incident response triage and aids in mapping detection rules to specific threat behaviors.

-Daily Outcome: Completed phase identification task in Unified Kill Chain room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 5, 2026
Focus: TryHackMe SOC Level 1 - Unified Kill Chain

-What I did (TryHackMe): Answered comprehension questions covering Unified Kill Chain (UKC) phases on TryHackMe. Correctly mapped tactics including email phishing, social engineering password resets, C2 infrastructure setup during Weaponization, Exploitation, Pivoting between targets, and maintaining access via Persistence.
-Takeaway (TryHackMe): Categorizing individual adversary actions into standardized UKC phases reinforces rapid incident response triage and aids in mapping detection rules to specific threat behaviors.

-Daily Outcome: Completed phase identification task in Unified Kill Chain room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 4, 2026
Focus: TryHackMe SOC Level 1 - Unified Kill Chain

-What I did (TryHackMe): Analyzed the Initial Access phase group of the Unified Kill Chain framework on TryHackMe, spanning Reconnaissance, Weaponization, Social Engineering, Exploitation, Persistence, Defense Evasion, Command & Control, and Pivoting. Mapped each operational phase to corresponding MITRE ATT&CK Tactics (TA0043, TA0001, TA0002, TA0003, TA0005, TA0011, TA0008).
-Takeaway (TryHackMe): Analyzing initial foothold phases through the UKC model highlights how adversaries layer defense evasion and persistence alongside C2 and pivoting, allowing blue teams to disrupt intrusion paths before lateral movement occurs.

-Daily Outcome: Completed Initial Access module in Unified Kill Chain room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 3, 2026
Focus: TryHackMe SOC Level 1 - Unified Kill Chain

-What I did (TryHackMe): Analyzed Paul Pols' Unified Kill Chain (UKC) framework and its 18 phases, comparing its modern scope against traditional models like Lockheed Martin's Cyber Kill Chain and MITRE ATT&CK. Evaluated the model's non-linear, iterative approach to post-exploitation, pivoting, and adversary intent.
-Takeaway (TryHackMe): The UKC accurately reflects real-world operational threats by modeling iterative attack loops—such as post-exploitation pivoting and secondary reconnaissance—where static, linear frameworks fail.

-Daily Outcome: Completed Unified Kill Chain introductory module. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 2, 2026
Focus: TryHackMe SOC Level 1 - Threat Modeling

-What I did (TryHackMe): Studied threat modeling principles within cybersecurity environments, focusing on asset identification, vulnerability assessment, remediation planning, and SDLC policy implementation. Evaluated risk frameworks such as STRIDE, DREAD, and CVSS to map attack surfaces alongside the Unified Kill Chain (UKC).
-Takeaway (TryHackMe): Proactive threat modeling translates technical vulnerabilities into operational risk, enabling security teams to implement preventative SDLC controls and prioritize defensive engineering effort before exploitation occurs.

-Daily Outcome: Completed Threat Modeling introduction module. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.

# September 1, 2026
Focus: TryHackMe SOC Level 1 - Cyber Kill Chain

-What I did (TryHackMe): Reviewed the core foundational concepts of the Cyber Kill Chain framework on TryHackMe. Analyzed how military intrusion models translate to offensive cybersecurity methodologies and defensive strategy alignment to disrupt adversary operations.
-Takeaway (TryHackMe): Understanding the sequential stages of an adversary's intrusion path allows blue teams to map defensive controls at each layer, enabling early detection and active disruption before attackers achieve their primary objectives.

-Daily Outcome: Completed Introduction section of Cyber Kill Chain room. Note ongoing/paused tracks: Manual Wazuh SOC Lab rebuild ongoing; SentinelX, GATE CSE, and LeetCode tracks on hold.
