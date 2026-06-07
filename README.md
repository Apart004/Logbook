# 📔 Engineering Logbook
Welcome to my daily engineering journal. This repository tracks my hands-on progression through security operations, infrastructure deployment, scripting, and system administration.

---

# 📅 June 7, 2026

## 🛡️ Advanced Threat Intelligence Platform (TIP)

Continued development of the **Finance & Banking Threat Intelligence Platform (TIP) & Dynamic Policy Enforcer**, focusing on improving threat visibility and analyst decision-making.

### 🔧 Enhancements Implemented
- Added **Severity Classification** to enforcement logs:
  - 🔴 Critical (Score ≥ 9)
  - 🟠 High (Score ≥ 8)
  - 🟡 Medium

- Added **Blocked Status Tracking**:
  - Blocked
  - Rolled Back

### ⚙️ Elasticsearch & Kibana Operations
- Rebuilt the `enforcement_logs` Elasticsearch index to apply schema updates.
- Performed a complete re-synchronization of enforcement data.
- Verified all enforcement records were successfully indexed.
- Confirmed enriched threat data was displayed correctly in Kibana dashboards.

### 🎯 Why It Matters
These enhancements provide SOC analysts with richer context, faster prioritization of threats, and improved visibility into enforcement actions and rollback decisions.

---

## 🏢 Wazuh SOC Homelab

Continued hands-on work within my self-hosted **Wazuh-Based SOC Homelab**.

### 🔍 Security Monitoring Activities
- Verified Wazuh Manager, Indexer, and Dashboard services.
- Validated endpoint connectivity and SIEM health.
- Explored the Threat Hunting module.
- Generated Windows security events by creating a temporary user account.
- Monitored account-management events collected by the Wazuh Agent.
- Investigated event ingestion and dashboard visibility.

### 🎯 Why It Matters
Successfully validated the complete monitoring pipeline from endpoint event generation to centralized SIEM analysis, simulating a real SOC investigation workflow.

---

## 🎓 TryHackMe

### ✅ Computer Types Room Completed

Studied:
- Workstations and desktops
- Enterprise servers
- Mobile and embedded devices
- Cloud computing platforms
- Specialized computing systems

### 🎯 Why It Matters
Strengthened foundational knowledge of the different computing environments that security teams monitor, defend, and investigate in enterprise networks.

---

## 🚀 Daily Outcome

Today's work improved **threat intelligence enrichment**, **SIEM visibility**, and **SOC investigation capabilities** while reinforcing core knowledge of enterprise computing systems and cybersecurity operations.