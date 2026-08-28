# csd-assessment-report

A Git-Ape plugin that assesses ISV readiness for Microsoft **Solutions Partner with Certified Software Designations** (CSD). Generates a print-ready HTML report (save as PDF).

## What is CSD?

Solutions Partner with Certified Software is a Microsoft partner designation that validates your software solution's interoperability with the Microsoft Cloud and demonstrates a proven track record of customer success. It unlocks go-to-market, sales, and marketing benefits through Partner Center.

**Two pathways:**
- **Solution Area** — Azure, Business Applications, Modern Work, Security
- **Industry AI** — Healthcare, Retail, Financial Services, Manufacturing, Sustainability, Energy, Telecom/Media, Government, Education, Defense & Intelligence, Non-Profit

## Assessment Pillars

| Pillar | What It Evaluates |
|--------|-------------------|
| **Marketplace Readiness** | Offer published, transactable, IP co-sell eligible, listing quality |
| **Technical Interoperability** | Azure audit (Data Ops, AI/ML, Customer Services, DevOps), M365 compliance, Sentinel, or MISA |
| **Customer Success** | MBS thresholds, net-new customers, transactions, ratings, case studies |
| **Industry AI Alignment** | Industry Cloud scenario mapping, AI pattern (Copilot Agents / Fabric / AI Model) |

## Install

```bash
/plugin marketplace add dawright22/csd-assessment-report
/plugin install csd-assessment-report
```

## Prerequisites

- [Git-Ape](https://github.com/Azure/git-ape) core plugin
- [git-ape-azure-saas-skills](https://github.com/dawright22/azure-saas-skills) plugin
- Azure CLI (`az`) >= 2.58.0

## Usage

```
@git-ape /csd-assessment-report current --designation azure
@git-ape /csd-assessment-report . --designation industry-ai --industry healthcare
@git-ape /csd-assessment-report https://github.com/org/saas-app --designation azure,security
```

## What It Does

1. **Discovery** — Scans repo for IaC, app code, marketplace config, existing SaaS skill docs
2. **Assessment** — Evaluates each CSD pillar using existing Git-Ape skills
3. **Scoring** — Rates each pillar: 🟢 Ready / 🟡 Partial / 🔴 Not Ready
4. **Report** — Generates print-ready HTML with Clawpilot theme
5. **PDF** — Auto-converts via Edge/Chrome headless, or Print → Save as PDF

## Report Sections

1. Executive Summary — overall readiness, top blockers, timeline
2. Marketplace Readiness — transactability, co-sell, listing quality
3. Technical Interoperability — per-category audit readiness with evidence
4. Customer Success — metrics vs. thresholds, metering implementation
5. Industry AI Alignment — scenario mapping, AI pattern evidence
6. Action Plan — 0-30 / 30-60 / 60-90 day roadmap
7. Audit Preparation Checklist — everything needed before Partner Center audit
8. Appendix — full findings, file references, documentation links

## Skills Invoked

| Skill | Purpose |
|-------|---------|
| `marketplace-onboarding` | Marketplace listing readiness |
| `fulfillment-and-metering` | SaaS fulfillment & metering |
| `onboard-to-marketplace` | Go-live checklist |
| `multi-tenant_SaaS` | Architecture maturity |
| `tenant-isolation-models` | Isolation model |
| `security-and-compliance` | Security controls |
| `azure-security-analyzer` | IaC security |
| `azure-policy-advisor` | Policy compliance |
| `deployment-blueprints` | Deployment topology |
| `scale-and-sre` | Observability & SRE |
| `azure-principal-architect` | WAF review |

## Output

```
.azure/assessments/csd-readiness-YYYY-MM-DD.html
.azure/assessments/csd-readiness-YYYY-MM-DD.pdf   (if auto-converted)
```

## Source Documentation

- [CSD Introduction](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-designations-introduction)
- [Solution Area Requirements](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-solution-area)
- [Industry AI Requirements](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-industry-ai)
- [Azure Technical Audit](https://aka.ms/Certifiedsoftware_audit_Azure)
- [Industry AI Playbook](https://assetsprod.microsoft.com/en-us/solutions-partner-with-certified-software-industry-ai-playbook.pdf)

## License

MIT
