

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