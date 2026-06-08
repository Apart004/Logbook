# June 8, 2026
Focus: Telemetry Validation & Brute-Force Simulation

-What I did: Triggered manual credential-stuffing and brute-force failures on a Windows test account. Pivoted to the Wazuh dashboard to verify live ingestion and successfully isolated real-time alerts matching logon failure Event IDs.

-Takeaway: Continuous simulation is the only way to confirm parsing rules, forwarders, and dashboards maintain true visibility.

# June 7, 2026
Focus: SIEM Validation & Active Log Testing

-What I did: Ran a Wazuh health check and generated live Windows security events by creating temporary user accounts. Confirmed the account-management logs successfully routed, indexed, and appeared on the SIEM dashboard.

-Takeaway: Never trust a SIEM works until you manually detonate events and trace them to the dashboard.