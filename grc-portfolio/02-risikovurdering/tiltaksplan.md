# Risikobehandlingsplan

*Tiltak for alle risikoer over akseptnivå (≥ 10), prioritert etter risikoreduksjon per krone. Hvert tiltak er mappet til ISO/IEC 27001:2022 Annex A og NSM Grunnprinsipper, og restrisiko er estimert etter implementering.*

## Prioriterte tiltak

### T1 — Obligatorisk phishing-resistent MFA og kondisjonell tilgang (adresserer R1, R2, delvis R8)

- **Tiltak:** Håndheve MFA for alle brukere i Salesforce, Jira, Azure og e-post via Entra ID Conditional Access. Prioriter phishing-resistente metoder (FIDO2/passkeys) for administratorer og supportteam. Blokkér legacy-autentisering.
- **Begrunnelse:** Microsofts telemetri viser at MFA stopper det store flertallet av kontoovertakelsesangrep. Høyeste risikoreduksjon til lavest kostnad i hele planen.
- **Referanse:** ISO 27001 A.5.17, A.8.5; NSM GP 2.6.4 • **Eier:** Driftsansvarlig • **Frist:** 1 måned
- **Restrisiko:** R1: 16 → 4 (Lav) · R2: 20 → 10 (Høy — krever også T2)

### T2 — Kontinuerlig sikkerhetsopplæring med phishing-simulering (adresserer R2, R5, R7, R9)

- **Tiltak:** Programmet beskrevet i `05-sikkerhetskultur/`: kvartalsvise kurs, månedlige phishing-simuleringer med prioritet til support, målsatt klikkrate < 5 % innen 12 måneder.
- **Referanse:** ISO 27001 A.6.3; NSM GP 1.1 • **Eier:** Sikkerhetsansvarlig • **Frist:** oppstart 2 måneder
- **Restrisiko:** R2: 10 → 8 (Moderat) i kombinasjon med T1

### T3 — Geo-redundans, immutable backup og DDoS-beskyttelse i Azure (adresserer R4, delvis R6)

- **Tiltak:** Geo-redundant lagring og failover for kritiske kundemiljøer, automatisert backup til separat region med immutability (beskytter mot at løsepengevirus krypterer backup), lastbalansering og Azure DDoS Protection.
- **Referanse:** ISO 27001 A.8.13, A.8.14, A.5.29; NSM GP 2.9 • **Eier:** Driftsansvarlig • **Frist:** 3 måneder
- **Restrisiko:** R4: 15 → 5 (Moderat)

### T4 — Segmentering og herding av MSP-verktøykjeden (adresserer R6, R8)

- **Tiltak:** Nettverkssegmentering mellom kundemiljøer og mellom kunde- og administrasjonsnett; dedikerte, herdede admin-arbeidsstasjoner (PAW) for privilegert tilgang; just-in-time-tilgang via Entra PIM; sikkerhetsvurdering og oppdateringsregime for fjernstyringsverktøy.
- **Begrunnelse:** Adresserer den strukturelle MSP-risikoen — ett innbrudd skal ikke kunne bli alle kunders innbrudd.
- **Referanse:** ISO 27001 A.8.22, A.8.2, A.8.19; NSM GP 2.2, 2.5 • **Eier:** Driftsansvarlig • **Frist:** 6 måneder
- **Restrisiko:** R6: 15 → 8 · R8: 10 → 5 (begge Moderat)

### T5 — Sikring av API-integrasjoner (adresserer R3)

- **Tiltak:** mTLS og OAuth 2.0 med kortlivede tokens på integrasjonen Salesforce ↔ Jira, hemmelighetshåndtering i Azure Key Vault, logging av integrasjonstrafikk.
- **Referanse:** ISO 27001 A.8.21, A.8.24 • **Eier:** Utviklingsansvarlig • **Frist:** 3 måneder
- **Restrisiko:** R3: 12 → 4 (Lav)

### T6 — Rollebasert tilgangsstyring og periodisk tilgangsrevisjon (adresserer R5, R1)

- **Tiltak:** RBAC etter minste privilegium i Salesforce og Azure; kvartalsvis tilgangsrevisjon; automatisk deaktivering ved fratredelse. Policy i `04-isms/policy-tilgangsstyring.md`.
- **Referanse:** ISO 27001 A.5.15, A.5.18, A.8.2; NSM GP 2.6 • **Eier:** Sikkerhetsansvarlig • **Frist:** 4 måneder
- **Restrisiko:** R5: 8 → 4 (Lav)

### T7 — Baseline-konfigurasjon og teknisk revisjon av Azure (adresserer R10)

- **Tiltak:** Definert sikker baseline (CIS Benchmark for Azure), kontinuerlig overvåking med Microsoft Defender for Cloud, månedlig gjennomgang av avvik, ekstern penetrasjonstest to ganger årlig.
- **Referanse:** ISO 27001 A.8.9, A.8.8; NSM GP 2.3 • **Eier:** Driftsansvarlig • **Frist:** 3 måneder
- **Restrisiko:** R10: 12 → 6 (Moderat)

### T8 — Hendelsesrespons- og bruddrutiner (adresserer R9, reduserer konsekvens for alle)

- **Tiltak:** Hendelsesresponsplan (`04-isms/hendelsesresponsplan.md`) med definert eskalering, 72-timersvurdering etter GDPR art. 33, varslingsmaler og årlig øvelse.
- **Referanse:** ISO 27001 A.5.24–A.5.28; GDPR art. 33–34 • **Eier:** Sikkerhetsansvarlig • **Frist:** 2 måneder
- **Restrisiko:** R9: 9 → 3 (Lav)

## Styring og oppfølging

- Det etableres en **sikkerhets- og personvernkomité** ledet av sikkerhetsansvarlig, med driftsansvarlig og personvernkontakt, som rapporterer kvartalsvis til daglig leder og årlig til styret.
- Planen revideres ved vesentlige endringer i systemlandskap eller trusselbilde, minimum årlig.
- Restrisiko som fortsatt er Moderat (R2, R4, R6, R10) etter tiltak fremlegges daglig leder for formell aksept.

## Kost/nytte-oppsummering

| Tiltak | Kostnadsindikasjon | Risikoreduksjon | Prioritet |
|---|---|---|---|
| T1 MFA | Lav (lisenser finnes ofte allerede) | Svært høy | 1 |
| T8 Hendelsesrespons | Lav (arbeidstid) | Høy (konsekvensreduserende) | 2 |
| T2 Opplæring | Lav–moderat | Høy | 3 |
| T5 API-sikring | Moderat | Høy | 4 |
| T3 Redundans/backup | Høy | Høy | 5 |
| T6 RBAC | Moderat | Moderat | 6 |
| T7 Baseline/revisjon | Moderat | Moderat | 7 |
| T4 Segmentering/PAW | Høy | Høy (strukturell) | 8* |

\* T4 er kostbar og tidkrevende, men strategisk viktigst på lang sikt for en MSP; den startes parallelt selv om full effekt kommer sist.
