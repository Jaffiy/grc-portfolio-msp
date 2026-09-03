# Hendelsesresponsplan

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Øvelse | Minimum årlig, som skrivebordsøvelse |
| Hjemmel | ISO 27001 A.5.24 til A.5.28. GDPR artikkel 33 og 34. SLA-forpliktelser. NSM Grunnprinsipper 4.1 til 4.4 |
| Adresserer | R9 direkte, og reduserer konsekvensen for alle øvrige risikoer, gjennom tiltak T8 |

En merknad om regelverk før vi går videre. Varslingsplikt etter en fremtidig norsk gjennomføring av NIS2 er tatt inn i varslingsmatrisen som en betinget rad. Mjøsdata er etter alt å dømme ikke pliktsubjekt etter dagens digitalsikkerhetslov, som gjennomfører NIS1. Kapittel 06 går gjennom dette.

## 1. Formål

Planen skal sikre at sikkerhetshendelser blir oppdaget, håndtert og lært av, på en måte som begrenser skaden både for Mjøsdata og for kundene, og som oppfyller varslingspliktene innen frist.

Som driftsleverandør har Mjøsdata et dobbelt ansvar. Selskapet skal håndtere sine egne hendelser, og det skal varsle og bistå berørte kunder. Det siste er ofte det mest tidskritiske, fordi kundenes egne frister begynner å løpe fra Mjøsdata varsler dem.

## 2. Alvorlighetsgrader

| Grad | Kriterium | Eksempel | Responstid |
|---|---|---|---|
| Kritisk | Aktiv kompromittering som berører kunder, eller løsepengevirus i et hvilket som helst miljø | Angriper inne i et kundemiljø via Mjøsdatas fjernstyringsverktøy | Umiddelbart, hele døgnet |
| Alvorlig | Bekreftet brudd uten at kundepåvirkning foreløpig er påvist | Kompromittert intern konto med supportrettigheter | Under 1 time i arbeidstiden, under 4 timer ellers |
| Moderat | Mistenkelig aktivitet av begrenset omfang, eller ethvert mulig personvernbrudd | Vellykket phishing-klikk uten bekreftet fotfeste. Tap av enhet med kundedata | Under 8 timer |
| Lav | Policyavvik uten datainvolvering og uten aktiv trussel | Ulåst skjerm observert på kontoret. Kryptert enhet mistet, verifisert uten lokale kundedata | Under 3 virkedager |

Tap av utstyr fortjener en egen presisering. En enhet som kan inneholde kundedata klassifiseres alltid som minst moderat, og utløser obligatorisk vurdering etter GDPR artikkel 33, også når enheten er fjernslettet. Fjernsletting virker bare dersom enheten kommer på nett igjen, og er derfor ikke i seg selv dokumentasjon på at data ikke er eksponert. Først når full diskkryptering er verifisert utrullet gjennom tiltak T9 kan et enhetstap håndteres som lav. Da er tapet et utstyrstap og ikke et databrudd. Det er den praktiske grunnen til at T9 prioriteres høyt selv om R7 har lavt risikonivå.

## 3. Organisering

| Rolle | Hvem | Ansvar |
|---|---|---|
| Hendelsesleder | Sikkerhetsansvarlig, med driftsansvarlig som stedfortreder | Klassifisering, koordinering og beslutning om eskalering |
| Teknisk respons | Driftsteamet, eventuelt med ekstern partner på rammeavtale | Inndemming, utrydding, gjenoppretting og bevissikring |
| Personvernvurdering | Personvernkontakt | Vurdering etter artikkel 33 og 34, og utkast til melding |
| Kommunikasjon | Daglig leder | Eier all ekstern kommunikasjon, mot kunder, Datatilsynet og media |

Kontaktlisten med døgnnumre til interne, ekstern partner og kundenes nødkontakter oppbevares utenfor produksjonsmiljøet, i en kopi som også finnes offline. En beredskapsplan som bare ligger i systemet den skal redde, er ingen beredskapsplan.

## 4. Fasene

Fasene følger livssyklusen i NIST SP 800-61. Jeg har valgt en etablert modell framfor en egendefinert fordi den er gjenkjennelig for eksterne responspartnere og forsikringsselskaper.

### Forberedelse

Logging er sentralisert og beskyttet mot sletting. Backup er uforanderlig gjennom tiltak T3. Det gjennomføres skrivebordsøvelse med ledelsen hvert år. Rammeavtale med ekstern responspartner inngås før den trengs, ikke i det den trengs. Planen er kjent for alle ansatte gjennom opplæringsprogrammet.

### Deteksjon og analyse

Hendelser kommer inn fra Microsoft Defender for Cloud, fra endepunktsikring, fra ansatte som rapporterer phishing, fra kunder og fra leverandørvarsler.

Hendelseslederen klassifiserer hendelsen og oppretter en hendelseslogg med tidslinje. Alle tidspunkter føres i UTC. Blandede tidssoner i en tidslinje er en av de vanligste kildene til feilkonklusjoner i etterforskning.

Bevissikring starter fra første time. Ved kritiske og alvorlige hendelser vurderes minnedump og diskbilde før opprydding settes i gang. Alle handlinger logges med hvem som gjorde hva, og når. Det er avgjørende dersom saken ender hos politiet eller forsikringsselskapet, og det er umulig å rekonstruere i etterkant.

### Inndemming, utrydding og gjenoppretting

Kortsiktig inndemming betyr å isolere berørte kontoer og nettverkssegmenter. Segmenteringen fra tiltak T4 er forutsetningen for at dette kan gjøres per kunde i stedet for å ta ned alt.

Utrydding betyr å fjerne fotfestet, rotere alle hemmeligheter og privilegerte legitimasjoner, og tette inngangsvektoren.

Gjenoppretting skjer fra en backup som er verifisert ren. Overvåkingen forsterkes i 30 dager etterpå, fordi angripere ofte kommer tilbake når inngangsvektoren ikke er fullt forstått.

### Læring

Rapport skrives innen ti virkedager. Den skal inneholde tidslinje, rotårsak, hva som fungerte og hva som sviktet, og konkrete tiltak som føres inn i risikoregisteret. Gjennomgangen er uten skyldfordeling. Poenget er å finne ut hvorfor hendelsen var mulig, ikke hvem som gjorde noe galt.

## 5. Varslingsmatrise

| Situasjon | Hvem varsles | Frist | Ansvarlig |
|---|---|---|---|
| Personvernbrudd der Mjøsdata er databehandler | Berørt kunde, som er behandlingsansvarlig | Uten ugrunnet opphold, internt mål under 24 timer | Hendelsesleder |
| Personvernbrudd der Mjøsdata er behandlingsansvarlig, med risiko for de registrerte | Datatilsynet | 72 timer fra Mjøsdata ble kjent med bruddet | Personvernkontakt |
| Høy risiko for de registrertes rettigheter | De registrerte | Uten ugrunnet opphold | Daglig leder |
| Driftsavbrudd som berører SLA | Berørte kunder | Etter den enkelte SLA | Leveranseansvarlig |
| Mistanke om straffbart forhold | Politiet, eventuelt forsikringsselskapet | Etter beslutning av daglig leder | Daglig leder |
| Betinget: vesentlig hendelse dersom Mjøsdata blir omfattet av en fremtidig NIS2-gjennomføring | Sektormyndighet eller NSM | Tidlig varsel 24 timer, oppdatering 72 timer, sluttrapport 1 måned | Hendelsesleder |

Hendelsesloggen skal alltid dokumentere vurderingen av om bruddet er meldepliktig, også når konklusjonen er nei. Formuleringen vurdert, ikke meldepliktig, fordi, med dato og signatur, er den dokumentasjonen som beskytter virksomheten i ettertid. En manglende vurdering er et selvstendig avvik, uavhengig av om melding faktisk skulle vært sendt.

## 6. Scenariokort

### Løsepengevirus oppdaget i ett kundemiljø

1. Isoler kundemiljøet på nettverksnivå. Ikke slå av maskiner. Avslåing ødelegger minnebevis som ofte er den eneste kilden til krypteringsnøkler og angriperverktøy.
2. Aktiver responsen for kritiske hendelser. Varsle hendelsesleder og daglig leder.
3. Sjekk om det har spredt seg til administrasjonsnettet eller andre kundemiljøer. Verktøykjeden er den kritiske veien.
4. Sikre bevis. Ta minnedump av berørte servere, og eksporter logger før noe endres.
5. Varsle berørt kunde innen 24 timer. Vurder meldeplikten etter artikkel 33, både for kunden og eventuelt for Mjøsdata.
6. Gjenopprett fra uforanderlig backup etter at den er verifisert ren. Roter all privilegert legitimasjon.
7. Forsterk overvåkingen i 30 dager. Skriv rapport innen ti virkedager.

### Kompromittert supportkonto oppdaget gjennom uvanlig innlogging

1. Deaktiver kontoen og avslutt aktive sesjoner. Å bytte passord alene stopper ikke en pågående sesjon.
2. Klassifiser som alvorlig, eller kritisk dersom kundemiljøer er berørt.
3. Kartlegg hva kontoen faktisk hadde tilgang til, og hva den har gjort ifølge loggene. Det er her tilgangsrevisjonen fra T6 betaler seg. Uten den er svaret alt.
4. Vurder personvernbrudd for hver berørt kunde. Dette er ofte flere separate vurderinger, ikke én felles.
5. Gjenutsted legitimasjon med phishing-resistent MFA før kontoen tas i bruk igjen.
6. Vurder om dette var en kjent phishing-kampanje, og om den bør brukes som case i neste simulering.

### Tap av bærbar enhet

1. Klassifiser som moderat, etter regelen om utstyrstap over.
2. Verifiser krypteringsstatus for akkurat den enheten i Intune. Ikke gå ut fra at policyen var aktiv på den maskinen.
3. Start fjernsletting og deaktiver enhetens tilgangstokener.
4. Vurder meldeplikt basert på hva som faktisk lå lagret lokalt. Ved verifisert full diskkryptering med enheten avslått er konklusjonen normalt at bruddet ikke er meldepliktig, men vurderingen dokumenteres uansett.
5. Meld til politiet ved mistanke om tyveri. Det er også nødvendig for forsikringen.
