# NIS2 og digitalsikkerhetsloven, omfangsvurdering

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, vurdert 1. september 2026 |
| Revisjon | Ved endringer i regelverket |

Formålet med dokumentet er å vurdere om og hvordan Mjøsdata treffes av NIS2 når direktivet gjennomføres i norsk rett, og hva det i så fall betyr for sikkerhetsarbeidet.

## 1. Hva som gjelder i dag

Dette er den viktigste presiseringen i dokumentet, og også den som oftest blir gjort feil i bransjen.

Digitalsikkerhetsloven som gjelder nå gjennomfører NIS1. Den retter seg mot tilbydere av samfunnsviktige tjenester innen energi, transport, helse, vannforsyning, bank og finansiell infrastruktur, og mot enkelte digitale tjenestetilbydere som nettbaserte markedsplasser, søkemotorer og skytjenester. En driftsleverandør av Mjøsdatas type og størrelse er etter alt å dømme ikke pliktsubjekt.

NIS2 er trådt i kraft i EU, men er ennå ikke innlemmet i EØS-avtalen og dermed ikke gjennomført i norsk rett. En ny norsk lov er varslet, men tidspunktet er ikke fastsatt.

Konsekvensen for hele denne porteføljen er at alt jeg skriver om NIS2-plikter er forberedelse og ikke gjeldende rett. Tiltakene er derfor begrunnet i risiko og kundekrav, som er reelle i dag, og ikke i en lovplikt som ennå ikke finnes. Forskjellen betyr mye for en virksomhet som skal prioritere budsjett.

## 2. Hvorfor spørsmålet likevel er aktuelt

NIS2 utvider virkeområdet betydelig sammenlignet med NIS1. Driftsleverandører og leverandører av sikkerhetstjenester er tatt inn som egne kategorier under sektoren for IKT-tjenestestyring i vedlegg I. En norsk driftsleverandør kan dermed bli direkte pliktsubjekt, ikke bare indirekte berørt gjennom kundenes krav.

To andre forhold gjør at det lønner seg å forberede seg uavhengig av når loven kommer.

Kundene får kravene først. Kommuner og helsevirksomheter er selv omfattede sektorer, og NIS2 pålegger dem uttrykkelig å stille sikkerhetskrav til leverandørkjeden. Kravene når Mjøsdata gjennom kontrakter og anskaffelser lenge før de eventuelt når selskapet gjennom lov.

Beredskap er billig, hastverk er dyrt. Tiltakene i kapittel 02 er begrunnet i risiko uansett. Å gjøre dem NIS2-kompatible koster lite ekstra nå, og vesentlig mer under tidspress senere.

## 3. Selve omfangsvurderingen

| Kriterium | Vurdering |
|---|---|
| Tjenestetype | IT-drift, skyadministrasjon og sikkerhetstjenester faller inn under kategorien i vedlegg I. Dette kriteriet er oppfylt |
| Størrelse | Uavklart, og avhenger av regnskapstallene. Se under |
| Kundeprofil | Drift for kommuner og helsevirksomheter, som selv er omfattede sektorer. Det forsterker både direkte og indirekte eksponering |
| Sannsynlig klassifisering | Viktig virksomhet, dersom selskapet omfattes |

### Størrelseskriteriet

NIS2 artikkel 2 nr. 1 gjelder virksomheter som kvalifiserer som mellomstore etter EU-kommisjonens rekommandasjon 2003/361, eller som er større enn det. En virksomhet er ikke liten, og dermed minst mellomstor, dersom den enten har 50 ansatte eller flere, eller har både årlig omsetning og balansesum over 10 millioner euro.

Med 45 ansatte ligger Mjøsdata under bemanningsterskelen. Avgjørelsen beror derfor på om begge de finansielle tersklene overskrides samtidig. Det er en strengere test enn omsetning eller balanse over 10 millioner, som er den formuleringen man ofte ser gjengitt, og forskjellen er avgjørende i akkurat dette grensetilfellet.

Det er også verdt å merke seg at partnerforetak og tilknyttede foretak skal konsolideres inn i beregningen. En driftsleverandør som inngår i et konsern kan derfor bli omfattet selv om selve driftsselskapet er lite.

### Vesentlig eller viktig virksomhet

For virksomheter i vedlegg I følger skillet størrelsen. Store virksomheter, altså de med minst 250 ansatte eller omsetning over 50 millioner euro og balanse over 43 millioner euro, blir vesentlige virksomheter. Mellomstore blir viktige virksomheter. Mjøsdata ville i alle realistiske scenarioer havne i den siste kategorien.

Den praktiske forskjellen er at kravene til sikkerhetstiltak er de samme, men at tilsynet skjer i etterkant og reaktivt i stedet for løpende, og at de øvre gebyrsatsene er lavere. Kravene til risikostyring i artikkel 21 er identiske. Det er altså ikke en forenklet variant av regelverket.

### Konklusjon

Mjøsdata bør planlegge som om selskapet blir omfattet. Selv om størrelseskriteriet ikke slår inn, vil kommunale kunder og helsekunder videreføre NIS2-kravene gjennom kontrakt. Kostnaden ved å være forberedt er lav. Kostnaden ved ikke å være det er tapte anbud, og det inntreffer lenge før eventuelle sanksjoner.

Vurderingen skal gjøres på nytt ved ny norsk lov, ved vekst forbi 50 ansatte, ved endringer i konsernstrukturen, og ved vesentlige endringer i kundeporteføljen.

## 4. Gap-analyse mot kravene i artikkel 21

Artikkel 21 nr. 2 krever risikostyringstiltak innenfor ti områder. Tabellen viser hva porteføljen allerede dekker, og hva som gjenstår.

| Krav | Dekket av | Gjenstående |
|---|---|---|
| Risikoanalyse og sikkerhetspolicyer | Kapittel 02, med metodikk, register og behandlingsplan | Formalisere en årlig syklus med dokumentert godkjenning fra ledelsen |
| Hendelseshåndtering | Hendelsesresponsplanen i kapittel 04 | Dekket. Varslingsfristene på 24 og 72 timer og én måned er tatt inn som betinget rad |
| Driftskontinuitet, backup og krisehåndtering | Tiltak T3, med geo-redundans og uforanderlig backup | Kontinuitetsplan med gjenopprettingstider per kundekategori. Kontroll A.5.30 er ikke påbegynt |
| Leverandørkjedesikkerhet | Tiltak T10, og databehandleravtalene i kapittel 03 | Selve gjennomføringen. Fjernstyringsverktøyene har høyest prioritet |
| Sikkerhet i anskaffelse, utvikling og drift | Tiltak T7, med baseline og penetrasjonstest | Sikkerhetskrav som fast del av anskaffelsesrutinen |
| Evaluering av tiltakenes effekt | Måltallene i kapittel 05, og restrisikoen i kapittel 02 | En samlet årlig gjennomgang av effekt |
| Cyberhygiene og opplæring | Kapittel 05 | Dekket |
| Kryptografi | Tiltak T5 og T9, og kontroll A.8.24 | Egen kryptopolicy med krav til algoritmer og nøkkelhåndtering |
| Personellsikkerhet og tilgangsstyring | Policyen for tilgangsstyring og tiltak T6 | Rutine for bakgrunnssjekk ved ansettelse i sikkerhetskritiske roller |
| MFA og sikret kommunikasjon | Tiltak T1 | Løsning for nødkommunikasjon ved totalt systemtap, delvis dekket av den offline kontaktlisten |

To av ti områder er dekket. De åtte andre har identifiserte gap som er prioritert. Ingen av dem krever ny teknologi. Alle er dokumentasjons- eller prosessarbeid, og seks av dem har allerede fått et tiltak med eier og frist.

## 5. Ledelsesansvar

NIS2 artikkel 20 gjør ledelsen personlig ansvarlig for å godkjenne og følge opp risikostyringstiltakene, og krever at ledelsen selv får opplæring i risikostyring. Ved grove overtredelser kan tilsynsmyndigheten midlertidig forby personer i ledende stillinger å utøve lederfunksjoner.

Dette er allerede reflektert i porteføljen. Styringsmodellen i tiltaksplanen har kvartalsvis rapportering til daglig leder og en årlig styresak, restrisiko krever dokumentert aksept fra daglig leder, og opplæringsprogrammet har en egen modul for ledelsen.

## 6. Varslingsplikten

NIS2 innfører varsling i tre trinn ved vesentlige hendelser. Innen 24 timer skal det sendes et tidlig varsel, der det blant annet skal opplyses om man mistenker en ulovlig eller ondsinnet handling, og om hendelsen har virkninger over landegrensene. Innen 72 timer skal det sendes en oppdatert vurdering med alvorlighetsgrad og indikatorer. Innen én måned skal det leveres en sluttrapport med rotårsak og iverksatte tiltak.

Dette er både strengere og bredere enn GDPR artikkel 33, som bare gjelder brudd på personopplysningssikkerheten. En driftshendelse uten persondata kan være varslingspliktig etter NIS2 og ikke etter GDPR. Fristene er tatt inn i varslingsmatrisen i hendelsesresponsplanen som en betinget rad, slik at hendelseslederen slipper å lete etter dem den dagen de begynner å gjelde.

## 7. Anbefalt handlingsplan

| Når | Hva |
|---|---|
| Løpende | Følge med på gjennomføringen av NIS2 i norsk rett. Avklare hvilken sektormyndighet som blir tilsynsorgan, og om det kommer registreringsplikt |
| 0 til 3 måneder | Lukke de billigste gapene: kryptopolicy, kontinuitetsplan med gjenopprettingstider, og sikkerhetskrav i anskaffelsesrutinen |
| 3 til 6 måneder | Etablere leverandørrisikoprogrammet i tiltak T10, med særlig vurdering av fjernstyringsverktøyene |
| 6 til 12 måneder | Første samlede gjennomgang av effekt, og ledelsens gjennomgang etter ISO 27001 punkt 9.3 |
| Løpende | Bruke NIS2-beredskapen aktivt i salg mot kommune- og helsesegmentet. Etterlevelse er et konkurransefortrinn, ikke bare en kostnad |

## 8. Kilder

* Direktiv (EU) 2022/2555, særlig artikkel 2, 20, 21 og 23, og vedlegg I
* Kommisjonens rekommandasjon 2003/361 om definisjonen av små og mellomstore bedrifter
* Lov om digital sikkerhet
* NSMs veiledning om digitalsikkerhetsloven
