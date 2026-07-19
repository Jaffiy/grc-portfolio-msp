# Risikovurderingsmetodikk

*Metodikken bygger på ISO/IEC 27005:2022 og er tilpasset en virksomhet på Mjøsdatas størrelse. Skalaene og akseptkriteriene under er vedtatt før analysen ble gjennomført, slik at vurderingene er etterprøvbare og konsistente.*

## 1. Tilnærming

Risiko vurderes hendelsesbasert: vi identifiserer uønskede hendelser der en **trussel** utnytter en **sårbarhet** og rammer en **informasjonsverdi**. Hver risiko vurderes for sannsynlighet og konsekvens, og konsekvens vurderes separat for konfidensialitet (K), integritet (I) og tilgjengelighet (T) — høyeste verdi styrer samlet konsekvens.

Risikonivå = Sannsynlighet × Konsekvens, presentert i en 5×5-matrise.

## 2. Sannsynlighetsskala

| Nivå | Betegnelse | Kriterium |
|---|---|---|
| 1 | Svært lav | Forventes sjeldnere enn hvert 10. år |
| 2 | Lav | Kan inntreffe i løpet av 5–10 år |
| 3 | Moderat | Kan inntreffe i løpet av 1–5 år |
| 4 | Høy | Forventes å inntreffe årlig |
| 5 | Svært høy | Forventes å inntreffe flere ganger årlig |

Vurderingen baseres på trusselbildet for norske SMB-er og MSP-er (NSM Risiko, Telenor/mnemonic trusselrapporter), bransjeerfaring og systemenes eksponering.

## 3. Konsekvensskala

| Nivå | Betegnelse | Økonomisk | Personopplysninger / juridisk | Omdømme / kunde |
|---|---|---|---|---|
| 1 | Ubetydelig | < 100 000 kr | Ingen personopplysninger berørt | Ingen merkbar effekt |
| 2 | Lav | 100 000 – 500 000 kr | Få registrerte, ikke-sensitive data | Enkeltklager |
| 3 | Moderat | 0,5 – 2 mill. kr | Mange registrerte eller meldepliktig brudd (art. 33) | Negativ lokal omtale, enkeltkunder vurderer exit |
| 4 | Alvorlig | 2 – 10 mill. kr | Særlige kategorier (art. 9) berørt; sannsynlig overtredelsesgebyr | Tap av nøkkelkunder, SLA-erstatninger |
| 5 | Kritisk | > 10 mill. kr | Omfattende brudd med art. 9-data; gebyr og erstatningskrav | Virksomhetens eksistens truet |

## 4. Risikoakseptkriterier

| Risikonivå (S×K) | Klassifisering | Håndtering |
|---|---|---|
| 1–4 | Lav | Aksepteres. Overvåkes ved årlig gjennomgang |
| 5–9 | Moderat | Aksepteres midlertidig; tiltak vurderes i neste budsjettperiode |
| 10–14 | Høy | Skal behandles; tiltaksplan innen 3 måneder |
| 15–25 | Svært høy | Uakseptabel; strakstiltak og ledelsesrapportering |

Restrisiko etter tiltak skal ned på nivå **moderat eller lavere**, og aksept av restrisiko besluttes av daglig leder etter innstilling fra sikkerhetsansvarlig.

## 5. Roller

- **Risikoeier:** daglig leder (øverste ansvar), delegert per risiko til prosesseiere
- **Fasilitator:** sikkerhetsansvarlig/CISO-funksjon
- **Deltakere:** leder support, driftsansvarlig Azure, personvernkontakt

## 6. Kilder

- ISO/IEC 27005:2022 — Information security risk management
- NSM Grunnprinsipper for IKT-sikkerhet 2.1
- NSM Risiko (årlig trusselvurdering)
- Datatilsynets veiledere om risikovurdering av personopplysninger
