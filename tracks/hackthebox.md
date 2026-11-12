











## HTB Academy — Lab Exercises & Target Environments
**Date:** November 12, 2026 | **Platform:** Hack The Box Academy | **Category:** Platform / Lab Workflow

### Summary
Reviewed how HTB Academy interactive exercises spin up isolated Docker and VM targets (`http://<ip>:<port>`), single-target concurrency limits, and session timers.

**Tools / Artifacts:** HTB Academy Web Interface, Docker Targets, VM Targets

---

### Notes & Workflow Mechanics
- **Target Spawning:** Clicking *Spawn the target system* provisions either a lightweight Docker container (accessible directly over standard internet connectivity without VPN setup, usually ready within seconds) or a full VM target.
- **Session Limits:** Only **one target per user** can run at a time, governed by a countdown timer with manual extend/re-spawn controls.
- **Access Format:** Targets expose `http://<ip>:<port>` endpoints (with one-click copy on the IP/port badge) alongside pre-configured test credentials when authentication is part of the exercise.

# Hack The Box — Lab Writeups

## Brutus (Sherlock — DFIR)
**Difficulty:** Very Easy | **OS:** Linux | **Category:** Log Analysis / DFIR

### Summary

**Artifacts:** `auth.log`, `wtmp`  
**Tools:** `grep`, `awk`, `utmp.py`

---

### Task 1: Brute-force source IP
> Analyze the auth.log. What is the IP address used by the attacker to carry out a brute force attack?

Extracted the lab zip using the password listed next to the download button on HTB. Opening `auth.log`, there are only two IPs showing up: the target server itself and `65.2.161.68` hammering SSH with failed login attempts.

Instead of scrolling manually, I counted failed attempts per IP:

```bash
grep "Failed password" auth.log | awk '{print $(NF-3)}' | sort | uniq -c | sort -nr
```

```text
# Paste your count output or 2-3 Failed password lines here
```

**Answer:** `65.2.161.68`

---

### Task 2: Compromised account
> The bruteforce attempts were successful and attacker gained access to an account on the server. What is the username of the account?

Filtered `auth.log` for successful logins (`Accepted`) to see which user the brute-force script actually cracked:

```bash
grep "Accepted" auth.log
```

```text
Mar  6 06:31:40 ip-172-31-35-28 sshd[2411]: Accepted password for root from 65.2.161.68 port 34782 ssh2
Mar  6 06:32:44 ip-172-31-35-28 sshd[2491]: Accepted password for root from 65.2.161.68 port 53184 ssh2
```

Both successful logins from `65.2.161.68` were against `root`.

**Answer:** `root`

---

### Task 3: Manual login timestamp (UTC)
> Identify the UTC timestamp when the attacker logged in manually to the server and established a terminal session to carry out their objectives.

In `auth.log`, the first login at `06:31:40` was just the brute-force script verifying the password—it disconnected immediately without spawning a shell. A minute later (`06:32:44`), the attacker logged in manually.

Since `wtmp` is binary, I used the `utmp.py` script included in the zip and forced the timezone to UTC (`TZ=UTC`) so it wouldn't default to my local system time:

```bash
TZ=UTC python3 utmp.py wtmp | tail -n 5
```

```text
"USER"	"2549"	"pts/1"	"ts/1"	"root"	"65.2.161.68"	"0"	"0"	"0"	"2024/03/06 06:32:45"	"387923"	"65.2.161.68"
```

The interactive terminal (`pts/1`) came up at `06:32:45 UTC`, one second after SSH authentication succeeded.

**Answer:** `2024-03-06 06:32:45`