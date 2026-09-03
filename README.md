# GRC-portefølje for en norsk IT-driftsleverandør

Dette er et selvstendig prosjekt der jeg har laget den dokumentasjonen en GRC-konsulent typisk leverer til en kunde. Kunden heter Mjøsdata AS og er en oppdiktet IT-driftsleverandør i Hamar med 45 ansatte. Tall, systemer og funn er konstruert, men oppgavene er de samme som i en virkelig leveranse.

Grunnen til at jeg valgte akkurat en driftsleverandør er at risikobildet deres er litt annerledes enn hos vanlige virksomheter. En leverandør som drifter IT for mange kunder har tilgang til alle systemene deres samtidig. Blir leverandøren kompromittert, er kundene det også. Det får konsekvenser både for hvordan risiko vurderes og for hvilke tiltak det er verdt å bruke penger på, og det er den tråden jeg har fulgt gjennom hele porteføljen.

Dokumentene er skrevet på norsk fordi det er arbeidsspråket i markedet dette retter seg mot.

## Den røde tråden

Alt i porteføljen følger én kjede. Hvert ledd er et dokument, og hvert dokument peker tilbake på det forrige:

Virksomhetskontekst (01) gir grunnlaget for risikovurderingen (02), som gir tiltaksplanen (02), som avgjør hvilke kontroller som havner i Statement of Applicability (04), som igjen operasjonaliseres i policyene og programmene (04 og 05). GDPR-analysen (03) og NIS2-vurderingen (06) henger på den samme kjeden fra hver sin side, og sporbarhetsmatrisen samler det hele.

Det som former hele porteføljen er én innsikt: en driftsleverandør bærer kundenes risiko samtidig. Ett innbrudd hos Mjøsdata er et innbrudd hos alle kundene på én gang. Det er derfor konsekvensnivåene ligger strukturelt høyere enn de ville gjort for en frittstående virksomhet med 45 ansatte, derfor nettverkssegmentering får penger selv om det er det dyreste tiltaket på listen, derfor hendelsesresponsplanen har dobbelt varslingsansvar, og derfor NIS2-beredskap behandles som et salgsargument i stedet for bare en kostnad.

## Innhold

| Mappe | Dokument | Hva det inneholder |
|---|---|---|
| 01 | [Virksomhetskontekst](01-virksomhetskontekst/virksomhetskontekst.md) | Hvem Mjøsdata er, hvilke systemer som bærer kjerneprosessen, hvilke krav kundene og myndighetene stiller, og hva analysen avgrenses til |
| 02 | [Metodikk](02-risikovurdering/metodikk.md) | Skalaer, akseptkriterier og fremgangsmåte, vedtatt før analysen ble gjort |
| 02 | [Risikoregister](02-risikovurdering/risikoregister.md) | Ti vurderte risikoer med begrunnelse og risikomatrise |
| 02 | [Tiltaksplan](02-risikovurdering/tiltaksplan.md) | Ti tiltak med eier, frist, kostnadsvurdering og beregnet restrisiko |
| 03 | [GDPR-analyse](03-gdpr/gdpr-analyse.md) | Rolleavklaring, artikkelgjennomgang, behandlingsprotokoll, DPIA-screening og vurdering av personvernombud |
| 04 | [Statement of Applicability](04-isms/statement-of-applicability.md) | De 36 kontrollene fra ISO 27001 Annex A som tiltaksplanen bygger på, med status og begrunnelse |
| 04 | [Policy for tilgangsstyring](04-isms/policy-tilgangsstyring.md) | Krav til autentisering, privilegert tilgang og livssyklus for tilganger |
| 04 | [Hendelsesresponsplan](04-isms/hendelsesresponsplan.md) | Alvorlighetsgrader, roller, faser, varslingsfrister og scenariokort |
| 05 | [Opplæringsprogram](05-sikkerhetskultur/opplaeringsprogram.md) | Målgrupper, innhold, kanaler og målbare KPI-er for sikkerhetskultur |
| 06 | [NIS2-vurdering](06-nis2/nis2-vurdering.md) | Om Mjøsdata omfattes, hva som eventuelt kreves, og gap mot dagens dokumentasjon |
| | [Sporbarhetsmatrise](sporbarhetsmatrise.md) | Sammenhengen fra risiko til tiltak til kontroll, samlet i én oversikt |

## Standarder og rammeverk

| Område | Rammeverk | Hvorfor jeg valgte det |
|---|---|---|
| Risikometodikk | ISO/IEC 27005:2022 | Risikostandarden som hører sammen med 27001. Den lar virksomheten definere sine egne skalaer, og det er poenget her: kriteriene settes før analysen, slik at vurderingene kan etterprøves |
| Sikkerhetsstyring | ISO/IEC 27001:2022 | Gir strukturen for styringssystemet og kontrollene i Annex A. Det er også standarden kommuner og helsekunder spør etter i anskaffelser |
| Personvern | GDPR og personopplysningsloven, med veiledere fra Datatilsynet | En driftsleverandør er behandlingsansvarlig og databehandler samtidig. Den dobbeltrollen er det mest interessante i hele personvernanalysen |
| Norsk basisnivå | NSM Grunnprinsipper for IKT-sikkerhet 2.1 | Det norske offentlige kunder faktisk forholder seg til. Tiltakene er mappet mot både ISO og NSM |
| Kommende regelverk | NIS2-direktivet | NIS2 nevner driftsleverandører som egen kategori. Se merknaden under om hva som gjelder i Norge i dag |
| Sikkerhetskultur | ENISA og SANS Security Awareness Maturity Model | Programmet måles mot modenhetsnivåer i stedet for å telle gjennomførte kurs |

## Om regelverket

Den norske digitalsikkerhetsloven som gjelder i dag gjennomfører NIS1. Den retter seg mot tilbydere av samfunnsviktige tjenester og noen digitale tjenestetilbydere, og en driftsleverandør som Mjøsdata er etter alt å dømme ikke omfattet. NIS2 er foreløpig ikke tatt inn i EØS-avtalen eller gjennomført i norsk rett.

Alt jeg skriver om NIS2 i denne porteføljen er derfor forberedelse, ikke gjeldende plikter. Jeg har merket det tydelig der det er relevant, fordi forskjellen betyr mye for en virksomhet som skal prioritere budsjett. [Kapittel 06](06-nis2/nis2-vurdering.md) går gjennom vurderingen i sin helhet.

## Videre arbeid

Det som står igjen, og som jeg har notert underveis:

* Utvide Statement of Applicability til alle 93 kontroller, med kontrolleier og dato for siste verifisering
* Skrive prosedyre for ledelsens gjennomgang og et program for internrevisjon, som er de to kravene i ISO 27001 kapittel 9 jeg ikke har dekket
* Lage en kontinuitetsplan med gjenopprettingstider per kundekategori
* Lage en vurderingsmal for Mjøsdatas egne underleverandører
* Bygge et lite kommandolinjeverktøy for gap-analyse mot NSM Grunnprinsipper

## Forfatter

Jafar Hajsaleh. Masterstudent i informasjonssikkerhet ved NTNU Gjøvik, med bachelor i cybersikkerhet fra Høyskolen Kristiania. Prosjektet bygger videre på emnearbeid og er utvidet til en selvstendig arbeidsprøve.

## Lisens

Dokumentasjonen er utgitt under [CC BY 4.0](LICENSE). Bruk og bygg videre på den gjerne, men oppgi kilde.
