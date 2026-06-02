# 📔 Engineering Logbook
Welcome to my daily engineering journal. This repository tracks my hands-on progression through security operations, infrastructure deployment, scripting, and system administration.

---

Rollback mechanism✓ complete
Built rollback.py — a SOC analyst tool that reverses automated iptables firewall blocks when a false positive is detected. The script queries the enforcement_logs MongoDB collection, executes iptables -D to unblock the IP, marks the log entry as rolled_back: True, and resets the indicator status to "reviewed". Tested successfully against a live blocked IP (162.243.103.246) and verified the active block count dropped from 5 to 4.
Git workflow✓ complete
Resolved a git push rejection caused by diverged remote history using git pull --rebase. Successfully merged and pushed Day 12 work to the main branch on GitHub.
TryHackMe — independent learning
HTTP vs HTTPS: HTTP (HyperText Transfer Protocol) is the foundation of web communication — it defines how requests and responses are structured between a client and server. HTTPS is the encrypted version, using TLS/SSL to protect data in transit from interception.
Why HTTPS matters in security: Without HTTPS, credentials and session tokens travel as plaintext — attackable via man-in-the-middle (MITM) attacks. All financial platforms must enforce HTTPS, directly relevant to the banking context of this internship project.
HTTP request structure: Learned how GET, POST, PUT, DELETE methods work, how headers carry metadata (User-Agent, Content-Type, Authorization), and how status codes (200, 301, 404, 500) communicate server responses.
Practical labs: Completed hands-on exercises examining raw HTTP traffic, identifying insecure vs secure requests, and understanding how cookies and sessions are transmitted.
Key concepts understood today
A rollback mechanism is a critical safety feature in automated security systems — automation must always have a human override path to prevent false positives from blocking legitimate traffic.
MongoDB's $unset operator removes fields from documents — used to cleanly reverse the blocked flag on rolled-back indicators.
HTTP is stateless — every request is independent. Sessions and cookies are the mechanism that creates the illusion of continuity across requests.
