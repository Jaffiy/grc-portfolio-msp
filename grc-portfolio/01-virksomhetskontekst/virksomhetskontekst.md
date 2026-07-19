# Virksomhetskontekst — Mjøsdata AS

*Dette dokumentet etablerer forretnings- og systemkonteksten som ligger til grunn for risikovurderingen (kap. 02) og etterlevelsesanalysene (kap. 03 og 06), jf. ISO/IEC 27001:2022 pkt. 4.1–4.2 (forståelse av organisasjonen og interessenters behov).*

## 1. Om virksomheten

Mjøsdata AS er en IT-driftsleverandør (MSP) med hovedkontor i Hamar og 45 ansatte fordelt på konsulenter, driftspersonell, support, salg og administrasjon. Selskapet leverer IT-drift, skytjenester og sikkerhetstjenester til små og mellomstore virksomheter i Innlandet, med tre hovedsegmenter:

- **Profesjonelle tjenesteytere** — advokatkontorer og regnskapsbyråer med strenge krav til konfidensialitet
- **Helsevirksomheter** — private helseklinikker og tannlegekontorer som behandler særlige kategorier av personopplysninger (helseopplysninger, GDPR art. 9)
- **Offentlig sektor** — kommuner og skoler som trenger bistand til digitalisering av administrative prosesser

Hoveddelen av omsetningen er abonnementsbasert (drift og support med tjenestenivåavtaler), noe som gjør **tilgjengelighet** til en direkte kommersiell forpliktelse: brudd på SLA utløser prisavslag og hever risikoen for kundeflukt.

## 2. Digital verdikjede

Tre systemer bærer kjerneprosessene:

| System | Rolle | Sentrale informasjonsverdier |
|---|---|---|
| **Salesforce (CRM)** | Kundeinformasjon, kontrakter, salgsoppfølging, registrering av supporthenvendelser | Kundedata, kontraktsvilkår, kontakthistorikk |
| **Jira Service Management** | Automatisert tildeling, prioritering og sporing av supportsaker | Supportlogger, feilbeskrivelser (kan inneholde personopplysninger) |
| **Microsoft Azure** | Skyplattform for kundemiljøer og intern databehandling; lagring, virtuelle maskiner, backup | Tekniske konfigurasjoner, kundedata i drift, sikkerhetskopier |

### Kjerneprosess: kundesupporthåndtering

1. Kunden melder inn en sak → registreres i **Salesforce** med kontaktinformasjon og problembeskrivelse
2. Saken overføres via API-integrasjon til **Jira Service Management**, som tildeler den automatisk etter prioritet og kompetanse
3. Supportteamet henter tekniske data (konfigurasjoner, logger) fra **Azure**, analyserer og løser saken
4. Løsningen registreres i Jira, status oppdateres i Salesforce, og kunden får tilbakemelding

Dataflyten krysser altså tre systemer og én API-integrasjon — hvert overgangspunkt er en potensiell angreps- og feilkilde, og behandles eksplisitt i risikovurderingen.

## 3. Hvorfor informasjonssikkerhet er forretningskritisk

KIT-egenskapene (konfidensialitet, integritet, tilgjengelighet) er ikke abstrakte prinsipper for Mjøsdata — de tilsvarer konkrete kommersielle og rettslige forpliktelser:

- **Konfidensialitet**: Klientdata fra advokatkontorer og helseklinikker er underlagt henholdsvis taushetsplikt og GDPR art. 9. En lekkasje rammer ikke bare Mjøsdata, men kundens egne rettslige forpliktelser — og MSP-er er attraktive mål nettopp fordi ett innbrudd gir tilgang til mange virksomheter (leverandørkjedeangrep).
- **Integritet**: Feil i supportlogger eller kundekonfigurasjoner kan gi driftsstans hos kunder og svekke bevisverdien av logger ved hendelser.
- **Tilgjengelighet**: 24/7-helpdesk og drift av tidskritiske kommunale systemer er kontraktsfestet gjennom SLA-er med oppetidsgaranti og responstidskrav.

## 4. Interessenter og krav

| Interessent | Krav/forventning | Kilde |
|---|---|---|
| Kunder (helse) | Vern av helseopplysninger, databehandleravtale | GDPR art. 9, 28; pasientjournalloven |
| Kunder (kommuner) | Oppetid, forsvarlig informasjonssikkerhet | SLA; forvaltningskrav, eForvaltningsforskriften |
| Datatilsynet | Etterlevelse av GDPR, meldeplikt ved brudd | GDPR art. 33–34 |
| NSM / sektormyndigheter | Grunnleggende sikkerhetsnivå; mulig NIS2-plikt | Digitalsikkerhetsloven (se kap. 06) |
| Eiere/ledelse | Lønnsomhet, omdømme, risikokontroll | Styrevedtak |

## 5. Avgrensning

Denne analysen omfatter kjerneprosessen kundesupporthåndtering og de tre bærende systemene. Interne støtteprosesser (HR, økonomi) og fysisk sikring av hovedkontoret berøres kun der de påvirker kjerneprosessen.
