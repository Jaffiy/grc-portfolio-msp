# Risikobehandlingsplan

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Oppfølging | Kvartalsvis |
| Hjemmel | ISO/IEC 27001:2022 punkt 6.1.3, ISO/IEC 27005:2022 |

Planen dekker alle risikoer over akseptnivå, altså nivå 10 og oppover: R1, R2, R3, R4, R6, R8 og R10. I tillegg tar den med tre moderate risikoer der tiltaket koster så lite at det ikke er forsvarlig å utsette det: R5, R7 og R9. Akseptkriteriene i metodikken åpner uttrykkelig for dette.

Restrisiko er oppgitt med både ny sannsynlighet og ny konsekvens, sammen med en begrunnelse for hvilken av de to tiltaket faktisk endrer. Et tiltak som bare oppgis som en endring fra 12 til 4 skjuler om det virker forebyggende eller skadebegrensende, og lar seg ikke etterprøve.

## Oversikt

| Tiltak | Kort beskrivelse | Adresserer | Kostnad | Frist | Prioritet |
|---|---|---|---|---|---|
| T1 | Phishing-resistent MFA og betinget tilgang | R1, R2, R8 | Lav | 1 måned | 1 |
| T8 | Hendelsesrespons og bruddrutiner | R9, og alle indirekte | Lav | 2 måneder | 2 |
| T9 | Full diskkryptering og endepunktkontroll | R7 | Lav | 2 måneder | 3 |
| T2 | Sikkerhetsopplæring og phishing-simulering | R2, R5, R9 | Lav til moderat | 2 måneder til oppstart | 4 |
| T5 | Sikring av API-integrasjonen | R3 | Moderat | 3 måneder | 5 |
| T7 | Baseline-konfigurasjon og teknisk revisjon | R10, R6 | Moderat | 3 måneder | 6 |
| T3 | Geo-redundans, uforanderlig backup og vern mot tjenestenektangrep | R4, R6 | Høy | 3 måneder | 7 |
| T6 | Rollebasert tilgangsstyring og tilgangsrevisjon | R5, R1 | Moderat | 4 måneder | 8 |
| T10 | Leverandør- og verktøykjedestyring | R8 | Lav til moderat | 6 måneder | 9 |
| T4 | Segmentering og herding av verktøykjeden | R6, R8, R2 | Høy | 6 måneder | 10 |

T4 kommer sist på listen fordi rangeringen følger risikoreduksjon per krone. Det betyr ikke at arbeidet skal vente. Se avsnittet om prioritering nederst.

## T1. Phishing-resistent MFA og betinget tilgang

Adresserer R1, R2 og delvis R8.

MFA håndheves for alle brukere i Salesforce, Jira, Azure og e-post gjennom betinget tilgang i Entra ID. Administratorer og supportpersonell skal bruke phishing-resistente metoder som FIDO2 eller passkeys. Autentiseringsprotokoller som ikke støtter MFA blokkeres.

Kontoovertakelse er inngangen i begge de to høyest rangerte risikoene. Sterk autentisering fjerner ikke angrepsforsøket, men bryter angrepskjeden på det punktet der det er billigst å bryte den. Lisensene ligger i all hovedsak allerede i Microsoft 365-avtalen, så dette gir mest risikoreduksjon per krone av alt i planen.

Kontroller: ISO 27001 A.5.17 og A.8.5. NSM Grunnprinsipper 2.6.
Eier: driftsansvarlig. Frist: 1 måned.

Restrisiko for R1 går fra 16 til 4. Sannsynligheten faller fra 4 til 1, mens konsekvensen står uendret på 4, siden dataene er like eksponerte dersom angrepet først lykkes. Restrisiko for R2 går fra 20 til 10. Sannsynligheten faller fra 4 til 2, og risikoen trenger både T2 og T4 for å komme ned på akseptabelt nivå.

## T2. Sikkerhetsopplæring og phishing-simulering

Adresserer R2, R5 og R9.

Programmet er beskrevet i [kapittel 05](../05-sikkerhetskultur/opplaeringsprogram.md). Kort oppsummert består det av kvartalsvise kurs, månedlige phishing-simuleringer med support som prioritert gruppe, og en kampanje som belønner rapportering. Målet er klikkrate under 5 prosent og rapporteringsrate over 60 prosent innen tolv måneder.

MFA stopper kontoovertakelse, men ikke sosial manipulering som får en ansatt til å utføre handlingen selv. Support er den mest eksponerte gruppen fordi de kombinerer stort e-postvolum, tidspress og bred systemtilgang i samme rolle.

Kontroller: ISO 27001 A.6.3. På den tekniske siden NSM Grunnprinsipper 2.8 om beskyttelse av e-post og nettleser.

Her er det verdt å nevne en detalj om rammeverkene. NSMs Grunnprinsipper for IKT-sikkerhet har ingen egen kategori for opplæring og sikkerhetskultur. Det dekkes i stedet av NSMs Grunnprinsipper for sikkerhetsstyring, under prinsippet om jevnlige øvelser, trening og opplæring. Jeg har derfor delt referansen mellom to NSM-rammeverk i stedet for å presse den inn i ett.

Eier: sikkerhetsansvarlig. Frist: oppstart innen 2 måneder, deretter løpende.

Restrisiko for R2 går fra 10 til 8, forutsatt at T1 og T4 også er på plass. Konsekvensen faller fra 5 til 4. Opplæring reduserer ikke antall phishing-forsøk, men rask rapportering forkorter tiden angriperen er uoppdaget, og segmentering begrenser hvor langt vedkommende kommer.

## T3. Geo-redundans, uforanderlig backup og vern mot tjenestenektangrep

Adresserer R4 og delvis R6.

Kritiske kundemiljøer får geo-redundant lagring og mulighet for failover. Backup automatiseres til en egen region med uforanderlig lagring, slik at løsepengevirus ikke kan kryptere eller slette sikkerhetskopiene. I tillegg kommer lastbalansering og Azure DDoS Protection. Gjenoppretting testes minst hvert halvår, siden en backup som aldri er testet er en antakelse og ikke et tiltak.

SLA-forpliktelsene gjør nedetid til en direkte kostnad. Uforanderlig backup er dessuten det ene tiltaket som skiller en løsepengevirushendelse man kommer seg ut av fra en man ikke kommer seg ut av.

Kontroller: ISO 27001 A.8.13, A.8.14, A.5.29 og A.5.30. NSM Grunnprinsipper 2.9.
Eier: driftsansvarlig. Frist: 3 måneder.

Restrisiko for R4 går fra 15 til 5. Sannsynligheten for langvarig utilgjengelighet faller fra 3 til 1, mens konsekvensen av et fullstendig regionsutfall står uendret. Derfor blir restrisikoen liggende på moderat.

## T4. Segmentering og herding av verktøykjeden

Adresserer R6 og R8, og bidrar til R2.

Nettverket segmenteres mellom kundemiljøene, og mellom kundenett og administrasjonsnett. Alt privilegert arbeid flyttes til dedikerte, herdede administrasjonsarbeidsstasjoner. Tilganger aktiveres just-in-time gjennom Entra Privileged Identity Management. Fjernstyringsverktøyene får en sikkerhetsvurdering og et fast oppdateringsregime.

Dette er tiltaket som treffer selve kjerneproblemet ved å være driftsleverandør: ett innbrudd skal ikke kunne bli alle kunders innbrudd. Segmenteringen er også en forutsetning for at inndemmingssteget i hendelsesresponsplanen i det hele tatt kan gjøres per kunde i stedet for å ta ned alt.

Kontroller: ISO 27001 A.8.22, A.8.2 og A.8.19. NSM Grunnprinsipper 2.2, 2.4 og 2.5.
Eier: driftsansvarlig. Frist: 6 måneder.

Restrisiko for R6 går fra 15 til 8. Her faller begge faktorene: herding senker sannsynligheten, og segmentering begrenser spredningen og dermed konsekvensen. Restrisiko for R8 går fra 10 til 5, forutsatt at T10 også gjennomføres. Sannsynligheten faller fra 2 til 1, mens konsekvensen ikke kan reduseres videre, siden et kompromittert fjernstyringsverktøy per definisjon har privilegier overalt.

## T5. Sikring av API-integrasjonen

Adresserer R3.

Integrasjonen mellom Salesforce og Jira får gjensidig TLS-autentisering og OAuth 2.0 med kortlivede tokens. Hemmeligheter flyttes til Azure Key Vault med automatisk rotasjon, og all integrasjonstrafikk logges til sentral lagring.

Integrasjonen er det eneste punktet der persondata går fra ett system til et annet uten at et menneske er involvert. Det gjør den både verdifull for en angriper og lett å glemme i drift, siden den fungerer uten at noen ser på den.

Kontroller: ISO 27001 A.8.21, A.8.24 og A.8.16. NSM Grunnprinsipper 2.5 og 2.7.
Eier: utviklingsansvarlig. Frist: 3 måneder.

Restrisiko for R3 går fra 12 til 4. Sannsynligheten faller fra 3 til 1, siden gjensidig autentisering og sertifikatvalidering fjerner angrepsformen. Konsekvensen ved et vellykket angrep er den samme som før.

## T6. Rollebasert tilgangsstyring og tilgangsrevisjon

Adresserer R5, og bidrar til R1.

Tilganger i Salesforce og Azure settes opp etter minste privilegium, med rollemaler per stilling. Hvert kvartal bekrefter ledere tilgangene til sine egne ansatte, og leveranseansvarlige bekrefter kundetilgangene. Tilganger deaktiveres automatisk ved fratredelse. Detaljene står i [policyen for tilgangsstyring](../04-isms/policy-tilgangsstyring.md).

Innsiderisiko håndteres ikke med mistillit til ansatte, men med at ingen har mer tilgang enn oppgavene krever. Bieffekten er minst like viktig: en kompromittert konto kan bare gjøre det kontoen faktisk har rett til.

Kontroller: ISO 27001 A.5.15, A.5.16, A.5.18 og A.8.2. NSM Grunnprinsipper 2.6.
Eier: sikkerhetsansvarlig. Frist: 4 måneder.

Restrisiko for R5 går fra 8 til 4. Sannsynligheten faller fra 2 til 1, mens konsekvensen av at noen misbruker en legitim tilgang står uendret. Det er nettopp derfor tilgangsrevisjon hjelper her, og ikke kryptering.

## T7. Baseline-konfigurasjon og teknisk revisjon av Azure

Adresserer R10, og bidrar til R6.

Det defineres en sikker baseline basert på CIS Benchmark for Azure, som blir utgangspunktet for alle nye kundemiljøer. Avvik overvåkes løpende med Microsoft Defender for Cloud og gjennomgås månedlig. I tillegg gjennomføres ekstern penetrasjonstest to ganger i året.

R10 er en menneskelig feil, ikke et angrep. Feilkonfigurasjoner forsvinner ikke av opplæring alene. De forsvinner når riktig konfigurasjon er standardvalget og avvik fanges opp automatisk.

Kontroller: ISO 27001 A.8.9, A.8.8, A.8.16 og A.5.23. NSM Grunnprinsipper 2.3, 3.1, 3.2 og 3.4.
Eier: driftsansvarlig. Frist: 3 måneder.

Restrisiko for R10 går fra 12 til 6. Både sannsynlighet og konsekvens faller, fra 3 til 2 og fra 4 til 3. Baselinen gjør feil mindre sannsynlige, og automatisk deteksjon korter ned tiden feilen står åpen.

## T8. Hendelsesrespons og bruddrutiner

Adresserer R9 direkte, og reduserer konsekvensen for alle de andre risikoene.

[Hendelsesresponsplanen](../04-isms/hendelsesresponsplan.md) definerer alvorlighetsgrader, eskaleringsvei, vurdering etter GDPR artikkel 33 innen 72 timer, varslingsmaler for kunder og Datatilsynet, og en årlig øvelse med ledelsen.

Dette er det billigste tiltaket i planen, og det eneste som virker på alle de andre risikoene samtidig. Det hindrer ikke hendelser, men det begrenser hva de koster. I tillegg lukker det R9, som er et rent prosessavvik uten angriper involvert.

Kontroller: ISO 27001 A.5.24 til A.5.28, og A.5.31. GDPR artikkel 33 og 34. NSM Grunnprinsipper 4.1 til 4.4.
Eier: sikkerhetsansvarlig. Frist: 2 måneder.

Restrisiko for R9 går fra 9 til 3. Sannsynligheten faller fra 3 til 1. Konsekvensen av et faktisk fristbrudd er den samme, men tiltaket gjør det usannsynlig at fristen brytes.

## T9. Full diskkryptering og endepunktkontroll

Adresserer R7.

BitLocker håndheves på alle bærbare enheter gjennom samsvarspolicy i Intune. Enheter uten kryptering nektes tilgang til Mjøsdatas ressurser gjennom betinget tilgang. Fjernsletting aktiveres, og skjermen låses automatisk etter fem minutter.

R7 ligger under behandlingsterskelen, men tiltaket koster i praksis bare konfigurasjonstid siden funksjonaliteten allerede er lisensiert. Å la en kjent sårbarhet som kan lukkes gratis stå åpen fordi den formelt er akseptabel er dårlig risikostyring. Tiltaket er dessuten forutsetningen for at et tapt utstyr ikke skal være et meldepliktig personvernbrudd, noe som er nærmere forklart under alvorlighetsgradene i hendelsesresponsplanen.

Kontroller: ISO 27001 A.8.1, A.7.9 og A.8.24. NSM Grunnprinsipper 2.7.
Eier: driftsansvarlig. Frist: 2 måneder.

Restrisiko for R7 går fra 6 til 2. Konsekvensen faller fra 3 til 1. Sannsynligheten for at en enhet blir mistet er den samme som før, men kryptering gjør at tapet ikke lenger er et databrudd.

## T10. Leverandør- og verktøykjedestyring

Adresserer R8.

Det opprettes et leverandørregister der leverandørene klassifiseres etter hvor kritiske de er. Sikkerhetskrav blir standard i alle nye avtaler. Kritiske leverandører risikovurderes årlig, med særlig vekt på fjernstyringsverktøy og andre verktøy som har stående privilegert tilgang. Det defineres også en prosess for å følge opp sikkerhetsvarsler og endringer fra leverandørene.

R8 er den eneste risikoen i registeret der Mjøsdata ikke selv kontrollerer sårbarheten. Segmentering begrenser skaden, men bare leverandørstyring reduserer sannsynligheten. Tiltaket lukker samtidig det største gapet mot NIS2s krav om leverandørkjedesikkerhet.

Kontroller: ISO 27001 A.5.19 til A.5.23. GDPR artikkel 28. NSM Grunnprinsipper 2.1.
Eier: sikkerhetsansvarlig. Frist: 6 måneder.

Restrisiko for R8 går fra 10 til 5, sammen med T4. Sannsynligheten faller fra 2 til 1 gjennom leverandørvurdering og oppdateringsregime. Konsekvensen kan ikke reduseres videre uten å fjerne hele verktøyklassen.

## Restrisiko og aksept

| Risiko | Før | Etter | Klassifisering | Beslutning |
|---|---|---|---|---|
| R1 | 16 | 4 | Lav | Aksepteres administrativt |
| R2 | 20 | 8 | Moderat | Krever formell aksept |
| R3 | 12 | 4 | Lav | Aksepteres administrativt |
| R4 | 15 | 5 | Moderat | Krever formell aksept |
| R5 | 8 | 4 | Lav | Aksepteres administrativt |
| R6 | 15 | 8 | Moderat | Krever formell aksept |
| R7 | 6 | 2 | Lav | Aksepteres administrativt |
| R8 | 10 | 5 | Moderat | Krever formell aksept |
| R9 | 9 | 3 | Lav | Aksepteres administrativt |
| R10 | 12 | 6 | Moderat | Krever formell aksept |

Alle restrisikoene ligger på moderat eller lavere, slik metodikken krever. De fem som ligger på moderat, altså R2, R4, R6, R8 og R10, legges fram for daglig leder for dokumentert aksept etter innstilling fra sikkerhetsansvarlig.

Matrisen etter tiltak ser slik ut:

| | K1 | K2 | K3 | K4 | K5 |
|---|---|---|---|---|---|
| S5 | | | | | |
| S4 | | | | | |
| S3 | | | | | |
| S2 | R7 | | R10 | R2, R6 | |
| S1 | | | R9 | R1, R3, R5 | R4, R8 |

Alle risikoene har flyttet seg nedover og til venstre. De som fortsatt ligger på konsekvens 4 og 5 er de der konsekvensen følger av forretningsmodellen og ikke lar seg fjerne med tiltak, bare med en annen måte å drive på.

## Prioritering og kostnad

| Prioritet | Tiltak | Kostnad | Risikoreduksjon | Hvorfor den ligger her |
|---|---|---|---|---|
| 1 | T1 MFA | Lav, lisenser finnes | Svært høy | Fjerner 16 og 10 risikopoeng på én måned |
| 2 | T8 Hendelsesrespons | Lav, i hovedsak arbeidstid | Høy, konsekvensreduserende | Virker på alle risikoene samtidig |
| 3 | T9 Diskkryptering | Lav, konfigurasjonstid | Moderat | Ren opprydding, ingen grunn til å vente |
| 4 | T2 Opplæring | Lav til moderat | Høy | Nødvendig for at T1 skal få full effekt |
| 5 | T5 API-sikring | Moderat | Høy | Avgrenset teknisk arbeid med tydelig effekt |
| 6 | T7 Baseline og revisjon | Moderat | Moderat | Hindrer at samme type feil gjentar seg |
| 7 | T3 Redundans og backup | Høy | Høy | Direkte knyttet til SLA-økonomien, men en reell driftskostnad |
| 8 | T6 Rollestyring | Moderat | Moderat | Krever organisatorisk arbeid, ikke bare teknikk |
| 9 | T10 Leverandørstyring | Lav til moderat | Moderat til høy | Prosessarbeid, og en forutsetning for NIS2-beredskap |
| 10 | T4 Segmentering | Høy | Høy, og strukturell | Dyrest per risikopoeng, men viktigst på sikt |

Om T4 er det verdt å si litt mer. Rangeringen over måler risikoreduksjon per krone, og på det målet kommer T4 sist. Men det er samtidig det eneste tiltaket som endrer den strukturelle risikoprofilen til en driftsleverandør, og full effekt tar seks måneder. Derfor startes arbeidet parallelt fra dag én. En prioriteringsliste som bare følger kroner per risikopoeng vil systematisk skyve slike tiltak foran seg til de blir akutte.

## Styring og oppfølging

Det opprettes en sikkerhets- og personvernkomité ledet av sikkerhetsansvarlig, med driftsansvarlig og personvernkontakt som faste medlemmer. Komiteen rapporterer kvartalsvis til daglig leder og årlig til styret.

Hvert kvartal går komiteen gjennom status per tiltak, avvik fra frist, nye risikoer som har kommet ut av hendelser, og måltallene fra opplæringsprogrammet. Årlig gjøres full revisjon av risikoregisteret, oppdatering av Statement of Applicability, ledelsens gjennomgang og ny aksept av restrisiko.

Planen revideres ellers ved vesentlige endringer i systemlandskapet, kundeporteføljen eller trusselbildet, og etter enhver hendelse klassifisert som kritisk eller alvorlig.

Dersom NIS2 blir gjennomført og Mjøsdata omfattes, vil ledelsen få et personlig ansvar for å godkjenne og følge opp risikostyringen. Styringsmodellen over er laget for å tåle det kravet allerede nå.
