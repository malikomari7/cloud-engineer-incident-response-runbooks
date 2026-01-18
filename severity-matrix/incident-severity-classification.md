# Incident Severity Classification Matrix

**Document Type:** Operational Reference  
**Environment:** Hybrid / Cloud  
**Incident Model:** Security-Led (24/7 Enterprise SOC)  
**Audience:** Cloud Engineers, Security Engineers, SOC Analysts, Incident Command

---

## 1. Purpose

This document defines a standardized severity classification model for security and availability incidents in a **24/7 enterprise SOC** environment.

Severity is determined using **both business impact and technical impact**.  
When in doubt, responders must **escalate to the higher severity**.

This matrix ensures:
- Consistent escalation decisions
- Clear communication to leadership
- Proper prioritization of response effort
- Alignment between security, cloud, and business teams

---

## 2. Severity Determination Model

Severity is evaluated across **two dimensions**:

### Business Impact
- Customer-facing impact
- Revenue or operational disruption
- Regulatory or legal exposure
- Reputational risk
- Executive visibility required

### Technical Impact
- Scope of compromise
- Privilege level affected
- Lateral movement or persistence
- Data access or exfiltration risk
- Control or detection failures

**Final severity equals the highest applicable level across either dimension.**

---

## 3. Severity Levels Overview

| Severity | Description | Typical Response |
|--------|------------|------------------|
| SEV-1 | Critical, enterprise-impacting incident | Immediate war room, continuous response |
| SEV-2 | High-impact or confirmed malicious activity | Rapid escalation, focused response |
| SEV-3 | Limited impact or isolated security issue | SOC-managed response |
| SEV-4 | Informational or false positive | Log and close |

---

## 4. SEV-1 — Critical Incident

### Definition
An active or imminent threat causing **major business impact** or **severe security exposure**.

### Business Impact Indicators
- Customer-facing outage or breach
- Financial loss or revenue interruption
- Regulatory or legal exposure
- Executive or board-level visibility required

### Technical Impact Indicators
- Confirmed compromise of production systems
- Privileged account abuse (admin, root, break-glass)
- Active lateral movement
- Data exfiltration suspected or confirmed
- Widespread blast radius or uncontrolled scope

### Response Expectations
- Immediate escalation to Security Incident Commander
- War room activation required
- Continuous monitoring and updates
- All remediation work prioritized over BAU activities
- Postmortem mandatory

---

## 5. SEV-2 — High Incident

### Definition
Confirmed malicious activity with **limited or contained business impact**.

### Business Impact Indicators
- Partial service degradation
- Internal system exposure
- Elevated customer risk without confirmed breach

### Technical Impact Indicators
- Confirmed malicious activity
- Limited scope or contained access
- No confirmed data exfiltration
- No confirmed privileged access escalation

### Response Expectations
- Rapid escalation to Security IC
- War room recommended
- Frequent status updates
- Mitigation prioritized within hours
- Postmortem required

---

## 6. SEV-3 — Medium Incident

### Definition
Suspicious or confirmed security issue with **minimal impact**.

### Business Impact Indicators
- No customer impact
- No revenue or regula

### Technical Impact Indicators
- Isolated system or user
- No privilege escalation
- No lateral movement
- No persistence identified

### Response Expectations
- SOC-managed investigation
- Documented analysis and remediation
- No executive escalation required
- Postmortem optional but encouraged for learning

---

## 7. SEV-4 — Low / Informational Incident

### Definition
Low-risk event or confirmed false positive.

### Business Impact Indicators
- None

### Technical Impact Indicators
- Benign activity
- Expected behavior
- Informational alerts only

### Response Expectations
- Document and close
- Tune detection rules if needed
- No escalation required

---

## 8. Automatic Severity Elevation Triggers

Any of the following conditions **automatically elevate severity** by at least one level:

- Production systems involved
- Privileged identities affected
- Multiple systems or users impacted
- Unknown or expanding blast radius
- Evidence of lateral movement
- Detection gaps discovered during investigation

Primary responders are expected to **err on the side of escalation**.

---

## 9. Primary Responder Responsibilities

The Primary Responder is responsible for:
- Initial severity recommendation
- Clear justification using this matrix
- Prompt escalation if severity is unclear
- Re-evaluating severity as new evidence emerges

Severity classification is **dynamic** and must be updated as the incident evolves.

---

## 10. AWS Mapping (Reference)

This severity model is platform-agnostic. Common AWS-related examples include:

- **Identity Impact:** IAM role compromise, access key misuse, MFA bypass
- **Compute Impact:** EC2 compromise, unauthorized AMI usage
- **Network Impact:** Malicious traffic detected via VPC Flow Logs
- **Data Impact:** S3 access anomalies, snapshot exposure
- **Detection:** GuardDuty, Security Hub, CloudTrail alerts

---

## 11. Key Principles

- Severity reflects **impact, not effort**
- Business and technical risk are equally important
- Escalation is safer than under-classification
- Documentation matters as much as mitigation

---

**End of Document**
