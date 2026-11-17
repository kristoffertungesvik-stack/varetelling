# Varetelling

Gratis app for varetelling i butikkar og bedrifter. Teikn butikken eller lageret i planverktøyet, tel vare for vare på telefonen, og få ferdig rapport til rekneskapsføraren og revisor.

**Opne appen:** https://kristoffertungesvik-stack.github.io/varetelling/

Appen finst på nynorsk og bokmål (vel i appen under Oppsett).

## Slik kjem du i gang

1. Opne appen på PC eller telefon, og skriv inn namnet på bedrifta.
2. **Teikn butikken.** Bruk planverktøyet til å teikne hallar, reolar, hyller, pallreolar, kjøl/frys, kasse og benkar. Alt du kan telje på, blir ein tellestad med eigen kode (A01, A02 …). Har du det travelt, kan du lage ein enkel plan berre ved å skrive kor mange reolar du har.
3. **Skriv ut tellelister** med kode og strekkode for kvar tellestad.
4. **Tel.** Trykk på ein reol i kartet eller skann koden på tellelista, skann eller skriv inn vara, og skriv inn kor mange.
5. **Avslutt og lag rapport.** Rapporten har sum per mva-sats, kost- og utsalsverdi, og kven som talde kva og når. Han kan skrivast ut eller lastast ned som Excel.

Varelista frå kassasystemet kan lastast inn som CSV eller Excel, så kjem namn, pris og mva-sats fram av seg sjølv når du skannar.

## Kvar blir data lagra?

- **Standard:** berre i nettlesaren på eininga du brukar. Ingenting blir sendt nokon stad.
- **Deling (valfritt):** skal fleire telje samstundes på kvar sin telefon, kan bedrifta kople appen til **sitt eige private GitHub-repo**. Teljinga, planen og varelista blir då lagra som JSON-filer der. Ingen andre, heller ikkje den som har laga appen, får tilgang.

### Slik slår du på deling

1. Lag ein gratis konto på github.com og eit **privat** repo, t.d. `varetelling-data`.
2. Lag ein *fine-grained* tilgangsnøkkel (Settings → Developer settings → Personal access tokens → Fine-grained tokens) som berre gjeld dette repoet, med **Contents: Read and write**.
3. Skriv inn eigar, repo og nøkkel under **Oppsett → Deling** i appen.
4. Dei tilsette koplar til ved å skanne QR-koden «Kople til telefon». Koden inneheld nøkkelen, så vis han berre til dei tilsette.

## Versjonar

| Adresse | For | Kva ein kan gjere |
|---|---|---|
| `/` | Den som styrer teljinga | Alt: plan, teljing, vareliste, tellelister, rapport, Excel, analyse og oppsett |
| `/tilsett/` | Dei som tel | Kart, teljing og nye varer. Ingen kronebeløp eller rapportar |
| `/plan/` | Den som teiknar | Planverktøyet for hallar, reolar og soner |

## Filer

- `index.html` – appen (administrator)
- `tilsett/index.html` – versjonen for tilsette
- `plan/index.html` – planverktøyet
- Alt er vanleg HTML og JavaScript i éi fil per side, utan byggjesteg og utan server.
