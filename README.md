# security-audit-agent

A Kiro CLI agent that scans your codebase for security vulnerabilities and produces a prioritized audit report.

---

## Purpose

Catch security issues before they reach production. The agent scans your code for common vulnerabilities and produces a `SECURITY_AUDIT.md` with findings, severity levels, and concrete fixes.

---

## How It Works

```
analyze_project → scan_vulnerabilities → generate_audit_report
```

| Skill | What it does |
|---|---|
| `analyze_project` | Detects language and framework |
| `scan_vulnerabilities` | Finds security issues across the codebase |
| `generate_audit_report` | Writes a prioritized report with remediation steps |

---

## What Gets Scanned

| Severity | Checks |
|---|---|
| Critical | Hardcoded secrets, SQL injection, command injection |
| High | XSS, path traversal, insecure deserialization, missing auth |
| Medium | Open redirects, sensitive data in logs, weak cryptography |
| Low | Verbose error messages, missing security headers |

---

## Output

`SECURITY_AUDIT.md` in your project root — never modifies source files.

Report includes:
- Summary of findings by severity
- File path and line number for each issue
- Vulnerable code snippet
- Recommended fix with corrected code example

---

## Installation

**1. Clone the repo**
```bash
git clone https://github.com/ramesherrorhunter/kiro-security-audit-agent.git
```

**2. Copy the agent into your project**
```bash
cp -r kiro-security-audit-agent/.kiro /path/to/your/project/
```

---

## Usage

1. Navigate to your project: `cd /path/to/your/project`
2. Start Kiro CLI: `kiro-cli`
3. Type `/agent` and select `security-audit-agent`

## License

MIT
