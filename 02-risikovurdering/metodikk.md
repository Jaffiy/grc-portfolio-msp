# 02.1 — Risikovurderingsmetodikk

| | |
|---|---|
| **Dokument** | Metodikk for risikovurdering |
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Revideres årlig |
| **Hjemmel** | ISO/IEC 27005:2022; ISO/IEC 27001:2022 pkt. 6.1.2–6.1.3; NSM Grunnprinsipper for IKT-sikkerhet 2.1 |
| **Leser videre** | [Risikoregister](risikoregister.md) · [Tiltaksplan](tiltaksplan.md) |

> Skalaene og akseptkriteriene under er vedtatt **før** analysen ble gjennomført. Dette er hele poenget med å dokumentere en metodikk: uten forhåndsdefinerte kriterier blir risikonivåer etterrasjonalisering av konklusjoner man allerede hadde, og vurderingene lar seg verken etterprøve eller sammenligne over tid. ISO/IEC 27001 pkt. 6.1.2 krever nettopp at kriteriene fastsettes og vedlikeholdes.

---

## 1. Tilnærming

Risiko vurderes **hendelsesbasert**: vi identifiserer uønskede hendelser der en *trussel* utnytter en *sårbarhet* og rammer en *informasjonsverdi*. Hver risiko vurderes for sannsynlighet (S) og konsekvens (K).

**Risikonivå = Sannsynlighet × Konsekvens**, presentert i en 5×5-matrise.

### 1.1 Hvordan konsekvens fastsettes

Konsekvens vurderes separat for hver sikkerhetsegenskap — konfidensialitet (K), integritet (I) og tilgjengelighet (T) — og **høyeste verdi styrer samlet konsekvens**. Begrunnelsen er at et sikkerhetsbrudd må håndteres ut fra sin alvorligste virkning; et snitt ville skjult den dimensjonen som faktisk gjør skade.

**Unntak — etterlevelsesrisiko:** Enkelte risikoer har sin vesentligste virkning i den juridiske eller omdømmemessige dimensjonen uten å utgjøre et brudd på K, I eller T i seg selv. Manglende evne til å oppdage og melde et personvernbrudd er det typiske eksempelet: selve prosessvikten kompromitterer ingen data, men utløser gebyr og tillitstap.

For slike risikoer settes konsekvensen **direkte fra den juridiske/omdømmemessige kolonnen i konsekvensskalaen**, og risikoen merkes med `E` (etterlevelse) i registeret. KIT-verdiene oppgis fortsatt, men er ikke styrende. Dette er en bevisst utvidelse av modellen framfor en tilpasning av tallene — alternativet, å presse etterlevelsesrisiko inn i en KIT-form den ikke passer i, gir enten systematisk undervurdering eller udokumenterte hopp i vurderingen.

### 1.2 Hva vurderingene bygger på

Sannsynlighet baseres på trusselbildet for norske SMB-er og MSP-er (NSM *Risiko*, nasjonale og kommersielle trusselvurderinger), bransjeerfaring og systemenes faktiske eksponering. Konsekvens baseres på kontraktsforpliktelser (SLA), regulatorisk eksponering (GDPR) og omsetningstall.

**Vurderingene er ekspertbaserte, ikke statistiske.** Med ett års hendelsesdata fra én virksomhet på 45 ansatte finnes ikke grunnlag for frekvensberegning. Skalaene er derfor kalibrert mot beskrevne kriterier, og vurderingene gjennomføres i gruppe (se pkt. 5) nettopp for å dempe enkeltpersoners skjevheter.

---

## 2. Sannsynlighetsskala

| Nivå | Betegnelse | Kriterium |
|:---:|---|---|
| **1** | Svært lav | Forventes sjeldnere enn hvert 10. år |
| **2** | Lav | Kan inntreffe i løpet av 5–10 år |
| **3** | Moderat | Kan inntreffe i løpet av 1–5 år |
| **4** | Høy | Forventes å inntreffe årlig |
| **5** | Svært høy | Forventes å inntreffe flere ganger årlig |

---

## 3. Konsekvensskala

| Nivå | Betegnelse | Økonomisk | Personopplysninger / juridisk | Omdømme / kunde |
|:---:|---|---|---|---|
| **1** | Ubetydelig | < 100 000 kr | Ingen personopplysninger berørt | Ingen merkbar effekt |
| **2** | Lav | 100 000 – 500 000 kr | Få registrerte, ikke-sensitive data | Enkeltklager |
| **3** | Moderat | 0,5 – 2 mill. kr | Mange registrerte, eller meldepliktig brudd (art. 33) | Negativ lokal omtale; enkeltkunder vurderer exit |
| **4** | Alvorlig | 2 – 10 mill. kr | Særlige kategorier (art. 9) berørt; sannsynlig overtredelsesgebyr | Tap av nøkkelkunder, SLA-erstatninger |
| **5** | Kritisk | > 10 mill. kr | Omfattende brudd med art. 9-data; gebyr og erstatningskrav | Virksomhetens eksistens truet |

**Kalibrering mot virksomhetens størrelse:** nivå 5 (> 10 mill. kr) tilsvarer en vesentlig andel av årsomsetningen for en virksomhet med 45 ansatte. At flere risikoer likevel havner på konsekvens 4–5 er ikke inflasjon, men en direkte følge av MSP-modellen: Mjøsdata bærer risiko på vegne av alle kundene sine samtidig, og et brudd multipliseres derfor gjennom kundeporteføljen. Se [kap. 01 pkt. 3](../01-virksomhetskontekst/virksomhetskontekst.md#3-hvorfor-informasjonssikkerhet-er-forretningskritisk).

---

## 4. Risikoakseptkriterier

| Risikonivå (S×K) | Klassifisering | Håndtering |
|:---:|---|---|
| **1–4** | 🟢 Lav | Aksepteres. Overvåkes ved årlig gjennomgang |
| **5–9** | 🟡 Moderat | Aksepteres midlertidig. Tiltak vurderes i neste budsjettperiode; iverksettes tidligere dersom kostnaden er lav |
| **10–14** | 🟠 Høy | Skal behandles. Tiltaksplan innen 3 måneder |
| **15–25** | 🔴 Svært høy | Uakseptabel. Strakstiltak og rapportering til daglig leder |

**Krav til restrisiko:** etter tiltak skal ingen risiko ligge høyere enn **moderat**. Restrisiko på moderat nivå krever formell, dokumentert aksept fra daglig leder etter innstilling fra sikkerhetsansvarlig. Restrisiko på lavt nivå aksepteres administrativt.

**Estimering av restrisiko:** restrisiko oppgis alltid som et nytt **S×K-par**, ikke bare som et produkt. Et tiltak virker enten på sannsynligheten (reduserer muligheten for at hendelsen inntreffer) eller på konsekvensen (begrenser skadeomfanget når den inntreffer) — og hvilken av delene som endres er den faktiske begrunnelsen for tiltaket. Et tall alene skjuler denne begrunnelsen og lar seg ikke etterprøve i revisjon.

---

## 5. Roller og gjennomføring

| Rolle | Hvem | Ansvar |
|---|---|---|
| **Risikoeier** | Daglig leder | Øverste ansvar; delegert per risiko til prosesseiere. Beslutter aksept av restrisiko |
| **Fasilitator** | Sikkerhetsansvarlig (CISO-funksjon) | Metodikk, gjennomføring, dokumentasjon, innstilling til aksept |
| **Deltakere** | Leder support, driftsansvarlig Azure, personvernkontakt | Fagvurderinger innen egne områder |

**Frekvens:** full gjennomgang årlig, samt ved vesentlige endringer i systemlandskap, kundeportefølje eller trusselbilde. Nye risikoer identifisert gjennom hendelser føres inn løpende via [læringsfasen i hendelsesresponsplanen](../04-isms/hendelsesresponsplan.md#44-læring).

---

## 6. Kilder

- ISO/IEC 27005:2022 — *Guidance on managing information security risks*
- ISO/IEC 27001:2022 — pkt. 6.1.2 (risikovurdering) og 6.1.3 (risikohåndtering)
- NSM: *Grunnprinsipper for IKT-sikkerhet 2.1*
- NSM: *Risiko* (årlig nasjonal trusselvurdering)
- Datatilsynet: veileder om risikovurdering og personvernkonsekvensvurdering
