# Sporbarhetsmatrise

| | |
|---|---|
| **Formål** | Vise hele kjeden fra identifisert risiko til implementert kontroll i én oversikt |
| **Versjon** | 2.0 · 01.09.2026 |
| **Kilder** | [Risikoregister](02-risikovurdering/risikoregister.md) · [Tiltaksplan](02-risikovurdering/tiltaksplan.md) · [SoA](04-isms/statement-of-applicability.md) |

> Sporbarhet er selve testen på om et styringssystem henger sammen. En revisor spør ikke «har dere en policy?», men «hvilken risiko begrunner denne kontrollen, og hvem eier tiltaket?». Denne matrisen skal kunne svare på det for hver eneste rad — i begge retninger.

---

## 1. Risiko → tiltak → kontroll → restrisiko

| Risiko | Nivå før | Tiltak | ISO 27001 Annex A | Eier | Frist | Nivå etter |
|:---:|:---:|---|---|---|:---:|:---:|
| [R1](02-risikovurdering/risikoregister.md) Kontoovertakelse i Salesforce | 🔴 16 | [T1](02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang), [T6](02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) | `A.5.17`, `A.8.5`, `A.5.15`, `A.5.16`, `A.5.18` | Driftsansvarlig | 1 mnd | 🟢 4 |
| [R2](02-risikovurdering/risikoregister.md) Phishing mot supportteamet | 🔴 20 | [T1](02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang), [T2](02-risikovurdering/tiltaksplan.md#t2--kontinuerlig-sikkerhetsopplæring-med-phishing-simulering), [T4](02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) | `A.8.5`, `A.6.3`, `A.5.26`, `A.8.22` | Sikkerhetsansvarlig | 2 mnd | 🟡 8 |
| [R3](02-risikovurdering/risikoregister.md) Angrep på API-integrasjonen | 🟠 12 | [T5](02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner) | `A.8.21`, `A.8.24`, `A.8.16` | Utviklingsansvarlig | 3 mnd | 🟢 4 |
| [R4](02-risikovurdering/risikoregister.md) Utilgjengelighet i Azure | 🔴 15 | [T3](02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse) | `A.8.13`, `A.8.14`, `A.5.29`, `A.5.30`, `A.5.23` | Driftsansvarlig | 3 mnd | 🟡 5 |
| [R5](02-risikovurdering/risikoregister.md) Misbruk av intern tilgang | 🟡 8 | [T6](02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon), [T2](02-risikovurdering/tiltaksplan.md#t2--kontinuerlig-sikkerhetsopplæring-med-phishing-simulering) | `A.5.15`, `A.5.16`, `A.5.18`, `A.8.2` | Sikkerhetsansvarlig | 4 mnd | 🟢 4 |
| [R6](02-risikovurdering/risikoregister.md) Løsepengevirus i driftsmiljøet | 🔴 15 | [T4](02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden), [T3](02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse), [T7](02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) | `A.8.22`, `A.8.2`, `A.8.13`, `A.8.8`, `A.5.26` | Driftsansvarlig | 6 mnd | 🟡 8 |
| [R7](02-risikovurdering/risikoregister.md) Tap av bærbar enhet | 🟡 6 | [T9](02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | `A.8.1`, `A.7.9`, `A.8.24`, `A.6.7` | Driftsansvarlig | 2 mnd | 🟢 2 |
| [R8](02-risikovurdering/risikoregister.md) Leverandørkjedeangrep via RMM | 🟠 10 | [T4](02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden), [T10](02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | `A.5.19`–`A.5.23`, `A.8.19`, `A.8.2` | Sikkerhetsansvarlig | 6 mnd | 🟡 5 |
| [R9](02-risikovurdering/risikoregister.md) Brudd på meldeplikt (art. 33) | 🟡 9 | [T8](02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) | `A.5.24`–`A.5.28`, `A.5.31`, `A.5.34` | Sikkerhetsansvarlig | 2 mnd | 🟢 3 |
| [R10](02-risikovurdering/risikoregister.md) Feilkonfigurering i Azure | 🟠 12 | [T7](02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) | `A.8.9`, `A.8.8`, `A.8.16`, `A.5.23` | Driftsansvarlig | 3 mnd | 🟡 6 |

---

## 2. Regelverkskrav → leveranse

| Krav | Kilde | Dekket av | Status |
|---|---|---|---|
| Organisasjonens kontekst og interessenter | ISO 27001 pkt. 4.1–4.3 | [Kap. 01](01-virksomhetskontekst/virksomhetskontekst.md) | 🟢 |
| Risikovurderingsprosess med kriterier | ISO 27001 pkt. 6.1.2 | [Metodikk](02-risikovurdering/metodikk.md) | 🟢 |
| Risikohåndteringsplan | ISO 27001 pkt. 6.1.3 | [Tiltaksplan](02-risikovurdering/tiltaksplan.md) | 🟢 |
| Statement of Applicability | ISO 27001 pkt. 6.1.3 d) | [SoA](04-isms/statement-of-applicability.md) | 🟡 Utdrag (36 av 93) |
| Ledelsens gjennomgang | ISO 27001 pkt. 9.3 | — | 🔴 Ikke utarbeidet |
| Internrevisjon | ISO 27001 pkt. 9.2 | — | 🔴 Ikke utarbeidet |
| Behandlingsprotokoll | GDPR art. 30 | [Kap. 03 pkt. 3](03-gdpr/gdpr-analyse.md#3-behandlingsprotokoll--utdrag-art-30) | 🟡 Utdrag |
| Databehandleravtaler | GDPR art. 28 | [Kap. 03](03-gdpr/gdpr-analyse.md) + [T10](02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) | 🟠 Gap |
| Sikkerhet ved behandling | GDPR art. 32 | T1, T3, T5, T6, T7, T9 | 🟡 Delvis |
| Brudd- og varslingsrutine | GDPR art. 33–34 | [Hendelsesresponsplan](04-isms/hendelsesresponsplan.md) | 🔵 Planlagt |
| DPIA-bistand | GDPR art. 28(3)(f), 35 | [Kap. 03 pkt. 4](03-gdpr/gdpr-analyse.md#4-dpia-screening-skydrift-av-helseklinikkdata) | 🟡 Delvis |
| Risikostyringstiltak | NIS2 art. 21 (fremtidig) | [Kap. 06 pkt. 4](06-nis2/nis2-vurdering.md#4-kravene-i-art-21--gap-analyse-mot-porteføljen) | 🟠 2 av 10 dekket |
| Varslingsplikt 24/72 t / 1 mnd | NIS2 art. 23 (fremtidig) | [Varslingsmatrise](04-isms/hendelsesresponsplan.md#5-varslingsmatrise) | 🔵 Betinget rad |

---

## 3. Kontroll → hvor den er operasjonalisert

Motsatt vei: for hver kontroll i SoA-utdraget, hvor i porteføljen den faktisk er beskrevet i drift.

| Kontrollgruppe | Operasjonalisert i |
|---|---|
| `A.5.15`–`A.5.18`, `A.8.2`, `A.8.5` — identitet og tilgang | [Policy for tilgangsstyring](04-isms/policy-tilgangsstyring.md) |
| `A.5.19`–`A.5.23` — leverandør og skytjenester | [T10](02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring), [kap. 03 pkt. 6](03-gdpr/gdpr-analyse.md#6-overføring-til-tredjeland) |
| `A.5.24`–`A.5.28` — hendelseshåndtering | [Hendelsesresponsplan](04-isms/hendelsesresponsplan.md) |
| `A.5.29`, `A.5.30`, `A.8.13`, `A.8.14` — kontinuitet | [T3](02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse); BCP/DRP identifisert som gap |
| `A.5.31`, `A.5.34` — regelverk og personvern | [Kap. 03](03-gdpr/gdpr-analyse.md), [kap. 06](06-nis2/nis2-vurdering.md) |
| `A.6.3` — opplæring | [Kap. 05](05-sikkerhetskultur/opplaeringsprogram.md) |
| `A.6.7`, `A.7.9`, `A.8.1` — endepunkt og fjernarbeid | [T9](02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) |
| `A.8.8`, `A.8.9`, `A.8.16` — konfigurasjon og overvåking | [T7](02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure) |
| `A.8.19`, `A.8.22` — segmentering og programvarekontroll | [T4](02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) |
| `A.8.21`, `A.8.24` — nettverkstjenester og kryptografi | [T5](02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner), [T9](02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll); kryptopolicy identifisert som gap |

---

## 4. Kjente gap

Gap dokumenteres her framfor å utelates. Et styringssystem som ikke vet hva det mangler, mangler først og fremst oversikt.

| Gap | Konsekvens | Planlagt lukket |
|---|---|---|
| Fullstendig SoA (93 kontroller) | Kan ikke sertifiseres på nåværende utdrag | Neste iterasjon |
| Prosedyre for ledelsens gjennomgang (pkt. 9.3) | ISO 27001-krav ikke oppfylt | Neste iterasjon |
| Internrevisjonsprogram (pkt. 9.2) | ISO 27001-krav ikke oppfylt | Neste iterasjon |
| BCP/DRP med RTO/RPO per kundekategori | `A.5.30` ikke påbegynt; NIS2-gap (c) | 0–3 mnd |
| Kryptopolicy | `A.8.24` delvis; NIS2-gap (h) | 0–3 mnd |
| Rutine for bakgrunnssjekk | NIS2-gap (i) | 3–6 mnd |
| Fullstendig behandlingsprotokoll | GDPR art. 30 | 0–3 mnd |
