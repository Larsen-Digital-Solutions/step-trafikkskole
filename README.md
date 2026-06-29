# STEP Trafikkskole – nettside (utkast)

High-end statisk nettside for **STEP Trafikkskole AS** (Drammen & Røyken), bygget ved å rebrande Elite Trafikkskole-malen til STEP sin merkevare og innhold.

## Forhåndsvisning
Fra prosjektmappen:

```
node scripts/serve.mjs        # http://localhost:5500
```

## Designgrunnlag
- **Mal:** Elite Trafikkskole (samme komponentbibliotek, kvalitet og selvhostede fonter – Space Grotesk + Plus Jakarta Sans).
- **Farger:** rebrandet fra Elites rød/koksgrå til **STEP sin palett** hentet fra logoen: dyp marineblå (`--bg-deep #0C2230`), cyan-blå aksent (`--accent #0875A0`), lys cyan (`--accent-bright #18B4D6`) og grønn «spark» (`#46C24A`).
- Ingen falske Google-score/garantier – kun STEPs egne elevsitater (Paula, Øystein, Silje).

## Sider
| Fil | Innhold |
|---|---|
| `index.html` | Hjem – hero, alle klasser, pakketilbud, to avdelinger, anmeldelser, FAQ |
| `klasse-b.html` | Klasse B (automat og manuell, trinn 1–4, FAQ) |
| `klasse-mc.html` | Klasse A, A1 og A2 – MC (inkl. MC grunnkurs) |
| `klasse-be.html` | Klasse BE/B96 – tilhenger |
| `trafikalt-grunnkurs.html` | **Trafikalt grunnkurs** (kurset Elite-malen manglet) |
| `priser.html` | Pakketilbud bil-automat + andre priser |
| `booking.html` | Booking-hub – TABS-kalender for Drammen og Røyken |
| `om-oss.html` | Om oss – to avdelinger, erfaring, Tesla-bilde |
| `kontakt.html` | Kontakt – begge avdelinger med kart + påmeldingsskjema |
| `vilkar.html` | Vilkår (foreløpige) |

## STEP-info (verifisert mot deres sider + Brønnøysund)
- **Org.nr** 913 177 843 · STEP TRAFIKKSKOLE AS · tlf **932 14 270** · steptrafikkskole@gmail.com
- **Drammen:** Hotvetveien vest 49, 3023 Drammen · booking `stepdrammen.tabs.no/kalender`
- **Røyken:** Spikkestadveien 118, 3430 Spikkestad · booking `steptrafikkskole.tabs.no/kalender`
- Åpent man–fre 07.00–17.00 · elevinnlogging `tabs.no/start`
- Instagram @steptrafikkskole · Facebook /Steptrafikkskole
- Etablert Røyken 2014, Drammen 2020 · ~90 % bestått første forsøk · universitetsutdannede lærere (Nord)

### Pakketilbud bil – automat (fra deres side)
| Pakke | Innhold | Pris | Spar |
|---|---|---|---|
| SMALL | Obligatorisk opplæring + leie av bil, ingen kjøretimer | 21 400 kr | 310 kr |
| MEDIUM | + 5 kjøretimer | 25 600 kr | 510 kr |
| LARGE | + 10 kjøretimer | 29 500 kr | 1 010 kr |

Trafikalt grunnkurs: intensivkurs i skoleferien fra **1 800 kr**.

## Bilder
- `img/logo.png` – STEP-logoen (vises hvit over hero/footer via `filter: brightness(0) invert(1)`).
- `img/step-hero.jpg` – hero (bil med henger).
- `img/tesla.jpg` – om oss.
- Øvrige bilder er nøytrale kjøre-/MC-/tilhengerfoto arvet fra malen.

## Må gjøres før lansering
- **Foto:** bytt nøytrale malbilder til STEPs egne der det er ønskelig.
- **Kontaktskjema:** bruker demo-handler (viser takk-melding). Koble til ekte endepunkt (f.eks. Web3Forms) – markert med TODO i `kontakt.html`.
- **Priser:** pakkepriser og trafikalt grunnkurs er hentet fra STEPs side. Manuell, MC og tilhenger settes opp som individuell plan – bekreft konkrete priser.
- **Kommende kurs:** lista på forsiden og booking henter fra `data/kurs.json` (TABS officeId **1253** Drammen / **765** Røyken). Live-APIet `api.tabs.no/api/v2/courses?...` krever Referer-header og tillater ikke CORS fra annet domene – oppdater `kurs.json` manuelt, eller sett opp en proxy ved hosting for live data.
- **Vilkår:** foreløpige – gjennomgå før publisering. Betalingsmetoder bør bekreftes.
- **Favicon/OG-bilde:** enkel favicon laget i STEP-farger; bytt gjerne til STEP-spesifikt motiv.
- **rebrand.mjs** i `scripts/` var engangs-rebrandingen fra Elite → STEP og kan slettes.

## Kilde
Research mot steptrafikkskole.no (Drammen + Røyken) og Brønnøysund Enhetsregisteret. Levert av Larsen Digital Solutions, 2026-06-29.
