---
mode: git-ape
description: "Assess ISV readiness for Microsoft Solutions Partner with Certified Software Designations (CSD). Covers Marketplace readiness, technical audit, customer success, and Industry AI alignment."
---

# Certified Software Designation Readiness Assessment

Assess the repository at **{{repoPath}}** for Microsoft **Solutions Partner with Certified Software Designations** readiness. Target designation: **{{designation}}**.

---

## Target Designations

Evaluate against the selected designation pathway(s). If none specified, assess for **Azure** by default.

**Solution Area Designations:** Azure | Business Applications | Modern Work | Security
**Industry AI Designations:** Healthcare AI | Retail AI | Financial Services AI | Manufacturing AI | Sustainability AI | Energy AI | Telecom/Media AI | Government AI | Education AI | Defense & Intelligence AI | Non-Profit AI

---

## Assessment Pillars

### Pillar 1: Microsoft Marketplace Readiness

Evaluate:
- Offer published and transactable in Microsoft Marketplace
- IP co-sell eligibility (Azure/Security require Azure IP co-sell; BizApps requires BizApps co-sell)
- Listing quality: description, screenshots, search keywords, categories
- SaaS fulfillment API integration (resolve, activate, webhook handling)
- Landing page and webhook endpoints
- Plans and pricing configuration
- Co-sell materials (solution one-pager, reference architecture diagram)

### Pillar 2: Technical Interoperability

#### For Azure designation — assess all four categories:
1. **Data Operations & Management** — Azure data services integration, partitioning, backup/DR
2. **AI/ML Integration** — Azure OpenAI, Cognitive Services, responsible AI, content filtering
3. **Customer Deployed Services** — Multi-tenant architecture, tenant isolation, deployment automation
4. **Control Plane, Orchestration & DevOps** — CI/CD, IaC, monitoring, App Insights

#### For Business Applications — assess:
- Feature overlap with Dynamics 365 / Power Platform
- Operational excellence, data handling

#### For Modern Work — assess:
- Microsoft 365 App Compliance Program certification
- Teams app manifest, Graph API integration

#### For Security — assess:
- Sentinel Content Hub solution or MISA membership

#### For Industry AI (additional) — assess:
- AI pattern: Copilot Agents, Fabric Solutions, or AI Model/Service
- Microsoft AI capabilities usage (Azure OpenAI, Copilot SDK, Fabric, Azure ML)

### Pillar 3: Customer Success

Evaluate partner performance metrics (trailing 12 months — need ONE):

| Metric | Azure/Security | BizApps | Modern Work | Industry AI |
|---|---|---|---|---|
| Marketplace Billed Sales | $4M | $1M | $100K | $1M |
| Net-new customer adds (>$10K each) | 12 | — | — | 12 |
| Marketplace transactions (8 unique customers) | 30 | — | — | 30 |
| Azure Consumption (MACC) | $30M | — | — | $30M |
| BizApps PIR | — | $4M | — | — |
| Teams Apps MAU | — | — | 50,000 | — |

Plus solution satisfaction (need ONE):
- Marketplace rating >= 4.5 with >= 15 ratings
- >= 2 referenceable customer evidence artifacts (case studies)

### Pillar 4: Industry AI Alignment (if applicable)

- Alignment to >= 1 Microsoft Industry Cloud customer scenario
- Case studies show industry-specific AI usage
- AI capabilities built on Microsoft AI stack

---

## Report Output

Generate a **print-ready HTML report** (Clawpilot theme, `@media print` CSS) with:

1. **Executive Summary** — Overall readiness (Audit-Ready / Near-Ready / Planning Phase), top blockers, timeline
2. **Per-Pillar Scorecards** — 🟢 Ready / 🟡 Partial / 🔴 Not Ready with evidence
3. **Gap Analysis** — Missing items with severity and effort to close
4. **Action Plan** — Immediate (0-30d), Short-term (30-60d), Medium-term (60-90d)
5. **Audit Preparation Checklist** — Everything needed before scheduling Partner Center audit
6. **Appendix** — File references, Microsoft documentation links

Save to: `{{repoPath}}/.azure/assessments/csd-readiness-{{date}}.html`

---

## Skills to Invoke

| Skill | Purpose |
|---|---|
| `marketplace-onboarding` | Marketplace listing and Partner Center readiness |
| `fulfillment-and-metering` | SaaS fulfillment API and metering implementation |
| `onboard-to-marketplace` | Go-live checklist and certification gates |
| `multi-tenant_SaaS` | Architecture maturity for customer-deployed services |
| `tenant-isolation-models` | Isolation model evaluation |
| `security-and-compliance` | Security controls matrix |
| `azure-security-analyzer` | Per-resource IaC security assessment |
| `azure-policy-advisor` | Azure Policy compliance |
| `deployment-blueprints` | Deployment topology |
| `scale-and-sre` | Observability and operational excellence |
| `azure-principal-architect` | WAF review (feeds into technical interoperability) |
