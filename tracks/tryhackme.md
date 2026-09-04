











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
