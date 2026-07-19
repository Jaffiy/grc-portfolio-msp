# Policy for tilgangsstyring

| | |
|---|---|
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 1.0 · Gjelder fra 01.09.2026 · Revideres årlig |
| **Hjemmel** | ISO 27001 A.5.15–A.5.18, A.8.2, A.8.5; GDPR art. 32; risikoregister R1, R5, R8 |

## 1. Formål og omfang

Sikre at tilgang til Mjøsdatas og kunders systemer og data gis etter tjenstlig behov, kan spores til enkeltpersoner, og fjernes når behovet opphører. Gjelder alle ansatte, innleide og systemkontoer i alle miljøer Mjøsdata administrerer.

## 2. Prinsipper

1. **Minste privilegium:** Ingen gis mer tilgang enn arbeidsoppgavene krever.
2. **Behovsprøving per kunde:** Tilgang til ett kundemiljø gir aldri automatisk tilgang til andre.
3. **Individuell identitet:** Delte kontoer er forbudt. Systemkontoer har navngitt eier.
4. **Sporbarhet:** All privilegert aktivitet logges og kan knyttes til person.

## 3. Krav

### Autentisering
- MFA er obligatorisk for alle brukerkontoer i alle systemer. Administratorer og supportpersonell skal bruke phishing-resistent metode (FIDO2/passkey).
- Passord: minimum 16 tegn, ingen tvungen periodisk utskifting, kontroll mot kjente kompromitterte passord ved etablering.
- Legacy-protokoller uten MFA-støtte skal være deaktivert.

### Privilegert tilgang
- Stående administratortilgang er ikke tillatt; privilegier aktiveres just-in-time via Entra PIM med tidsbegrensning og begrunnelse.
- Privilegert arbeid mot kundemiljøer utføres kun fra herdede admin-arbeidsstasjoner (PAW).

### Livssyklus
- **Onboarding:** Tilgang tildeles via rollemaler godkjent av nærmeste leder; kundetilgang godkjennes i tillegg av leveranseansvarlig for kunden.
- **Endring:** Rollebytte utløser full re-vurdering, ikke akkumulering av gamle rettigheter.
- **Offboarding:** Alle tilganger deaktiveres senest ved arbeidsforholdets slutt; sjekkliste eies av HR med teknisk utførelse hos drift, bekreftes innen 24 timer.

### Revisjon
- Kvartalsvis tilgangsrevisjon: hver leder bekrefter sine ansattes tilganger; leveranseansvarlige bekrefter kundetilganger.
- Avvik lukkes innen 14 dager og rapporteres til sikkerhets- og personvernkomiteen.

## 4. Unntak

Unntak krever skriftlig, tidsbegrenset godkjenning fra sikkerhetsansvarlig, dokumenteres i avvikslogg og revurderes ved utløp.

## 5. Brudd på policyen

Brudd behandles etter personalreglementet og meldes som sikkerhetshendelse etter hendelsesresponsplanen.
