# NIS2 / digitalsikkerhetsloven — omfangsvurdering for Mjøsdata AS

*Formål: vurdere om og hvordan Mjøsdata treffes av NIS2-direktivet slik det gjennomføres i norsk rett (digitalsikkerhetsloven med forskrifter), og hva det betyr for sikkerhetsprogrammet. Regelverket er under utvikling — vurderingen angir metode og må oppdateres mot endelig forskrift.*

## 1. Hvorfor spørsmålet er relevant

NIS2 utvider virkeområdet fra det opprinnelige NIS-direktivet til å omfatte blant annet **«managed service providers» (MSP) og «managed security service providers» (MSSP)** som egne kategorier av digitale tjenester. En norsk MSP kan dermed bli direkte pliktsubjekt — ikke bare indirekte berørt via kundenes leverandørkrav.

## 2. Omfangsvurdering

| Kriterium | Vurdering for Mjøsdata |
|---|---|
| **Tjenestetype** | IT-drift, skyadministrasjon og sikkerhetstjenester = MSP/MSSP-kategorien i NIS2 vedlegg — treffer |
| **Størrelse** | 45 ansatte → over grensen for mellomstor virksomhet (≥ 50 ansatte **eller** > 10 mill. € omsetning/balanse). Med ~45 ansatte må omsetningen sjekkes; vekst kan tippe vurderingen. Size-cap-regelen må vurderes konkret |
| **Kundeprofil** | Drift for kommuner og helsevirksomheter — sektorer som selv er omfattet; forsterker både direkte og indirekte eksponering |
| **Sannsynlig klassifisering** | **Viktig virksomhet** («important entity») dersom omfattet — tilsyn i etterkant, men samme grunnkrav som vesentlige virksomheter |

**Konklusjon:** Mjøsdata bør planlegge som om virksomheten blir omfattet. Selv i scenarioet der størrelseskriteriet ikke slår inn, vil kommunale og helsekunder videreføre NIS2-krav kontraktuelt (leverandørkjedesikkerhet er et eksplisitt NIS2-krav hos kundene). Kostnaden ved å være forberedt er lav; kostnaden ved å ikke være det er tapte anbud.

## 3. Kravene — og hvor Mjøsdata allerede er dekket

NIS2 art. 21 krever risikostyringstiltak innen ti områder. Gap-visning mot dette prosjektets leveranser:

| NIS2-krav (art. 21) | Dekket av | Gap |
|---|---|---|
| Risikoanalyse og sikkerhetspolicyer | Kap. 02 (metodikk, register, plan) | Formalisere årlig syklus med ledelsesgodkjenning |
| Hendelseshåndtering | Hendelsesresponsplan (kap. 04) | Innarbeide varslingsfrister til myndighet (24 t tidlig varsel / 72 t oppdatering / 1 mnd sluttrapport) |
| Kontinuitet, backup, kriseberedskap | T3 (geo-redundans, immutable backup) | Dokumentert BCP/DRP med RTO/RPO per kunde­kategori |
| Leverandørkjedesikkerhet | Delvis (art. 28-avtaler, kap. 03) | Systematisk leverandørrisikovurdering — også av *egne* verktøyleverandører (RMM-verktøy!) |
| Sikkerhet i anskaffelse, utvikling, drift | T7 (baseline, pentest) | Sikkerhetskrav i anskaffelsesrutiner |
| Evaluering av tiltakenes effekt | KPI-er i kap. 05; restrisiko i kap. 02 | Samlet årlig effektivitetsgjennomgang |
| Cyberhygiene og opplæring | Kap. 05 | — |
| Kryptografi | T5, A.8.24 | Kryptopolicy (algoritmer, nøkkelhåndtering) |
| Personellsikkerhet og tilgangsstyring | Policy for tilgangsstyring (kap. 04) | Bakgrunnssjekk-rutine ved ansettelse |
| MFA og sikret kommunikasjon | T1 | — |

**Ledelsesansvar:** NIS2 gjør styret/ledelsen personlig ansvarlig for å godkjenne og følge opp risikostyringen, og krever opplæring av ledelsen. Dette er allerede reflektert i styringsmodellen (kvartalsrapportering, årlig styresak) og ledermodulen i opplæringsprogrammet.

## 4. Varslingsplikt

NIS2 innfører trestegs varsling til myndighet ved vesentlige hendelser: **tidlig varsel innen 24 timer**, oppdatert vurdering innen 72 timer, sluttrapport innen én måned. Dette er strengere og bredere enn GDPR art. 33 (som kun gjelder personopplysninger) og er innarbeidet i varslingsmatrisen i hendelsesresponsplanen.

## 5. Anbefalt handlingsplan

1. **Nå:** Følge gjennomføringen av digitalsikkerhetsloven og forskrifter; avklare sektormyndighet og registreringsplikt
2. **0–3 mnd:** Lukke gap med lav kostnad — kryptopolicy, BCP-dokumentasjon, varslingsfrister inn i IR-planen
3. **3–6 mnd:** Etablere leverandørrisikoprogram med særskilt vurdering av fjernstyrings-/RMM-verktøy
4. **Løpende:** Bruke NIS2-beredskap aktivt i salg mot kommunal- og helsesegmentet — etterlevelse som konkurransefortrinn, ikke bare kostnad
