










# August 30, 2026
Focus: Cyber Kill Chain - Actions on Objectives

-What I did: Analyzed Phase 7 (Actions on Objectives) of the Cyber Kill Chain room on TryHackMe. Evaluated post-exploitation activities including credential harvesting, privilege escalation, lateral movement, data exfiltration, and adversary tactics like destroying Windows Shadow Copies to prevent system recovery.
-Takeaway: The final phase of the Cyber Kill Chain represents impact; monitoring for volume shadow copy deletion (`vssadmin delete shadows`) is critical to early detection of ransomware or destruction attempts before data loss occurs.

# August 29, 2026
Focus: Cyber Kill Chain - Command & Control (C2)

-What I did: Analyzed Phase 6 (Command and Control / C2) of the Cyber Kill Chain room on TryHackMe. Evaluated modern beaconing mechanisms across common egress channels including HTTP/HTTPS (ports 80/443) and DNS Tunneling, comparing them to legacy detection vectors like IRC.
-Takeaway: Adversaries leverage high-volume legitimate protocols (HTTP/S, DNS) for C2 beaconing to blend with regular network noise; detecting C2 requires identifying subtle periodicity and anomalous payload patterns in outbound traffic.

# August 28, 2026
Focus: Git Detached HEAD & Aborted Rebase Recovery

-What I did: Recovered from a stuck `rebase-merge` state and detached HEAD state in `~/VS Code/Github/Logbook`. Aborted the interrupted rebase session (`git rebase --abort`), checked back into the `main` branch, and successfully rebased and pushed local commits to the remote repository.
-Takeaway: When Git enters a stuck rebase state or detached HEAD, aborting the active rebase (`git rebase --abort`) before pulling allows a safe return to the target tracking branch.
