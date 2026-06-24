# Emotet Attack - MITRE ATT&CK Mapping

## Phase 1: Initial Access
**What happened:** Attacker sends phishing email with malicious attachment
**MITRE Tactic:** Initial Access (TA0001)
**MITRE Technique:** Phishing (T1566)
**Sub-Technique:** Phishing - Spearphishing Attachment (T1566.001)
**Observables:** Email with .exe, .zip, or document attachment
**Link:** https://attack.mitre.org/techniques/T1566/001/

---

## Phase 2: Execution
**What happened:** User opens attachment, malware executes
**MITRE Tactic:** Execution (TA0002)
**MITRE Technique:** User Execution (T1204)
**Sub-Technique:** User Execution - Malicious File (T1204.002)
**Observables:** Suspicious process launch from temp folder
**Link:** https://attack.mitre.org/techniques/T1204/002/

---

## Phase 3: Persistence
**What happened:** Malware creates scheduled task to run on system startup
**MITRE Tactic:** Persistence (TA0003)
**MITRE Technique:** Scheduled Task/Job (T1053)
**Sub-Technique:** Scheduled Task/Job - Scheduled Task (T1053.005)
**Observables:** New scheduled task in Windows Task Scheduler
**Link:** https://attack.mitre.org/techniques/T1053/005/

---

## Phase 4: Defense Evasion
**What happened:** Malware hides itself and disables security tools
**MITRE Tactic:** Defense Evasion (TA0005)
**MITRE Technique:** Impair Defenses (T1562)
**Sub-Technique:** Impair Defenses - Disable or Modify Tools (T1562.001)
**Observables:** Antivirus disabled, Windows Defender turned off
**Link:** https://attack.mitre.org/techniques/T1562/001/

---

## Phase 5: Credential Access
**What happened:** Malware steals credentials from the system
**MITRE Tactic:** Credential Access (TA0006)
**MITRE Technique:** OS Credential Dumping (T1003)
**Sub-Technique:** OS Credential Dumping - LSASS Memory (T1003.001)
**Observables:** lsass.exe accessed by suspicious process
**Link:** https://attack.mitre.org/techniques/T1003/001/

---

## Phase 6: Lateral Movement
**What happened:** Attacker uses stolen credentials to move to other systems
**MITRE Tactic:** Lateral Movement (TA0008)
**MITRE Technique:** Remote Services (T1021)
**Sub-Technique:** Remote Services - SMB/Windows Admin Shares (T1021.002)
**Observables:** Unusual SMB connections between internal systems
**Link:** https://attack.mitre.org/techniques/T1021/002/

---

## Phase 7: Command & Control
**What happened:** Malware contacts attacker's server for instructions
**MITRE Tactic:** Command & Control (TA0011)
**MITRE Technique:** Application Layer Protocol (T1071)
**Sub-Technique:** Application Layer Protocol - Web Protocols (T1071.001)
**Observables:** Suspicious outbound HTTP/HTTPS to unknown domain
**Link:** https://attack.mitre.org/techniques/T1071/001/

---

## Phase 8: Exfiltration
**What happened:** Attacker steals data (passwords, emails, documents)
**MITRE Tactic:** Exfiltration (TA0010)
**MITRE Technique:** Exfiltration Over C2 Channel (T1041)
**Observables:** Large outbound data transfer to C2 server
**Link:** https://attack.mitre.org/techniques/T1041/

---

## Summary
- **Total Techniques Mapped:** 8
- **Attack Phases Covered:** 8
- **Primary Tactic:** Initial Access → Persistence → Exfiltration
