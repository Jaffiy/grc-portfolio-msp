# Policy for tilgangsstyring

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Revisjon | Årlig |
| Hjemmel | ISO 27001 A.5.15, A.5.16, A.5.17, A.5.18, A.8.2 og A.8.5. GDPR artikkel 32. NSM Grunnprinsipper 2.6 |
| Adresserer | R1, R5 og R8, gjennom tiltak T1, T4 og T6 |

## 1. Formål og omfang

Formålet er å sikre at tilgang til Mjøsdatas og kundenes systemer og data gis etter tjenstlig behov, kan spores til enkeltpersoner, og fjernes når behovet opphører.

Policyen gjelder alle ansatte, innleide konsulenter og systemkontoer, i alle miljøer Mjøsdata administrerer. Det gjelder både selskapets egne miljøer og kundenes.

## 2. Prinsipper

Minste privilegium. Ingen får mer tilgang enn arbeidsoppgavene krever, og ikke lenger enn de krever den.

Behovsprøving per kunde. Tilgang til ett kundemiljø gir aldri automatisk tilgang til andre. Dette er den bestemmelsen som i praksis skiller en driftsleverandør med kontroll fra en uten. Uten den blir ett kompromittert brukernavn til alle kunders problem.

Individuell identitet. Delte kontoer er ikke tillatt. Systemkontoer skal ha en navngitt eier og et dokumentert formål.

Sporbarhet. All privilegert aktivitet logges, og skal kunne knyttes til en fysisk person.

## 3. Krav

### Autentisering

MFA er obligatorisk for alle brukerkontoer i alle systemer, også de som oppfattes som interne.

Administratorer og supportpersonell skal bruke phishing-resistente metoder, altså FIDO2 eller passkey. Engangskoder på SMS godtas ikke for disse rollene.

Passord skal være minst 16 tegn. Det er ingen tvungen periodisk utskifting. Nye passord kontrolleres mot lister over kjente kompromitterte passord.

Protokoller som ikke støtter MFA skal være deaktivert.

At vi ikke krever periodisk bytte av passord er et bevisst valg, i tråd med gjeldende anbefalinger fra blant annet NIST og britiske NCSC. Tvungen utskifting gir målbart svakere passord, fordi folk kompenserer med forutsigbare varianter, og gevinsten er ikke dokumentert når MFA og kompromitteringskontroll er på plass. Bytte kreves derimot umiddelbart ved mistanke om at et passord er kompromittert.

### Privilegert tilgang

Stående administratortilgang er ikke tillatt. Privilegier aktiveres ved behov gjennom Entra Privileged Identity Management, med tidsbegrensning, begrunnelse og godkjenning.

Privilegert arbeid mot kundemiljøer gjøres bare fra herdede administrasjonsarbeidsstasjoner. Den samme maskinen skal ikke brukes til e-post, nettlesing og administrasjon av kundemiljøer.

Det opprettes to kontoer for nødtilgang, med legitimasjon oppbevart forseglet fysisk. Disse er unntatt fra betinget tilgang, og all bruk utløser varsling.

### Livssyklus

Ved onboarding tildeles tilgang gjennom rollemaler som er godkjent av nærmeste leder. Tilgang til et kundemiljø krever i tillegg godkjenning fra leveranseansvarlig for den kunden.

Ved rollebytte gjøres en full ny vurdering av tilgangene. Nye rettigheter legges ikke oppå de gamle. Akkumulering ved rollebytte er den vanligste grunnen til at rettigheter sprer seg over tid.

Ved offboarding deaktiveres alle tilganger senest den dagen arbeidsforholdet slutter. Sjekklisten eies av HR, drift utfører det tekniske, og gjennomføringen bekreftes skriftlig innen 24 timer.

Innleide får alltid tilgang med utløpsdato satt til kontraktens slutt. Forlengelse skal være en aktiv handling, ikke standardvalget.

### Revisjon

Hvert kvartal bekrefter hver leder tilgangene til sine egne ansatte, og leveranseansvarlige bekrefter kundetilgangene. Blir en tilgang ikke bekreftet innen fristen, fjernes den. Den videreføres altså ikke automatisk.

Avvik lukkes innen 14 dager og rapporteres til sikkerhets- og personvernkomiteen. Systemkontoer og eierskapet til dem gjennomgås hvert halvår.

## 4. Unntak

Unntak krever skriftlig og tidsbegrenset godkjenning fra sikkerhetsansvarlig. De dokumenteres i avviksloggen med begrunnelse og kompenserende tiltak, og vurderes på nytt ved utløp. Et unntak som fornyes tre ganger bør behandles som et behov for å endre policyen, ikke som et permanent unntak.

## 5. Brudd på policyen

Brudd behandles etter personalreglementet, og meldes som sikkerhetshendelse etter [hendelsesresponsplanen](hendelsesresponsplan.md).

Å melde fra om eget brudd behandles alltid mildere enn at bruddet blir oppdaget av andre. Det er en bevisst rutine, og den henger sammen med rapporteringskulturen som bygges gjennom opplæringsprogrammet.
