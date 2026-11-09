# Awesome-Startup-Launchpad-Business-Formation

# Awesome Startup Launchpad & Business Formation

> A curated list of top Startup Launchpad and Business Formation platforms — both SaaS/Hosted commercial solutions and open-source alternatives for incorporating a company, managing founder equity, and handling early-stage legal and compliance workflows.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Stripe Atlas](#stripe-atlas)
  - [Clerky](#clerky)
  - [Firstbase](#firstbase)
  - [doola](#doola)
  - [ZenBusiness](#zenbusiness)
  - [LegalZoom](#legalzoom)
- [Open-Source Software](#-open-source-software)
  - [Kosmitor](#kosmitor)
  - [Captan](#captan)
  - [BC Registry Services (business-create-ui)](#bc-registry-services-business-create-ui)
  - [Codify Core](#codify-core)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Startup Launchpad and Business Formation platforms. These are not open-source but are included as reference points for feature comparison.

### Stripe Atlas
**Type:** Delaware C-Corp formation with banking integration  
Stripe Atlas is the most polished formation service for venture-track startups, offering a flat $500 package that includes Delaware C-Corp filing, Orrick-drafted founder paperwork, EIN acquisition (including for non-US founders), and a Mercury bank account that provisions automatically once the Delaware filing clears [citation:7][citation:12]. Ongoing registered agent service is $100/year after the first year, the lowest renewal rate among mainstream services [citation:7]. **Key limitations:** Delaware is the default and the flow is biased toward it; Atlas does not file the annual franchise tax return on your behalf, a common compliance miss for first-year Delaware C-Corps [citation:7]. **Best for:** Non-US founders and venture-track startups planning to raise from US investors on standard SAFE/preferred terms, who value clean founder paperwork and remote banking without a US presence.

### Clerky
**Type:** Venture-grade legal paperwork for Delaware C-Corps  
Clerky is the favorite of YC partners and venture lawyers because it was built by ex-WilmerHale lawyers specifically for the YC document stack [citation:12]. The Company Lifetime Package is $819 one-time and includes Delaware C-Corp formation, first-year registered agent, and Clerky's fundraising and hiring documents for the company's life [citation:1]. **Trade-off:** Less hand-holding than Atlas — no bank account integration and no partner perks — but the paperwork is what big-firm lawyers prefer to review [citation:12]. **Best for:** Founders who already have a lawyer or are deeply embedded in the YC/venture ecosystem and want the cleanest possible legal foundation, accepting less convenience in exchange.

### Firstbase
**Type:** Formation with optional back-office add-ons  
Firstbase offers a similar formation package to Atlas at $399, with bookkeeping, payroll, and tax filing available as paid add-ons [citation:12]. The legal templates are competent but less battle-tested than Orrick's (used by Atlas) or Clerky's (used by YC) [citation:12]. **Best for:** Non-venture-track founders who still want a real US C-Corp or LLC and may need ongoing back-office services bundled alongside formation.

### doola
**Type:** Budget formation for solo founders  
doola is the cheapest packaged option at $297, targeting solo founders who want a US LLC or C-Corp for tax or banking reasons rather than fundraising [citation:12]. Templates are thinner and banking integration is less seamless than Atlas or Firstbase [citation:12]. **Best for:** Solo founders running e-commerce or freelance businesses who need a US entity for banking or tax purposes but have no near-term venture plans.

### ZenBusiness
**Type:** LLC-focused formation with tiered packages  
ZenBusiness is an LLC-focused formation service with tiered packages. The annual LLC tax in Delaware is $400 as of January 2026 [citation:1]. **Best for:** US-resident founders forming a simple LLC who want a mainstream, well-known formation provider with a range of package options.

### LegalZoom
**Type:** Broad legal services with business formation  
LegalZoom is a broad legal services platform that includes business formation alongside trademark, wills, and other legal products. It is a mainstream option for founders who want a recognized brand and may need adjacent legal services, though it is less specialized for venture-track startups than Atlas or Clerky.

---

## 🟩 Open-Source Software

Self-hosted, community-driven tools for business formation and equity management. The open-source ecosystem for **full incorporation services** is essentially nonexistent — incorporation requires interacting with government registries and payment rails that are inherently centralized. However, open-source tools exist for **cap table management** and **legal document structuring**, which are critical adjacent workflows.

### Kosmitor
**Stack:** TypeScript / PostgreSQL / React | **License:** Open Source (per repository)  
Kosmitor is a full-stack open-source **cap table and equity management platform** for private companies, covering ownership tracking, equity grants and vesting (cliffs, back-loading, milestones, acceleration), SAFE and note conversion, priced-round modeling, exit waterfalls, and compliance checks (ISO $100K, Rule 701, 83(b), 409A, QSBS) [citation:15]. The core domain engine is a dependency-free TypeScript package that does the real financial math, with tests whose expected values are derived from the underlying rules rather than from the code [citation:15]. It includes e-signature and a stakeholder portal, with 24 screens in the React frontend. **Important disclaimer:** The project explicitly states it is not legal, tax, or financial advice, and results can be wrong or incomplete — every figure must be checked with a qualified attorney or accountant [citation:15].  
**Best for:** Founders and early-stage companies wanting to self-host their cap table and equity records with auditability, particularly those not yet ready to pay for Carta or Pulley.

### Captan
**Stack:** Node.js / JSON (no database) | **License:** Open Source (per npm)  
Captan is a lightweight, hackable CLI tool for managing startup cap tables using a single JSON file and Git for version control — zero database required [citation:4]. It provides real cap table math (outstanding vs. fully diluted), vesting schedules with cliffs, SAFE investments (with cap, discount, and conversion simulation), an audit log for every action, and CSV/JSON export for investors and lawyers [citation:4]. Commands include `init` (with interactive wizard), `grant`, `safe`, `convert`, and `chart` [citation:4]. **Trade-off:** It is a CLI tool, not a hosted platform — you manage the JSON file and Git workflow yourself, and there is no web UI or multi-user access control.  
**Best for:** Technical founders wanting a simple, Git-native cap table that can be reviewed and audited as plain text, without a SaaS subscription or vendor lock-in.

### BC Registry Services (business-create-ui)
**Stack:** TypeScript | **License:** Open Source (Government of British Columbia)  
The BC Registry Services' `business-create-ui` is an open-source incorporation application frontend built by the Government of British Columbia, used for creating legal entities in the BC registry [citation:6][citation:11]. It is a real-world example of a government agency open-sourcing its business formation UI, providing a reference for how incorporation workflows can be implemented as public digital infrastructure. **Limitation:** It is specific to British Columbia's registry system and not a general-purpose formation platform.  
**Best for:** Developers and policy teams interested in how government digital services for business formation are built, or organizations building on the BC registry ecosystem.

### Codify Core
**Stack:** Python / Akoma Ntoso XML | **License:** Apache-2.0  
Codify Core converts legal documents (PDFs, text, Akoma Ntoso XML) into structured data that can be inspected, searched, and reused — preserving articles, sections, tables, and references with anchors and validation findings [citation:3]. While not a formation platform, it is relevant to startup launchpad workflows for structuring the legal documents (certificates of incorporation, bylaws, operating agreements) that formation services produce. It provides a Python library, CLI, local web app, REST API, and MCP server [citation:3]. **Important:** Structural checks do not establish legal accuracy, and jurisdiction configurations are not complete legal corpora [citation:3].  
**Best for:** Teams building tooling that needs to parse and structure legal formation documents, particularly for comparison or archival workflows.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Formation Service | Cap Table | Self-Hosted | Best For |
|----------|---------|-------|-------------------|-----------|-------------|----------|
| **Stripe Atlas** | Proprietary | Cloud | ✅ (Delaware C-Corp) | ❌ | ❌ | Venture-track non-US founders |
| **Clerky** | Proprietary | Cloud | ✅ (Delaware C-Corp) | (Documents) | ❌ | YC/venture with legal counsel |
| **Firstbase** | Proprietary | Cloud | ✅ (C-Corp/LLC) | ❌ | ❌ | Non-venture with back-office needs |
| **doola** | Proprietary | Cloud | ✅ (LLC/C-Corp) | ❌ | ❌ | Budget solo founders |
| **Kosmitor** | Open Source | TypeScript/Postgres | ❌ | ✅ Full | ✅ | Self-hosted cap table |
| **Captan** | Open Source | Node.js/JSON | ❌ | ✅ CLI | ✅ (Local) | Git-native cap table |
| **BC Registry UI** | Open Source | TypeScript | ✅ (BC only) | ❌ | ✅ (Reference) | Government formation UI reference |
| **Codify Core** | Apache-2.0 | Python | ❌ (Doc structuring) | ❌ | ✅ | Legal document structuring |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Startup Launchpad or Business Formation tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem for **incorporation itself** is fundamentally limited: filing with a state registry requires interacting with government systems and payment rails that cannot be replaced by self-hosted software. The viable open-source contributions are in **adjacent workflows**: cap table management (Kosmitor, Captan), legal document structuring (Codify Core), and government digital service reference implementations (BC Registry). For actual formation, commercial services like Stripe Atlas, Clerky, and Firstbase remain the practical options, with the right choice depending on whether you are venture-track, budget-constrained, or need back-office services bundled.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
