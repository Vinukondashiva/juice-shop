# Open-Source Supply Chain Security Audit: Juice-Shop Project

## 1. Executive Summary

This report details the findings of a security audit performed on the OWASP Juice Shop project. The scan was conducted on October 11, 2025, using the Snyk CLI tool to identify vulnerabilities within its open-source dependencies.

The scan identified a total of **61 security issues**. Among these, we found several high and critical vulnerabilities that could pose a significant risk to the application's stability and security. This report will focus on the most critical findings and provide actionable remediation strategies.

## 2. Critical Vulnerability Analysis: Uncaught Exception in 'multer' package

- **Vulnerability ID:** SNYK-JS-MULTER-10299078
- **Severity:** **Critical** (CVSS Score: [Snyk link open chesi chudu, score kanipiste ikkada rayi, lekapothe ee line teesey])
- **Vulnerable Component:** `multer` version `1.4.5-lts.2`
- **Description:** The vulnerability exists in the `multer` package, which is used for handling file uploads. An attacker can upload a specially crafted file with multiple parts. When the `multer` package tries to process this malicious file, it fails to handle an error correctly, leading to an "Uncaught Exception" that crash

### Business Impact Analysis
Exploiting this vulnerability could have a severe impact on the business, including:
- **Denial of Service (DoS):** The primary risk is that an attacker can repeatedly send a specially crafted file to the server. This causes the application to crash, making it completely unavailable for all legitimate users.
- **Reputational Damage:** Frequent downtime will cause customers to lose trust in the application and the company.
- **Financial Loss:** For any e-commerce or transactional site, downtime directly translates to a loss of revenue and business opportunities.

### Recommended Remediation Plan
- **Immediate Action:** The `multer` package must be upgraded from the vulnerable version `1.4.5-lts.2` to a patched version like `2.0.2` or higher, as recommended by the Snyk scan.
- **Action Command:** The development team should run `npm install multer@latest` to apply the fix.
