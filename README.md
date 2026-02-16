# Skill Security Scanner 🔍

A security scanning tool for OpenClaw skills. Scan skills for security issues, suspicious permissions, and get a trust score before installing.

![OpenClaw](https://img.shields.io/badge/OpenClaw-Security-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Version](https://img.shields.io/badge/Version-1.0.0-orange)

## ⚡ Quick Start

```bash
# Clone this skill
git clone https://github.com/Steffano198/skill-security-scanner.git ~/.openclaw/skills/skill-security-scanner

# Or use clawhub (coming soon)
clawhub install skill-security-scanner

# Scan a skill
./scripts/scan-skill.sh /path/to/skill
```

## 📖 What is this?

Skill Security Scanner helps you make informed decisions about which OpenClaw skills to trust. After the ClawHavoc incident (February 2026, where 341 malicious skills were discovered), security is more important than ever.

This scanner:
- Analyzes skill permissions and dependencies
- Detects suspicious patterns
- Calculates a trust score (0-100)
- Provides recommendations

## 🎯 Features

| Feature | Description |
|---------|-------------|
| Trust Score | 0-100 score based on multiple factors |
| Risk Level | 🟢 Low / 🟡 Medium / 🟠 High / 🔴 Critical |
| Permission Analysis | What bins/envs the skill needs |
| Pattern Detection | Finds suspicious code patterns |
| Recommendations | Clear advice on whether to use |

## 📊 Trust Score

| Score | Risk | Action |
|-------|------|--------|
| 80-100 | 🟢 Low | Safe to use |
| 60-79 | 🟡 Medium | Review before use |
| 40-59 | 🟠 High | Use with caution |
| 0-39 | 🔴 Critical | Don't use |

### Score Factors

| Factor | Weight |
|--------|--------|
| Permission scope | 30% |
| Code patterns | 25% |
| Documentation | 20% |
| Author reputation | 15% |
| Update frequency | 10% |

## 🚨 Detection Patterns

### High Risk
- Network exfiltration attempts
- Credential harvesting
- Destructive file operations
- Obfuscated commands

### Medium Risk
- Excessive permissions
- Unknown third-party dependencies
- Outdated (6+ months no updates)

### Green Flags
- Official OpenClaw skill
- Minimal permissions
- Clear documentation
- Known author

## 📁 Files

```
skill-security-scanner/
├── SKILL.md              # OpenClaw skill definition
├── README.md             # This file
├── LICENSE               # MIT License
├── scripts/
│   └── scan-skill.sh    # Main scanner script
└── examples/
    ├── scan-output.md   # Example output
    └── report.md        # Example report
```

## 💻 Usage

### Basic Scan

```bash
./scripts/scan-skill.sh ~/.openclaw/skills/github
```

### Full Report

See `examples/report.md` for detailed report format.

## 🔧 Configuration

No configuration needed! Just run the scanner.

## 📝 Example Output

```
🔍 Scanning: github
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Trust Score: 95/100 (🟢 Low)

📋 Permissions:
   • bins: gh

✅ Positive Signs:
   • Official OpenClaw skill
   • Has proper metadata
   • Well documented

💡 Recommendation:
   Safe to use - well documented, standard permissions
```

## 🛡️ Security

This skill itself has been security-scanned:

```
🔍 Scanning: skill-security-scanner
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 Trust Score: 70/100 (🟡 Medium)

⚠️ Issues Found:
   • [MEDIUM] Makes network calls to external domains
   • [LOW] Requests API keys/tokens - verify needed

✅ Positive Signs:
   • Has proper metadata
   • Well documented

💡 Recommendation:
   Review before use, monitor usage
```

## 🤝 Contributing

1. Fork the repo
2. Create a feature branch
3. Submit a PR

## 📄 License

MIT License - see LICENSE file.

## 👤 Author

- **Steff** (@DevSef / Steffano198)
- OpenClaw enthusiast

## 🔗 Links

- [OpenClaw Docs](https://docs.openclaw.ai)
- [ClawHub](https://clawhub.com)
- [ClawHavoc Incident](https://www.authmind.com/post/openclaw-malicious-skills-agentic-ai-supply-chain)

---

**Note:** This tool provides automated analysis but cannot guarantee 100% accuracy. Always review skills manually before installing.
