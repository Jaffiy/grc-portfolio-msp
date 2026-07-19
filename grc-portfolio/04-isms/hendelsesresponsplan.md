# Hendelsesresponsplan

| | |
|---|---|
| **Dokumenteier** | Sikkerhetsansvarlig |
| **Versjon** | 1.0 · Øves minimum årlig (tabletop) |
| **Hjemmel** | ISO 27001 A.5.24–A.5.28; GDPR art. 33–34; SLA-forpliktelser; digitalsikkerhetsloven (varslingsplikt, se kap. 06) |

## 1. Formål

Sikre at sikkerhetshendelser oppdages, håndteres og læres av på en måte som begrenser skade for Mjøsdata **og kundene**, og som oppfyller alle varslingsplikter. Som MSP har Mjøsdata et dobbelt ansvar: egen hendelseshåndtering og varsling/bistand til berørte kunder.

## 2. Definisjoner og alvorlighetsgrader

| Grad | Kriterium | Eksempel | Responstid |
|---|---|---|---|
| **Kritisk (S1)** | Aktiv kompromittering med kundepåvirkning, eller løsepengevirus | Angriper i kundemiljø via Mjøsdatas verktøy | Umiddelbart, 24/7 |
| **Alvorlig (S2)** | Bekreftet brudd uten (foreløpig) kundepåvirkning | Kompromittert intern konto | < 1 time i arbeidstid, < 4 utenfor |
| **Moderat (S3)** | Mistenkelig aktivitet, avgrenset | Vellykket phishing-klikk uten bekreftet fotfeste | < 8 timer |
| **Lav (S4)** | Policybrudd/avvik uten aktiv trussel | Ukryptert enhet mistet, men fjernslettet | < 3 virkedager |

## 3. Organisering

- **Hendelsesleder:** Sikkerhetsansvarlig (stedfortreder: driftsansvarlig)
- **Teknisk respons:** Driftsteam + eventuelt ekstern IR-partner (rammeavtale, kontaktinfo i vedlegg)
- **Personvernvurdering:** Personvernkontakt
- **Kommunikasjon:** Daglig leder eier all ekstern kommunikasjon (kunder, Datatilsynet, media)

Kontaktliste med døgnnumre vedlikeholdes utenfor produksjonsmiljøet (offline-kopi), slik at den er tilgjengelig selv ved totalt systemtap.

## 4. Fasene (basert på NIST-livssyklusen)

### 4.1 Forberedelse
Logging sentralisert og beskyttet mot sletting; immutable backup (T3); øvelser årlig; denne planen kjent for alle ansatte.

### 4.2 Deteksjon og analyse
- Kilder: Defender for Cloud-varsler, EDR, phishing-rapportering fra ansatte, kundemeldinger
- Hendelsesleder klassifiserer (S1–S4), oppretter hendelseslogg med tidslinje (alle tidspunkter i UTC)
- **Bevissikring fra første time:** minnedump og diskbilde vurderes *før* opprydding ved S1/S2; alle handlinger logges med hvem/hva/når (kontinuitetsprinsippet — avgjørende hvis saken ender hos politi eller forsikring)

### 4.3 Inndemming, utrydding, gjenoppretting
- Kortsiktig inndemming: isolere berørte kontoer/segmenter — segmenteringen fra T4 er forutsetningen for at dette er mulig per kunde
- Utrydding: fjerne fotfeste, rotere hemmeligheter, patche inngangsvektor
- Gjenoppretting: fra verifisert ren backup; forsterket overvåking i 30 dager etter

### 4.4 Læring
Post-hendelsesrapport innen 10 virkedager: tidslinje, rotårsak, hva fungerte/sviktet, tiltak inn i risikoregisteret. Blame-fri gjennomgang.

## 5. Varslingsmatrise

| Situasjon | Hvem varsles | Frist | Ansvarlig |
|---|---|---|---|
| Personvernbrudd der Mjøsdata er databehandler | Berørt kunde (behandlingsansvarlig) | **Uten ugrunnet opphold** — internt mål: < 24 t | Hendelsesleder |
| Personvernbrudd der Mjøsdata er behandlingsansvarlig, med risiko | Datatilsynet | **72 timer** fra kjennskap | Personvernkontakt |
| Høy risiko for registrerte | De registrerte | Uten ugrunnet opphold | Daglig leder |
| Hendelse hos virksomhet omfattet av digitalsikkerhetsloven | Sektormyndighet/NSM (varslingsplikt) | Iht. forskrift (se kap. 06) | Hendelsesleder |
| SLA-relevant driftsavbrudd | Berørte kunder | Iht. SLA | Leveranseansvarlig |
| Mistanke om straffbart forhold | Politiet (og ev. forsikring) | Etter beslutning av daglig leder | Daglig leder |

**Bruddvurderingsskjema (art. 33):** hendelseslogg skal alltid dokumentere vurderingen av om brudd er meldepliktig — også når konklusjonen er nei. «Vurdert, ikke meldepliktig, fordi …» er dokumentasjonen som beskytter virksomheten i ettertid.

## 6. Scenariokort (utdrag)

**Scenario: Løsepengevirus oppdaget i ett kundemiljø**
1. Isoler kundemiljøet (nettverkssegment av) — ikke slå av maskiner (bevarer minnebevis)
2. Aktiver S1-respons; varsle hendelsesleder og daglig leder
3. Sjekk spredning til admin-nett og andre kunder (verktøykjeden!)
4. Bevissikring: minnedump av berørte servere, sikre logger
5. Varsle berørt kunde < 24 t; vurder art. 33-plikt (kundens og ev. egen)
6. Gjenopprett fra immutable backup etter verifikasjon; roter all privilegert tilgang
