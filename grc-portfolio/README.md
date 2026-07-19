# GRC Portfolio — Security Governance for a Norwegian Managed Service Provider

A self-directed governance, risk and compliance (GRC) project built around **Mjøsdata AS**, a fictional Norwegian IT managed service provider (MSP) serving SMBs, health clinics and municipalities in Innlandet.

The project simulates the deliverables a junior GRC consultant would produce for a real client: business and system context, a formal risk assessment, a GDPR compliance analysis, the core of an ISO 27001-aligned ISMS, a security awareness programme, and a NIS2 scoping analysis.

> **Note:** Mjøsdata AS is entirely fictional. All data, systems and findings are constructed for demonstration purposes. Core deliverables are written in Norwegian (the working language of the target market); this README summarises each in English.

## Frameworks and standards used

| Area | Framework |
|---|---|
| Risk assessment methodology | ISO/IEC 27005:2022, supported by NSM Grunnprinsipper for IKT-sikkerhet 2.1 |
| Security management | ISO/IEC 27001:2022 (Annex A control mapping in the Statement of Applicability) |
| Privacy | GDPR / personopplysningsloven, guidance from Datatilsynet |
| Regulatory horizon | NIS2-direktivet / forslag til ny digitalsikkerhetslov |
| Awareness & behaviour | ENISA guidance, SANS security awareness maturity model |

## Repository structure

```
01-virksomhetskontekst/   Business context, digital value chain, information assets
02-risikovurdering/       Methodology, risk register, risk treatment plan
03-gdpr/                  GDPR article mapping, ROPA extract, DPIA screening
04-isms/                  Statement of Applicability (extract), access control
                          policy, incident response plan
05-sikkerhetskultur/      Security awareness & behaviour change programme
06-nis2/                  NIS2 / digitalsikkerhetsloven scoping analysis
```

## Deliverables at a glance

1. **Business context** (`01`) — who Mjøsdata is, its core support process (Salesforce → Jira Service Management → Azure), and why the CIA properties map directly to its commercial promises (SLA uptime, confidentiality of client health/legal data).
2. **Risk assessment** (`02`) — a documented ISO 27005 methodology with explicit likelihood/consequence scales and risk acceptance criteria, a 10-item risk register, and a prioritised, cost-aware treatment plan mapped to ISO 27001 Annex A controls.
3. **GDPR analysis** (`03`) — role analysis (controller vs. processor — the interesting part for an MSP), article-by-article obligations, a records-of-processing extract (Art. 30) and a DPIA screening for health-clinic customer data.
4. **ISMS core documents** (`04`) — a Statement of Applicability extract covering the controls invoked by the treatment plan, plus two operational policies written to be usable, not ornamental.
5. **Awareness programme** (`05`) — risk-driven target-group analysis, curriculum, delivery channels, and a gamified behaviour-change campaign with measurable KPIs.
6. **NIS2 scoping** (`06`) — analysis of whether an MSP with municipal and healthcare customers falls in scope, what "important entity" status would require, and a gap view against the measures already proposed in `02` and `04`.

## What I would do next

- Extend the SoA to full Annex A coverage and add a management review procedure
- Build a small compliance gap-analysis tool (CLI) against NSM Grunnprinsipper
- Add supplier risk: a processor-assessment template for Mjøsdata's own subcontractors

## Author

Master's student in Information Security (NTNU), B.Sc. Cyber Security (Høyskolen Kristiania). This project generalises and substantially extends coursework into a standalone portfolio piece.
