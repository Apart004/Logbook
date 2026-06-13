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