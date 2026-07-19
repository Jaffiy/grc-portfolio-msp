# Program for sikkerhetsbevissthet og atferdsendring

*Programmet er risikodrevet: temaene er valgt direkte fra risikoregisteret (R1, R2, R5, R7), og effekten måles mot definerte mål. Jf. ISO 27001 A.6.3 og tiltak T2.*

## 1. Menneskelige risikoer som skal adresseres

| Risiko | Atferd i dag | Ønsket atferd |
|---|---|---|
| Phishing (R2) | Klikk under tidspress; usikkerhet om rapportering | Stopp–tenk–rapportér; rapportering oppleves trygt og gir anerkjennelse |
| Svak autentisering (R1) | Gjenbrukte passord, MFA oppfattes som friksjon | Passordhåndterer + passkeys som standard |
| Uautorisert datadeling (R5) | Kundedata deles i chat «for å være effektiv» | Deling kun i godkjente kanaler, minimering som refleks |
| Fysisk slurv (R7) | Ulåste skjermer, enheter i bil/kafé | Lås skjermen, enheter aldri uten tilsyn |

## 2. Målgrupper og innhold

| Gruppe | Behov | Innhold |
|---|---|---|
| **Alle ansatte** | Grunnleggende motstandskraft | Phishing, passord/MFA, datadeling, fysisk sikkerhet, hvordan rapportere |
| **Supportteamet** | Høyest eksponering + bred tilgang | Fordypning: sosial manipulering mot helpdesk (vishing, «haster»-press fra falske kunder), verifisering av innringere |
| **Teknisk personell** | Privilegert tilgang | Sikker administrasjon (PAW, PIM), Azure-herding, sikker hemmelighetshåndtering |
| **Ledelsen** | Eierskap og forbilde | Risikostyring, hendelsesledelse, hvorfor ledere er spydspiss-mål (CEO-fraud) |

## 3. Kanaler og frekvens

| Kanal | Frekvens | Formål |
|---|---|---|
| Interaktive kurs med case fra egen hverdag | Kvartalsvis | Kunnskap og holdning |
| Phishing-simuleringer (varierende vanskelighetsgrad) | Månedlig | Trening + måling; support prioriteres |
| Korte intranett-drypp (sjekklister, 2-min video) | Ukentlig | Vedlikehold av oppmerksomhet |
| Teknisk workshop (hands-on) | Halvårlig | Dybde for drift/utvikling |
| Tabletop-øvelse med ledelsen | Årlig | Hendelsesberedskap (kobles til hendelsesresponsplanen) |

## 4. Atferdskampanje: «Vær Mjøsdatas skjold — ett klikk om gangen»

Gamification med poengprofil på intranettet: poeng for rapportert phishing (ekte *og* simulert), gjennomførte kurs, sterk MFA-metode aktivert. Månedlig kåring med små premier og synlig «sikkerhetsstyrke»-dashboard for hele selskapet.

**Viktige designvalg (læring fra forskning på sikkerhetskultur):**
- **Belønn rapportering, aldri straff klikk.** Straff gir underrapportering — det farligste utfallet. Den som klikker og *melder fra* skal få positiv respons.
- **Historiefortelling framfor pekefinger:** ukentlige anonymiserte nesten-hendelser fra egen virksomhet («Da support nesten klikket…») gjør risikoen konkret.
- **Ledelsen deltar synlig** — kulturprogrammer dør uten det.

## 5. Måling og mål

| KPI | Baseline | Mål 12 mnd | Kilde |
|---|---|---|---|
| Klikkrate simulert phishing | Etableres måned 1 | **< 5 %** | Simuleringsverktøy |
| Rapporteringsrate simulert phishing | Etableres måned 1 | **> 60 %** | Simuleringsverktøy |
| Median tid til første rapport | — | < 15 min | Simuleringsverktøy |
| Ansatte med passkey/FIDO2 aktivert | — | 100 % (adm/support), > 80 % øvrige | Entra ID |
| Kunnskapsscore årlig undersøkelse | — | > 80 % | Spørreundersøkelse |

Resultater rapporteres kvartalsvis til sikkerhets- og personvernkomiteen og inngår i årsrapporten til ledelsen. Manglende måloppnåelse utløser justering av programmet — ikke av målene.
