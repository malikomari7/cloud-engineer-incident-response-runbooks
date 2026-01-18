# Blameless Security Incident Postmortem Template

**Document Type:** Post-Incident Review  
**Environment:** Hybrid / Cloud  
**Incident Model:** Security-Led (24/7 Enterprise SOC)  
**Audience:** Engineering, Security, Leadership (Sanitized Version)

---

## 1. Purpose

This postmortem template is used to analyze security incidents objectively, identify systemic improvements, and reduce the likelihood of recurrence.

The focus is on **systems, processes, and controls**, not individuals.  
This document supports:
- Internal technical review
- Sanitized leadership communication
- Audit and compliance evidence

Postmortems are mandatory for **SEV-1 and SEV-2** incidents and recommended for SEV-3 incidents with learning value.

---

## 2. Postmortem Principles

- Blameless by default
- Fact-based and timestamped
- Written for long-term reference
- Action-oriented outcomes

Avoid speculation. Clearly state unknowns when applicable.

---

## 3. Incident Summary (Executive-Safe)

**Incident ID:**  
**Date(s):**  
**Severity:**  
**Incident Type:** (Security, Availability, Hybrid)

**Summary:**  
Brief, non-technical description of what occurred, the impact, and the resolution.

**Business Impact:**
- Customer impact
- Operational or revenue impact
- Regulatory, legal, or reputational considerations

---

## 4. Incident Timeline (Authoritative Record)

> All timestamps must be in UTC. No estimates.

| Time (UTC) | Event | Notes |
|-----------|------|-------|
| | Alert detected | |
| | Alert validated | |
| | Severity declared | |
| | Security IC engaged | |
| | War room activated | |
| | Containment executed | |
| | Threat neutralized | |
| | Recovery completed | |

---

## 5. Technical Details (Internal Only)

> This section may be redacted or summarized for leadership distribution.

**Affected Assets:**
- Hosts / Instances
- Cloud services
- Accounts / Identities
- Network segments

**Detection Source:**
- Tool or alert mechanism
- Why it triggered
- Detection gaps or delays identified

**Threat Analysis:**
- Initial access vector
- Privilege level obtained
- Lateral movement observed
- Persistence mechanisms (if any)

---

## 6. Root Cause Analysis

Root cause analysis must explain **why existing controls failed**, not just what happened.

**Primary Root Cause:**  
Concise explanation of the underlying cause.

**Contributing Factors:**
- Configuration gaps
- Monitoring or logging blind spots
- Process weaknesses
- Architectural decisions or trade-offs

Avoid generic statements such as “human error” without systemic context.

---

## 7. Containment and Remediation

**Immediate Containment Actions:**
- Actions taken
- Rationale
- Evidence preserved

**Remediation Actions:**
- Fixes applied
- Validation steps
- Monitoring enhancements

---

## 8. What Went Well

Highlight effective actions and behaviors.

Examples:
- Rapid alert detection
- Timely escalation
- Clear communication
- Effective runbook usage

This reinforces positive operational patterns.

---

## 9. What Didn’t Go Well

Identify gaps and friction points.

Examples:
- Alert fatigue or noise
- Unclear ownership
- Missing logs or telemetry
- Manual steps that increased response time

Focus on improvement, not fault.

---

## 10. Preventative and Corrective Actions

All actions must be owned and tracked.

| Action | Owner | Priority | Due Date | Status |
|------|------|---------|---------|--------|
| | | | | |

Actions should address:
- Detection improvements
- Access control changes
- Architectural updates
- Process or documentation gaps

---

## 11. Leadership Summary (Optional)

This section is included when sharing externally or with executive stakeholders.

- High-level cause
- Confirmation of resolution
- Summary of preventative measures
- Assurance of follow-up actions

Exclude sensitive technical detail.

---

## 12. Distribution and Storage

- Markdown version stored in GitHub repository
- PDF exported for:
  - Leadership review
  - Audit evidence
  - Interview discussion
- Version control required for all updates

---

## 13. Closure Criteria

A postmortem is considered complete when:
- Root cause is clearly documented
- Preventative actions are assigned
- Ownership and deadlines are established
- Lessons learned are communicated

---

## 14. Key Takeaways

- Blameless does not mean uncritical
- Learning is the primary objective
- Strong postmortems improve systems and teams
- Documentation protects engineers and organizations

---

**End of Template**

