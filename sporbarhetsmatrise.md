# Sporbarhetsmatrise

| | |
|---|---|
| Formål | Vise sammenhengen fra risiko til tiltak til kontroll i én oversikt |
| Versjon | 2.0, 1. september 2026 |
| Kilder | [Risikoregister](02-risikovurdering/risikoregister.md), [Tiltaksplan](02-risikovurdering/tiltaksplan.md), [Statement of Applicability](04-isms/statement-of-applicability.md) |

Sporbarhet er testen på om et styringssystem henger sammen. En revisor spør sjelden om dere har en policy. Spørsmålet er hvilken risiko som begrunner en gitt kontroll, og hvem som eier tiltaket. Denne oversikten skal kunne svare på det for hver eneste rad, og den skal fungere begge veier.

## 1. Fra risiko til restrisiko

| Risiko | Nivå før | Tiltak | Kontroller i Annex A | Eier | Frist | Nivå etter |
|---|---|---|---|---|---|---|
| R1, kontoovertakelse i Salesforce | 16 | T1 og T6 | A.5.17, A.8.5, A.5.15, A.5.16, A.5.18 | Driftsansvarlig | 1 mnd | 4 |
| R2, phishing mot supportteamet | 20 | T1, T2 og T4 | A.8.5, A.6.3, A.5.26, A.8.22 | Sikkerhetsansvarlig | 2 mnd | 8 |
| R3, angrep på API-integrasjonen | 12 | T5 | A.8.21, A.8.24, A.8.16 | Utviklingsansvarlig | 3 mnd | 4 |
| R4, utilgjengelighet i Azure | 15 | T3 | A.8.13, A.8.14, A.5.29, A.5.30, A.5.23 | Driftsansvarlig | 3 mnd | 5 |
| R5, misbruk av intern tilgang | 8 | T6 og T2 | A.5.15, A.5.16, A.5.18, A.8.2 | Sikkerhetsansvarlig | 4 mnd | 4 |
| R6, løsepengevirus i driftsmiljøet | 15 | T4, T3 og T7 | A.8.22, A.8.2, A.8.13, A.8.8, A.5.26 | Driftsansvarlig | 6 mnd | 8 |
| R7, tap av bærbar enhet | 6 | T9 | A.8.1, A.7.9, A.8.24, A.6.7 | Driftsansvarlig | 2 mnd | 2 |
| R8, leverandørkjedeangrep | 10 | T4 og T10 | A.5.19 til A.5.23, A.8.19, A.8.2 | Sikkerhetsansvarlig | 6 mnd | 5 |
| R9, brudd på meldeplikten | 9 | T8 | A.5.24 til A.5.28, A.5.31, A.5.34 | Sikkerhetsansvarlig | 2 mnd | 3 |
| R10, feilkonfigurering i Azure | 12 | T7 | A.8.9, A.8.8, A.8.16, A.5.23 | Driftsansvarlig | 3 mnd | 6 |

## 2. Fra regelverkskrav til leveranse

| Krav | Kilde | Dekket av | Status |
|---|---|---|---|
| Organisasjonens kontekst og interessenter | ISO 27001 punkt 4.1 til 4.3 | Kapittel 01 | Dekket |
| Risikovurderingsprosess med kriterier | ISO 27001 punkt 6.1.2 | Metodikken | Dekket |
| Risikohåndteringsplan | ISO 27001 punkt 6.1.3 | Tiltaksplanen | Dekket |
| Statement of Applicability | ISO 27001 punkt 6.1.3 bokstav d | Kapittel 04 | Utdrag med 36 av 93 kontroller |
| Ledelsens gjennomgang | ISO 27001 punkt 9.3 | | Ikke utarbeidet |
| Internrevisjon | ISO 27001 punkt 9.2 | | Ikke utarbeidet |
| Behandlingsprotokoll | GDPR artikkel 30 | Kapittel 03 punkt 3 | Utdrag |
| Databehandleravtaler | GDPR artikkel 28 | Kapittel 03 og tiltak T10 | Gap |
| Sikkerhet ved behandling | GDPR artikkel 32 | T1, T3, T5, T6, T7 og T9 | Delvis |
| Rutine for brudd og varsling | GDPR artikkel 33 og 34 | Hendelsesresponsplanen | Planlagt |
| Bistand ved konsekvensvurdering | GDPR artikkel 28 og 35 | Kapittel 03 punkt 4 | Delvis |
| Risikostyringstiltak | NIS2 artikkel 21, fremtidig | Kapittel 06 punkt 4 | To av ti områder dekket |
| Varslingsplikt i tre trinn | NIS2 artikkel 23, fremtidig | Varslingsmatrisen | Betinget rad |

## 3. Fra kontroll til hvor den er operasjonalisert

Denne veien er ofte den revisor faktisk går: fra en kontroll i SoA til dokumentet der den er beskrevet i drift.

| Kontroller | Beskrevet i |
|---|---|
| A.5.15 til A.5.18, A.8.2 og A.8.5, om identitet og tilgang | Policy for tilgangsstyring |
| A.5.19 til A.5.23, om leverandører og skytjenester | Tiltak T10, og kapittel 03 punkt 6 om tredjelandsoverføring |
| A.5.24 til A.5.28, om hendelseshåndtering | Hendelsesresponsplanen |
| A.5.29, A.5.30, A.8.13 og A.8.14, om kontinuitet | Tiltak T3. Kontinuitetsplanen er identifisert som gap |
| A.5.31 og A.5.34, om regelverk og personvern | Kapittel 03 og kapittel 06 |
| A.6.3, om opplæring | Kapittel 05 |
| A.6.7, A.7.9 og A.8.1, om endepunkt og fjernarbeid | Tiltak T9 |
| A.8.8, A.8.9 og A.8.16, om konfigurasjon og overvåking | Tiltak T7 |
| A.8.19 og A.8.22, om segmentering og programvarekontroll | Tiltak T4 |
| A.8.21 og A.8.24, om nettverkstjenester og kryptografi | Tiltak T5 og T9. Kryptopolicyen er identifisert som gap |

## 4. Kjente gap

Gapene står oppført her i stedet for å bli utelatt. Et styringssystem som ikke vet hva det mangler, mangler først og fremst oversikt.

| Gap | Hva det betyr | Planlagt lukket |
|---|---|---|
| Fullstendig SoA med alle 93 kontroller | Kan ikke sertifiseres på grunnlag av dagens utdrag | Neste iterasjon |
| Prosedyre for ledelsens gjennomgang | Krav i ISO 27001 punkt 9.3 er ikke oppfylt | Neste iterasjon |
| Program for internrevisjon | Krav i ISO 27001 punkt 9.2 er ikke oppfylt | Neste iterasjon |
| Kontinuitetsplan med gjenopprettingstider | A.5.30 er ikke påbegynt, og det er et gap mot NIS2 | 0 til 3 måneder |
| Kryptopolicy | A.8.24 er bare delvis dekket, og det er et gap mot NIS2 | 0 til 3 måneder |
| Rutine for bakgrunnssjekk | Gap mot NIS2 | 3 til 6 måneder |
| Fullstendig behandlingsprotokoll | Krav i GDPR artikkel 30 | 0 til 3 måneder |
