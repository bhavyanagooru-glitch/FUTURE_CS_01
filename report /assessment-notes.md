Website Vulnerability Assessment Notes

Target Information

- Target: OWASP Juice Shop
- Environment: Local practice lab
- Assessment Date: To be recorded

Tools Used

- Nmap
- OWASP ZAP Passive Scan
- Browser Developer Tools

Assessment Observations

Results will be added after testing.

Risk Classification

Risk levels will be assigned based on verified evidence.

Remediation

Recommendations will be documented for confirmed findings.

Evidence

Screenshots and scan results will be added after testing.

Disclaimer

Testing is restricted to an authorized local lab environment.

Observation 1: HTTP Response Status

- Target: OWASP Juice Shop (local lab)
- Observation: A browser request returned HTTP status code 200 OK.
- Meaning: The server successfully processed the request.
- Security impact: No vulnerability can be concluded from this status code alone.
- Evidence: Browser Developer Tools → Network → Headers.
- Result: Informational observation only.

Observation 2: HTTP Response Security Headers

- Target: OWASP Juice Shop (local lab)
- Evidence: Browser Developer Tools → Network → document request → Response Headers.
- Headers observed: "X-Content-Type-Options: nosniff" and "X-Frame-Options: SAMEORIGIN".
- Meaning: These headers provide browser-side security protections.
- Assessment: Informational observation; no vulnerability confirmed.
- Evidence screenshot: Refer to the uploaded screenshot if it shows these headers.

Observation 3: Content Security Policy (CSP) Header

- Target: OWASP Juice Shop (local lab)
- Check performed: Inspected the main document response headers using Browser Developer Tools.
- Observation: The "Content-Security-Policy" header was not visible in the inspected response.
- Security impact: Not confirmed. Further verification is required before classifying this as a security issue.
- Evidence: Browser Developer Tools → Network → document request → Response Headers.
- Status: Preliminary observation.

Observation 4: Cookie Security Attributes

- Target: OWASP Juice Shop (local lab)
- Check performed: Inspected cookies using Firefox Developer Tools → Storage → Cookies.
- Observation: The cookie table displayed "language", "GSAD", and "SID" entries. Some cookies showed "HttpOnly = True", while "Secure = False" was displayed. SameSite values included "Strict" and "None".
- Security impact: Cookies without the Secure attribute may be exposed over unencrypted HTTP connections. The impact depends on the cookie's purpose and deployment configuration.
- Evidence: Firefox Developer Tools → Storage → Cookies.
- Status: Preliminary finding; verify each cookie's exact attributes before assigning a risk level.
