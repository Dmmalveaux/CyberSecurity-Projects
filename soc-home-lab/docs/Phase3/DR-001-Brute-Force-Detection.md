**# DR-001: Windows Brute Force Login Detection

## Rule Information

| Field | Value |
|-------|-------|
| Detection ID | DR-001 |
| Rule Name | Windows Brute Force Detection |
| Severity | High |
| Status | Active |
| Platform | Windows |
| Log Source | Windows Security Event Logs |
| MITRE ATT&CK | T1110 - Brute Force |
| Data Source | Windows Security Logs |
| Detection Type | Authentication Monitoring |

---

## Objective

Detect multiple failed Windows authentication attempts originating from the same source within a short period of time. Excessive failed logins may indicate password spraying or brute-force attacks against user accounts.

---

## Detection Logic

Trigger an alert when:

- Five or more failed logon attempts
- Same source IP
- Within five minutes

---

## SPL Query

```spl
EventCode=4625
| bucket span=5m _time
| stats count by Source_Network_Address, Account_Name, host, _time
| where count >= 5
| sort -count
```

---

## Alert Configuration

**Trigger Condition**

- Number of Results > 0

**Schedule**

Every 5 Minutes

**Time Range**

Last 5 Minutes

---

## Expected Output

| Time | Source IP | Username | Failed Attempts |
|------|-----------|----------|----------------|
| 10:34 | 192.168.1.50 | Administrator | 12 |

---

## Investigation Steps

SOC analysts should verify:

- Source IP address
- Username targeted
- Number of failed attempts
- Successful logins after failures
- Geographic location (if applicable)
- Similar activity on other hosts

---

## Possible False Positives

- User mistyped password
- Forgotten password
- Password expiration
- Automated vulnerability scanner
- Internal penetration testing

---

## Response Actions

1. Identify source IP
2. Review successful logins following failures
3. Check account lockout events
4. Verify user activity
5. Block malicious IP if confirmed
6. Reset affected credentials if necessary

---

## MITRE ATT&CK Mapping

| Tactic | Technique |
|---------|-----------|
| Credential Access | T1110 - Brute Force |

---

## Sample Incident

An attacker attempted to authenticate against the domain controller using multiple incorrect passwords. Twelve failed login attempts were detected against the Administrator account from a single workstation over a three-minute period.

---

## Validation

Generate failed login attempts using:

```cmd
runas /user:Administrator cmd
```

Enter an incorrect password multiple times.

The detection should generate an alert once the threshold is exceeded.

---

## Lessons Learned

Repeated failed logins are often an early indicator of credential attacks. Monitoring authentication failures helps identify brute-force attempts before an attacker successfully gains access.**
