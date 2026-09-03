# Metodikk for risikovurdering

| | |
|---|---|
| Dokumenteier | Sikkerhetsansvarlig |
| Godkjent av | Daglig leder |
| Versjon | 2.0, gjeldende fra 1. september 2026 |
| Revisjon | Årlig |
| Hjemmel | ISO/IEC 27005:2022, ISO/IEC 27001:2022 punkt 6.1.2 og 6.1.3 |

Skalaene og akseptkriteriene i dette dokumentet ble vedtatt før analysen ble gjennomført. Det er hele poenget med å skrive ned en metodikk. Uten kriterier bestemt på forhånd blir risikonivåene i praksis en etterrasjonalisering av konklusjoner man allerede hadde, og vurderingene kan verken etterprøves eller sammenlignes fra år til år.

## 1. Fremgangsmåte

Risiko vurderes hendelsesbasert. Vi identifiserer uønskede hendelser der en trussel utnytter en sårbarhet og rammer en informasjonsverdi. Hver hendelse vurderes for sannsynlighet og konsekvens, og risikonivået er produktet av de to. Resultatet vises i en matrise med fem trinn på hver akse.

### Hvordan konsekvens fastsettes

Konsekvens vurderes separat for konfidensialitet, integritet og tilgjengelighet, og den høyeste av de tre styrer den samlede konsekvensen. Begrunnelsen er at et sikkerhetsbrudd må håndteres ut fra den alvorligste virkningen sin. Et gjennomsnitt ville skjult akkurat den dimensjonen som gjør skade.

Det finnes ett unntak. Noen risikoer har sin vesentligste virkning juridisk eller omdømmemessig uten at de i seg selv innebærer et brudd på konfidensialitet, integritet eller tilgjengelighet. Manglende evne til å oppdage og melde et personvernbrudd er det typiske eksempelet. Selve prosessvikten kompromitterer ingen data, men den utløser gebyr og tap av tillit.

For slike risikoer settes konsekvensen direkte fra den juridiske kolonnen i konsekvensskalaen, og risikoen merkes med E for etterlevelse i registeret. Verdiene for konfidensialitet, integritet og tilgjengelighet oppgis fortsatt, men de er ikke styrende. Jeg har valgt å utvide modellen i stedet for å justere tallene, siden alternativet enten gir systematisk undervurdering av etterlevelsesrisiko eller udokumenterte hopp i vurderingen.

### Grunnlaget for vurderingene

Sannsynlighet bygger på trusselbildet for norske små og mellomstore virksomheter og driftsleverandører, slik det beskrives i NSMs årlige risikorapport og tilsvarende vurderinger, sammen med bransjeerfaring og hvor eksponert systemene faktisk er. Konsekvens bygger på kontraktsforpliktelsene i SLA-ene, regulatorisk eksponering etter GDPR, og omsetningstallene.

Vurderingene er ekspertbaserte, ikke statistiske. Med ett års hendelsesdata fra én virksomhet på 45 ansatte finnes det ikke grunnlag for å regne frekvenser. Skalaene er derfor kalibrert mot beskrevne kriterier, og vurderingene gjøres i gruppe for å dempe skjevheter hos enkeltpersoner.

## 2. Sannsynlighetsskala

| Nivå | Betegnelse | Kriterium |
|---|---|---|
| 1 | Svært lav | Forventes sjeldnere enn hvert tiende år |
| 2 | Lav | Kan inntreffe i løpet av fem til ti år |
| 3 | Moderat | Kan inntreffe i løpet av ett til fem år |
| 4 | Høy | Forventes å inntreffe årlig |
| 5 | Svært høy | Forventes å inntreffe flere ganger i året |

## 3. Konsekvensskala

| Nivå | Betegnelse | Økonomisk | Personopplysninger og juridisk | Omdømme og kunder |
|---|---|---|---|---|
| 1 | Ubetydelig | Under 100 000 kroner | Ingen personopplysninger berørt | Ingen merkbar effekt |
| 2 | Lav | 100 000 til 500 000 kroner | Få registrerte, ikke sensitive data | Enkeltklager |
| 3 | Moderat | 0,5 til 2 millioner | Mange registrerte, eller meldepliktig brudd etter artikkel 33 | Negativ lokal omtale, enkeltkunder vurderer å bytte |
| 4 | Alvorlig | 2 til 10 millioner | Særlige kategorier etter artikkel 9 berørt, sannsynlig overtredelsesgebyr | Tap av nøkkelkunder og erstatning etter SLA |
| 5 | Kritisk | Over 10 millioner | Omfattende brudd med artikkel 9-data, gebyr og erstatningskrav | Virksomhetens eksistens er truet |

Nivå 5 tilsvarer en vesentlig andel av årsomsetningen for en virksomhet med 45 ansatte. At flere risikoer likevel havner på nivå 4 og 5 er ikke inflasjon i skalaen, men følger av forretningsmodellen. Mjøsdata bærer risiko for alle kundene sine samtidig, og et brudd blir dermed multiplisert gjennom kundeporteføljen.

## 4. Akseptkriterier

| Risikonivå | Klassifisering | Håndtering |
|---|---|---|
| 1 til 4 | Lav | Aksepteres. Følges opp ved den årlige gjennomgangen |
| 5 til 9 | Moderat | Aksepteres midlertidig. Tiltak vurderes i neste budsjettperiode, og iverksettes tidligere dersom kostnaden er lav |
| 10 til 14 | Høy | Skal behandles. Tiltaksplan innen tre måneder |
| 15 til 25 | Svært høy | Uakseptabelt. Strakstiltak og rapportering til daglig leder |

Etter at tiltakene er gjennomført skal ingen risiko ligge høyere enn moderat. Restrisiko på moderat nivå krever dokumentert aksept fra daglig leder etter innstilling fra sikkerhetsansvarlig. Restrisiko på lavt nivå aksepteres administrativt.

Restrisiko oppgis alltid med både ny sannsynlighet og ny konsekvens, ikke bare som et produkt. Et tiltak virker enten forebyggende, ved å redusere sjansen for at hendelsen inntreffer, eller skadebegrensende, ved å redusere omfanget når den først skjer. Hvilken av delene som endres er selve begrunnelsen for tiltaket. Et enkelt tall skjuler det og kan ikke etterprøves i en revisjon.

## 5. Roller og gjennomføring

| Rolle | Hvem | Ansvar |
|---|---|---|
| Risikoeier | Daglig leder | Øverste ansvar, delegert per risiko til prosesseierne. Beslutter aksept av restrisiko |
| Fasilitator | Sikkerhetsansvarlig | Metodikk, gjennomføring, dokumentasjon og innstilling til aksept |
| Deltakere | Leder for support, driftsansvarlig for Azure, personvernkontakt | Fagvurderinger innenfor sine områder |

Full gjennomgang gjøres årlig, og ellers ved vesentlige endringer i systemlandskapet, kundeporteføljen eller trusselbildet. Nye risikoer som dukker opp gjennom hendelser føres inn løpende via læringsfasen i [hendelsesresponsplanen](../04-isms/hendelsesresponsplan.md).

## 6. Kilder

* ISO/IEC 27005:2022, Guidance on managing information security risks
* ISO/IEC 27001:2022, punkt 6.1.2 og 6.1.3
* NSM, Grunnprinsipper for IKT-sikkerhet 2.1
* NSM, Risiko, den årlige nasjonale trusselvurderingen
* Datatilsynets veileder om risikovurdering og personvernkonsekvensvurdering
