# security-audit-agent

An intelligent Kiro CLI agent that scans your codebase for security vulnerabilities and produces a prioritized audit report — no manual configuration needed.

---

## Purpose

Catch security issues before they reach production. The agent scans your code for common vulnerabilities across all severity levels and produces a `SECURITY_AUDIT.md` with findings, file locations, and concrete fixes.

---

## Solutions Offered

| Problem | Solution |
|---|---|
| Hardcoded secrets in source code | Detected and flagged as Critical |
| SQL injection vulnerabilities | Identified with parameterized query fix examples |
| Missing authentication on routes | Flagged as High with remediation steps |
| Weak cryptography usage | Detected and replaced with secure alternatives |
| No visibility into security posture | Produces a full prioritized report |

---

## Benefits

- **Zero config** — infers everything from your project files
- **Read-only** — never modifies your source code, only produces a report
- **Prioritized findings** — Critical → High → Medium → Low
- **Multi-language support** — Node.js, Python, Go, Java, Rust, Ruby
- **Actionable output** — every finding includes file, line, snippet, and fix

---

## How It Works

The agent runs 3 skills in sequence:

```
analyze_project → scan_vulnerabilities → generate_audit_report
```

| Skill | What it does |
|---|---|
| `analyze_project` | Detects language and framework in a single pass |
| `scan_vulnerabilities` | Finds security issues across the codebase |
| `generate_audit_report` | Writes a prioritized report with remediation steps |

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

Or copy into the current directory:
```bash
cp -r kiro-security-audit-agent/.kiro .
```

That's it — the agent and all skills are now available in your project.

---

## SOP — Standard Operating Procedure

### Prerequisites
- Kiro CLI installed
- Project directory accessible

### Steps

**1. Navigate to your project**
```bash
cd /path/to/your/project
```

**2. Start Kiro CLI**
```bash
kiro-cli
```

**3. Select the agent**

Type `/agent` and from the dropdown select `security-audit-agent`

**4. Review generated report**
```
SECURITY_AUDIT.md    ← prioritized findings with fixes
```

### What Gets Scanned

| Severity | Checks |
|---|---|
| Critical | Hardcoded secrets, SQL injection, command injection |
| High | XSS, path traversal, insecure deserialization, missing auth |
| Medium | Open redirects, sensitive data in logs, weak cryptography |
| Low | Verbose error messages, missing security headers |

### Expected Output

| Section | Description |
|---|---|
| Summary | Total findings by severity |
| Findings | File, line, snippet, and fix for each issue |
| Quick Wins | High-impact, low-effort fixes to prioritize |
| Dependencies | Known-vulnerable packages detected |

### Notes
- The agent never modifies source files — only produces `SECURITY_AUDIT.md`
- Re-run after adding new routes, dependencies, or authentication logic

## License

MIT
