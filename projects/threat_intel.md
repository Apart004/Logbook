# June 10, 2026
Focus: User Account Monitoring & Privilege Escalation Audits

-What I did: Successfully cleared Day 11 criteria by validating user account tracking metrics and setting up custom detection alerts to map potential privilege escalation parameters. Conducted health verification checks on the endpoint forwarding loop and updated the project tracking map before initializing architectural boundaries for Day 12 automated active defensive actions.
-Takeaway: Continuous visibility into user management lifecycle and account mutations is critical for detecting baseline post-exploitation maneuvers and unauthorized elevation vectors before they achieve persistence.

# June 9, 2026
Focus: Technical Documentation Architecture & Project Baseline Sync

-What I did: Rewrote the entire project README.md from scratch to shift documentation from an early-stage threat feed scraper to a complete production-ready Threat Intelligence Platform. Documented the entire 20-day project lifecycle, mapping out the full folder structure, environmental dependencies, 5-step pipeline execution sequence, MongoDB/Elasticsearch/Docker stack matrices, Kibana dashboard panel specs, dynamic risk-scoring metrics, and the SOC automated firewall rollback mechanics.

-Takeaway: Documentation must evolve at the same velocity as the codebase; a comprehensive README transforms raw code into deployable security engineering tools.

# June 8, 2026
Focus: Repo Security & Cache Purge

-What I did: Found that Git was still tracking data/ and logs/ even after adding them to .gitignore. Ran git ls-files to inspect the index, then used git rm --cached to evict them from remote tracking without deleting my local files. Cleaned up .gitignore for .pyc clutter and verified .env.example has no leaked keys.

-Takeaway: .gitignore doesn't apply to files that are already tracked. You have to manually untrack them via git rm --cached.

# June 7, 2026
Focus: Data Pipeline Enrichment & Schema Rebuild

-What I did: Upgraded the Elasticsearch pipeline schema by injecting dynamic severity tiers (Critical/High/Medium) and a blocked_status tracker. Dropped the old enforcement_logs index, rebuilt it with the new fields, ran a complete data re-sync, and validated the new visualization inside Kibana.

-Takeaway: Telemetry is useless without immediate context. Dynamic severity tagging lets analysts prioritize high-risk alerts instantly.

# May 31, 2026
Focus: Automated Mitigation Safeguards (rollback.py)

-What I did: Developed rollback.py to mitigate false positives from automated bans. The script queries MongoDB, passes an executive system call to trigger iptables -D to drop the firewall ban at the kernel level, and updates the index flag to rolled_back: True. Detonated a live test against target 162.243.103.246 and verified an instant unban.

-Takeaway: Automated defense requires a kill-switch. Never build blocking automation without a reliable human-override pathway.