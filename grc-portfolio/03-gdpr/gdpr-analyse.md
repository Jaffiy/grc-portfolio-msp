# GDPR-analyse — Mjøsdata AS

## 1. Rolleanalyse: behandlingsansvarlig eller databehandler?

Det viktigste — og oftest oversette — GDPR-spørsmålet for en MSP er *rollen*. Mjøsdata opptrer i begge:

| Behandling | Mjøsdatas rolle | Konsekvens |
|---|---|---|
| Egne kunderegistre, kontrakter, fakturering (Salesforce) | **Behandlingsansvarlig** | Fullt ansvar for grunnlag, informasjon, sletting |
| Egne ansattdata (HR) | **Behandlingsansvarlig** | Som over |
| Drift av kunders systemer og data i Azure | **Databehandler** | Krever databehandleravtale (art. 28) med *hver* kunde; skal kun behandle etter dokumentert instruks |
| Bruk av Microsoft (Azure/365), Salesforce, Atlassian | Mjøsdata er kunde; leverandørene er **underdatabehandlere/databehandlere** | Databehandleravtaler og vurdering av tredjelandsoverføring (art. 44 flg.) |

Denne dobbeltrollen betyr at Mjøsdata må ha orden på **to avtalekjeder**: nedover mot egne leverandører og oppover mot egne kunder — inkludert plikten til å varsle kundene (behandlingsansvarlige) *uten ugrunnet opphold* ved brudd, slik at kundene kan overholde sin egen 72-timersfrist.

## 2. Sentrale forpliktelser og status

| Artikkel | Krav | Relevans for Mjøsdata | Tiltak |
|---|---|---|---|
| Art. 5 | Prinsipper: formålsbegrensning, dataminimering, lagringsbegrensning, integritet/konfidensialitet | Kundedata i Salesforce og persondata i supportlogger må minimeres og slettes etter definerte frister | Slette-/minimeringspolicy; automatisk sletting av logger etter 12 mnd der ikke annet kreves |
| Art. 6 / 9 | Behandlingsgrunnlag; særlige kategorier | Egne behandlinger hjemles i avtale (6(1)(b)) og berettiget interesse (6(1)(f)); helseklinikkers data (art. 9) behandles kun som databehandler etter instruks | Grunnlagsvurdering per behandling i behandlingsprotokollen |
| Art. 25 | Innebygd personvern | Nye kundeoppsett i Azure skal ha kryptering, minimert tilgang og logging som standard | Baseline-konfigurasjon (jf. tiltak T7) |
| Art. 28 | Databehandleravtaler | Kreves med alle kunder Mjøsdata drifter for, og mot Microsoft/Salesforce/Atlassian | Avtalerevisjon; standard DBA-mal |
| Art. 30 | Behandlingsprotokoll | Plikt både som ansvarlig (30(1)) og databehandler (30(2)) | Se utdrag i pkt. 3 |
| Art. 32 | Sikkerhet ved behandling | Kryptering, tilgangsstyring, testing — sammenfaller med tiltaksplanen i kap. 02 | T1, T5, T6, T7 |
| Art. 33–34 | Meldeplikt (72 t) og varsling av registrerte | Som databehandler: varsle kunden straks; som ansvarlig: melde Datatilsynet | Hendelsesresponsplan med bruddvurderingsskjema |
| Art. 35 | DPIA ved høy risiko | Drift av helseklinikkdata i sky kan utløse DPIA-plikt hos kunden; Mjøsdata må kunne bistå | DPIA-screening i pkt. 4 |
| Art. 37 | Personvernombud | Ikke åpenbart pliktig (privat virksomhet, ikke kjernevirksomhet i storskala særlige kategorier) — men **personvernkontakt** utpekes som god praksis | Rolle beskrevet i styringsmodellen |
| Art. 44 flg. | Overføring til tredjeland | Amerikanske skyleverandører: vurdere overføringsgrunnlag (adequacy/SCC) og konfigurere EU-datalagring | Velge EU-regioner i Azure; dokumentere overføringsvurdering |

## 3. Behandlingsprotokoll — utdrag (art. 30)

**Som behandlingsansvarlig:**

| Behandling | Formål | Kategorier registrerte/opplysninger | Grunnlag | Lagringstid | Mottakere |
|---|---|---|---|---|---|
| Kundeadministrasjon (Salesforce) | Avtaleoppfølging, support | Kontaktpersoner hos kunder; navn, e-post, telefon, saks­historikk | Art. 6(1)(b) | Avtaletid + 3 år | Salesforce (databehandler) |
| Fakturering | Regnskap | Kontaktpersoner; fakturadata | Art. 6(1)(c) (bokføringsloven) | 5 år | Regnskapsfører |

**Som databehandler (art. 30(2)):**

| Kunde(-kategori) | Behandling utført | Kategorier | Underdatabehandlere | Overføring tredjeland |
|---|---|---|---|---|
| Helseklinikker | Drift, backup, support av journal- og kontorsystemer | Pasientdata (art. 9) — kun etter instruks | Microsoft (Azure EU-region) | Nei (EU-lagring; SCC som fallback) |
| Kommuner | Drift av administrative systemer | Ansatt- og innbyggerdata | Microsoft | Nei |

## 4. DPIA-screening: skydrift av helseklinikkdata

Etter Datatilsynets liste over behandlinger som alltid krever DPIA, og art. 35(3):

| Screeningkriterium | Vurdering |
|---|---|
| Særlige kategorier i stor skala? | Ja — pasientdata for flere klinikker |
| Systematisk overvåking? | Nei |
| Ny teknologi? | Nei (etablert skyplattform) |
| Sårbare registrerte? | Ja — pasienter |

**Konklusjon:** DPIA-plikt utløses hos den behandlingsansvarlige (klinikken). Mjøsdata skal som databehandler bistå (art. 28(3)(f)) og har utarbeidet et underlagsdokument som beskriver sikkerhetstiltak, datalokasjon, tilgangsstyring og sletting — dette gjenbrukes på tvers av helsekundene og er et konkurransefortrinn i salg mot helsesegmentet.

## 5. Prioriterte etterlevelsestiltak

1. Etablere komplett behandlingsprotokoll (art. 30) — grunnmuren alt annet bygger på
2. Revidere/inngå databehandleravtaler i begge retninger (art. 28)
3. Innføre bruddhåndteringsrutine med 72-timersvurdering og kundevarslingsmaler (art. 33)
4. Konfigurere EU-datalagring og dokumentere overføringsvurderinger (art. 44 flg.)
5. Slette- og minimeringsregler i Salesforce og Jira (art. 5)
