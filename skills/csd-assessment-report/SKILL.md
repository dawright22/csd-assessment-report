---
name: csd-assessment-report
description: "Assesses ISV readiness for Microsoft Solutions Partner with Certified Software Designations (CSD). Evaluates Marketplace readiness, technical interoperability, customer success metrics, and Industry AI alignment. Generates a print-ready HTML report (save as PDF). Use when assessing CSD readiness for Azure, Business Applications, Modern Work, Security, or Industry AI designations."
argument-hint: "Path to the repo to assess, target designation (azure, bizapps, modernwork, security, industry-ai), or 'current' for active workspace"
user-invocable: true
last_updated: "2026-08-28"
---

# Certified Software Designation (CSD) Assessment Skill

## Purpose

Evaluates an ISV's SaaS solution and repository against Microsoft's **Solutions Partner with Certified Software Designations** program requirements. Produces a readiness report with clear scoring, gap analysis, and actionable next steps for each qualification pillar.

## Source Documentation

- [Introduction to CSD](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-designations-introduction)
- [Solution Area Requirements](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-solution-area)
- [Industry AI Requirements](https://learn.microsoft.com/en-us/partner-center/referrals/solutions-partner-certified-software-industry-ai)
- [Azure Technical Audit](https://aka.ms/Certifiedsoftware_audit_Azure)
- [Industry AI Playbook](https://assetsprod.microsoft.com/en-us/solutions-partner-with-certified-software-industry-ai-playbook.pdf)

## When to Use

- ISV asks "am I ready for certified software?"
- Partner wants to assess CSD qualification gaps
- Pre-audit readiness check before scheduling Partner Center technical audit
- Planning roadmap to achieve a certified software designation

## Designation Pathways

### Solution Area Designations

| Designation | Technical Requirement | Marketplace Requirement |
|---|---|---|
| **Azure** | Technical audit: Data Ops, AI/ML Integration, Customer Deployed Services, Control Plane/DevOps | Azure IP co-sell eligible |
| **Business Applications** | Technical audit: feature overlap, operational excellence, data handling | Business Applications co-sell eligible |
| **Modern Work** | Microsoft 365 App Compliance Program certification | Listed in Marketplace (transactability not required) |
| **Security** | Sentinel Content Hub publishing or MISA membership | Azure IP co-sell eligible |

### Industry AI Designations

| Designation | Industries |
|---|---|
| **Industry AI** | Healthcare, Retail, Financial Services, Manufacturing, Sustainability, Energy, Telecom/Media, Government, Education, Defense & Intelligence, Non-Profit |

Industry AI requires the solution area technical audit **plus** an AI Pattern audit (Copilot Agents, Fabric Solutions, or AI Model/Service).

## Assessment Framework

### Pillar 1: Microsoft Marketplace Readiness

Evaluate the solution's Marketplace presence and transactability:

| Check | Azure | BizApps | Modern Work | Security | Industry AI |
|---|---|---|---|---|---|
| Offer published in Marketplace | Required | Required | Required | Required | Required |
| Transactable offer (SaaS, VM, Container, Managed App) | Required | Not yet required | Not yet required | Required | Required |
| IP co-sell eligible | Required | BizApps co-sell | N/A | Required | Required |
| Offer listing quality (description, screenshots, videos) | Best practice | Best practice | Best practice | Best practice | Best practice |
| Plans and pricing configured | Required | Required | Listed | Required | Required |

**What to check in the repo:**
- `marketplace.json`, `plugin.json`, or Partner Center config references
- Marketplace offer metadata in docs (offer ID, plans, pricing)
- Landing page and webhook endpoints for SaaS fulfillment
- Fulfillment API integration code
- Co-sell materials (solution one-pager, reference architecture)

### Pillar 2: Technical Interoperability

Evaluate the solution's integration with Microsoft Cloud products.

#### Azure Technical Audit Categories

| Category | What to Assess | Evidence in Repo |
|---|---|---|
| **Data Operations & Management** | Azure data services integration (Cosmos DB, SQL, Storage, Data Lake), data pipeline design, backup/DR | IaC templates, data layer code, connection strings, SDK usage |
| **AI/ML Integration** | Azure OpenAI, Cognitive Services, ML model deployment, responsible AI | AI service configuration, model endpoints, content filtering, RAG patterns |
| **Customer Deployed Services** | Multi-tenant architecture, tenant isolation, deployment automation | Tenant isolation docs, provisioning code, ARM/Bicep templates |
| **Control Plane, Orchestration & DevOps** | CI/CD pipelines, IaC, monitoring, deployment automation | GitHub Actions, azure-pipelines.yml, Bicep/Terraform, App Insights config |

#### Modern Work Technical Audit

| Check | Evidence |
|---|---|
| M365 App Compliance Program certification | Certification ID, compliance documentation |
| Teams app manifest and validation | teams-manifest.json, app package |
| Graph API integration | Graph SDK usage, permissions config |

#### Security Technical Audit

| Check | Evidence |
|---|---|
| Sentinel Content Hub solution published | Solution package, data connectors |
| MISA membership (if not Sentinel) | MISA enrollment confirmation |

#### Industry AI Technical Audit (additional)

| AI Pattern | What to Assess | Evidence |
|---|---|---|
| **Copilot Agents** | Industry-specific copilot agent built on Microsoft AI | Agent code, Foundry config, copilot SDK usage |
| **Fabric Solutions** | Application built on or embedding Fabric capabilities | Fabric workspace config, data pipeline code |
| **AI Model or Service** | Industry-specific AI model hosted on Azure | Model deployment config, Azure ML workspace, custom model code |

### Pillar 3: Customer Success

Evaluate commercial performance and customer satisfaction metrics.

#### Partner Performance Criteria (trailing 12 months — meet ONE)

| Metric | Azure / Security | Business Applications | Modern Work | Industry AI |
|---|---|---|---|---|
| **Marketplace Billed Sales (MBS)** | $4M USD | $1M USD | $100K USD | $1M USD |
| **Net-new customer adds** | 12 customers > $10K each | N/A | N/A | 12 customers > $10K each |
| **Marketplace transactions** | 30 txns, 8 unique customers (min $100 each) | N/A | N/A | 30 txns, 8 unique customers |
| **Azure Consumption (MACC)** | $30M USD | N/A | N/A | $30M USD |
| **BizApps PIR** | N/A | $4M USD | N/A | N/A |
| **Teams Apps MAU** | N/A | N/A | 50,000 MAU | N/A |

#### Solution Satisfaction Criteria (meet ONE)

| Metric | Threshold |
|---|---|
| **Marketplace rating** | >= 4.5 average with >= 15 ratings |
| **Customer evidence artifacts** | >= 2 referenceable case studies / customer artifacts |

**What to check in the repo:**
- Customer case studies in docs/
- Marketplace rating references
- Usage telemetry and metering implementation (for tracking MBS/transactions)
- Metering API integration for overage billing

### Pillar 4: Industry AI Alignment (if targeting Industry AI)

| Check | Evidence |
|---|---|
| Solution aligns to >= 1 Microsoft Industry Cloud customer scenario | Industry scenario mapping document |
| Case studies demonstrate industry-specific AI usage | Industry-tagged customer evidence |
| AI capabilities use Microsoft AI stack | Azure OpenAI, Copilot SDK, Fabric, Azure ML references in code |

## Scoring Methodology

### Per-Pillar Readiness

| Score | Status | Meaning |
|---|---|---|
| 🟢 **Ready** | All requirements met | Can schedule audit |
| 🟡 **Partial** | Some requirements met, gaps identified | 30-60 day remediation path |
| 🔴 **Not Ready** | Major requirements missing | 90+ day roadmap needed |
| ⬜ **N/A** | Pillar doesn't apply to target designation | Skip |

### Overall CSD Readiness Score

| Level | Criteria |
|---|---|
| **Audit-Ready** | All pillars 🟢 Ready — schedule the Partner Center audit |
| **Near-Ready** | No 🔴 pillars, at least one 🟡 — close gaps then schedule |
| **Planning Phase** | One or more 🔴 pillars — build roadmap, target 90-day milestone |

## Workflow

### Phase 1: Discovery

1. **Identify target designation(s)** — Ask user which CSD pathway (Azure, BizApps, Modern Work, Security, Industry AI)
2. **Scan repository** — IaC, app code, CI/CD, docs, marketplace config
3. **Check existing skill outputs** — Reuse SaaS skill docs if present (tenant-isolation-model.md, security-and-compliance.md, fulfillment-and-metering.md, marketplace-onboarding.md)

### Phase 2: Assess Each Pillar

Invoke existing skills where applicable:

| Pillar | Skills to Invoke |
|---|---|
| Marketplace Readiness | `marketplace-onboarding`, `fulfillment-and-metering`, `onboard-to-marketplace` |
| Technical (Azure) | `azure-security-analyzer`, `azure-policy-advisor`, `multi-tenant_SaaS`, `tenant-isolation-models`, `deployment-blueprints` |
| Technical (AI) | Check for Azure OpenAI / Copilot SDK / Fabric usage in codebase |
| Customer Success | `fulfillment-and-metering` (metering implementation), marketplace docs |
| Industry AI | Industry scenario mapping, AI pattern identification |

### Phase 3: Score & Gap Analysis

For each pillar, produce:
1. **Current state** — what exists in the repo with file path evidence
2. **Readiness score** — 🟢 Ready / 🟡 Partial / 🔴 Not Ready
3. **Gaps** — specific missing items with severity
4. **Actions** — what to do, with effort estimate (S/M/L) and priority

### Phase 4: Generate Report

Build a **self-contained HTML file** using the `web-artifacts-builder` Clawpilot theme with `@media print` CSS for PDF output.

#### Report Sections

1. **Cover Page** — Solution name, target designation(s), assessment date, overall readiness
2. **Executive Summary** — Overall readiness level, top blockers, recommended timeline
3. **Designation Roadmap** — Visual timeline showing path to audit-ready status
4. **Pillar 1: Marketplace Readiness** — Checklist with status per item
5. **Pillar 2: Technical Interoperability** — Per-category audit readiness with evidence
6. **Pillar 3: Customer Success** — Metrics status, gap to threshold, metering implementation
7. **Pillar 4: Industry AI Alignment** — (if applicable) Scenario mapping, AI pattern evidence
8. **Action Plan** — Prioritized next steps grouped by timeline:
   - **Immediate** (0-30 days) — Blockers and quick wins
   - **Short-term** (30-60 days) — Technical gaps
   - **Medium-term** (60-90 days) — Customer success & evidence gathering
9. **Audit Preparation Checklist** — Everything needed before scheduling the Partner Center audit
10. **Appendix** — Full findings, file references, links to Microsoft documentation

### Phase 5: Save & Convert

1. Save HTML to `.azure/assessments/csd-readiness-YYYY-MM-DD.html`
2. Auto-convert to PDF if Edge/Chrome headless available:
   ```bash
   msedge --headless --print-to-pdf=report.pdf --no-margins report.html
   ```
3. Otherwise: **Open HTML in browser → Print → Save as PDF**

## Print-Optimized CSS Requirements

```css
@media print {
  body { font-size: 11pt; color: #000; background: #fff; }
  .no-print { display: none; }
  h1, h2, h3 { page-break-after: avoid; }
  table, figure, .card { page-break-inside: avoid; }
  .page-break { page-break-before: always; }
  @page { margin: 0.75in; size: letter; }
  @page :first { margin-top: 0; }
}
```

## Example Invocation

```
@git-ape /csd-assessment-report current --designation azure
@git-ape /csd-assessment-report . --designation industry-ai --industry healthcare
@git-ape /csd-assessment-report https://github.com/org/saas-app --designation azure,security
```
