# Program for sikkerhetsbevissthet og atferdsendring

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Evaluering | Årlig |
| Hjemmel | ISO 27001 A.6.3. NSM Grunnprinsipper for sikkerhetsstyring. GDPR artikkel 32 |
| Adresserer | R2, R5, R7 og R9, gjennom tiltak T2 |

Programmet er bygget ut fra risikoregisteret, ikke ut fra en generisk kursliste. Temaene er hentet direkte fra risikoene, målgruppene fra hvem som faktisk bærer dem, og effekten måles mot mål som er satt på forhånd. Et opplæringsprogram der man ikke kan spore hvert tema tilbake til en identifisert risiko er en aktivitet, ikke et tiltak.

## 1. Hvilke risikoer programmet skal treffe

| Risiko | Slik det er i dag | Slik vi vil ha det | Hvordan det måles |
|---|---|---|---|
| Phishing, R2 | Folk klikker under tidspress, og er usikre på hvordan og til hvem de skal rapportere | Stopp, tenk, rapporter. Rapportering oppleves trygt og blir lagt merke til | Klikkrate og rapporteringsrate i simuleringer |
| Svak autentisering, R1 | Gjenbrukte passord, og MFA oppleves som friksjon | Passordhåndterer og passkeys som standard | Andel med FIDO2 eller passkey aktivert i Entra ID |
| Uautorisert datadeling, R5 | Kundedata deles i chat for å gå raskere | Deling skjer bare i godkjente kanaler, og minimering sitter i ryggmargen | Stikkprøver og selvrapportering |
| Fysisk uoppmerksomhet, R7 | Ulåste skjermer, og enheter som blir liggende i bilen eller på kafé | Skjermlås som vane, og enheter aldri uten tilsyn | Observasjonsrunder og antall meldte utstyrstap |
| Sen bruddmelding, R9 | Usikkerhet om hva som faktisk er et personvernbrudd, og hvem som skal varsles | Enhver mistanke meldes til hendelsesleder samme dag | Median tid fra observasjon til melding |

## 2. Målgrupper og innhold

| Gruppe | Hvorfor akkurat denne gruppen | Innhold |
|---|---|---|
| Alle ansatte | Grunnleggende motstandskraft. Alle har e-post | Phishing, passord og MFA, datadeling, fysisk sikkerhet, og hvordan og når man rapporterer |
| Supportteamet | Høyest eksponering kombinert med bredest tilgang. Det er den kombinasjonen som gjør dem til det naturlige målet | Fordypning i sosial manipulering mot helpdesk: telefonsvindel, hastepress fra falske kunder, og verifisering av innringere før tilgang gis eller passord tilbakestilles |
| Teknisk personell | Har privilegert tilgang, og feil her rammer alle kunder | Sikker administrasjon, herding av Azure, håndtering av hemmeligheter, og hvorfor avvik fra baseline betyr noe |
| Ledelsen | Er både beslutningstakere og selv attraktive mål | Risikostyring og aksept av restrisiko, hendelsesledelse, direktørsvindel, og det personlige ledelsesansvaret som kommer med NIS2 |

Inndelingen følger eksponering, ikke stillingsnivå. Support får mest opplæring fordi de har mest risiko, ikke fordi de har kortest ansiennitet.

## 3. Kanaler og frekvens

| Kanal | Frekvens | Formål |
|---|---|---|
| Interaktive kurs med eksempler fra egen hverdag | Kvartalsvis | Kunnskap og holdning |
| Phishing-simuleringer med varierende vanskelighetsgrad | Månedlig | Trening og måling. Support prioriteres |
| Korte innslag på intranett, sjekkliste eller kort video | Ukentlig | Holde oppmerksomheten oppe mellom kursene |
| Teknisk verksted med praktiske øvelser | Hvert halvår | Dybde for drift og utvikling |
| Skrivebordsøvelse med ledelsen | Årlig | Beredskap, koblet til hendelsesresponsplanen |

Om frekvensen: effekten av et enkeltstående årlig kurs forsvinner i løpet av noen uker. Kombinasjonen av sjeldne og dype økter med hyppige og korte påminnelser er valgt fordi det er repetisjonen, og ikke lengden på kurset, som flytter atferd.

## 4. Atferdskampanje

Kampanjen heter Vær Mjøsdatas skjold, ett klikk om gangen.

Den bygger på en poengprofil på intranettet. Man får poeng for rapportert phishing, både ekte og simulert, for gjennomførte kurs, og for å ha aktivert en sterk MFA-metode. Hver måned kåres en vinner med en liten premie, og hele selskapet ser en oversikt over hvordan det ligger an.

Fire designvalg er verdt å begrunne.

Vi belønner rapportering og straffer aldri klikk. Straff gir underrapportering, som er det farligste utfallet, fordi det forlenger tiden en angriper er uoppdaget. Den som klikker og melder fra skal møtes med takk, ikke tilsnakk.

Vi bruker fortellinger framfor pekefinger. Hver uke deles en anonymisert nesten-hendelse fra egen virksomhet, av typen den gangen support nesten klikket. Det gjør risikoen konkret på en måte statistikk ikke gjør.

Ledelsen deltar synlig. Kulturprogrammer som ledelsen setter bort til andre, dør. Deltakelse er en forutsetning, ikke en bonus.

Vi måler på gruppenivå og ikke på individnivå. Individuelle rangeringer over hvem som klikker skaper skam og dermed underrapportering. Poeng gis for ønsket atferd, og trekkes ikke for uønsket.

Faglig bygger programmet på ENISAs anbefalinger for arbeid med sikkerhetsbevissthet, og på SANS Security Awareness Maturity Model. Mjøsdata ligger i dag på nivå én til to i den modellen, altså mellom ingenting og et program som bare handler om å krysse av for etterlevelse. Målet er nivå fire innen tre år. Modellen er valgt fordi den skiller tydelig mellom å gjennomføre opplæring og å endre atferd, og det er nettopp det skillet programmet er bygget rundt.

## 5. Måling og mål

| Måltall | Utgangspunkt | Mål etter tolv måneder | Kilde |
|---|---|---|---|
| Klikkrate i simulert phishing | Etableres i måned én | Under 5 prosent | Simuleringsverktøy |
| Rapporteringsrate i simulert phishing | Etableres i måned én | Over 60 prosent | Simuleringsverktøy |
| Median tid til første rapport | Etableres i måned én | Under 15 minutter | Simuleringsverktøy |
| Ansatte med passkey eller FIDO2 aktivert | 0 prosent | 100 prosent for administratorer og support, over 80 prosent for øvrige | Entra ID |
| Kunnskapsscore i årlig undersøkelse | Etableres i måned én | Over 80 prosent | Spørreundersøkelse |
| Gjennomføringsgrad på kvartalskurs | | Over 95 prosent | Læringsplattform |

Rapporteringsraten er det viktigste tallet i tabellen. Klikkraten måler hvor mange som gjør feil. Rapporteringsraten måler hvor raskt organisasjonen oppdager at noen har gjort det, og det er den variabelen som avgjør om en hendelse blir et avvik eller en krise. En virksomhet med 10 prosent klikkrate og 80 prosent rapportering er tryggere enn en med 3 prosent klikkrate og 10 prosent rapportering.

Resultatene rapporteres kvartalsvis til sikkerhets- og personvernkomiteen, og inngår i den årlige rapporten til ledelsen. Dersom målene ikke nås, justerer vi programmet. Vi justerer ikke målene.

## 6. Kilder

* ISO/IEC 27001:2022 A.6.3, med veiledningen i ISO/IEC 27002:2022
* ENISA, veiledning om sikkerhetsbevissthet
* SANS, Security Awareness Maturity Model
* NSM, Grunnprinsipper for sikkerhetsstyring, om jevnlige øvelser, trening og opplæring
