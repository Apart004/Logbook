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