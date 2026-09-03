# 04.3 — Hendelsesresponsplan

| | |
|---|---|
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Øves minimum årlig (tabletop) |
| **Hjemmel** | ISO/IEC 27001:2022 `A.5.24`–`A.5.28` · GDPR art. 33–34 · SLA-forpliktelser · NSM GP 4.1–4.4 |
| **Adresserer** | [R9](../02-risikovurdering/risikoregister.md) direkte; konsekvensreduserende for alle risikoer via [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) |

> **Merknad om regelverk:** varslingsplikt etter en fremtidig norsk NIS2-gjennomføring er tatt inn i [varslingsmatrisen](#5-varslingsmatrise) som **betinget** rad. Mjøsdata er etter alt å dømme ikke pliktsubjekt etter gjeldende digitalsikkerhetslov, som gjennomfører NIS1. Se [kap. 06](../06-nis2/nis2-vurdering.md).

---

## 1. Formål

Sikre at sikkerhetshendelser oppdages, håndteres og læres av på en måte som begrenser skaden for Mjøsdata **og kundene**, og som oppfyller alle varslingsplikter innen frist.

Som MSP har Mjøsdata et dobbelt ansvar: egen hendelseshåndtering, og varsling og bistand til berørte kunder. Det andre er ofte det tidskritiske — kundens frister løper fra Mjøsdata varsler.

---

## 2. Definisjoner og alvorlighetsgrader

| Grad | Kriterium | Eksempel | Responstid |
|:---:|---|---|---|
| 🔴 **Kritisk (S1)** | Aktiv kompromittering med kundepåvirkning, eller løsepengevirus i noe miljø | Angriper i kundemiljø via Mjøsdatas fjernstyringsverktøy | Umiddelbart, 24/7 |
| 🟠 **Alvorlig (S2)** | Bekreftet brudd uten (foreløpig) påvist kundepåvirkning | Kompromittert intern konto med support-rettigheter | < 1 time i arbeidstid, < 4 timer utenfor |
| 🟡 **Moderat (S3)** | Mistenkelig aktivitet, avgrenset — eller ethvert mulig personvernbrudd | Vellykket phishing-klikk uten bekreftet fotfeste. **Tap av enhet med kundedata** | < 8 timer |
| 🟢 **Lav (S4)** | Policyavvik uten datainvolvering og uten aktiv trussel | Ulåst skjerm observert på kontoret; kryptert og fjernslettet enhet mistet, verifisert uten lokal kundedata | < 3 virkedager |

> **Om tap av utstyr.** Tap av en enhet som *kan* inneholde kundedata klassifiseres alltid som minimum **S3**, og utløser obligatorisk vurdering etter GDPR art. 33 — også når enheten er fjernslettet. Fjernsletting virker bare dersom enheten kommer på nett igjen, og er derfor ikke i seg selv dokumentasjon på at data ikke er eksponert. Først når [full diskkryptering (T9)](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) er verifisert utrullet, kan et enhetstap håndteres som S4 — kryptering gjør tapet til et utstyrstap i stedet for et databrudd. Dette er den praktiske grunnen til at T9 prioriteres høyt til tross for lavt risikonivå på [R7](../02-risikovurdering/risikoregister.md).

---

## 3. Organisering

| Rolle | Hvem | Ansvar |
|---|---|---|
| **Hendelsesleder** | Sikkerhetsansvarlig (stedfortreder: driftsansvarlig) | Klassifisering, koordinering, beslutning om eskalering |
| **Teknisk respons** | Driftsteam, ev. ekstern IR-partner på rammeavtale | Inndemming, utrydding, gjenoppretting, bevissikring |
| **Personvernvurdering** | Personvernkontakt | Vurdering etter art. 33–34, utkast til melding |
| **Kommunikasjon** | Daglig leder | Eier all ekstern kommunikasjon: kunder, Datatilsynet, media |

Kontaktliste med døgnnumre — internt, IR-partner, kundenes nødkontakter — vedlikeholdes **utenfor produksjonsmiljøet** i offline-kopi, slik at den er tilgjengelig ved totalt systemtap. En beredskapsplan som bare finnes i systemet den skal redde er ingen beredskapsplan.

---

## 4. Faser

Basert på NIST SP 800-61-livssyklusen, som er valgt framfor en egendefinert modell fordi den er gjenkjennelig for eksterne IR-partnere og forsikringsselskaper.

### 4.1 Forberedelse

Sentralisert og slettebeskyttet logging; immutable backup ([T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse)); årlig tabletop-øvelse med ledelsen; rammeavtale med ekstern IR-partner inngått **før** den trengs; planen kjent for alle ansatte gjennom [opplæringsprogrammet](../05-sikkerhetskultur/opplaeringsprogram.md).

### 4.2 Deteksjon og analyse

- **Kilder:** varsler fra Microsoft Defender for Cloud, EDR, phishing-rapportering fra ansatte, kundemeldinger, leverandørvarsler.
- Hendelsesleder klassifiserer (S1–S4) og oppretter hendelseslogg med tidslinje. **Alle tidspunkter føres i UTC** — blandede tidssoner i en tidslinje er en av de vanligste kildene til feilkonklusjoner i etterforskning.
- **Bevissikring fra første time:** ved S1 og S2 vurderes minnedump og diskbilde *før* opprydding. Alle handlinger logges med hvem, hva og når (kontinuitetsprinsippet) — avgjørende dersom saken ender hos politi eller forsikring, og umulig å rekonstruere i etterkant.

### 4.3 Inndemming, utrydding, gjenoppretting

| Steg | Innhold |
|---|---|
| **Kortsiktig inndemming** | Isolere berørte kontoer og nettverkssegmenter. [Segmenteringen fra T4](../02-risikovurdering/tiltaksplan.md#t4--segmentering-og-herding-av-msp-verktøykjeden) er forutsetningen for at dette lar seg gjøre per kunde framfor å ta ned alt |
| **Utrydding** | Fjerne fotfeste, rotere alle hemmeligheter og privilegerte legitimasjoner, patche inngangsvektoren |
| **Gjenoppretting** | Gjenoppretting fra verifisert ren backup. Forsterket overvåking i 30 dager etter — gjenkomst er vanlig når inngangsvektoren ikke er fullt forstått |

### 4.4 Læring

Post-hendelsesrapport innen **10 virkedager**: tidslinje, rotårsak, hva som fungerte og hva som sviktet, samt konkrete tiltak som føres inn i [risikoregisteret](../02-risikovurdering/risikoregister.md). Gjennomgangen er **blame-fri** — formålet er å finne ut hvorfor det var mulig, ikke hvem som gjorde det.

---

## 5. Varslingsmatrise

| Situasjon | Hvem varsles | Frist | Ansvarlig |
|---|---|---|---|
| Personvernbrudd der Mjøsdata er **databehandler** | Berørt kunde (behandlingsansvarlig) | **Uten ugrunnet opphold** — internt mål: **< 24 timer** | Hendelsesleder |
| Personvernbrudd der Mjøsdata er **behandlingsansvarlig**, med risiko for de registrerte | Datatilsynet | **72 timer** fra Mjøsdata ble kjent med bruddet | Personvernkontakt |
| Høy risiko for de registrertes rettigheter og friheter | De registrerte | Uten ugrunnet opphold | Daglig leder |
| SLA-relevant driftsavbrudd | Berørte kunder | Iht. den enkelte SLA | Leveranseansvarlig |
| Mistanke om straffbart forhold | Politiet, ev. forsikringsselskap | Etter beslutning av daglig leder | Daglig leder |
| *Betinget:* vesentlig hendelse dersom Mjøsdata blir omfattet av fremtidig NIS2-gjennomføring | Sektormyndighet / NSM | Tidlig varsel **24 t** → oppdatering **72 t** → sluttrapport **1 mnd** | Hendelsesleder |

> **Bruddvurderingsskjema (art. 33).** Hendelsesloggen skal alltid dokumentere vurderingen av om bruddet er meldepliktig — **også når konklusjonen er nei**. Formuleringen «vurdert, ikke meldepliktig, fordi …» med dato og signatur er den dokumentasjonen som beskytter virksomheten i ettertid. En manglende vurdering er et selvstendig avvik, uavhengig av om melding faktisk skulle vært sendt.

---

## 6. Scenariokort (utdrag)

<details>
<summary><strong>Scenario A: Løsepengevirus oppdaget i ett kundemiljø</strong></summary>

1. **Isoler** kundemiljøet på nettverksnivå — men **ikke slå av maskiner**: avslåing ødelegger minnebevis som ofte er eneste kilde til krypteringsnøkler og angriperverktøy.
2. **Aktiver S1-respons.** Varsle hendelsesleder og daglig leder.
3. **Sjekk spredning** til administrasjonsnettet og andre kundemiljøer — verktøykjeden er den kritiske veien.
4. **Bevissikring:** minnedump av berørte servere, sikre og eksporter logger før noe endres.
5. **Varsle berørt kunde innen 24 timer.** Vurder art. 33-plikt for kunden og eventuelt for Mjøsdata selv.
6. **Gjenopprett** fra immutable backup etter verifisering av at backupen er ren. Roter all privilegert legitimasjon.
7. **Forsterket overvåking** i 30 dager. Post-hendelsesrapport innen 10 virkedager.

</details>

<details>
<summary><strong>Scenario B: Kompromittert supportkonto oppdaget gjennom uvanlig innlogging</strong></summary>

1. **Deaktiver kontoen** og avslutt aktive sesjoner (token revocation — passordbytte alene stopper ikke en pågående sesjon).
2. **Klassifiser som S2**, eller S1 dersom kundemiljøer er berørt.
3. **Kartlegg** hva kontoen faktisk hadde tilgang til, og hva den har gjort i loggene. Her betaler [tilgangsrevisjonen (T6)](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon) seg: uten den er svaret «alt».
4. **Vurder personvernbrudd** per berørt kunde — dette er ofte flere separate vurderinger, ikke én.
5. **Gjenutsted** legitimasjon med phishing-resistent MFA før kontoen åpnes igjen.
6. **Læring:** var dette en kjent phishing-kampanje? Skal den inn som case i neste [simulering](../05-sikkerhetskultur/opplaeringsprogram.md#3-kanaler-og-frekvens)?

</details>

<details>
<summary><strong>Scenario C: Tap av bærbar enhet</strong></summary>

1. **Klassifiser som S3** (se [merknaden om utstyrstap](#2-definisjoner-og-alvorlighetsgrader)).
2. **Verifiser krypteringsstatus** for den konkrete enheten i Intune — ikke anta at policyen var i kraft på akkurat den maskinen.
3. **Initier fjernsletting** og deaktiver enhetens tilgangstokener.
4. **Vurder art. 33** basert på hva som faktisk var lagret lokalt. Ved verifisert full diskkryptering med enheten avslått er utfallet normalt «ikke meldepliktig» — men vurderingen dokumenteres uansett.
5. **Meld til politiet** ved mistanke om tyveri (nødvendig for forsikring).

</details>
