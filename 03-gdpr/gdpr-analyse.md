# GDPR-analyse

| | |
|---|---|
| Dokumenteier | Personvernkontakt |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Revisjon | Årlig |
| Hjemmel | Personvernforordningen, personopplysningsloven, veiledere fra Datatilsynet |

## 1. Er Mjøsdata behandlingsansvarlig eller databehandler?

Dette er det viktigste personvernspørsmålet for en driftsleverandør, og også det som oftest blir hoppet over. Rollen følger av hvem som faktisk bestemmer formålet med og midlene for behandlingen, ikke av hva partene har kalt seg i avtalen. Mjøsdata opptrer i begge roller samtidig.

| Behandling | Rolle | Hva det innebærer |
|---|---|---|
| Egne kunderegistre, kontrakter og fakturering i Salesforce | Behandlingsansvarlig | Fullt ansvar for behandlingsgrunnlag, informasjonsplikt, sletting og de registrertes rettigheter |
| Egne ansattdata i HR, lønn og tilgangslogger | Behandlingsansvarlig | Som over, med særlige krav der det dreier seg om kontrolltiltak i arbeidsforhold |
| Sikkerhetslogging og hendelseshåndtering i egne systemer | Behandlingsansvarlig | Grunnlaget er berettiget interesse, og det krever en dokumentert interesseavveining |
| Drift av kundenes systemer og data i Azure | Databehandler | Krever databehandleravtale med hver enkelt kunde, og behandling kun etter dokumentert instruks |
| Bruk av Microsoft, Salesforce og Atlassian | Mjøsdata er kunde, leverandørene er databehandlere | Databehandleravtaler nedover i kjeden, og vurdering av overføring til tredjeland |

### Hvorfor dobbeltrollen er den vanskelige delen

Mjøsdata må holde orden på to avtalekjeder samtidig, nedover mot egne leverandører og oppover mot egne kunder. Det praktisk viktigste utslaget gjelder brudd.

Ved et brudd som rammer kundedata er Mjøsdata databehandler. Da har selskapet ingen 72-timersfrist mot Datatilsynet. Plikten er å varsle kunden, som er behandlingsansvarlig, uten ugrunnet opphold, slik at kunden rekker sin egen frist. I praksis betyr det at Mjøsdatas interne frist må være vesentlig kortere enn 72 timer. Hendelsesresponsplanen setter den til 24 timer.

Denne forskjellen er den vanligste feilen i bransjen. Leverandøren venter på en 72-timersfrist som ikke gjelder for dem, og kunden mister sin.

## 2. Sentrale forpliktelser og status

| Artikkel | Krav | Hva det betyr for Mjøsdata | Tiltak | Status |
|---|---|---|---|---|
| 5 | Prinsippene, blant annet formålsbegrensning, dataminimering og lagringsbegrensning | Kundedata i Salesforce og persondata i supportlogger må minimeres og slettes etter faste frister | Slettepolicy, og automatisk sletting av supportlogger etter tolv måneder der annet ikke kreves | Gap |
| 6 og 9 | Behandlingsgrunnlag og særlige kategorier | Egne behandlinger hjemles i avtale, rettslig forpliktelse og berettiget interesse. Pasientdata behandles bare som databehandler etter instruks, så Mjøsdata trenger ikke eget grunnlag etter artikkel 9 for disse | Grunnlagsvurdering per behandling i protokollen | Delvis |
| 25 | Innebygd og standardinnstilt personvern | Nye kundeoppsett i Azure skal ha kryptering, minimert tilgang og logging som standard, ikke som noe man huker av for | Baseline-konfigurasjon, tiltak T7 | Delvis |
| 28 | Databehandleravtaler | Kreves mot alle kunder Mjøsdata drifter for, og mot Microsoft, Salesforce og Atlassian. Underdatabehandlere skal godkjennes på forhånd | Avtalerevisjon, standardmal, leverandørregister i T10 | Gap |
| 30 | Behandlingsprotokoll | Plikt både som behandlingsansvarlig og databehandler. Unntaket for virksomheter under 250 ansatte gjelder ikke her, siden behandlingen ikke er leilighetsvis og omfatter data etter artikkel 9 | Se utdraget i punkt 3 | Gap |
| 32 | Sikkerhet ved behandling | Kryptering, tilgangsstyring, evne til gjenoppretting og regelmessig testing. Overlapper i stor grad med tiltaksplanen | T1, T3, T5, T6, T7 og T9 | Delvis |
| 33 og 34 | Meldeplikt og varsling av de registrerte | Som databehandler: varsle kunden uten ugrunnet opphold. Som behandlingsansvarlig: melde Datatilsynet innen 72 timer | Hendelsesresponsplanen med bruddvurderingsskjema, tiltak T8 | Gap |
| 35 | Personvernkonsekvensvurdering ved høy risiko | Skydrift av helseklinikkdata utløser DPIA-plikt hos kunden. Mjøsdata skal bistå | Screening i punkt 4 | Delvis |
| 37 | Personvernombud | Her er det reell tvil, se punkt 5 | Anbefaling om frivillig utpeking | Gap |
| 44 og utover | Overføring til tredjeland | Amerikanske skyleverandører, se punkt 6 | EU-regioner i Azure og dokumentert overføringsvurdering | Delvis |

## 3. Behandlingsprotokoll, utdrag

### Som behandlingsansvarlig

| Behandling | Formål | Registrerte og opplysninger | Grunnlag | Lagringstid | Mottakere |
|---|---|---|---|---|---|
| Kundeadministrasjon i Salesforce | Avtaleoppfølging og support | Kontaktpersoner hos kunder, med navn, e-post, telefon og sakshistorikk | Artikkel 6 nr. 1 bokstav b, avtale | Avtaletid pluss tre år | Salesforce som databehandler |
| Fakturering og regnskap | Oppfylle bokføringsplikten | Kontaktpersoner og fakturadata | Artikkel 6 nr. 1 bokstav c, bokføringsloven | Fem år etter regnskapsårets slutt | Regnskapsfører som databehandler |
| Personaladministrasjon | Gjennomføring av arbeidsforholdet | Ansatte, med personalia, stilling, lønn og fravær | Artikkel 6 nr. 1 bokstav b og c, arbeidsmiljøloven og folketrygdloven | Arbeidsforhold pluss fem år | Lønnsleverandør og NAV |
| Sikkerhetslogging og hendelseshåndtering | Ivareta informasjonssikkerhet, oppdage og håndtere hendelser | Ansatte og eksterne brukere, med bruker-ID, IP-adresse, tidsstempel og handling | Artikkel 6 nr. 1 bokstav f, berettiget interesse | Tolv måneder, lenger bare ved pågående sak | Ingen eksterne, eventuelt politiet ved anmeldelse |

Om den siste raden: sikkerhetslogging er uttrykkelig anerkjent som en berettiget interesse i fortalen til forordningen. Interesseavveiningen er likevel dokumentert særskilt, siden logging av ansattes aktivitet også er et kontrolltiltak etter arbeidsmiljøloven og skal drøftes med de tillitsvalgte.

### Som databehandler

| Kundekategori | Behandling utført på kundens vegne | Kategorier opplysninger | Underdatabehandlere | Overføring til tredjeland |
|---|---|---|---|---|
| Helseklinikker | Drift, backup og support av journal- og kontorsystemer | Pasientdata, herunder helseopplysninger, bare etter dokumentert instruks | Microsoft, i Azure-region i EU eller EØS | Ikke ved normal drift, se punkt 6 om support |
| Kommuner | Drift av administrative systemer | Ansatt- og innbyggerdata | Microsoft, i Azure-region i EU eller EØS | Ikke ved normal drift |
| Advokat- og regnskapskontorer | Drift og backup av saks- og klientsystemer | Klientdata underlagt taushetsplikt | Microsoft, i Azure-region i EU eller EØS | Ikke ved normal drift |

Protokollen skal etter artikkel 30 nr. 2 også inneholde kontaktopplysninger for hver behandlingsansvarlig og en generell beskrivelse av sikkerhetstiltakene. Disse feltene ligger i den fullstendige protokollen. Utdraget her viser strukturen.

## 4. DPIA-screening for skydrift av helseklinikkdata

Vurdert mot artikkel 35 nr. 3 og Datatilsynets liste over behandlinger som alltid krever konsekvensvurdering.

| Kriterium | Vurdering | Utslagsgivende |
|---|---|---|
| Særlige kategorier i stor skala | Ja, pasientdata for flere klinikker samlet på én plattform | Ja |
| Systematisk overvåking av offentlig tilgjengelig område | Nei | |
| Ny teknologi | Nei, etablert skyplattform | |
| Sårbare registrerte | Ja, pasienter står i et avhengighetsforhold og kan ikke velge bort behandlingen | Ja |
| Sammenstilling av datasett | Nei, kundemiljøene holdes adskilt | |
| Automatiserte avgjørelser med rettsvirkning | Nei | |

To utslagsgivende kriterier er oppfylt. DPIA-plikten utløses hos den behandlingsansvarlige, altså klinikken, og ikke hos Mjøsdata. Mjøsdata skal som databehandler bistå etter artikkel 28 nr. 3 bokstav f.

I praksis er dette løst ved at Mjøsdata har laget et standardisert underlagsdokument som beskriver sikkerhetstiltak, hvor dataene ligger, tilgangsstyring, underdatabehandlere og slettefrister. Dokumentet gjenbrukes på tvers av helsekundene. Det sparer tid, og det er samtidig et salgsargument. En klinikk som skal gjennomføre en DPIA får halve jobben gjort av leverandøren.

## 5. Personvernombud

Den enkle konklusjonen ville vært at Mjøsdata ikke har plikt til å utpeke personvernombud. Virksomheten er privat, den utøver ikke offentlig myndighet, og kjernevirksomheten er IT-drift og ikke behandling av helseopplysninger. Jeg mener den konklusjonen er for rask.

Argumentet for at plikten gjelder ligger i artikkel 37 nr. 1 bokstav c. Bestemmelsen gjelder uttrykkelig både behandlingsansvarlige og databehandlere der kjernevirksomheten består i behandling av særlige kategorier i stor skala. Veiledningen fra Artikkel 29-gruppen understreker at kjernevirksomhet omfatter behandling som er en uatskillelig del av tjenesten, ikke bare virksomhetens formål. En driftsleverandør som drifter journalsystemer for flere klinikker behandler helseopplysninger som en nødvendig og løpende del av selve tjenesten, ikke som en støttefunksjon. Skalaen er heller ikke ubetydelig når flere klinikkers pasientdata samles hos én leverandør.

Argumentet mot er at Mjøsdata behandler dataene bare etter instruks, uten tilgang til innholdet i normal drift, og uten egen interesse i opplysningene. Det er teknisk drift, ikke bruk.

Spørsmålet er ikke avklart, og en feilvurdering kan sanksjoneres i seg selv. Jeg anbefaler derfor at Mjøsdata utpeker personvernombud frivillig og registrerer det hos Datatilsynet. Begrunnelsen er tredelt. Det fjerner en rettslig usikkerhet til en kostnad som er lav for en virksomhet som uansett trenger personvernkompetanse. Et frivillig utpekt ombud må oppfylle de samme kravene til uavhengighet, så det finnes ingen forenklet variant, men det gir en definert rolle som ellers ville flytt mellom sikkerhetsansvarlig og daglig leder. Og helse- og kommunekunder spør om det i anskaffelser.

Uansett konklusjon skal vurderingen dokumenteres skriftlig, slik ansvarlighetsprinsippet i artikkel 24 forutsetter. Det er selve dokumentasjonen som beskytter virksomheten dersom Datatilsynet skulle være uenig.

## 6. Overføring til tredjeland

Skyleverandørene til Mjøsdata er amerikanske. Overføringsgrunnlaget er derfor et eget spørsmål, uavhengig av hvor dataene fysisk lagres.

Alle kundemiljøer settes opp i Azure-regioner innenfor EU eller EØS. Det er både et sikkerhetstiltak og et minimeringstiltak, men det er ikke i seg selv et overføringsgrunnlag.

Grunnlaget er EU-kommisjonens tilstrekkelighetsbeslutning for Data Privacy Framework mellom EU og USA fra juli 2023, som dekker overføring til amerikanske virksomheter som er sertifisert under ordningen. Beslutningen ble opprettholdt av underretten i EU-domstolen i Latombe-saken i 2025, men avgjørelsen kan ankes videre.

Standard personvernbestemmelser med tilhørende overføringsvurdering holdes oppdatert som reserveløsning. Historikken fra Safe Harbour og Privacy Shield tilsier at et rammeverk som er rettslig utfordret bør ha et alternativ klart på forhånd, ikke etableres i etterkant.

Det er også verdt å være oppmerksom på supportsituasjonen. Selv med lagring i EU kan support fra leverandørens personell utenfor EØS utgjøre en overføring. Dette må sjekkes mot vilkårene til den enkelte leverandøren og eventuelt begrenses i avtale. Sertifiseringene til leverandørene verifiseres årlig mot den offisielle listen, som en del av leverandørstyringen i T10.

## 7. Prioriterte tiltak

| Rekkefølge | Tiltak | Hvorfor akkurat her |
|---|---|---|
| 1 | Etablere komplett behandlingsprotokoll etter artikkel 30 | Grunnmuren alt annet bygger på. Man kan ikke sikre, slette eller melde det man ikke vet at man har |
| 2 | Innføre bruddhåndtering med frister og maler etter artikkel 33 og 34 | Størst risiko for sanksjon på kort sikt, og det billigste tiltaket i porteføljen |
| 3 | Revidere og inngå databehandleravtaler i begge retninger | Kontraktuell eksponering både mot kunder og leverandører |
| 4 | Utpeke personvernombud og dokumentere vurderingen etter artikkel 37 | Fjerner rettslig usikkerhet, og er en forutsetning for troverdighet i helsesegmentet |
| 5 | Dokumentere overføringsvurdering og verifisere sertifiseringer | Krever dialog med leverandørene og tar tid |
| 6 | Innføre slette- og minimeringsregler i Salesforce og Jira | Teknisk arbeid som forutsetter at protokollen er ferdig |

## 8. Kilder

* Personvernforordningen, forordning (EU) 2016/679
* Lov om behandling av personopplysninger
* Artikkel 29-gruppen, Guidelines on Data Protection Officers, WP243
* Datatilsynets veiledere om databehandleravtaler, konsekvensvurdering og avviksmelding
* Kommisjonens gjennomføringsbeslutning om Data Privacy Framework mellom EU og USA
