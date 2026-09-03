# 03 — GDPR-analyse

| | |
|---|---|
| **Dokument** | Personvernanalyse for Mjøsdata AS |
| **Dokumenteier** | Personvernkontakt |
| **Godkjent av** | Daglig leder |
| **Versjon** | 2.0 · Gjeldende fra 01.09.2026 · Revideres årlig |
| **Hjemmel** | Personvernforordningen (GDPR); personopplysningsloven; Datatilsynets veiledere |
| **Leser videre** | [Risikoregister](../02-risikovurdering/risikoregister.md) · [Hendelsesresponsplan](../04-isms/hendelsesresponsplan.md) · [SoA](../04-isms/statement-of-applicability.md) |

---

## 1. Rolleanalyse: behandlingsansvarlig eller databehandler?

Det viktigste — og oftest oversette — personvernspørsmålet for en MSP er *rollen*. Rollen følger av hvem som faktisk bestemmer formål og midler for behandlingen, ikke av hva partene har kalt seg i avtalen. Mjøsdata opptrer i begge roller samtidig:

| Behandling | Mjøsdatas rolle | Konsekvens |
|---|---|---|
| Egne kunderegistre, kontrakter, fakturering (Salesforce) | **Behandlingsansvarlig** | Fullt ansvar for behandlingsgrunnlag, informasjonsplikt, sletting og de registrertes rettigheter |
| Egne ansattdata (HR, lønn, tilgangslogger) | **Behandlingsansvarlig** | Som over; særlige krav ved kontrolltiltak i arbeidsforhold |
| Sikkerhetslogging og hendelseshåndtering i egne systemer | **Behandlingsansvarlig** | Grunnlag i berettiget interesse; krever interesseavveining |
| Drift av kunders systemer og data i Azure | **Databehandler** | Krever databehandleravtale (art. 28) med *hver* kunde; skal kun behandle etter dokumentert instruks |
| Bruk av Microsoft (Azure/365), Salesforce, Atlassian | Mjøsdata er kunde; leverandørene er **databehandlere/underdatabehandlere** | Databehandleravtaler nedover, og vurdering av tredjelandsoverføring (art. 44 flg.) |

### Hvorfor dobbeltrollen er den vanskelige delen

Mjøsdata må holde orden på **to avtalekjeder samtidig**: nedover mot egne leverandører og oppover mot egne kunder. Det praktisk viktigste utslaget gjelder brudd:

> Ved et brudd som rammer kundedata er Mjøsdata **databehandler**. Da har Mjøsdata ingen 72-timersfrist mot Datatilsynet — plikten er å varsle **kunden** (den behandlingsansvarlige) *uten ugrunnet opphold*, slik at kunden rekker sin egen frist. I praksis betyr det at Mjøsdatas interne frist må være vesentlig kortere enn 72 timer; [hendelsesresponsplanen](../04-isms/hendelsesresponsplan.md#5-varslingsmatrise) setter den til 24 timer.

Denne distinksjonen er den vanligste feilen i MSP-bransjen: leverandøren venter på egen 72-timersfrist som ikke finnes, og kunden mister sin.

---

## 2. Sentrale forpliktelser og status

| Artikkel | Krav | Relevans for Mjøsdata | Tiltak | Status |
|---|---|---|---|---|
| **Art. 5** | Prinsipper: formålsbegrensning, dataminimering, lagringsbegrensning, integritet og konfidensialitet | Kundedata i Salesforce og persondata i supportlogger må minimeres og slettes etter definerte frister | Slette- og minimeringspolicy; automatisk sletting av supportlogger etter 12 mnd der annet ikke kreves | 🟠 Gap |
| **Art. 6 / 9** | Behandlingsgrunnlag; særlige kategorier | Egne behandlinger hjemles i avtale (6(1)(b)), rettslig forpliktelse (6(1)(c)) og berettiget interesse (6(1)(f)). Helseklinikkers pasientdata (art. 9) behandles **kun som databehandler etter instruks** — Mjøsdata trenger ikke eget art. 9-grunnlag for disse | Grunnlagsvurdering per behandling i behandlingsprotokollen | 🟡 Delvis |
| **Art. 25** | Innebygd og standardinnstilt personvern | Nye kundeoppsett i Azure skal ha kryptering, minimert tilgang og logging som standard, ikke som tilvalg | Baseline-konfigurasjon ([T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure)) | 🟡 Delvis |
| **Art. 28** | Databehandleravtaler | Kreves mot alle kunder Mjøsdata drifter for, og mot Microsoft, Salesforce og Atlassian. Krav om forhåndsgodkjenning av underdatabehandlere | Avtalerevisjon; standard DBA-mal; leverandørregister ([T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring)) | 🟠 Gap |
| **Art. 30** | Behandlingsprotokoll | Plikt både som behandlingsansvarlig (30(1)) og databehandler (30(2)). Unntaket for virksomheter under 250 ansatte gjelder **ikke** her, siden behandlingen ikke er leilighetsvis og omfatter art. 9-data | Se utdrag i [pkt. 3](#3-behandlingsprotokoll--utdrag-art-30) | 🟠 Gap |
| **Art. 32** | Sikkerhet ved behandling | Kryptering, tilgangsstyring, gjenopprettingsevne og regelmessig testing — sammenfaller i stor grad med tiltaksplanen | [T1](../02-risikovurdering/tiltaksplan.md#t1--obligatorisk-phishing-resistent-mfa-og-betinget-tilgang), [T3](../02-risikovurdering/tiltaksplan.md#t3--geo-redundans-immutable-backup-og-ddos-beskyttelse), [T5](../02-risikovurdering/tiltaksplan.md#t5--sikring-av-api-integrasjoner), [T6](../02-risikovurdering/tiltaksplan.md#t6--rollebasert-tilgangsstyring-og-periodisk-tilgangsrevisjon), [T7](../02-risikovurdering/tiltaksplan.md#t7--baseline-konfigurasjon-og-teknisk-revisjon-av-azure), [T9](../02-risikovurdering/tiltaksplan.md#t9--full-diskkryptering-og-endepunktkontroll) | 🟡 Delvis |
| **Art. 33–34** | Meldeplikt (72 t) og varsling av registrerte | Som databehandler: varsle kunden uten ugrunnet opphold. Som behandlingsansvarlig: melde Datatilsynet innen 72 timer | [Hendelsesresponsplan](../04-isms/hendelsesresponsplan.md) med bruddvurderingsskjema ([T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner)) | 🟠 Gap |
| **Art. 35** | DPIA ved høy risiko | Skydrift av helseklinikkdata utløser DPIA-plikt hos kunden; Mjøsdata skal bistå etter art. 28(3)(f) | DPIA-screening i [pkt. 4](#4-dpia-screening-skydrift-av-helseklinikkdata) | 🟡 Delvis |
| **Art. 37** | Personvernombud | **Reell tvil — se [pkt. 5](#5-personvernombud-art-37--en-reell-tvil)** | Anbefaling: frivillig utpeking | 🟠 Gap |
| **Art. 44 flg.** | Overføring til tredjeland | Amerikanske skyleverandører; se [pkt. 6](#6-overføring-til-tredjeland) | EU/EØS-regioner i Azure; dokumentert overføringsvurdering | 🟡 Delvis |

---

## 3. Behandlingsprotokoll — utdrag (art. 30)

### 3.1 Som behandlingsansvarlig (art. 30(1))

| Behandling | Formål | Kategorier registrerte / opplysninger | Grunnlag | Lagringstid | Mottakere |
|---|---|---|---|---|---|
| Kundeadministrasjon (Salesforce) | Avtaleoppfølging og support | Kontaktpersoner hos kunder: navn, e-post, telefon, sakshistorikk | Art. 6(1)(b) — avtale | Avtaletid + 3 år | Salesforce (databehandler) |
| Fakturering og regnskap | Oppfyllelse av bokføringsplikt | Kontaktpersoner; fakturadata | Art. 6(1)(c) — bokføringsloven | 5 år etter regnskapsårets slutt | Regnskapsfører (databehandler) |
| Personaladministrasjon | Arbeidsforholdets gjennomføring | Ansatte: personalia, stilling, lønn, fravær | Art. 6(1)(b) og 6(1)(c) — arbeidsmiljøloven, folketrygdloven | Arbeidsforhold + 5 år | Lønnsleverandør, NAV |
| Sikkerhetslogging og hendelseshåndtering | Ivareta informasjonssikkerhet, oppdage og håndtere hendelser | Ansatte og eksterne brukere: bruker-ID, IP, tidsstempel, handling | Art. 6(1)(f) — berettiget interesse; interesseavveining dokumentert | 12 mnd, lengre kun ved pågående hendelsessak | Ingen (intern); ev. politi ved anmeldelse |

> **Om berettiget interesse (6(1)(f)):** sikkerhetslogging er uttrykkelig anerkjent som en berettiget interesse i GDPR fortalepunkt 49. Interesseavveiningen er likevel dokumentert særskilt, fordi logging av ansattes aktivitet også er et kontrolltiltak i arbeidsmiljølovens forstand og krever drøfting med de tillitsvalgte.

### 3.2 Som databehandler (art. 30(2))

| Kunde(-kategori) | Behandling utført på vegne av kunden | Kategorier opplysninger | Underdatabehandlere | Overføring tredjeland |
|---|---|---|---|---|
| Helseklinikker | Drift, backup og support av journal- og kontorsystemer | Pasientdata, herunder helseopplysninger (art. 9) — kun etter dokumentert instruks | Microsoft (Azure, EU/EØS-region) | Nei ved normal drift; se [pkt. 6](#6-overføring-til-tredjeland) om support |
| Kommuner | Drift av administrative systemer | Ansatt- og innbyggerdata | Microsoft (Azure, EU/EØS-region) | Nei ved normal drift |
| Advokat- og regnskapskontorer | Drift og backup av saks- og klientsystemer | Klientdata underlagt taushetsplikt | Microsoft (Azure, EU/EØS-region) | Nei ved normal drift |

Protokollen skal etter art. 30(2) også inneholde kontaktopplysninger for hver behandlingsansvarlig og en generell beskrivelse av sikkerhetstiltakene etter art. 32. Disse feltene føres i den fullstendige protokollen; utdraget her viser strukturen.

---

## 4. DPIA-screening: skydrift av helseklinikkdata

Vurdert mot art. 35(3) og Datatilsynets liste over behandlinger som alltid krever personvernkonsekvensvurdering:

| Screeningkriterium | Vurdering | Utslagsgivende? |
|---|---|:---:|
| Særlige kategorier i stor skala? | **Ja** — pasientdata for flere klinikker samlet på én plattform | ✅ |
| Systematisk overvåking av offentlig tilgjengelig område? | Nei | — |
| Ny teknologi? | Nei — etablert skyplattform | — |
| Sårbare registrerte? | **Ja** — pasienter står i et avhengighetsforhold og kan ikke velge bort behandlingen | ✅ |
| Sammenstilling av datasett? | Nei — kundemiljøene holdes adskilt | — |
| Automatiserte avgjørelser med rettsvirkning? | Nei | — |

**Konklusjon:** to utslagsgivende kriterier er oppfylt, og DPIA-plikten utløses hos **den behandlingsansvarlige** — altså klinikken, ikke Mjøsdata. Mjøsdata skal som databehandler bistå, jf. art. 28(3)(f).

**Praktisk håndtering:** Mjøsdata har utarbeidet et standardisert underlagsdokument som beskriver sikkerhetstiltak, datalokasjon, tilgangsstyring, underdatabehandlere og slettefrister. Dokumentet gjenbrukes på tvers av helsekundene. Det er både en effektivisering og et salgsargument: en klinikk som skal gjennomføre DPIA får halve jobben gjort av leverandøren.

---

## 5. Personvernombud (art. 37) — en reell tvil

Den enkle konklusjonen ville vært at Mjøsdata ikke har plikt til å utpeke personvernombud: virksomheten er privat, den utøver ikke myndighet, og kjernevirksomheten er IT-drift — ikke behandling av helseopplysninger. **Den konklusjonen er for rask.**

**Argumentet for plikt (art. 37(1)(c)):** bestemmelsen gjelder uttrykkelig både behandlingsansvarlige *og databehandlere* der kjernevirksomheten består i behandling av særlige kategorier i stor skala. Artikkel 29-gruppens veiledning (WP243) understreker at «kjernevirksomhet» omfatter behandling som er en uatskillelig del av tjenesten — ikke bare virksomhetens formål. En MSP som drifter journalsystemer for flere klinikker behandler helseopplysninger som en *nødvendig og løpende del av selve tjenesten*, ikke som en støttefunksjon. Skalaen er heller ikke ubetydelig når flere klinikkers pasientdata samles hos én leverandør.

**Argumentet mot plikt:** Mjøsdata behandler dataene kun etter instruks, uten tilgang til innholdet i normal drift, og har ingen egen interesse i opplysningene. Behandlingen er teknisk drift, ikke bruk.

**Vurdering og anbefaling:** spørsmålet er ikke avklart, og en feilvurdering er selvstendig sanksjonerbar. Mjøsdata anbefales derfor å **utpeke personvernombud frivillig** og registrere det hos Datatilsynet. Begrunnelsen er tredelt:

1. Det fjerner en rettslig usikkerhet til en kostnad som er lav for en virksomhet som uansett trenger personvernkompetanse.
2. Frivillig utpekt ombud må oppfylle de samme kravene til uavhengighet — det er altså ingen «light-versjon» — men det gir en definert rolle som ellers ville flytt mellom sikkerhetsansvarlig og daglig leder.
3. Helse- og kommunekunder spør om det i anskaffelser.

Vurderingen dokumenteres skriftlig uansett utfall, slik art. 24 forutsetter — det er selve dokumentasjonen av vurderingen som beskytter virksomheten dersom Datatilsynet er uenig i konklusjonen.

---

## 6. Overføring til tredjeland

Mjøsdatas skyleverandører er amerikanske. Overføringsgrunnlaget er derfor et selvstendig spørsmål, uavhengig av hvor dataene lagres.

| Forhold | Vurdering |
|---|---|
| **Lagringssted** | Alle kundemiljøer konfigureres i Azure-regioner innenfor EU/EØS. Dette er et sikkerhetstiltak og et minimeringstiltak, men det er *ikke i seg selv* et overføringsgrunnlag |
| **Overføringsgrunnlag** | EU-kommisjonens tilstrekkelighetsbeslutning for **EU–US Data Privacy Framework** (10. juli 2023) dekker overføring til amerikanske virksomheter som er sertifisert under ordningen. Beslutningen ble opprettholdt av EU-domstolens underrett i *Latombe v. Kommisjonen* (2025), men avgjørelsen kan ankes videre |
| **Fallback** | Standard personvernbestemmelser (SCC) med tilhørende **overføringsvurdering (TIA)** holdes oppdatert som reserveløsning. Historikken fra Safe Harbour og Privacy Shield tilsier at et rammeverk som er rettslig utfordret bør ha et alternativ klart, ikke etableres i etterkant |
| **Supportsituasjonen** | Selv med EU-lagring kan support fra leverandørens personell utenfor EØS utgjøre en overføring. Dette må sjekkes mot den enkelte leverandørs vilkår og eventuelt begrenses avtalemessig |
| **Kontroll av sertifisering** | Leverandørenes DPF-sertifisering verifiseres årlig mot den offisielle DPF-listen som del av [leverandørstyringen (T10)](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) |

---

## 7. Prioriterte etterlevelsestiltak

| # | Tiltak | Hvorfor i denne rekkefølgen | Knyttet til |
|:---:|---|---|---|
| 1 | Etablere komplett behandlingsprotokoll (art. 30) | Grunnmuren alt annet bygger på — man kan ikke sikre, slette eller melde det man ikke vet at man har | — |
| 2 | Innføre bruddhåndteringsrutine med varslingsfrister og maler (art. 33–34) | Høyest risiko for sanksjon på kort sikt; billigste tiltak i porteføljen | [T8](../02-risikovurdering/tiltaksplan.md#t8--hendelsesrespons--og-bruddrutiner) |
| 3 | Revidere og inngå databehandleravtaler i begge retninger (art. 28) | Kontraktuell eksponering mot både kunder og leverandører | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) |
| 4 | Utpeke personvernombud og dokumentere art. 37-vurderingen | Fjerner rettslig usikkerhet; forutsetning for troverdighet i helsesegmentet | — |
| 5 | Dokumentere overføringsvurdering og verifisere DPF-sertifiseringer (art. 44 flg.) | Krever leverandørdialog og tar tid | [T10](../02-risikovurdering/tiltaksplan.md#t10--leverandør--og-verktøykjedestyring) |
| 6 | Slette- og minimeringsregler i Salesforce og Jira (art. 5) | Teknisk arbeid som forutsetter at protokollen er ferdig | — |

---

## 8. Kilder

- Personvernforordningen (EU) 2016/679 (GDPR)
- Lov om behandling av personopplysninger (personopplysningsloven)
- Artikkel 29-gruppen: *Guidelines on Data Protection Officers* (WP243 rev.01)
- Datatilsynet: veiledere om databehandleravtaler, personvernkonsekvensvurdering og avviksmelding
- EU-kommisjonens gjennomføringsbeslutning (EU) 2023/1795 — EU–US Data Privacy Framework
