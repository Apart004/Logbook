# June 7, 2026
Focus: Threat Intel Platform, Wazuh Lab, TryHackMe, GATE Prep

## Advanced Threat Intelligence Platform (TIP)
Upgraded the Elasticsearch sync pipeline by adding `severity` and `blocked_status` enrichment fields to the enforcement logs. This automates severity classification for blocked indicators and adds tracking to differentiate active blocks from rollbacks. Rebuilt the `enforcement_logs` index, ran a full re-sync, and verified that Kibana is cleanly pulling the new threat context. 
Takeaway: Telemetry is useless without immediate analyst context for prioritization.

---

## Wazuh SOC Homelab
Ran a health check on the Wazuh environment (services, endpoints, dashboard connectivity). To test the logging pipeline, I dropped into the Threat Hunting module and generated live Windows security events by creating a few temporary user accounts. Confirmed that the account-management logs successfully routed from the endpoint, got processed/indexed, and popped up on the SIEM dashboard.
Takeaway: Don't trust a SIEM works until you manually detonate events and trace them to the dashboard.

---

## TryHackMe — Computer Types
Finished the "Computer Types" room, looking at the structural differences between workstations, servers, embedded systems, and IoT devices. 
Takeaway: You can't defend an enterprise network if you don't understand the distinct attack surfaces of its hardware assets.

---

## GATE CSE 2027 Preparation
Locked down my official subject sequence, daily study strategy, and long-term timeline leading up to the exam. The goal here is a balanced, daily grind through core CS theory that integrates smoothly with my active coding and cybersecurity lab work rather than trying to cram it all at the last minute.
Takeaway: Consistency beats intensity. 

---

## Daily Outcome
Enriched TIP log metadata in Elasticsearch, verified end-to-end endpoint monitoring in Wazuh, cleared the THM hardware basics lab, and finalized the GATE 2027 study roadmap. Passed today's update to the main logbook branch.