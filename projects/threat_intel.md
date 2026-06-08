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