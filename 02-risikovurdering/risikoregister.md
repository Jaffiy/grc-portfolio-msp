# 02.2 — Risikoregister: kundesupportprosessen

| | |
|---|---|
| **Dokument** | Risikoregister |
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Versjon** | 2.0 · Vurdert 01.09.2026 · Revideres årlig og ved vesentlige endringer |
| **Metodikk** | [metodikk.md](metodikk.md) |
| **Leser videre** | [Tiltaksplan](tiltaksplan.md) · [Statement of Applicability](../04-isms/statement-of-applicability.md) |

> **Lesehjelp.** K/I/T = konsekvens per sikkerhetsegenskap (1–5). **Kons.** = samlet konsekvens = høyeste KIT-verdi. **S** = sannsynlighet. **Nivå** = S × Kons. Risikoer merket `E` er etterlevelsesrisiko der konsekvensen settes direkte fra den juridiske/omdømmemessige kolonnen i konsekvensskalaen — se [metodikk pkt. 1.1](metodikk.md#11-hvordan-konsekvens-fastsettes).

---

## 1. Register

| ID | Uønsket hendelse | Trussel → sårbarhet | Verdi berørt | K | I | T | Kons. | S | Nivå |
|:---:|---|---|---|:---:|:---:|:---:|:---:|:---:|---|
| **R1** | Kontoovertakelse i Salesforce eksponerer kundedata | Ekstern aktør → svake passord; MFA ikke håndhevet for alle brukere | Kundedata, kontrakter | 4 | 3 | 2 | **4** | 4 | 🔴 **16 — Svært høy** |
| **R2** | Phishing mot supportteamet gir fotfeste i interne systemer | Ekstern aktør → manglende trening; support håndterer høyt e-postvolum under tidspress | Alle systemer | 5 | 3 | 2 | **5** | 4 | 🔴 **20 — Svært høy** |
| **R3** | Avlytting eller manipulasjon av API-integrasjonen Salesforce ↔ Jira | Ekstern aktør → svak autentisering på integrasjonen, manglende sertifikatvalidering | Supportsaker med persondata | 4 | 3 | 1 | **4** | 3 | 🟠 **12 — Høy** |
| **R4** | Langvarig utilgjengelighet i Azure-baserte kundemiljøer | Teknisk svikt eller DDoS → utilstrekkelig redundans; backup i samme region | Kundemiljøer, SLA | 1 | 2 | 5 | **5** | 3 | 🔴 **15 — Svært høy** |
| **R5** | Misbruk av intern tilgang (innsiderisiko) | Intern aktør → manglende rollebasert tilgangsstyring; bred stående tilgang | Kundedata på tvers av kunder | 4 | 3 | 1 | **4** | 2 | 🟡 **8 — Moderat** |
| **R6** | Løsepengevirus via kompromittert klient sprer seg til driftsmiljøet | Ekstern aktør → manglende segmentering mellom kundemiljøer og admin-nett; uoppdatert programvare | Alle verdier | 4 | 5 | 5 | **5** | 3 | 🔴 **15 — Svært høy** |
| **R7** | Tap eller tyveri av bærbar enhet med lokalt lagrede kundedata | Tyveri → ufullstendig utrulling av diskkryptering | Lokalt lagrede data | 3 | 1 | 1 | **3** | 2 | 🟡 **6 — Moderat** |
| **R8** | Leverandørkjedeangrep via Mjøsdatas egne fjernstyringsverktøy (RMM) | Ekstern aktør → verktøy med privilegert tilgang til alle kunder; ingen leverandørrisikovurdering | Kundemiljøer | 5 | 5 | 4 | **5** | 2 | 🟠 **10 — Høy** |
| **R9** `E` | Brudd på meldeplikt ved personvernbrudd (art. 33) | Prosessvikt → uklare interne rutiner for å oppdage, vurdere og eskalere brudd | Etterlevelse, omdømme | 2 | 2 | 1 | **3** | 3 | 🟡 **9 — Moderat** |
| **R10** | Feilkonfigurering i Azure eksponerer kundelagring mot internett | Menneskelig feil → manglende baseline-konfigurasjon og teknisk revisjon | Kundedata, backup | 4 | 2 | 2 | **4** | 3 | 🟠 **12 — Høy** |

**Om R9:** samlet konsekvens er satt til 3 fra den juridiske kolonnen («meldepliktig brudd etter art. 33»), ikke som høyeste KIT-verdi (som ville vært 2). Dette er unntaksregelen for etterlevelsesrisiko i [metodikk pkt. 1.1](metodikk.md#11-hvordan-konsekvens-fastsettes) — anvendt eksplisitt og med begrunnelse, ikke som et enkelttilfelle av avvik fra modellen. Selve prosessvikten kompromitterer ingen data, men manglende eller forsinket melding er et selvstendig regelbrudd med gebyrpotensial uavhengig av den underliggende hendelsen.

---

## 2. Risikomatrise (før tiltak)

|  | **K1** | **K2** | **K3** | **K4** | **K5** |
|---|:---:|:---:|:---:|:---:|:---:|
| **S5** | | | | | |
| **S4** | | | | 🔴 R1 | 🔴 R2 |
| **S3** | | | 🟡 R9 | 🟠 R3, R10 | 🔴 R4, R6 |
| **S2** | | | 🟡 R7 | 🟡 R5 | 🟠 R8 |
| **S1** | | | | | |

🟢 Lav (1–4) · 🟡 Moderat (5–9) · 🟠 Høy (10–14) · 🔴 Svært høy (15–25)

### Fordeling

| Klassifisering | Antall | Risikoer |
|---|:---:|---|
| 🔴 Svært høy | 4 | R1, R2, R4, R6 |
| 🟠 Høy | 3 | R3, R8, R10 |
| 🟡 Moderat | 3 | R5, R7, R9 |
| 🟢 Lav | 0 | — |

Sju av ti risikoer ligger over akseptnivå og krever behandling. At ingen havner i 🟢 er ikke en feil i skalaen, men en konsekvens av at analysen er avgrenset til kjerneprosessen: risikoer som allerede er godt håndtert er ikke tatt inn som egne registeroppføringer.

---

## 3. Hovedfunn

**1 — Menneske- og identitetsrettede angrep dominerer toppen.** R1 og R2 er de høyeste risikoene i registeret, drevet av høy sannsynlighet i dagens trusselbilde kombinert med at supportteamet har bred tilgang på tvers av kundeporteføljen. Det gjør identitetssikring til den enkeltinvesteringen med størst effekt — se [T1](tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang).

**2 — MSP-rollen konsentrerer risiko strukturelt.** R6 og R8 er ikke bare «store risikoer»; de er en annen *type* risiko. Kompromittering av Mjøsdata er samtidig kompromittering av kundene, og konsekvensnivået blir derfor systematisk høyere enn for en enkeltvirksomhet av samme størrelse. Dette er begrunnelsen for at [T4](tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) prioriteres til tross for høy kostnad.

**3 — Tilgjengelighet er en kontraktsrisiko, ikke bare en teknisk risiko.** R4 scorer svært høyt fordi SLA-forpliktelsene omdanner nedetid direkte til prisavslag og kundeflukt. En rent teknisk risikovurdering ville plassert denne lavere.

**4 — Etterlevelsesrisiko er reell selv uten angrep.** R9 minner om at manglende rutiner alene — uavhengig av trusselaktører — kan gi gebyr og omdømmetap. Dette er også den billigste risikoen å redusere, se [T8](tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner).

**5 — Den laveste risikoen har den billigste løsningen.** R7 (6, moderat) ligger under behandlingsterskelen, men sårbarheten — ufullstendig diskkryptering — lukkes med et tiltak som i praksis er gratis. [T9](tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) er tatt med av denne grunn, ikke fordi akseptkriteriene krever det.

---

## 4. Risikoer utenfor omfang

Følgende er identifisert, men ligger utenfor [omfanget i kap. 01](../01-virksomhetskontekst/virksomhetskontekst.md#5-omfang-og-avgrensning-iso-27001-pkt-43) og er ikke vurdert i denne omgangen. De dokumenteres her for å vise at utelatelsen er bevisst:

| Område | Begrunnelse for utelatelse |
|---|---|
| Fysisk sikring av hovedkontor | Ingen egen datasenterdrift; kontoret har ikke kundedata utover endepunkter (dekket av R7) |
| HR- og lønnsprosesser | Egne systemer utenfor kjerneprosessen; personvern dekket separat i [kap. 03](../03-gdpr/gdpr-analyse.md) |
| Kundenes egne interne risikoer | Mjøsdatas ansvar er avgrenset av databehandleravtalen; inngår i kundens eget risikoarbeid |
| Økonomisk svindel (CEO-fraud, fakturasvindel) | Ikke informasjonssikkerhet i snever forstand, men adressert i [opplæringsprogrammet](../05-sikkerhetskultur/opplaeringsprogram.md#2-målgrupper-og-innhold) |
