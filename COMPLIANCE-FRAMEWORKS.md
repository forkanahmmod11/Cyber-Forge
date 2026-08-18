# CyberForge Compliance Framework Coverage

CyberForge provides **technical evidence mapping**, not certification.

## Supported frameworks

| Framework | Coverage focus |
|---|---|
| NIST CSF 2.0 | Governance context, identity/access, data/platform protection, monitoring, response/recovery support |
| ISO/IEC 27001:2022 Annex A | Vulnerability management, access control, cloud, network security, cryptography, secure development |
| SOC 2 TSC | Access, system boundaries, transmission, monitoring, change management, risk mitigation |
| PCI DSS 4.0.1 | Network controls, secure configuration, cryptography, secure development, authentication, testing |
| GDPR | Technical safeguards supporting Articles 25, 32, 33 and 35 |
| HIPAA Security Rule | Access, audit controls, integrity, authentication, transmission security |
| OWASP ASVS 5.0 | Authentication, sessions, access control, validation, data protection, APIs, configuration |
| CIS Controls v8.1 | Asset/software inventory, secure configuration, accounts, access, vulnerability management, network defense, application security |

## Assessment statuses

- `OBSERVED_OK`: relevant technical checks produced no mapped high/medium-risk finding.
- `PARTIAL`: relevant checks produced medium-risk findings or limited evidence.
- `GAP`: relevant checks produced critical/high-risk findings.
- `NOT_ASSESSED`: no evidence was collected for the mapped module.

These statuses are **not equivalent to certification or legal compliance**.

## Command

```bash
./cyberforge --scope scope.txt compliance-audit https://YOUR-AUTHORIZED-DOMAIN --frameworks all
```

Selected frameworks:

```bash
./cyberforge --scope scope.txt compliance-audit https://YOUR-AUTHORIZED-DOMAIN --frameworks nist,iso27001,soc2,pci
```
