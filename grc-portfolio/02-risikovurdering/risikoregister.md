# Risikoregister — kundesupportprosessen

*Vurdert etter metodikken i `metodikk.md`. K/I/T angir konsekvens per sikkerhetsegenskap (1–5); samlet konsekvens = høyeste verdi. S = sannsynlighet.*

## Risikoregister

| ID | Uønsket hendelse | Trussel → sårbarhet | Verdi berørt | K | I | T | S | Kons. | Nivå |
|---|---|---|---|---|---|---|---|---|---|
| R1 | Kontoovertakelse i Salesforce eksponerer kundedata | Ekstern aktør → svake passord, MFA ikke håndhevet for alle brukere | Kundedata, kontrakter | 4 | 3 | 2 | 4 | 4 | **16 – Svært høy** |
| R2 | Phishing mot supportteamet gir fotfeste i interne systemer | Ekstern aktør → manglende trening; support håndterer høyt e-postvolum under tidspress | Alle systemer | 5 | 3 | 2 | 4 | 5 | **20 – Svært høy** |
| R3 | Avlytting/manipulasjon av API-integrasjonen Salesforce ↔ Jira | Ekstern aktør → svak autentisering på integrasjon, manglende sertifikatvalidering | Supportsaker med persondata | 4 | 3 | 1 | 3 | 4 | **12 – Høy** |
| R4 | Langvarig utilgjengelighet i Azure-baserte kundemiljøer | Teknisk svikt/DDoS → utilstrekkelig redundans, backup i samme region | Kundemiljøer, SLA | 1 | 2 | 5 | 3 | 5 | **15 – Svært høy** |
| R5 | Misbruk av intern tilgang (innsiderisiko) | Intern aktør → manglende rollebasert tilgangsstyring, bred stående tilgang | Kundedata på tvers av kunder | 4 | 3 | 1 | 2 | 4 | **8 – Moderat** |
| R6 | Løsepengevirus via kompromittert klient sprer seg til driftsmiljø | Ekstern aktør → manglende segmentering mellom kundemiljøer og admin-nett, uoppdatert programvare | Alle verdier | 4 | 5 | 5 | 3 | 5 | **15 – Svært høy** |
| R7 | Tap/tyveri av bærbar enhet med lagrede kundedata | Tyveri → ufullstendig utrulling av diskkryptering | Lokalt lagrede data | 3 | 1 | 1 | 2 | 3 | **6 – Moderat** |
| R8 | Leverandørkjedeangrep via Mjøsdatas egne fjernstyringsverktøy | Ekstern aktør → MSP-verktøy med privilegert tilgang til alle kunder | Kundemiljøer | 5 | 5 | 4 | 2 | 5 | **10 – Høy** |
| R9 | Brudd på meldeplikt ved personvernbrudd (art. 33) | Prosessvikt → uklare interne rutiner for å oppdage, vurdere og eskalere brudd | Etterlevelse, omdømme | 2 | 2 | 1 | 3 | 3* | **9 – Moderat** |
| R10 | Feilkonfigurering i Azure eksponerer kundelagring mot internett | Menneskelig feil → manglende baseline-konfigurasjon og teknisk revisjon | Kundedata, backup | 4 | 2 | 2 | 3 | 4 | **12 – Høy** |

\* R9 vurderes primært på juridisk/omdømmedimensjonen i konsekvensskalaen.

## Risikomatrise (før tiltak)

|  | **K1** | **K2** | **K3** | **K4** | **K5** |
|---|---|---|---|---|---|
| **S5** | | | | | |
| **S4** | | | | R1 | R2 |
| **S3** | | | R9 | R3, R10 | R4, R6 |
| **S2** | | | R7 | R5 | R8 |
| **S1** | | | | | |

## Hovedfunn

1. **Menneske- og identitetsrettede angrep dominerer toppen.** R1 og R2 (kontoovertakelse og phishing) er de høyeste risikoene, drevet av høy sannsynlighet i dagens trusselbilde og alvorlig konsekvens fordi supportteamet har bred tilgang.
2. **MSP-rollen konsentrerer risiko.** R6 og R8 viser det strukturelle problemet for en driftsleverandør: kompromittering av Mjøsdata er samtidig kompromittering av kundene. Konsekvensnivået blir derfor systematisk høyere enn hos en enkeltvirksomhet.
3. **Tilgjengelighet er en kontraktsrisiko, ikke bare en teknisk risiko.** R4 scorer svært høyt fordi SLA-forpliktelsene omdanner nedetid direkte til økonomisk tap og kundetap.
4. **Etterlevelsesrisiko er reell selv uten angrep.** R9 minner om at manglende rutiner alene — uavhengig av trusselaktører — kan gi gebyr og omdømmetap.

Tiltak for risikoer over akseptnivå følger i `tiltaksplan.md`.
