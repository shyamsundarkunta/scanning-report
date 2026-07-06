# Network Reconnaissance Report

## Scope

This assessment was conducted against the authorized TryHackMe Nmap lab environment for educational purposes. The objective was to identify active hosts, discover open ports, enumerate services, fingerprint the operating system, compare scanning techniques, and evaluate basic evasion methods.

---

## Methodology

The following sequence of scans was performed:

1. Host Discovery
2. Full TCP Port Scan
3. Service & Version Detection
4. Manual Banner Grabbing
5. OS Detection
6. SYN Scan
7. TCP Connect Scan
8. Fragmentation Scan
9. Slow Timing Scan

---

## Findings

| Host | Port | Service | Version | Notes |
|------|------|---------|---------|------|
| <TARGET-IP> | 22 | SSH | OpenSSH x.x | Remote administration |
| <TARGET-IP> | 80 | HTTP | Apache x.x | Web server |
| <TARGET-IP> | 139 | NetBIOS | Samba | File Sharing |
| <TARGET-IP> | 445 | SMB | Samba | Windows File Sharing |

(Add your actual results here.)

---

## Risk Observations

- Multiple services were publicly accessible.
- Outdated software versions may expose known vulnerabilities.
- SMB services increase the attack surface.
- Service banners reveal software information that can aid attackers.

---

## Scan Comparison

### SYN Scan

- Faster
- More stealthy
- Does not complete the TCP handshake
- Less likely to be logged

### TCP Connect Scan

- Completes the full handshake
- Easier to detect
- Useful without root privileges

For stealth-focused engagements, the SYN scan is preferred because it minimizes the likelihood of detection while providing reliable results.

---

## Firewall / IDS Evasion

### Fragmentation

Packet fragmentation splits packets into smaller fragments, which may bypass poorly configured firewalls.

### Timing Scan

Using slower timing templates reduces the rate of probe packets, making scans less noticeable.

### Decoy Scanning

Decoy scanning (-D) sends packets that appear to originate from multiple IP addresses, making it harder to identify the real scanner.

### Proxy Chaining

Proxy chaining routes traffic through multiple proxy servers to conceal the scanner's IP address and improve anonymity.

---

## Recommendations

1. Disable unnecessary network services.
2. Update outdated software to the latest secure versions.
3. Restrict access to administrative services using firewall rules.
4. Perform regular vulnerability assessments.
5. Monitor network logs for suspicious scanning activity.

---

## Conclusion

The reconnaissance successfully identified active services and demonstrated several Nmap scanning techniques, including host discovery, service enumeration, OS fingerprinting, scan comparison, and basic evasion methods. All activities were conducted within the authorized TryHackMe lab environment.
