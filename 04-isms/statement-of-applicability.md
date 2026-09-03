# 04.1 — Statement of Applicability (utdrag)

| | |
|---|---|
| **Dokument** | Erklæring om anvendelighet (SoA), ISO/IEC 27001:2022 Annex A |
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Revideres årlig og ved endring i risikobildet |
| **Hjemmel** | ISO/IEC 27001:2022 pkt. 6.1.3 d) |
| **Leser videre** | [Tiltaksplan](../02-risikovurdering/tiltaksplan.md) · [Risikoregister](../02-risikovurdering/risikoregister.md) · [Sporbarhetsmatrise](../sporbarhetsmatrise.md) |

> **Om dette utdraget.** En fullstendig SoA dekker alle **93** kontroller i Annex A. Dette utdraget viser de **36** kontrollene som er direkte begrunnet i risikovurderingen og risikobehandlingsplanen, i det formatet en revisor forventer: kontroll, anvendelighet, begrunnelse med risikoreferanse, tilhørende tiltak og implementeringsstatus.
>
> **Ekskluderinger begrunnes alltid.** En SoA uten begrunnede «Nei» er et rødt flagg for revisor — det tyder på at applikabiliteten aldri er vurdert, bare krysset av.

**Statusforklaring:** 🟢 Implementert · 🟡 Delvis implementert · 🔵 Planlagt (med frist) · 🔴 Ikke påbegynt · ⚪ Ikke anvendelig

---

## A.5 — Organisatoriske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risikoreferanse | Tiltak | Status |
|:---:|---|:---:|---|:---:|---|
| **A.5.7** | Trusseletterretning | Ja | MSP-er er prioriterte mål i det nasjonale trusselbildet; abonnement på varsler fra NSM/NorCERT og leverandører er forutsetning for å oppdage kampanjer rettet mot bransjen | — | 🔴 |
| **A.5.15** | Tilgangsstyring | Ja | R1, R5 — minste privilegium på tvers av kundemiljøer | [T6](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) | 🟡 |
| **A.5.16** | Identitetshåndtering | Ja | R1, R5 — individuelle identiteter, forbud mot delte kontoer, navngitt eier for systemkontoer | [T6](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) | 🟡 |
| **A.5.17** | Autentiseringsinformasjon | Ja | R1 — passordpolicy og håndhevet MFA | [T1](../02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang) | 🔵 1 mnd |
| **A.5.18** | Tilgangsrettigheter | Ja | R5 — tildeling, endring og fjerning av rettigheter; kvartalsvis tilgangsrevisjon | [T6](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) | 🔵 4 mnd |
| **A.5.19** | Informasjonssikkerhet i leverandørforhold | Ja | R8 — leverandørregister med kritikalitetsklassifisering mangler i dag | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🔴 |
| **A.5.20** | Håndtering av informasjonssikkerhet i leverandøravtaler | Ja | R8 — sikkerhetskrav som standard i avtaler; databehandleravtaler etter GDPR art. 28 | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🟡 |
| **A.5.21** | Håndtering av informasjonssikkerhet i IKT-leverandørkjeden | Ja | R8 — fjernstyringsverktøy (RMM) med stående privilegert tilgang til alle kunder er Mjøsdatas største enkeltstående leverandøravhengighet | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🔴 |
| **A.5.22** | Overvåking, gjennomgang og endringshåndtering av leverandørtjenester | Ja | R8 — årlig vurdering av kritiske leverandører; oppfølging av leverandørens sikkerhetsvarsler | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🔴 |
| **A.5.23** | Informasjonssikkerhet ved bruk av skytjenester | Ja | R4, R10 — hele leveransemodellen er skybasert; regionvalg, baseline og exit-strategi | [T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure), [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🟡 |
| **A.5.24** | Planlegging og forberedelse av hendelseshåndtering | Ja | R9 — roller, eskaleringsvei og beredskap definert på forhånd | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🔵 2 mnd |
| **A.5.25** | Vurdering av og beslutning om informasjonssikkerhetshendelser | Ja | R9 — alvorlighetsklassifisering S1–S4 avgjør respons og varslingsplikt | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🔵 2 mnd |
| **A.5.26** | Respons på informasjonssikkerhetshendelser | Ja | R2, R6, R9 — inndemming, utrydding, gjenoppretting etter definert prosedyre | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🔵 2 mnd |
| **A.5.27** | Læring fra informasjonssikkerhetshendelser | Ja | R9 — post-hendelsesrapport innen 10 virkedager; funn føres tilbake i risikoregisteret | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🔵 2 mnd |
| **A.5.28** | Innsamling av bevis | Ja | Bevissikring ved hendelser i kundemiljøer er kontraktskrav og forutsetning for anmeldelse og forsikringsdekning | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🔴 |
| **A.5.29** | Informasjonssikkerhet ved avbrudd | Ja | R4 — sikkerhetsnivået skal opprettholdes også under gjenoppretting | [T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse) | 🟡 |
| **A.5.30** | IKT-beredskap for driftskontinuitet | Ja | R4, R6 — RTO/RPO per kundekategori mangler; identifisert som gap også mot NIS2 | [T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse) | 🔴 |
| **A.5.31** | Juridiske, regulatoriske og kontraktsmessige krav | Ja | GDPR, personopplysningsloven, SLA-forpliktelser og kommende NIS2-krav — se [kap. 03](../03-gdpr/gdpr-analyse.md) og [kap. 06](../06-nis2/nis2-vurdering.md) | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | 🟡 |
| **A.5.34** | Personvern og beskyttelse av personopplysninger | Ja | Hele [kap. 03](../03-gdpr/gdpr-analyse.md) — dobbeltrollen som behandlingsansvarlig og databehandler | — | 🟡 |

## A.6 — Personellkontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risikoreferanse | Tiltak | Status |
|:---:|---|:---:|---|:---:|---|
| **A.6.3** | Bevisstgjøring, utdanning og opplæring i informasjonssikkerhet | Ja | R2 — support er den mest eksponerte gruppen; se [kap. 05](../05-sikkerhetskultur/opplaeringsprogram.md) | [T2](../02-risikovurdering/tiltaksplan.md#t2--kontinuerlig-sikkerhetsopplæring-med-phishing-simulering) | 🔵 2 mnd |
| **A.6.7** | Fjernarbeid | Ja | Hybrid arbeidsmodell; sikkerhetskrav ved arbeid utenfor kontoret | [T9](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | 🟡 |

## A.7 — Fysiske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risikoreferanse | Tiltak | Status |
|:---:|---|:---:|---|:---:|---|
| **A.7.9** | Sikkerhet for utstyr utenfor lokaler | Ja | R7 — bærbare enheter brukes hjemme, hos kunder og på reise | [T9](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | 🔵 2 mnd |
| **A.7.13** | Vedlikehold av utstyr | **Nei** ⚪ | Mjøsdata har ingen egen serverinfrastruktur eller datasenterutstyr; all produksjon kjører i Azure, der leverandøren er ansvarlig for maskinvarevedlikehold. Kontorutstyr er dekket av A.8.1 | — | ⚪ |

## A.8 — Teknologiske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risikoreferanse | Tiltak | Status |
|:---:|---|:---:|---|:---:|---|
| **A.8.1** | Brukerendepunktutstyr | Ja | R7 — håndhevet diskkryptering og samsvarskrav før enheten får tilgang til ressurser | [T9](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | 🔵 2 mnd |
| **A.8.2** | Privilegerte tilgangsrettigheter | Ja | R6, R8 — just-in-time-tilgang (PIM) og herdede administrasjonsarbeidsstasjoner (PAW) | [T4](../02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) | 🔵 6 mnd |
| **A.8.5** | Sikker autentisering | Ja | R1, R2 — phishing-resistent MFA (FIDO2/passkeys) for administratorer og support | [T1](../02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang) | 🔵 1 mnd |
| **A.8.8** | Håndtering av tekniske sårbarheter | Ja | R6, R10 — patchregime og halvårlig penetrasjonstest | [T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) | 🟡 |
| **A.8.9** | Konfigurasjonsstyring | Ja | R10 — CIS Benchmark som baseline for alle nye kundemiljøer | [T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) | 🔵 3 mnd |
| **A.8.13** | Sikkerhetskopiering | Ja | R4, R6 — immutable, geo-redundant backup med testet gjenoppretting | [T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse) | 🟡 |
| **A.8.14** | Redundans i informasjonsbehandlingsanlegg | Ja | R4 — failover for kritiske kundemiljøer; SLA-forpliktelser | [T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse) | 🔵 3 mnd |
| **A.8.16** | Overvåkingsaktiviteter | Ja | R6, R10 — Defender for Cloud, sentralisert logging, logging av integrasjonstrafikk | [T5](../02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner), [T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) | 🟡 |
| **A.8.19** | Installasjon av programvare på driftssystemer | Ja | R8 — kontroll på hvilke fjernstyringsverktøy som kjører med privilegert tilgang | [T4](../02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) | 🟡 |
| **A.8.21** | Sikkerhet i nettverkstjenester | Ja | R3 — mTLS og OAuth 2.0 på API-integrasjonen Salesforce ↔ Jira | [T5](../02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner) | 🔵 3 mnd |
| **A.8.22** | Segregering av nettverk | Ja | R6, R8 — skille mellom kundemiljøer og mellom kunde- og administrasjonsnett | [T4](../02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) | 🔴 |
| **A.8.24** | Bruk av kryptografi | Ja | R3, R7, R10 — TLS i transitt, diskkryptering på endepunkt, lagringskryptering i Azure. Kryptopolicy med algoritme- og nøkkelkrav mangler | [T5](../02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner), [T9](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | 🟡 |
| **A.8.30** | Utkontraktert utvikling | **Nei** ⚪ | Mjøsdata utvikler ikke egne systemer og setter ingen systemutvikling ut til tredjepart. API-integrasjonen er konfigurasjon av standardprodukter, ikke utvikling. Kontrollen revurderes dersom egenutvikling igangsettes | — | ⚪ |

---

## Statusoversikt

| Status | Antall | Andel av utdraget |
|---|:---:|---|
| 🟢 Implementert | 0 | 0 % |
| 🟡 Delvis implementert | 13 | 36 % |
| 🔵 Planlagt med frist | 14 | 39 % |
| 🔴 Ikke påbegynt | 7 | 19 % |
| ⚪ Ikke anvendelig | 2 | 6 % |
| **Sum** | **36** | **100 %** |

At ingen kontroll står som fullt implementert er en ærlig gjengivelse av utgangspunktet, ikke en svakhet ved dokumentet. En SoA som viser grønt over hele linjen ved første revisjon er som regel enten uriktig eller uttrykk for at ambisjonsnivået er satt etter dagens praksis framfor etter risikoen.

---

## Neste iterasjon

1. Utvide SoA til fullstendig dekning av alle 93 kontroller med begrunnelse for hver ekskludering.
2. Legge til kolonner for kontrolleier og siste verifiseringsdato — nødvendig for intern revisjon etter ISO 27001 pkt. 9.2.
3. Etablere prosedyre for ledelsens gjennomgang (pkt. 9.3) med SoA som fast agendapunkt.
