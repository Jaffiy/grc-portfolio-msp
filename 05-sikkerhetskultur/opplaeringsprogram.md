# 05 — Program for sikkerhetsbevissthet og atferdsendring

| | |
|---|---|
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Evalueres årlig |
| **Hjemmel** | ISO/IEC 27001:2022 `A.6.3` · NSM Grunnprinsipper for sikkerhetsstyring · GDPR art. 32 |
| **Adresserer** | [R2](../02-risikovurdering/risikoregister.md), [R5](../02-risikovurdering/risikoregister.md), [R7](../02-risikovurdering/risikoregister.md), [R9](../02-risikovurdering/risikoregister.md) via [T2](../02-risikovurdering/tiltaksplan.md#t2--kontinuerlig-sikkerhetsopplæring-med-phishing-simulering) |

> **Programmet er risikodrevet, ikke generisk.** Temaene er hentet direkte fra risikoregisteret, målgruppene fra hvem som faktisk bærer risikoen, og effekten måles mot forhåndsdefinerte mål. Et opplæringsprogram som ikke kan spore hvert tema tilbake til en identifisert risiko er en aktivitet, ikke et tiltak.

---

## 1. Menneskelige risikoer som skal adresseres

| Risiko | Atferd i dag | Ønsket atferd | Hvordan det måles |
|---|---|---|---|
| **Phishing** ([R2](../02-risikovurdering/risikoregister.md)) | Klikk under tidspress; usikkerhet om hvordan og til hvem man rapporterer | Stopp – tenk – rapportér. Rapportering oppleves trygt og gir anerkjennelse | Klikkrate og rapporteringsrate i simuleringer |
| **Svak autentisering** ([R1](../02-risikovurdering/risikoregister.md)) | Gjenbrukte passord; MFA oppleves som friksjon | Passordhåndterer og passkeys som standardvalg | Andel med FIDO2/passkey aktivert i Entra ID |
| **Uautorisert datadeling** ([R5](../02-risikovurdering/risikoregister.md)) | Kundedata deles i chat «for å være effektiv» | Deling kun i godkjente kanaler; minimering som refleks | Stikkprøver og selvrapportering |
| **Fysisk uoppmerksomhet** ([R7](../02-risikovurdering/risikoregister.md)) | Ulåste skjermer; enheter etterlatt i bil eller på kafé | Skjermlås som vane; enheter aldri uten tilsyn | Observasjonsrunder; antall meldte utstyrstap |
| **Sen bruddmelding** ([R9](../02-risikovurdering/risikoregister.md)) | Usikkerhet om hva som *er* et personvernbrudd, og hvem som skal varsles | Enhver mistanke meldes til hendelsesleder samme dag | Median tid fra observasjon til melding |

---

## 2. Målgrupper og innhold

| Gruppe | Hvorfor akkurat denne gruppen | Innhold |
|---|---|---|
| **Alle ansatte** | Grunnleggende motstandskraft; alle har e-post | Phishing, passord og MFA, datadeling, fysisk sikkerhet, hvordan og når man rapporterer |
| **Supportteamet** | Høyest eksponering kombinert med bredest tilgang — den kombinasjonen gjør dem til det naturlige målet | Fordypning i sosial manipulering mot helpdesk: vishing, «haster»-press fra falske kunder, verifisering av innringere før tilgang gis eller passord tilbakestilles |
| **Teknisk personell** | Privilegert tilgang; feil her rammer alle kunder | Sikker administrasjon (PAW, PIM), Azure-herding, hemmelighetshåndtering, hvorfor baseline-avvik betyr noe |
| **Ledelsen** | Er både beslutningstakere og spydspiss-mål | Risikostyring og aksept av restrisiko, hendelsesledelse, CEO-fraud, og — når NIS2 gjennomføres — det personlige ledelsesansvaret |

Målgruppeinndelingen følger eksponering, ikke stillingsnivå. Support får mest opplæring fordi de har mest risiko, ikke fordi de har lavest ansiennitet.

---

## 3. Kanaler og frekvens

| Kanal | Frekvens | Formål |
|---|---|---|
| Interaktive kurs med case fra egen hverdag | Kvartalsvis | Kunnskap og holdning |
| Phishing-simuleringer med varierende vanskelighetsgrad | Månedlig | Trening og måling; support prioriteres |
| Korte intranett-drypp (sjekkliste, 2-minutters video) | Ukentlig | Vedlikehold av oppmerksomhet mellom kursene |
| Teknisk workshop, hands-on | Halvårlig | Dybde for drift og utvikling |
| Tabletop-øvelse med ledelsen | Årlig | Beredskap; kobles direkte til [hendelsesresponsplanen](../04-isms/hendelsesresponsplan.md) |

**Om frekvensvalget:** effekten av enkeltstående årlig opplæring forsvinner i løpet av uker. Kombinasjonen av sjeldne, dype økter og hyppige, korte påminnelser er valgt fordi det er repetisjonen — ikke lengden på kurset — som flytter atferd.

---

## 4. Atferdskampanje

**«Vær Mjøsdatas skjold — ett klikk om gangen»**

Gamification med poengprofil på intranettet: poeng for rapportert phishing (ekte *og* simulert), gjennomførte kurs og aktivert sterk MFA-metode. Månedlig kåring med små premier og et synlig «sikkerhetsstyrke»-dashbord for hele selskapet.

### Designvalg og begrunnelse

| Valg | Begrunnelse |
|---|---|
| **Belønn rapportering, straff aldri klikk** | Straff gir underrapportering — det farligste mulige utfallet, fordi det forlenger tiden en angriper er uoppdaget. Den som klikker og *melder fra* skal møtes med takk, ikke tilsnakk |
| **Historiefortelling framfor pekefinger** | Ukentlige anonymiserte nesten-hendelser fra egen virksomhet («Da support nesten klikket …») gjør risikoen konkret på en måte statistikk ikke gjør |
| **Ledelsen deltar synlig** | Kulturprogrammer som ledelsen delegerer bort, dør. Deltakelse er en forutsetning, ikke en bonus |
| **Måling på gruppenivå, ikke individnivå** | Individuelle rangeringer av hvem som klikker skaper skam og underrapportering. Poeng gis for ønsket atferd, ikke trekkes for uønsket |

**Faglig grunnlag:** programmet bygger på ENISAs anbefalinger for awareness-arbeid (målgruppetilpasning, kontinuitet, måling) og på **SANS Security Awareness Maturity Model**, der Mjøsdata i dag ligger på nivå 1–2 («Non-existent» til «Compliance-focused») og har nivå 4 («Long-term sustainment») som ambisjon innen tre år. Modellen er valgt fordi den skiller tydelig mellom å *gjennomføre* opplæring og å *endre* atferd — skillet dette programmet er bygget rundt.

---

## 5. Måling og mål

| KPI | Baseline | Mål 12 mnd | Kilde |
|---|---|---|---|
| Klikkrate, simulert phishing | Etableres i måned 1 | **< 5 %** | Simuleringsverktøy |
| Rapporteringsrate, simulert phishing | Etableres i måned 1 | **> 60 %** | Simuleringsverktøy |
| Median tid til første rapport | Etableres i måned 1 | **< 15 min** | Simuleringsverktøy |
| Ansatte med passkey/FIDO2 aktivert | 0 % | **100 %** (adm./support), **> 80 %** øvrige | Entra ID |
| Kunnskapsscore, årlig undersøkelse | Etableres i måned 1 | **> 80 %** | Spørreundersøkelse |
| Gjennomføringsgrad, kvartalskurs | — | **> 95 %** | Læringsplattform |

**Hvorfor rapporteringsraten er den viktigste av dem:** klikkraten måler hvor mange som gjør feil. Rapporteringsraten måler hvor raskt organisasjonen oppdager at noen har gjort det — og det er den variabelen som avgjør om en hendelse blir et avvik eller en krise. En virksomhet med 10 % klikkrate og 80 % rapportering er tryggere enn en med 3 % klikkrate og 10 % rapportering.

Resultatene rapporteres kvartalsvis til [sikkerhets- og personvernkomiteen](../02-risikovurdering/tiltaksplan.md#styring-og-oppfølging) og inngår i den årlige rapporten til ledelsen.

> **Manglende måloppnåelse utløser justering av programmet — ikke av målene.**

---

## 6. Kilder

- ISO/IEC 27001:2022 `A.6.3`; ISO/IEC 27002:2022 veiledning til samme kontroll
- ENISA: veiledning om sikkerhetsbevissthet og awareness-programmer
- SANS: *Security Awareness Maturity Model*
- NSM: *Grunnprinsipper for sikkerhetsstyring* — «Gjennomfør jevnlige øvelser, trening og opplæring»
