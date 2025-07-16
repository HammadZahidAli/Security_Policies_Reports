# ✅ Monthly Website Security Checklist for xyz.com

A practical checklist for maintaining the security and integrity of your website on a monthly basis.

---

## 🔐 1. Server & Infrastructure

- [ ] Update server OS and packages
- [ ] Update web server software (e.g., Apache, Nginx)
- [ ] Disable unused services (FTP, Telnet, etc.)
- [ ] Ensure firewall rules are active (e.g., UFW, iptables)
- [ ] Run port scan: `sudo nmap -sS xyz.com`

---

## 🌐 2. Web Application Security

- [ ] Update CMS or backend framework (e.g., WordPress, Laravel)
- [ ] Remove unused plugins/themes
- [ ] Run vulnerability scans (Nikto / OWASP ZAP)
- [ ] Test SSL configuration with [SSL Labs](https://www.ssllabs.com/ssltest/)
- [ ] Verify secure cookie flags (`Secure`, `HttpOnly`, `SameSite`)
- [ ] Test input validation (SQL Injection, XSS)

---

## 👤 3. User Access & Authentication

- [ ] Audit admin user accounts
- [ ] Enforce strong password policies
- [ ] Enable 2FA for all administrator accounts
- [ ] Limit login attempts / implement brute-force protection
- [ ] Review user permission roles (principle of least privilege)

---

## 📊 4. Monitoring & Logging

- [ ] Review server and application access logs
- [ ] Monitor for suspicious login/IP behavior
- [ ] Enable alerts for failed logins, file changes
- [ ] Integrate with log monitoring tools (e.g., ELK, Fail2Ban)

---

## 🔒 5. Backup & Recovery

- [ ] Verify automatic backups are running
- [ ] Test backup restore process
- [ ] Store backups offsite or in cloud storage
- [ ] Encrypt backup files

---

## 🛡️ 6. External Vulnerability Testing

- [ ] Run Nmap vuln script:  
  `sudo nmap -sV --script vuln xyz.com`
- [ ] Run Nikto scan:  
  `nikto -h https://xyz.com`
- [ ] Run full OWASP ZAP scan
- [ ] Check CVEs for your software & plugins monthly

---

## 📁 7. File & Directory Permissions

- [ ] Ensure file permissions (`644`) and folder permissions (`755`)
- [ ] Ensure no world-writable files
- [ ] Confirm `.env`, config, or `.git` files are not public
- [ ] Disable directory listing (e.g., Apache `Options -Indexes`)

---

## 📤 8. Email & Domain Security

- [ ] Check SPF, DKIM, and DMARC records
- [ ] Scan domain at [MXToolbox](https://mxtoolbox.com/)
- [ ] Confirm domain is not blacklisted or flagged

---

## 👁️ 9. Browser & Frontend Security

- [ ] Add security headers:
  - `Strict-Transport-Security`
  - `Content-Security-Policy`
  - `X-Frame-Options`
  - `X-Content-Type-Options`
- [ ] Remove unused or vulnerable JavaScript libraries

---

## 🚨 10. Emergency Response Readiness

- [ ] Review & update incident response plan
- [ ] Run a simulated breach test or tabletop exercise
- [ ] Ensure contact & support information is documented and accessible

---




