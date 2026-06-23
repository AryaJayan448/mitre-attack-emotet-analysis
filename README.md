# mitre-attack-emotet-analysis
MITRE ATT&amp;CK threat analysis &amp; Sigma detection rules for Emotet trojan
# Emotet Trojan - MITRE ATT&CK Threat Analysis & Detection Lab

## 🎯 Project Overview

This project analyzes the **Emotet trojan malware** and maps attacker techniques to the **MITRE ATT&CK framework**. I then develop **Sigma detection rules** for each technique — simulating a SOC analyst's defensive workflow.

**Goal:** Understand how attackers operate → Build detection rules → Reduce incident response time

---

## 📊 Attack Summary

| Metric | Details |
|--------|---------|
| **Malware** | Emotet Trojan |
| **Delivery Method** | Phishing email with malicious attachment |
| **Attack Phases** | 8 phases (Initial Access → Exfiltration) |
| **MITRE Techniques Mapped** | 8 major techniques |
| **Detection Rules Created** | 8 Sigma rules |
| **Rules Production-Ready** | 3 (5 require environment-specific tuning) |

---

## 📁 Repository Structure

```
mitre-attack-emotet-analysis/
├── README.md (this file)
├── QUICKSTART.md (quick overview for newcomers)
├── ATTACK_OUTLINE.md (attack phases overview)
├── EMOTET_ATTACK_MAPPING.md (detailed MITRE mapping - 8 techniques)
├── SIGMA_RULES_INDEX.md (index of all detection rules)
├── sigma-rules/ (folder with all detection rules)
│   ├── rule-001-phishing.yml
│   ├── rule-002-execution.yml
│   ├── rule-003-persistence.yml
│   ├── rule-004-defense-evasion.yml
│   ├── rule-005-credential-access.yml
│   ├── rule-006-lateral-movement.yml
│   ├── rule-007-c2-communication.yml
│   └── rule-008-exfiltration.yml
├── TESTING_RESULTS.md (validation results + false positive analysis)
├── LESSONS_LEARNED.md (key insights from the project)
└── RESOURCES.md (references and learning materials)
```

---

## 🚀 Quick Start

### For Learners
1. **Start here:** [QUICKSTART.md](QUICKSTART.md)
2. **Understand the attack:** [ATTACK_OUTLINE.md](ATTACK_OUTLINE.md)
3. **Learn MITRE mapping:** [EMOTET_ATTACK_MAPPING.md](EMOTET_ATTACK_MAPPING.md)
4. **Study detection rules:** [SIGMA_RULES_INDEX.md](SIGMA_RULES_INDEX.md)
5. **Review testing:** [TESTING_RESULTS.md](TESTING_RESULTS.md)

### For SOC Professionals
1. Review [EMOTET_ATTACK_MAPPING.md](EMOTET_ATTACK_MAPPING.md) for MITRE context
2. Deploy rules from `sigma-rules/` in your SIEM
3. Reference [TESTING_RESULTS.md](TESTING_RESULTS.md) for tuning guidance
4. Adjust thresholds based on your environment

### For Interviews
1. Understand [EMOTET_ATTACK_MAPPING.md](EMOTET_ATTACK_MAPPING.md) to explain MITRE thinking
2. Review `sigma-rules/` to discuss detection rule approach
3. Study [TESTING_RESULTS.md](TESTING_RESULTS.md) to discuss false positives & tuning
4. Reference [LESSONS_LEARNED.md](LESSONS_LEARNED.md) for key takeaways

---

## 🔍 What is Emotet?

Emotet is a sophisticated trojan malware that:
- Spreads via phishing emails with malicious attachments
- Establishes persistence on infected systems
- Disables security tools (antivirus)
- Steals credentials and sensitive data
- Spreads laterally across networks
- Communicates with attacker command & control servers
- Exfiltrates stolen data back to attacker

**This project maps each of these stages to MITRE ATT&CK techniques and creates detection rules for defenders.**

---

## 📋 Key Files Explained

### ATTACK_OUTLINE.md
High-level overview of the 8 attack phases. Start here to understand the attack flow.

### EMOTET_ATTACK_MAPPING.md
**Detailed mapping of all 8 attack techniques to MITRE ATT&CK framework.** This is the core of the project showing how each attacker action maps to an official MITRE technique with links to the framework.

### SIGMA_RULES_INDEX.md
Index of all 8 Sigma detection rules with status, purpose, and MITRE mapping for each rule.

### sigma-rules/ (Folder)
Contains the actual Sigma detection rules in YAML format. These are production-quality rules that can be deployed to a SIEM.

### TESTING_RESULTS.md
Validation results for each rule. Shows:
- Which rules are production-ready
- False positive assessment
- Tuning guidance for each rule
- Real-world implementation notes

### LESSONS_LEARNED.md
Key insights from building this project:
- How MITRE ATT&CK works in practice
- Why detection rule tuning is critical
- How to balance detection vs false positives
- Career value of this knowledge

### RESOURCES.md
Complete list of references, learning materials, and tools used in this project.

---

## 🎯 What Each Detection Rule Does

| Rule | Technique | Detects |
|------|-----------|---------|
| Rule 1 | T1566.001 (Phishing) | Emails with executable attachments |
| Rule 2 | T1204.002 (Malicious File Execution) | .exe launched from temp folder |
| Rule 3 | T1053.005 (Scheduled Task) | Suspicious scheduled task creation |
| Rule 4 | T1562.001 (Disable AV) | Windows Defender disabled |
| Rule 5 | T1003.001 (Credential Dumping) | LSASS memory access |
| Rule 6 | T1021.002 (SMB Lateral Movement) | SMB connection to admin shares |
| Rule 7 | T1071.001 (C2 Communication) | Suspicious outbound HTTPS |
| Rule 8 | T1041 (Exfiltration) | Large data transfer to external IP |

---

## 🛠️ Technologies Used

- **MITRE ATT&CK Framework** — Standard threat classification
- **Sigma** — SIEM-agnostic detection rule format
- **Git/GitHub** — Version control and documentation
- **Markdown** — Documentation format
- **YAML** — Detection rule syntax

---

## 📈 Project Statistics

```
Total Attack Phases Analyzed: 8
MITRE Techniques Mapped: 8
Sigma Detection Rules: 8
Documentation Files: 10+
GitHub Commits: 12+
Time Investment: 5-6 hours
Project Duration: 1 week
```

---

## 💡 Key Learnings

### 1. MITRE ATT&CK is the Standard Language
Every organization uses MITRE to classify threats. Understanding the framework is essential for SOC work.

### 2. Detection Rules Need Tuning
Writing a rule is easy; making it work in production without false positives is hard. Every environment is different.

### 3. Early Detection is More Effective
Detecting attacks at the "Initial Access" or "Execution" phase is far better than waiting for "Exfiltration."

### 4. False Positives are the Enemy
Too many false alarms = alert fatigue = analysts ignore real threats. Rule tuning is critical.

### 5. Sigma Rules are Portable
Sigma rules work across Splunk, ELK, QRadar, and other SIEMs. Learning Sigma makes you immediately valuable.

---

## 🎓 Skills Demonstrated

✅ **MITRE ATT&CK Framework** — Understanding threat classification  
✅ **Threat Intelligence Analysis** — Analyzing real attack patterns  
✅ **Sigma Detection Rule Writing** — Production-quality detection rules  
✅ **SOC Analysis Workflow** — Understanding defender operations  
✅ **Technical Documentation** — Clear, professional communication  
✅ **Git/GitHub** — Version control and collaboration  
✅ **SIEM Concepts** — How detection rules work in practice  

---

## 💼 Career Applications

This project is directly applicable to:

- **SOC Analyst Tier 1/2/3** — Demonstrates detection thinking
- **Threat Intelligence Analyst** — MITRE framework fluency
- **Detection Engineer** — Sigma rule writing expertise
- **Security Operations** — Operational SOC workflow
- **Incident Response** — Attack chain analysis

**Employers see this project and know you:**
- Understand attack methodology
- Can write production detection rules
- Think like a defender
- Communicate technical findings clearly
- Are self-driven and committed to security

---

## 🚀 How to Deploy These Rules

### In Splunk
1. Copy Sigma rules
2. Convert to Splunk Query Language (SPL)
3. Create saved searches
4. Set up alerts
5. Monitor and tune

### In ELK Stack
1. Copy Sigma rules
2. Convert to Elasticsearch Query
3. Create detection rules in Kibana
4. Set up alerts
5. Monitor and tune

### In Other SIEMs (QRadar, ArcSight, etc.)
1. Reference `sigma-rules/` folder
2. Translate YAML syntax to your platform
3. Deploy and test
4. Reference `TESTING_RESULTS.md` for tuning guidance

---

## ⚠️ Important Notes

### False Positives
Several rules (5-8) will generate false positives in most environments. This is normal. Refer to `TESTING_RESULTS.md` for tuning guidance.

### Environment-Specific Tuning
These rules are templates. Every organization needs to:
- Whitelist legitimate processes
- Adjust thresholds based on baseline
- Filter by authorized users/IPs
- Correlate multiple rule triggers

### Rule Effectiveness
- **High confidence rules:** 1, 2, 4 (low false positives)
- **Medium confidence rules:** 3, 6 (medium false positives)
- **Requires tuning:** 5, 7, 8 (high false positives without tuning)

See `TESTING_RESULTS.md` for detailed assessment.

---

## 📚 Learning Resources

### MITRE ATT&CK
- Official website: https://attack.mitre.org
- Emotet page: https://attack.mitre.org/software/S0367/
- Tactics and techniques: https://attack.mitre.org/tactics/enterprise/

### Sigma Detection Rules
- Sigma repository: https://github.com/SigmaHQ/sigma
- Rule specification: https://github.com/SigmaHQ/sigma/wiki/Specification
- Sigma online validator: https://sigmaonline.sigmahq.io/validator/

### Threat Intelligence
- CISA alerts: https://www.cisa.gov/news-events/cybersecurity-advisories
- Malwarebytes research: https://www.malwarebytes.com/
- MITRE threat reports: https://attack.mitre.org/resources/

### Hands-On Practice
- TryHackMe SOC Analyst path: https://tryhackme.com/path/outline/soc-analyst
- HackTheBox: https://www.hackthebox.com/
- CyberDefenders: https://cyberdefenders.org/

---

## 🎯 Next Steps

### To Deepen This Project
1. **Deploy in a SIEM** — Test rules against real/simulated traffic
2. **Analyze another malware** — Apply the same methodology to APT28, Trickbot, etc.
3. **Create correlation rules** — Detect when multiple rules fire together
4. **Contribute to SigmaHQ** — Submit your rules to the official Sigma repository
5. **Build a detection lab** — Set up ELK or Splunk with these rules running

### To Use for Career Growth
1. **Reference in interviews** — "I've analyzed threats using MITRE ATT&CK..."
2. **Share on LinkedIn** — Link to this GitHub project
3. **Update resume** — Add under "Security Projects"
4. **Network** — Discuss with security professionals
5. **Apply to SOC roles** — Use as proof of capability

---

## 📊 Project Status

| Component | Status | Notes |
|-----------|--------|-------|
| MITRE Mapping | ✅ Complete | All 8 techniques mapped |
| Sigma Rules | ✅ Complete | All 8 rules written and validated |
| Testing | ✅ Complete | False positive assessment done |
| Documentation | ✅ Complete | Full docs for learners and professionals |
| GitHub | ✅ Complete | Professional repo with clear structure |

**Overall Status:** ✅ **Production-Ready & Portfolio-Quality**

---

## 👤 Author

**Arya Jayan**  
MSc Cybersecurity | Dublin Business School  
Master of Computer Applications (MCA) | First Class with Distinction

---

## 📞 Contact & Connect

- **GitHub:** github.com/AryaJayan448/mitre-attack-emotet-analysis
- **LinkedIn:** linkedin.com/in/arya-jayan55
- **Email:** aryaj6212@gmail.com

---

## 📄 License

This project is open-source and available for educational and professional use. Feel free to:
- ✅ Learn from the analysis
- ✅ Use the detection rules in your SIEM
- ✅ Reference in interviews
- ✅ Adapt for your organization
- ✅ Contribute improvements

Please credit the original repository if you use these rules.

---

## 🙏 Acknowledgments

- MITRE ATT&CK Framework for standardized threat classification
- SigmaHQ for the Sigma detection rule format
- CISA for threat intelligence and incident reporting
- Malwarebytes for detailed Emotet analysis
- Open-source security community
