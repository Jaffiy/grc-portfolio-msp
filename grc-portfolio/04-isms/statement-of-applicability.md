# Statement of Applicability (utdrag) — ISO/IEC 27001:2022

*Fullstendig SoA dekker alle 93 kontroller i Annex A. Dette utdraget viser kontrollene som er direkte begrunnet i risikobehandlingsplanen (kap. 02), med status og begrunnelse — formatet en revisor forventer.*

| Kontroll | Navn | Anvendes | Begrunnelse / risikoreferanse | Status |
|---|---|---|---|---|
| A.5.15 | Tilgangsstyring | Ja | R1, R5 — minste privilegium på tvers av kunder | Delvis implementert |
| A.5.17 | Autentiseringsinformasjon | Ja | R1 — passordpolicy og MFA (T1) | Planlagt (1 mnd) |
| A.5.18 | Tilgangsrettigheter | Ja | R5 — kvartalsvis tilgangsrevisjon (T6) | Planlagt (4 mnd) |
| A.5.24 | Planlegging av hendelseshåndtering | Ja | R9 — hendelsesresponsplan (T8) | Planlagt (2 mnd) |
| A.5.26 | Respons på hendelser | Ja | R2, R6, R9 | Planlagt (2 mnd) |
| A.5.28 | Innsamling av bevis | Ja | Bevissikring ved hendelser hos kunder — kontraktskrav | Ikke påbegynt |
| A.5.29 | Sikkerhet ved avbrudd | Ja | R4 — kontinuitet for SLA-forpliktelser (T3) | Delvis implementert |
| A.5.31 | Juridiske og regulatoriske krav | Ja | GDPR, digitalsikkerhetsloven (kap. 03, 06) | Delvis implementert |
| A.6.3 | Sikkerhetsopplæring | Ja | R2 — opplæringsprogram (T2) | Planlagt (2 mnd) |
| A.8.2 | Privilegerte tilgangsrettigheter | Ja | R6, R8 — PIM/PAW (T4) | Planlagt (6 mnd) |
| A.8.5 | Sikker autentisering | Ja | R1, R2 — phishing-resistent MFA (T1) | Planlagt (1 mnd) |
| A.8.8 | Håndtering av tekniske sårbarheter | Ja | R6, R10 — patching, pentest (T7) | Delvis implementert |
| A.8.9 | Konfigurasjonsstyring | Ja | R10 — CIS baseline, Defender for Cloud (T7) | Planlagt (3 mnd) |
| A.8.13 | Sikkerhetskopiering | Ja | R4, R6 — immutable, geo-redundant backup (T3) | Delvis implementert |
| A.8.14 | Redundans | Ja | R4 — failover for kritiske kundemiljøer (T3) | Planlagt (3 mnd) |
| A.8.19 | Installasjon av programvare | Ja | R8 — kontroll på fjernstyringsverktøy (T4) | Delvis implementert |
| A.8.21 | Sikkerhet i nettverkstjenester | Ja | R3 — API-sikring (T5) | Planlagt (3 mnd) |
| A.8.22 | Nettverkssegmentering | Ja | R6, R8 — skille kunde- og adminmiljøer (T4) | Ikke påbegynt |
| A.8.24 | Bruk av kryptografi | Ja | R3, R7, R10 — TLS, diskkryptering, lagringskryptering | Delvis implementert |
| A.7.9 | Sikkerhet for utstyr utenfor lokaler | Ja | R7 — hjemmekontor/hybrid modell, diskkryptering | Delvis implementert |
| A.6.7 | Fjernarbeid | Ja | Hybrid arbeidsmodell | Delvis implementert |
| A.5.7 | Trusseletterretning | Ja | MSP-er er prioriterte mål; abonnere på NSM/NorCERT-varsler | Ikke påbegynt |
| A.8.30 | Utkontraktert utvikling | **Nei** | Ingen utkontraktert systemutvikling per i dag | — |
| A.7.13 | Vedlikehold av utstyr | **Nei** (begrenset) | Minimal egen infrastruktur; skybasert drift | — |

**Ekskluderinger begrunnes alltid** — en SoA uten begrunnede «Nei» er et rødt flagg for revisor.
