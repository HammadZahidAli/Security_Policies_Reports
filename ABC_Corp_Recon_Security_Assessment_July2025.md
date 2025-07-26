

# Security Recon Assessment Report

**Target:** example.com  
**Conducted By:** Hammad Zahid  
**Date:** July 26, 2025  
**Scope:** Passive & Active Reconnaissance  
**Authorization ID:** Ghulam Murtaza Abro

---

## Executive Summary

This report outlines the findings from a security assessment of a target domain using both passive and active reconnaissance techniques. The goal is to identify potential weaknesses that could be exploited by malicious actors and suggest mitigations.

---

## 1. Passive Reconnaissance

### 1.1 Objective

To gather publicly available information about the target domain without directly interacting with its systems.

### 1.2 WHOIS Summary

| Item | Value |
|------|-------|
| Domain Name | example.com |
| Registrar | NameCheap, Inc. |
| Registrar WHOIS Server | whois.namecheap.com |
| Registrar Abuse Contact | abuse@namecheap.com, +1.661.310.2107 |
| Creation Date | 2025-06-03 |
| Expiration Date | 2026-06-03 |
| Updated Date | 2025-06-04 |
| Domain Status | clientTransferProhibited |
| Name Servers | renan.ns.cloudflare.com, tricia.ns.cloudflare.com |
| DNSSEC | Unsigned |

### 1.3 DNS A Records

example.com resolves to the following IPv4 addresses via Cloudflare, indicating CDN and DDoS protection:

- 192.0.2.1  
- 192.0.2.2  
- 192.0.2.3  
- 192.0.2.4  
- 192.0.2.5  
- 192.0.2.6  
- 192.0.2.7

### 1.4 Certificate Transparency Log

Certificate Transparency logs show multiple wildcard and domain-specific certificates issued by Let's Encrypt, Google Trust Services, and Amazon CA since 2019. This implies historical or previous ownership. Wildcard certificates (*.example.com) suggest the existence or planning of subdomains like api, mail, dev.

### 1.5 Subdomain Enumeration

Sublist3r was used to passively enumerate subdomains. Only one subdomain (www.example.com) was discovered. This limited result is likely due to the domain's recent registration and rate-limiting from public data sources.

### 1.6 Identified Email

admin@example.com (likely admin or support contact)

---

## 2. Active Reconnaissance

### 2.1 Nmap Scan

An Nmap scan using `-sV -sC` revealed the following open ports:

- 80/tcp: open (tcpwrapped)  
- 8080/tcp: open (tcpwrapped)  
- 8443/tcp: open (tcpwrapped)

SSL Certificate: Valid, issued for example.com and *.example.com  
997 ports were filtered, suggesting a firewall or Cloudflare protection.

### 2.2 Netcat Test

A netcat connection on port 80 returned a 301 Moved Permanently response redirecting to HTTPS.  
The server is protected by Cloudflare. Inverse DNS lookups failed, which is common for CDN IPs.

### 2.3 Recommendations

- Enable DNSSEC for DNS record integrity  
- Implement strict HTTPS enforcement and certificate monitoring  
- Hide or restrict access to non-essential subdomains and directories  
- Use WAF and rate-limiting for additional protection
