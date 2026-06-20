# June 20, 2026
Focus: Day 15 – IOC Extraction from AlienVault OTX Threat Intelligence Feeds

-What I did: Advanced the automated custom Threat Intelligence Engine to Day 15 specifications by transitioning from raw pulse ingestion to extracting actionable Indicators of Compromise (IOCs). Validated secure REST API transport contexts leveraging an authenticated AlienVault OTX credentials key. Engineered a specialized parsing pipeline in Python to traverse nested JSON responses, isolating pulse metadata (title, author, timestamps) and pulling out atomic IOC categories—including MD5, SHA1, and SHA256 file hashes alongside domain indicators. Isolated and debugged command invocation errors, variable scope naming inconsistencies, and JSON object navigation mismatches to generate a clean, structured indicator telemetry payload.
-Takeaway: Ingesting raw threat feeds provides value only if the underlying data can be structurally decomposed; extracting normalized atomic IOCs establishes the critical data layer required for upstream database indexing and real-time SIEM alert correlation.

# June 13, 2026
Focus: AlienVault OTX API Authentication & Threat Feed JSON Parsing

-What I did: Completed Day 14 of the custom Threat Intelligence integration. Stabilized the Ubuntu server's Python virtual environment package dependencies and validated secure HTTPS API communication with the AlienVault Open Threat Exchange (OTX) platform using authenticated configuration headers. Developed a specialized Python data acquisition script using the `Requests` library to query active subscribed pulse endpoints. Successfully fetched and parsed raw JSON data payloads into structured formats, extracting core threat pulse metrics including pulse names, authors, and timestamps for tracking high-profile vulnerabilities (e.g., *ClickFix Evolves with PySoxy Proxying*, *The Gentlemens Leak*).
-Takeaway: Defensive SIEM engineering requires proactive ingestion; programmatically fetching and flattening unstructured threat intelligence streams into clean JSON schemas is a prerequisite step before executing indicators extraction or database normalization workflows.

# June 12, 2026
Focus: AlienVault OTX Threat Intelligence API Framework

-What I did: Initiated an open-source threat intelligence ecosystem on the Wazuh SIEM manager by preparing an isolated workspace environment (`~/threat-intel`). Addressed modern Ubuntu package management constraints by instantiating an active Python virtual environment to host the AlienVault OTX Python SDK (`OTXv2`). Designed an abstract file structure to securely read and parse OTX API credentials without exposure in application code. Conducted live syntax validation testing on an initial Indicator of Compromise (IOC) retrieval script, isolating specific interactive python interpreter syntax errors for refactoring in the next sprint.
-Takeaway: Threat intelligence feeds are critical for contextual SIEM alerting, but programmatic integrations must prioritize compartmentalized dependencies and credential isolation to avoid credential leakage or dependency hell.


# June 11, 2026
Focus: Active Response Automated Framework & Queue Configuration

-What I did: Configured the Wazuh Active Response engine on the SIEM manager, modifying core parameters to trigger automated defensive scripts for rule alerts matching severity Level 10+. Checked syntax validity with the analysis daemon testing utility, verified active engine queues upon restarting services, and detonated a Level 13 pseudo-privilege escalation alert via `sudo` execution. Observed that while alerting triggers are functional, automated scripts like `host-deny` safely filter out executions missing explicit network tuple dependencies.
-Takeaway: Automated defense pipelines must be built defensively; ensuring your response triggers validate matching telemetry parameters prevents broken script executions or system service instability.

# June 10, 2026
Focus: User Account Monitoring & Privilege Escalation Audits

-What I did: Successfully cleared Day 11 criteria by validating user account tracking metrics and setting up custom detection alerts to map potential privilege escalation parameters. Conducted health verification checks on the endpoint forwarding loop and updated the project tracking map before initializing architectural boundaries for Day 12 automated active defensive actions.
-Takeaway: Continuous visibility into user management lifecycle and account mutations is critical for detecting baseline post-exploitation maneuvers and unauthorized elevation vectors before they achieve persistence.

# June 9, 2026
Focus: Real-Time File Integrity Monitoring (FIM) Configuration

-What I did: Troubleshooted missing endpoint event states and configured real-time File Integrity Monitoring (FIM) across the Windows infrastructure. Audited and modified the client-side `ossec.conf` file to inject a custom evaluation rule targeting `C:\Desktop` with active realtime tracking flags enabled. Restarted the underlying agent architecture via administrative PowerShell, validated telemetry syncs, and performed live detonation cycles (creation, modification, structural deletions) to verify zero-latency alert ingestion on the SIEM Threat Hunting dashboard.

-Takeaway: File Integrity Monitoring provides a core behavioral line of defense; mapping precise local directories via agent profiles ensures malicious persistence mechanisms or unexpected system changes are caught at the exact second of entry.

# June 8, 2026
Focus: Telemetry Validation & Brute-Force Simulation

-What I did: Triggered manual credential-stuffing and brute-force failures on a Windows test account. Pivoted to the Wazuh dashboard to verify live ingestion and successfully isolated real-time alerts matching logon failure Event IDs.

-Takeaway: Continuous simulation is the only way to confirm parsing rules, forwarders, and dashboards maintain true visibility.

# June 7, 2026
Focus: SIEM Validation & Active Log Testing

-What I did: Ran a Wazuh health check and generated live Windows security events by creating temporary user accounts. Confirmed the account-management logs successfully routed, indexed, and appeared on the SIEM dashboard.

-Takeaway: Never trust a SIEM works until you manually detonate events and trace them to the dashboard.