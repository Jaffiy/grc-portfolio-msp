# Statement of Applicability, utdrag

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Revisjon | Årlig, og ved endringer i risikobildet |
| Hjemmel | ISO/IEC 27001:2022 punkt 6.1.3 bokstav d |

En fullstendig Statement of Applicability dekker alle 93 kontrollene i Annex A. Dette utdraget viser de 36 kontrollene som er direkte begrunnet i risikovurderingen og tiltaksplanen, satt opp slik en revisor forventer å se det: kontroll, om den anvendes, begrunnelse med henvisning til risiko, hvilket tiltak som gjennomfører den, og status.

Ekskluderinger begrunnes alltid. En SoA uten begrunnede nei-svar er et faresignal for en revisor, fordi det tyder på at anvendeligheten aldri er vurdert, bare krysset av.

Statusverdiene som brukes er implementert, delvis implementert, planlagt med frist, ikke påbegynt, og ikke anvendelig.

## Organisatoriske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risiko | Tiltak | Status |
|---|---|---|---|---|---|
| A.5.7 | Trusseletterretning | Ja | Driftsleverandører er prioriterte mål i trusselbildet. Varsler fra NSM og NorCERT er en forutsetning for å oppdage kampanjer rettet mot bransjen | | Ikke påbegynt |
| A.5.15 | Tilgangsstyring | Ja | R1 og R5. Minste privilegium på tvers av kundemiljøer | T6 | Delvis |
| A.5.16 | Identitetshåndtering | Ja | R1 og R5. Individuelle identiteter, forbud mot delte kontoer, navngitt eier for systemkontoer | T6 | Delvis |
| A.5.17 | Autentiseringsinformasjon | Ja | R1. Passordpolicy og håndhevet MFA | T1 | Planlagt, 1 mnd |
| A.5.18 | Tilgangsrettigheter | Ja | R5. Tildeling, endring og fjerning av rettigheter, med kvartalsvis revisjon | T6 | Planlagt, 4 mnd |
| A.5.19 | Informasjonssikkerhet i leverandørforhold | Ja | R8. Leverandørregister med klassifisering mangler i dag | T10 | Ikke påbegynt |
| A.5.20 | Sikkerhet i leverandøravtaler | Ja | R8. Sikkerhetskrav som standard i avtaler, og databehandleravtaler etter GDPR artikkel 28 | T10 | Delvis |
| A.5.21 | Sikkerhet i IKT-leverandørkjeden | Ja | R8. Fjernstyringsverktøy med stående privilegert tilgang til alle kunder er den største enkeltavhengigheten selskapet har | T10 | Ikke påbegynt |
| A.5.22 | Overvåking og endringshåndtering av leverandørtjenester | Ja | R8. Årlig vurdering av kritiske leverandører, og oppfølging av sikkerhetsvarsler | T10 | Ikke påbegynt |
| A.5.23 | Sikkerhet ved bruk av skytjenester | Ja | R4 og R10. Hele leveransemodellen er skybasert. Gjelder regionvalg, baseline og exit-strategi | T7 og T10 | Delvis |
| A.5.24 | Planlegging og forberedelse av hendelseshåndtering | Ja | R9. Roller, eskaleringsvei og beredskap definert på forhånd | T8 | Planlagt, 2 mnd |
| A.5.25 | Vurdering av og beslutning om hendelser | Ja | R9. Klassifiseringen fra kritisk til lav avgjør både respons og varslingsplikt | T8 | Planlagt, 2 mnd |
| A.5.26 | Respons på hendelser | Ja | R2, R6 og R9. Inndemming, utrydding og gjenoppretting etter fast prosedyre | T8 | Planlagt, 2 mnd |
| A.5.27 | Læring fra hendelser | Ja | R9. Rapport innen ti virkedager, og funn tilbake i risikoregisteret | T8 | Planlagt, 2 mnd |
| A.5.28 | Innsamling av bevis | Ja | Bevissikring i kundemiljøer er kontraktskrav, og en forutsetning for anmeldelse og forsikringsdekning | T8 | Ikke påbegynt |
| A.5.29 | Informasjonssikkerhet ved avbrudd | Ja | R4. Sikkerhetsnivået skal holdes oppe også under gjenoppretting | T3 | Delvis |
| A.5.30 | IKT-beredskap for driftskontinuitet | Ja | R4 og R6. Gjenopprettingstider per kundekategori mangler. Også et gap mot NIS2 | T3 | Ikke påbegynt |
| A.5.31 | Juridiske og regulatoriske krav | Ja | GDPR, personopplysningsloven, SLA-forpliktelser og kommende NIS2-krav | T8 | Delvis |
| A.5.34 | Personvern og beskyttelse av personopplysninger | Ja | Hele kapittel 03, og særlig dobbeltrollen som behandlingsansvarlig og databehandler | | Delvis |

## Personellkontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risiko | Tiltak | Status |
|---|---|---|---|---|---|
| A.6.3 | Bevisstgjøring og opplæring | Ja | R2. Support er den mest eksponerte gruppen | T2 | Planlagt, 2 mnd |
| A.6.7 | Fjernarbeid | Ja | Hybrid arbeidsmodell, med sikkerhetskrav for arbeid utenfor kontoret | T9 | Delvis |

## Fysiske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risiko | Tiltak | Status |
|---|---|---|---|---|---|
| A.7.9 | Sikkerhet for utstyr utenfor lokaler | Ja | R7. Bærbare enheter brukes hjemme, hos kunder og på reise | T9 | Planlagt, 2 mnd |
| A.7.13 | Vedlikehold av utstyr | Nei | Mjøsdata har ingen egen serverinfrastruktur. All produksjon kjører i Azure, der leverandøren har ansvaret for maskinvaren. Kontorutstyr dekkes av A.8.1 | | Ikke anvendelig |

## Teknologiske kontroller

| Kontroll | Navn | Anvendes | Begrunnelse og risiko | Tiltak | Status |
|---|---|---|---|---|---|
| A.8.1 | Brukerendepunktutstyr | Ja | R7. Håndhevet diskkryptering og samsvarskrav før enheten får tilgang | T9 | Planlagt, 2 mnd |
| A.8.2 | Privilegerte tilgangsrettigheter | Ja | R6 og R8. Tilgang aktiveres ved behov, og privilegert arbeid gjøres fra herdede maskiner | T4 | Planlagt, 6 mnd |
| A.8.5 | Sikker autentisering | Ja | R1 og R2. Phishing-resistent MFA for administratorer og support | T1 | Planlagt, 1 mnd |
| A.8.8 | Håndtering av tekniske sårbarheter | Ja | R6 og R10. Patcherutine og penetrasjonstest hvert halvår | T7 | Delvis |
| A.8.9 | Konfigurasjonsstyring | Ja | R10. CIS Benchmark som baseline for alle nye kundemiljøer | T7 | Planlagt, 3 mnd |
| A.8.13 | Sikkerhetskopiering | Ja | R4 og R6. Uforanderlig og geo-redundant backup, med testet gjenoppretting | T3 | Delvis |
| A.8.14 | Redundans | Ja | R4. Failover for kritiske kundemiljøer, knyttet til SLA-forpliktelsene | T3 | Planlagt, 3 mnd |
| A.8.16 | Overvåkingsaktiviteter | Ja | R6 og R10. Defender for Cloud, sentralisert logging og logging av integrasjonstrafikk | T5 og T7 | Delvis |
| A.8.19 | Installasjon av programvare på driftssystemer | Ja | R8. Kontroll på hvilke fjernstyringsverktøy som kjører med privilegert tilgang | T4 | Delvis |
| A.8.21 | Sikkerhet i nettverkstjenester | Ja | R3. Gjensidig TLS og OAuth 2.0 på integrasjonen | T5 | Planlagt, 3 mnd |
| A.8.22 | Segregering av nettverk | Ja | R6 og R8. Skille mellom kundemiljøer, og mellom kundenett og administrasjonsnett | T4 | Ikke påbegynt |
| A.8.24 | Bruk av kryptografi | Ja | R3, R7 og R10. TLS i transitt, diskkryptering på endepunkt, lagringskryptering i Azure. Egen kryptopolicy mangler | T5 og T9 | Delvis |
| A.8.30 | Utkontraktert utvikling | Nei | Mjøsdata utvikler ikke egne systemer og setter ingen systemutvikling ut. Integrasjonen er konfigurasjon av standardprodukter, ikke utvikling. Kontrollen vurderes på nytt dersom egenutvikling startes | | Ikke anvendelig |

## Status samlet

| Status | Antall |
|---|---|
| Implementert | 0 |
| Delvis implementert | 13 |
| Planlagt med frist | 14 |
| Ikke påbegynt | 7 |
| Ikke anvendelig | 2 |
| Sum | 36 |

At ingen kontroll står som fullt implementert er en ærlig beskrivelse av utgangspunktet, ikke en svakhet ved dokumentet. En SoA som er grønn over hele linjen ved første gjennomgang er som regel enten uriktig, eller et tegn på at ambisjonsnivået er satt etter dagens praksis i stedet for etter risikoen.

## Neste iterasjon

Tre ting står igjen. SoA bør utvides til alle 93 kontroller med begrunnelse for hver ekskludering. Tabellen bør få kolonner for kontrolleier og dato for siste verifisering, som trengs for internrevisjon etter ISO 27001 punkt 9.2. Og det bør skrives en prosedyre for ledelsens gjennomgang etter punkt 9.3, der SoA er et fast punkt på agendaen.
