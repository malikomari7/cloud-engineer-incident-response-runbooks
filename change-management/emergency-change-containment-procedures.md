# Emergency Change & Security Containment Procedures

**Document Type:** Operational Procedure  
**Environment:** Hybrid / Cloud  
**Incident Model:** Security-Led (24/7 Enterprise SOC)  
**Change Model:** Emergency changes with retroactive approval  
**Audience:** Cloud Engineers, Security Engineers, SOC, Incident Command

---

## 1. Purpose

This document defines how **security-driven emergency changes** are executed during active incidents while maintaining:
- System stability
- Evidence integrity
- Auditability
- Post-incident accountability

Emergency changes prioritize **risk containment and blast-radius reduction** over standard change controls, with **mandatory retroactive approval** after the incident.

---

## 2. Definition: Emergency Change

An **emergency change** is any unplanned modification that must be executed immediately to:
- Stop or contain active malicious activity
- Prevent further compromise
- Protect sensitive data
- Reduce operational or security risk during an incident

Emergency changes bypass normal change windows and CAB approval **only during the incident**.

---

## 3. Authorization Model

### During the Incident
- Emergency actions are authorized verbally or in-writing by the **Security Incident Commander (IC)**
- The **Primary Responder** executes the change
- Actions are documented in real time within the incident timeline

### After the Incident
- All emergency changes are formally documented
- Changes are submitted for **retroactive approval**
- Deviations are reviewed, justified, and corrected if necessary

This model balances **speed, safety, and governance**.

---

## 4. Guiding Principles

- Contain first, investigate second
- Preserve evidence before remediation
- Prefer isolation over destruction
- Minimize irreversible actions
- Document everything

---

## 5. Approved Emergency Containment Actions

The following actions may be performed **without prior CAB approval** when authorized by the Security IC.

### 5.1 Identity and Access Control
- Disable or rotate compromised credentials
- Revoke elevated privileges
- Enforce step-up authentication or MFA
- Lock or suspend compromised user accounts

**AWS Mapping**
- IAM access key deactivation
- Policy attachment/removal
- Role session revocation
- MFA enforcement

---

### 5.2 Network Isolation
- Restrict inbound or outbound traffic
- Isolate affected systems into quarantine segments
- Block known malicious IPs, domains, or CIDR ranges

**AWS Mapping**
- Security Group rule changes
- NACL restrictions
- Route table modifications
- VPC traffic isolation patterns

---

### 5.3 Compute and Workload Containment
- Stop or quarantine compromised hosts
- Detach affected workloads from production traffic
- Capture system state prior to remediation

**AWS Mapping**
- EC2 stop (avoid terminate)
- EBS snapshot creation
- AMI creation for forensics
- Instance isolation via security groups

---

### 5.4 Logging and Evidence Preservation
- Preserve relevant logs before remediation
- Prevent log rotation or deletion
- Ensure chain-of-custody for artifacts

**AWS Mapping**
- CloudTrail retention enforcement
- VPC Flow Log preservation
- Centralized logging accounts
- S3 versioning or object lock

---

## 6. Prohibited Actions (Without Explicit Approval)

The following actions **must not be performed** unless explicitly approved by the Security IC:

- Terminating or destroying compromised systems
- Deleting logs, snapshots, or forensic artifacts
- Broad or unscoped credential resets
- Large-scale network changes impacting unrelated systems
- Irreversible configuration changes

---

## 7. Documentation Requirements (Mandatory)

Every emergency change must include:
- Timestamp (UTC)
- Executor (name/role)
- Action performed
- Reason for action
- Systems affected
- Expected impact
- Rollback plan (if applicable)

Documentation must begin **during the incident**, not after.

---

## 8. Rollback and Safety Considerations

Where possible:
- Validate rollback steps before execution
- Stage containment changes incrementally
- Monitor system health immediately after changes
- Coordinate rollback decisions with Security IC

Rollback is not mandatory if it increases risk.

---

## 9. Retroactive Change Review

Within the post-incident window:
- Emergency changes are reviewed for correctness
- Gaps in controls or process are identified
- Required follow-up changes are scheduled
- Runbooks and procedures are updated if needed

This review feeds directly into the postmortem process.

---

## 10. Audit and Compliance Considerations

Emergency changes must be:
- Traceable to an incident ID
- Linked to supporting evidence
- Approved retroactively
- Retained according to compliance requirements

Audit readiness is achieved through **clear documentation**, not slowed response.

---

## 11. Key Takeaways

- Speed and safety are not mutually exclusive
- Emergency changes are expected in real incidents
- Governance happens after containment
- Documentation protects engineers and the organization

---

**End of Document**

