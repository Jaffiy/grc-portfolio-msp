# 04.2 — Policy for tilgangsstyring

| | |
|---|---|
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Revideres årlig |
| **Hjemmel** | ISO/IEC 27001:2022 `A.5.15`, `A.5.16`, `A.5.17`, `A.5.18`, `A.8.2`, `A.8.5` · GDPR art. 32 · NSM GP 2.6 |
| **Adresserer** | [R1](../02-risikovurdering/risikoregister.md), [R5](../02-risikovurdering/risikoregister.md), [R8](../02-risikovurdering/risikoregister.md) via [T1](../02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang), [T4](../02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden), [T6](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) |

---

## 1. Formål og omfang

Sikre at tilgang til Mjøsdatas og kundenes systemer og data gis etter tjenstlig behov, kan spores til enkeltpersoner, og fjernes når behovet opphører.

Policyen gjelder alle ansatte, innleide konsulenter og systemkontoer i alle miljøer Mjøsdata administrerer — både egne og kunders.

---

## 2. Prinsipper

1. **Minste privilegium.** Ingen gis mer tilgang enn arbeidsoppgavene krever, og ikke lenger enn de krever den.
2. **Behovsprøving per kunde.** Tilgang til ett kundemiljø gir aldri automatisk tilgang til andre. Dette er den enkeltbestemmelsen som skiller en MSP med kontroll fra en uten: uten den blir ett kompromittert brukernavn til alle kunders problem.
3. **Individuell identitet.** Delte kontoer er forbudt. Systemkontoer skal ha navngitt eier og dokumentert formål.
4. **Sporbarhet.** All privilegert aktivitet logges og skal kunne knyttes til en fysisk person.

---

## 3. Krav

### 3.1 Autentisering

| Krav | Detalj |
|---|---|
| MFA | Obligatorisk for alle brukerkontoer i alle systemer, uten unntak for «interne» systemer |
| Phishing-resistent metode | Påkrevd for administratorer og supportpersonell (FIDO2/passkey). SMS og engangskoder aksepteres ikke for disse rollene |
| Passord | Minimum 16 tegn. **Ingen** tvungen periodisk utskifting. Kontroll mot kjente kompromitterte passord ved etablering og endring |
| Legacy-protokoller | Protokoller uten MFA-støtte skal være deaktivert i alle tenants |

> **Om passordreglene:** fravær av tvungen rotasjon er et bevisst valg i tråd med gjeldende anbefalinger fra NIST og NCSC. Periodisk utskifting gir målbart svakere passord fordi brukere kompenserer med forutsigbare varianter, og gir ingen dokumentert sikkerhetsgevinst når MFA og kompromitteringskontroll er på plass. Utskifting kreves derimot umiddelbart ved mistanke om kompromittering.

### 3.2 Privilegert tilgang

- Stående administratortilgang er **ikke tillatt**. Privilegier aktiveres just-in-time via Entra Privileged Identity Management, med tidsbegrensning, begrunnelse og godkjenning.
- Privilegert arbeid mot kundemiljøer utføres kun fra herdede administrasjonsarbeidsstasjoner (PAW). Samme maskin skal ikke brukes til e-post, nettlesing og administrasjon av kundemiljøer.
- Nødtilgang («break glass») etableres som to dedikerte kontoer med lagret legitimasjon i forseglet fysisk oppbevaring, unntatt fra betinget tilgang, med varsling ved enhver bruk.

### 3.3 Livssyklus

| Fase | Krav |
|---|---|
| **Onboarding** | Tilgang tildeles via rollemaler godkjent av nærmeste leder. Kundetilgang krever i tillegg godkjenning fra leveranseansvarlig for den aktuelle kunden |
| **Endring** | Rollebytte utløser **full re-vurdering** av tilganger, ikke akkumulering av gamle rettigheter oppå nye. Dette er det vanligste opphavet til rettighetsspredning over tid |
| **Offboarding** | Alle tilganger deaktiveres senest ved arbeidsforholdets slutt. Sjekklisten eies av HR med teknisk utførelse hos drift; gjennomføring bekreftes skriftlig innen 24 timer |
| **Innleide** | Tilgang gis alltid med utløpsdato satt til kontraktens slutt, og forlenges aktivt ved behov — aldri som standardvalg |

### 3.4 Revisjon

- **Kvartalsvis tilgangsrevisjon:** hver leder bekrefter sine ansattes tilganger, og leveranseansvarlige bekrefter kundetilganger. Manglende bekreftelse innen fristen medfører at tilgangen fjernes, ikke at den videreføres.
- Avvik lukkes innen 14 dager og rapporteres til sikkerhets- og personvernkomiteen.
- Systemkontoer og deres eierskap gjennomgås halvårlig.

---

## 4. Unntak

Unntak krever skriftlig, tidsbegrenset godkjenning fra sikkerhetsansvarlig, dokumenteres i avviksloggen med begrunnelse og kompenserende tiltak, og revurderes ved utløp. Et unntak som fornyes tre ganger skal behandles som et endringsbehov i policyen, ikke som et permanent unntak.

---

## 5. Brudd på policyen

Brudd behandles etter personalreglementet og meldes som sikkerhetshendelse etter [hendelsesresponsplanen](hendelsesresponsplan.md). Å melde fra om eget brudd behandles alltid mildere enn at bruddet oppdages av andre — det er en bevisst rutine, ikke en tilfeldighet, og henger sammen med rapporteringskulturen som bygges i [kap. 05](../05-sikkerhetskultur/opplaeringsprogram.md#4-atferdskampanje).
