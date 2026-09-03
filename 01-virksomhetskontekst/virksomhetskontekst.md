# Virksomhetskontekst

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Revisjon | Årlig |
| Hjemmel | ISO/IEC 27001:2022 punkt 4.1 til 4.3 |

Dette dokumentet beskriver forretnings- og systemkonteksten som resten av porteføljen bygger på. ISO 27001 krever at organisasjonen forstår seg selv og interessentene sine før omfang og risiko fastsettes. Rekkefølgen er ikke tilfeldig. Uten forretningskonteksten blir risikovurderingen en liste over tekniske svakheter i stedet for et grunnlag noen kan ta beslutninger på.

## 1. Om virksomheten

Mjøsdata AS er en IT-driftsleverandør med hovedkontor i Hamar og 45 ansatte. De fordeler seg på konsulenter, driftspersonell, support, salg og administrasjon. Selskapet leverer IT-drift, skytjenester og sikkerhetstjenester til små og mellomstore virksomheter i Innlandet.

Kundene fordeler seg på tre segmenter:

| Segment | Typiske kunder | Hva som gjør segmentet krevende |
|---|---|---|
| Profesjonelle tjenesteytere | Advokatkontorer og regnskapsbyråer | Lovpålagt taushetsplikt, og klientdata som er konkurransesensitive |
| Helsevirksomheter | Private helseklinikker og tannlegekontorer | Særlige kategorier av personopplysninger etter GDPR artikkel 9, og krav etter pasientjournalloven |
| Offentlig sektor | Kommuner og skoler | Anskaffelsesregler, forvaltningskrav og høye krav til oppetid |

Mesteparten av omsetningen kommer fra abonnementsbasert drift og support med tjenestenivåavtaler. Det betyr at tilgjengelighet ikke bare er en teknisk ambisjon, men en kommersiell forpliktelse. Brytes en SLA, utløser det avtalefestet prisavslag, og sannsynligheten for at kunden ikke fornyer går opp.

## 2. Digital verdikjede

Tre systemer bærer kjerneprosessene.

| System | Rolle | Sentrale informasjonsverdier | GDPR-rolle for Mjøsdata |
|---|---|---|---|
| Salesforce | Kundeinformasjon, kontrakter, salgsoppfølging og registrering av supporthenvendelser | Kundedata, kontraktsvilkår, kontakthistorikk | Behandlingsansvarlig |
| Jira Service Management | Tildeling, prioritering og sporing av supportsaker | Supportlogger og feilbeskrivelser, som kan inneholde personopplysninger | Varierer, se note under |
| Microsoft Azure | Skyplattform for kundemiljøer og intern databehandling, med lagring, virtuelle maskiner og backup | Tekniske konfigurasjoner, kundedata i drift, sikkerhetskopier | Databehandler |

Rollen i Jira avhenger av om saken gjelder Mjøsdatas eget kundeforhold eller behandling utført på vegne av kunden. Rolleanalysen i [kapittel 03](../03-gdpr/gdpr-analyse.md) går nærmere inn på skillet.

### Kjerneprosessen: håndtering av kundesupport

1. Kunden melder inn en sak. Den registreres i Salesforce med kontaktinformasjon og problembeskrivelse.
2. Saken overføres via API-integrasjon til Jira Service Management, som tildeler den etter prioritet og kompetanse.
3. Supportteamet henter tekniske data som konfigurasjoner og logger fra Azure, analyserer og løser saken.
4. Løsningen registreres i Jira, status oppdateres i Salesforce, og kunden får tilbakemelding.

Dataflyten krysser tre systemer og én integrasjon. Hvert overgangspunkt er både en mulig angrepsflate og et sted der data kan gå tapt eller bli forvansket. Integrasjonen mellom Salesforce og Jira er derfor vurdert som en egen risiko, R3 i [risikoregisteret](../02-risikovurdering/risikoregister.md).

## 3. Hvorfor sikkerhet er forretningskritisk

Konfidensialitet, integritet og tilgjengelighet er ikke abstrakte prinsipper for Mjøsdata. De tilsvarer konkrete forpliktelser selskapet har påtatt seg.

Konfidensialitet handler om at klientdata fra advokatkontorer og helseklinikker er underlagt taushetsplikt og GDPR artikkel 9. En lekkasje rammer ikke bare Mjøsdata, den utløser kundenes egne rettslige forpliktelser. Driftsleverandører er attraktive mål nettopp fordi ett innbrudd gir tilgang til mange virksomheter samtidig. Det er dette som ligger bak R6 og R8 i risikoregisteret.

Integritet handler om at feil i supportlogger eller kundekonfigurasjoner kan gi driftsstans hos kundene. Feil i logger svekker også bevisverdien når noe skal etterforskes i ettertid. Uten pålitelige logger blir en hendelsesetterforskning gjetting.

Tilgjengelighet er kontraktsfestet. Døgnbemannet helpdesk og drift av tidskritiske kommunale systemer er dekket av SLA-er med oppetidsgaranti og krav til responstid. Nedetid blir dermed regnet om til penger nesten umiddelbart.

Dette får en direkte konsekvens for risikovurderingen. Fordi Mjøsdata bærer risiko på vegne av mange kunder samtidig, ligger konsekvensnivåene systematisk høyere enn de ville gjort for en frittstående virksomhet av samme størrelse. Det er begrunnet i [konsekvensskalaen](../02-risikovurdering/metodikk.md).

## 4. Interessenter og krav

| Interessent | Krav og forventning | Kilde | Status |
|---|---|---|---|
| Kunder i helsesektoren | Vern av helseopplysninger, databehandleravtale, bistand ved DPIA | GDPR artikkel 9, 28 og 32, pasientjournalloven, personopplysningsloven | Delvis dekket, se kapittel 03 |
| Kunder innen advokat og regnskap | Konfidensialitet og taushetsplikt også i leverandørleddet | Advokatforskriften, bokføringsloven, avtale | Delvis dekket |
| Kommuner | Oppetid, forsvarlig informasjonssikkerhet, dokumenterbar etterlevelse | SLA, eForvaltningsforskriften, anskaffelseskrav | Delvis dekket |
| Datatilsynet | Etterlevelse av GDPR og meldeplikt ved brudd | GDPR artikkel 33 og 34 | Gap, se tiltak T8 |
| NSM og sektormyndighet | Grunnleggende sikkerhetsnivå. Mjøsdata er ikke pliktsubjekt etter dagens digitalsikkerhetslov, men kan bli det når NIS2 gjennomføres | NSM Grunnprinsipper 2.1 som anbefaling, NIS2 som kommende regelverk | Under overvåking, se kapittel 06 |
| Underleverandører | Databehandleravtaler og sikkerhetskrav i avtale | GDPR artikkel 28, ISO 27001 A.5.19 til A.5.23 | Gap, se tiltak T10 |
| Eiere og ledelse | Lønnsomhet, omdømme og dokumentert risikokontroll | Styrevedtak | Dekket i styringsmodellen |

En presisering om regelverket er nødvendig her. Digitalsikkerhetsloven som gjelder i dag gjennomfører NIS1 og retter seg mot tilbydere av samfunnsviktige tjenester og enkelte digitale tjenestetilbydere. Mjøsdata er sannsynligvis ikke omfattet. NIS2, som uttrykkelig nevner driftsleverandører, er ennå ikke innlemmet i EØS-avtalen. Henvisninger til NIS2 i denne porteføljen er derfor forberedende, ikke uttrykk for gjeldende plikter.

## 5. Omfang og avgrensning

Analysen omfatter kjerneprosessen for kundesupport, de tre bærende systemene, integrasjonen mellom dem, identitets- og tilgangsstyring på tvers, og endepunktene support- og driftspersonell bruker.

Interne støtteprosesser som HR og økonomi, og fysisk sikring av hovedkontoret, er holdt utenfor. De berøres bare der de påvirker kjerneprosessen direkte. Offboarding er et eksempel på noe som formelt er en HR-prosess, men som har så tydelig sikkerhetseffekt at den er tatt inn i [tilgangsstyringspolicyen](../04-isms/policy-tilgangsstyring.md).

Begrunnelsen for avgrensningen er praktisk. Kundesupportprosessen er både der Mjøsdata tjener pengene sine og der de bærer størst risiko på vegne av andre. En avgrenset analyse som faktisk kan gjennomføres og forsvares er mer verdt enn en overflatisk gjennomgang av hele virksomheten. Utvidelse til de øvrige prosessene er neste steg.

## 6. Kilder

* ISO/IEC 27001:2022, punkt 4.1 til 4.3
* NSM, Grunnprinsipper for IKT-sikkerhet 2.1
* Datatilsynets veiledere om behandlingsansvarlig og databehandler
* Lov om digital sikkerhet (digitalsikkerhetsloven)
