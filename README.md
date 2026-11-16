# DevSecOps Automated Shift-Left Security Pipeline

An end-to-end automated DevSecOps CI pipeline built with **GitHub Actions** and open-source security tools:

1. **Secret Scanning:** [Gitleaks](https://github.com/gitleaks/gitleaks) detects hardcoded API keys, tokens, and credentials.
2. **SAST (Static Application Security Testing):** [Semgrep](https://semgrep.dev/) inspects Python source code for OWASP Top 10 vulnerabilities.
3. **Container & Dependency Scanning:** [Trivy](https://aquasecurity.github.io/trivy/) scans OS packages and Python dependencies for Critical/High CVEs.

---

## Architecture
```
Push / Pull Request
       │
       ▼
[1. Gitleaks Secret Scan]
       │
       ▼
[2. Semgrep SAST Scan]
       │
       ▼
[3. Trivy Container & CVE Scan]
       │
       ├──► Failed? Block Pull Request
       └──► Passed? Ready for Deployment
```
