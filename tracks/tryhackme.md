--
# June 27, 2026
Focus: Windows Registry Architecture & System Configuration Hives

-What I did: Explored Windows system configuration mechanics on TryHackMe by analyzing the Windows Registry structure. Handled the Registry Editor (`regedit`) to understand the centralized hierarchical database that the operating system constantly references at runtime. Analyzed how data is distributed across hive structures to track individual user profile environments, application configurations, file type extension mappings, system hardware manifests, and active hardware communication ports.
-Takeaway: The Registry is the core state database of a Windows machine; understanding how to navigate keys and values is vital for identifying advanced persistence mechanisms, like malicious autorun modifications, during threat hunting.

# June 26, 2026
Focus: Live System Resource Monitoring & Administrative CLI Diagnostics

-What I did: Continued tracking Windows administrative infrastructure tools via TryHackMe. Dissected Resource Monitor (`resmon.exe`) across its four core structural telemetry sections: CPU scheduling, Memory commitment, Disk I/O operations, and Network bandwidth consumption. Audited live process trees, traced active file handle allocations, and mapped deadlocked application states. Switched to Command Prompt (`cmd.exe`) primitives to parse baseline host variables (`hostname`, `whoami`), manipulate network interface details (`ipconfig /?`), analyze socket connection matrices (`netstat`), and query local domain configurations using sub-command wrappers via `net help user` and `net help localgroup`.
-Takeaway: Combining visual hardware mapping trackers with raw command-line utility configurations allows an administrator to quickly spot hidden execution scripts, unprivileged service additions, or suspicious outbound sockets.

# June 25, 2026
Focus: Windows Administration Frameworks, UAC Isolation & System Telemetry Auditing

-What I did: Successfully concluded the "Windows Fundamentals Part 2" room on TryHackMe. Deconstructed User Account Control (UAC) security tiers, mapping out execution parameters for the four base alert slider levels (*Always Notify* down to *Never Notify*) and validating the role of Secure Desktop dimming against prompt interception. Navigated the complete `compmgmt.msc` console to audit System Tools (Task Scheduler automation rules, Event Viewer 3-pane logs, administrative hidden network shares `C$` and `ADMIN$`), Storage (Disk Management volume partitioning), and Services (Startup configurations, binary paths, and WMI/WMIC PowerShell abstraction behaviors).
-Takeaway: Dissecting administrative snap-ins like Event Viewer and local service configurations provides the essential baseline needed to construct precise threat detection rules and track privilege escalation paths within an enterprise infrastructure.

# June 24, 2026
Focus: Windows Fundamentals Part 2 – System Management Consoles & Multi-OS Interaction

-What I did: Launched "Windows Fundamentals Part 2" on TryHackMe. Deployed an interactive dual-system topology, spawning a Linux AttackBox side-by-side with a remote Windows machine. Navigated administrative system management utilities, executed basic configuration audits across early core tasks, and mapped out system configurations to successfully resolve the first 5 technical orientation questions.
-Takeaway: Interoperating with a remote Windows node from a Linux-based platform mirrors realistic defensive and offensive enterprise conditions; mastering administrative dashboard utilities is key for identifying hidden privilege vectors or misconfigured services.

# June 23, 2026
Focus: Administrative Access Control & UAC Defensive Topologies

-What I did: Officially completed the "Windows Fundamentals 1" module on TryHackMe. Advanced into systemic administrative controls by analyzing User Account Control (UAC) security mechanics. Investigated how Windows maps privilege isolation layers, forcing user processes to execute inside a constrained security context and intercepting unauthorized system-wide operations by mandating explicit cryptographic or administrative confirmation alerts before escalation.
-Takeaway: UAC acts as a primary defense-in-depth barrier against silent privilege elevation; understanding its underlying token architecture is vital for identifying misconfigurations that could allow malicious software to bypass security prompts.

# June 22, 2026
Focus: Windows System Architecture, Permissions & Defensive/Offensive Web Reconnaissance Baseline

-What I did: Fully wrapped up the active interactive components for the "Offensive Security Intro" and "Windows Fundamentals" pathways. Audited adversarial attack vectors by simulating target site directory discovery mapping, locating hidden sub-directories, and exploiting insecure application administrative portals. Shifted to system internals to analyze Windows OS blueprints across Task 4 through Task 6. Deconstructed the structural hierarchy of the Windows File System, parsed the integrity roles of system storage binaries within `C:\Windows\System32`, and mapped default user profile account categories alongside explicit Access Control List (ACL) security permissions.
-Takeaway: Knowing exactly how an attacker maps unlinked pages matches directly with knowing where critical operating system binaries and access permissions live; mastering basic Windows access controls and file structures prevents account privilege escalation and unauthorized path traversal.

 June 21, 2026
Focus: Windows Server Architecture & Operating System Fundamentals

-What I did: Pivoted from premium Linux modules to launch into the "Intro to Windows" core operational track on TryHackMe. Deployed a remote sandboxed Windows Server target environment to analyze the system's foundational layer. Evaluated fundamental operating system components, navigated the graphical file system structures, parsed baseline system details, and completed 6 technical orientation tasks tracking administrative workspace operations.
-Takeaway: Holistic security requires deep dual-OS competency; pivoting between Linux terminal structures and Windows administrative layouts ensures a well-rounded baseline for building cross-platform detection engineering rules.

# June 21, 2026

Focus: Windows Server Architecture & Operating System Fundamentals

-What I did: Pivoted from premium Linux modules to launch into the "Intro to Windows" core operational track on TryHackMe. Deployed a remote sandboxed Windows Server target environment to analyze the system's foundational layer. Evaluated fundamental operating system components, navigated the graphical file system structures, parsed baseline system details, and completed 6 technical orientation tasks tracking administrative workspace operations.
-Takeaway: Holistic security requires deep dual-OS competency; pivoting between Linux terminal structures and Windows administrative layouts ensures a well-rounded baseline for building cross-platform detection engineering rules.

# June 20, 2026
Focus: Advanced Linux Querying & Shell I/O Redirection Operators

-What I did: Advanced through "Linux Fundamentals Part 2" on TryHackMe. Shifted to data pipeline manipulation by mastering text-pattern matching via `grep` and multi-parameter file system indexing using `find`. Evaluated structural control flow and stream diversion redirection operators, utilizing `&` for background process spawning, `&&` for conditional string execution chaining, `>` for destructive standard output overwriting, and `>>` for persistent, non-destructive file appending loops.
-Takeaway: Command-line fluency requires mastering stream redirection and text-filtering tools; utilizing operators like `grep` and `>>` allows a security engineer to automate log analysis and script custom collection pipelines smoothly.

# June 19, 2026
Focus: Linux Fundamentals & System Interaction

-What I did: Commenced the "Intro to Linux" module on TryHackMe. Deployed an interactive Linux Virtual Machine instance to interface directly with the bash terminal interface. Practiced core command-line utility configurations for systemic file navigation and process enumeration, tracking absolute environments with `pwd`, investigating user context with `whoami`, listing structural contents with `ls`, changing branch paths with `cd`, and dumping raw output arrays via `cat`.
-Takeaway: A strong command over Linux system navigation is the absolute foundation for security auditing; defensive engineers must be fully comfortable interacting with raw shells to parse target file structures, analyze logs, and configure services securely.

# June 18, 2026
Focus: Offensive Security Intro & Web Application Reconnaissance

-What I did: Completed the "Offensive Security Intro" practical training module on TryHackMe. Adopted an adversarial engineering mindset to study basic web application target surfaces. Initiated sandboxed deployment labs to execute web-based reconnaissance mapping, directory busting to isolate unlinked hidden administrative pages, and simulated a basic web resource exploit sequence to gain unauthorized access to an exposed application admin portal.
-Takeaway: Effective defense requires an intimate understanding of adversarial methodology; tracking how attackers locate hidden directories and exploit weak administrative interfaces informs better routing isolation, path configurations, and defensive monitoring.

# June 17, 2026
Focus: Hybrid Cryptosystems & Defense-in-Depth Engineering

-What I did: Finalized the foundational Cryptography architectural module on TryHackMe. Deconstructed the real-world execution mechanics of hybrid cryptosystems used in TLS handshakes, analyzing how slow asymmetric primitives (RSA, ECC) are leveraged to negotiate a secure, shared ephemeral key, which is then passed to highly efficient symmetric encryption engines (AES, ChaCha20) for rapid high-volume payload transport. Map-profiled cryptography as a single operational layer within a robust defense-in-depth framework that demands auxiliary monitoring, strong credential patterns, and patch cycles.
-Takeaway: Cryptography is not a single fix-all solution; it ensures confidentiality and structural data integrity at rest and in transit, but it fails unless it is accompanied by safe key management and deep monitoring practices.

# June 16, 2026
Focus: Cryptographic Prerequisites & Symmetric Substitution Ciphers

-What I did: Initiated the foundational Cryptography training module on TryHackMe to study data protection frameworks. Evaluated essential security terms including plaintext inputs, ciphertext transformations, key distribution spaces, and mathematical hashing constraints. Completed hands-on practical decoding exercises by manually and programmatically breaking monoalphabetic symmetric substitution ciphers using the modular shifts of the Caesar Cipher technique.
-Takeaway: Cryptography forms the backbone of data security pipelines; understanding low-level mathematical character shifting and substitution primitives is essential before exploring modern asymmetric frameworks or multi-layered transportation protocols.

# June 15, 2026
Focus: InfoSec Principles & CIA Triad Culmination

-What I did: Concluded the foundational review of the CIA Triad architectural module on TryHackMe. Solidified the precise operational parameters of the core security triad: Confidentiality (restricting data telemetry exposure via encryption matrices and rigid ACLs), Integrity (guaranteeing unmitigated data fidelity utilizing cryptographic hashing routines), and Availability (ensuring non-disrupted platform uptime via load balancing and systemic fault tolerance design patterns).
-Takeaway: Internalizing the strict technical definitions of Confidentiality, Integrity, and Availability establishes the vital, overarching mindset required to model threats and audit modern enterprise networks.

# June 14, 2026
Focus: The CIA Triad & Core Information Security Pillars

-What I did: Completed the "CIA Triad" fundamental foundational training module on TryHackMe. Deep-dived into the baseline pillars of data security: Confidentiality (preventing unauthorized data exposure via mechanisms like encryption and access controls), Integrity (guaranteeing data remains unmodified and authentic using hashing and digital signatures), and Availability (ensuring consistent system and data uptime via redundancy and fault tolerance). Analyzed real-world breach scenarios to identify which specific pillars were compromised during tactical attack vectors.
-Takeaway: Every security policy, architectural constraint, and defensive control engineered across an enterprise infrastructure is explicitly designed to uphold one or more pillars of the CIA Triad; balancing these three constraints is the primary objective of information security frameworks.

# June 13, 2026
Focus: Text Encoding Architectures, Code Points & Serialization Standards

-What I did: Completed the "Data Encoding" architectural training module on TryHackMe. Audited the legacy structural boundaries of 7-bit ASCII systems and analyzed how the modern Unicode consortium abstracts character representation by mapping global, universal code points to cross-linguistic alphabets, technical symbols, and emoji sets. Dissected the byte-serialization mechanics, performance trade-offs, and storage overhead discrepancies between variable-width ($UTF-8$, $UTF-16$) and fixed-width ($UTF-32$) data streams inside network buffers.
-Takeaway: Protocol analysis and deep packet inspections require a granular understanding of serialization wrappers; defensive engineers must distinguish between raw binary markers and encoded unicode arrays to prevent buffer misinterpretations or bypass vulnerabilities.

# June 12, 2026
Focus: Data Representation & Positional Numeral Subsystems

-What I did: Cleared the "Intro to Digital Forensics / Base Systems" architectural training module on TryHackMe. Deconstructed numerical representation paradigms across computer hardware and memory registers, mapping the operational dynamics of Decimal (Base-10), Binary (Base-2), Hexadecimal (Base-16), and Octal (Base-8) counting logic. Analyzed low-level telemetry storage allocations—mapping individual bit/byte boundaries (octets) alongside 24-bit Hex RGB color space combinations ($2^{24} \approx 16.7\text{ million}$).
-Takeaway: Forensic log parsing and network packet analysis require deep agility with base systems, as malicious binaries, protocols, and data structures hide within native hex streams or raw byte signatures.

# June 11, 2026
Focus: Windows Administration & Attack Surface Baselines

-What I did: Completed the "Windows Basics" module on TryHackMe using a Windows Server 2019 lab instance. Explored essential system administration panels, distinguishing between native Settings and legacy Control Panel options, while monitoring live system processes inside Task Manager. Audited underlying security layers including Windows Update status, built-in Windows Security options, and inbound/outbound rules inside Windows Defender Firewall.
-Takeaway: Securing an enterprise endpoint requires mastery over its default OS monitoring interfaces and local firewall rules to quickly spot abnormal processes or unauthorized network traffic patterns.

### Room Completion Verification
![TryHackMe Windows Basics Completion Proof](../assets/tracks/thm_windows_basics_complete.png)

# June 10, 2026
Focus: OS Architecture, Execution Spaces & Resource Control

-What I did: Cleared the "Operating Systems Introduction" room on TryHackMe, examining structural asset abstractions, process lifecycle scheduling, and file system management. Analyzed the boundary security divide between privileged Kernel Space (direct device management and system calls) and isolated User Space instances, while mapping out speed and precision trade-offs between GUI environments and CLI workflows.
-Takeaway: Modern computer defense requires an intimate understanding of memory boundary protections; manipulating privileges and tracing user-space tools to kernel-level hooks forms the bedrock of host forensics.

# June 9, 2026
Focus: Cloud Computing Fundamentals & Deployment Architecture

-What I did: Cleared the fundamental Cloud Computing module on TryHackMe, analyzing core deployment models (Public, Private, Hybrid) and service archetypes (IaaS, PaaS, SaaS). Examined the mechanics of virtualized provisioning using AWS EC2 instances, evaluating key architectural benefits including high availability, global reach, elastic scalability, and the operational shift to a shared security and usage-based utility model.

-Takeaway: Cloud computing changes infrastructure design from rigid hardware procurement into elastic, software-defined services, making it essential to understand vendor-specific attack surfaces and the shared responsibility security model.

# June 8, 2026
Focus: Virtualization, Containerization & Infrastructure Isolation

-What I did: Cleared fundamental virtualization and containerization modules on TryHackMe, focusing on how hypervisors map physical hardware boundaries to isolated target machines. Dissected the core architectural differences between standard VMs running independent guest operating systems and lightweight containers sharing the host kernel. Analyzed the implementation of network ports as software-defined entry points routing traffic to containerized daemons, while assessing how virtualization patterns enable secure environment isolation and safe malware detonating workflows.

-Takeaway: Containers optimize resource footprints by sharing the host kernel, whereas hypervisors provide complete system-level isolation necessary for untrusted or volatile security environments.

# June 7, 2026
Focus: Hardware Classifications & Network Attack Surfaces

-What I did: Finished the "Computer Types" room on TryHackMe, analyzing the structural differences between workstations, servers, embedded systems, and IoT devices.

-Takeaway: You can't defend an enterprise network if you don't understand the distinct attack surfaces of its hardware assets.

# May 31, 2026
Focus: Web Protocol Fundamentals & Session Mechanics

-What I did: Completed the web protocols foundation lab, breaking down clear-text HTTP request/response structures against encrypted TLS/SSL communication states in HTTPS. Analyzed structural components of application-layer traffic (GET, POST, PUT, DELETE), header metadata parsing, and server status code classes. Examined raw clear-text traffic profiles to map how session cookies and authorization tokens travel exposed over insecure networks.

-Takeaway: You cannot secure application infrastructure without understanding the stateless nature of HTTP and how sessions are artificially maintained via token headers.