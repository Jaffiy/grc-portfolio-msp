# Risikoregister for kundesupportprosessen

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Versjon | 2.0, vurdert 1. september 2026 |
| Revisjon | Årlig, og ved vesentlige endringer |
| Metodikk | [metodikk.md](metodikk.md) |

I tabellen står K, I og T for konsekvens på henholdsvis konfidensialitet, integritet og tilgjengelighet, målt fra 1 til 5. Kons. er den samlede konsekvensen, som normalt er den høyeste av de tre. S er sannsynlighet. Nivået er produktet av sannsynlighet og samlet konsekvens. Risikoer merket med E er etterlevelsesrisiko, der konsekvensen settes fra den juridiske kolonnen i konsekvensskalaen i stedet.

## 1. Registeret

| ID | Uønsket hendelse | Trussel og sårbarhet | Verdi som rammes | K | I | T | Kons. | S | Nivå |
|---|---|---|---|---|---|---|---|---|---|
| R1 | Kontoovertakelse i Salesforce eksponerer kundedata | Ekstern aktør utnytter svake passord, og at MFA ikke er håndhevet for alle brukere | Kundedata og kontrakter | 4 | 3 | 2 | 4 | 4 | 16, svært høy |
| R2 | Phishing mot supportteamet gir fotfeste i interne systemer | Ekstern aktør utnytter manglende trening, og at support håndterer mye e-post under tidspress | Alle systemer | 5 | 3 | 2 | 5 | 4 | 20, svært høy |
| R3 | Avlytting eller manipulasjon av integrasjonen mellom Salesforce og Jira | Ekstern aktør utnytter svak autentisering og manglende sertifikatvalidering | Supportsaker med persondata | 4 | 3 | 1 | 4 | 3 | 12, høy |
| R4 | Langvarig utilgjengelighet i Azure-baserte kundemiljøer | Teknisk svikt eller tjenestenektangrep treffer utilstrekkelig redundans, med backup i samme region | Kundemiljøer og SLA | 1 | 2 | 5 | 5 | 3 | 15, svært høy |
| R5 | Misbruk av intern tilgang | Intern aktør utnytter manglende rollestyring og bred stående tilgang | Kundedata på tvers av kunder | 4 | 3 | 1 | 4 | 2 | 8, moderat |
| R6 | Løsepengevirus fra en kompromittert klient sprer seg til driftsmiljøet | Ekstern aktør utnytter manglende segmentering og uoppdatert programvare | Alle verdier | 4 | 5 | 5 | 5 | 3 | 15, svært høy |
| R7 | Tap eller tyveri av bærbar enhet med lokalt lagrede kundedata | Tyveri treffer ufullstendig utrulling av diskkryptering | Lokalt lagrede data | 3 | 1 | 1 | 3 | 2 | 6, moderat |
| R8 | Leverandørkjedeangrep gjennom Mjøsdatas egne fjernstyringsverktøy | Ekstern aktør utnytter verktøy med stående privilegert tilgang til alle kunder, uten leverandørvurdering | Kundemiljøer | 5 | 5 | 4 | 5 | 2 | 10, høy |
| R9 (E) | Brudd på meldeplikten ved personvernbrudd | Prosessvikt fordi rutinene for å oppdage, vurdere og eskalere brudd er uklare | Etterlevelse og omdømme | 2 | 2 | 1 | 3 | 3 | 9, moderat |
| R10 | Feilkonfigurering i Azure eksponerer kundelagring mot internett | Menneskelig feil på grunn av manglende baseline og teknisk revisjon | Kundedata og backup | 4 | 2 | 2 | 4 | 3 | 12, høy |

For R9 er samlet konsekvens satt til 3 fra den juridiske kolonnen, ikke som høyeste enkeltverdi, som ville gitt 2. Dette er unntaksregelen for etterlevelsesrisiko i metodikken, brukt bevisst og med begrunnelse i stedet for som et enkeltstående avvik. Prosessvikten kompromitterer ingen data i seg selv, men manglende eller forsinket melding er et selvstendig regelbrudd som kan gi gebyr uavhengig av den underliggende hendelsen.

## 2. Risikomatrise før tiltak

| | K1 | K2 | K3 | K4 | K5 |
|---|---|---|---|---|---|
| S5 | | | | | |
| S4 | | | | R1 | R2 |
| S3 | | | R9 | R3, R10 | R4, R6 |
| S2 | | | R7 | R5 | R8 |
| S1 | | | | | |

Fordelingen ser slik ut:

| Klassifisering | Antall | Risikoer |
|---|---|---|
| Svært høy | 4 | R1, R2, R4, R6 |
| Høy | 3 | R3, R8, R10 |
| Moderat | 3 | R5, R7, R9 |
| Lav | 0 | |

Sju av ti risikoer ligger over akseptnivået og krever behandling. At ingen havner i laveste kategori skyldes avgrensningen: risikoer som allerede er godt håndtert er ikke tatt inn som egne oppføringer i registeret.

## 3. Hovedfunn

Angrep rettet mot mennesker og identiteter dominerer toppen. R1 og R2 er de to høyeste risikoene, drevet av at sannsynligheten er høy i dagens trusselbilde og at supportteamet har bred tilgang på tvers av kundeporteføljen. Det gjør identitetssikring til den investeringen som gir mest effekt for pengene, og forklarer hvorfor tiltak T1 ligger øverst i planen.

Rollen som driftsleverandør konsentrerer risiko. R6 og R8 er ikke bare store risikoer, de er en annen type risiko. Blir Mjøsdata kompromittert, er kundene det samtidig, og konsekvensnivået blir dermed systematisk høyere enn for en enkeltvirksomhet av samme størrelse. Det er begrunnelsen for at T4 prioriteres selv om det er det dyreste tiltaket i planen.

Tilgjengelighet er en kontraktsrisiko, ikke bare en teknisk risiko. R4 scorer høyt fordi SLA-forpliktelsene gjør nedetid om til prisavslag og kundeflukt nesten umiddelbart. En rent teknisk vurdering ville plassert denne lavere.

Etterlevelsesrisiko er reell selv uten en angriper. R9 er en påminnelse om at manglende rutiner alene kan gi gebyr og omdømmetap. Det er også den billigste risikoen å redusere.

Den laveste risikoen har den enkleste løsningen. R7 ligger på 6 og dermed under behandlingsterskelen, men sårbarheten er ufullstendig diskkryptering, og den lukkes med et tiltak som i praksis bare koster konfigurasjonstid. Derfor er T9 tatt med, ikke fordi akseptkriteriene krever det.

## 4. Risikoer utenfor omfanget

Disse er identifisert, men ligger utenfor avgrensningen i kapittel 01. De står oppført her for å vise at utelatelsen er bevisst.

| Område | Begrunnelse |
|---|---|
| Fysisk sikring av hovedkontoret | Ingen egen datasenterdrift. Kontoret har ikke kundedata utover endepunktene, som dekkes av R7 |
| HR- og lønnsprosesser | Egne systemer utenfor kjerneprosessen. Personvernsiden dekkes i kapittel 03 |
| Kundenes egne interne risikoer | Mjøsdatas ansvar er avgrenset av databehandleravtalen. Dette hører hjemme i kundens eget risikoarbeid |
| Økonomisk svindel som direktørsvindel og fakturasvindel | Ikke informasjonssikkerhet i snever forstand, men tatt inn som tema i opplæringsprogrammet |

Tiltak for risikoene over akseptnivå står i [tiltaksplanen](tiltaksplan.md).
