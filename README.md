# wilma-smilde — Factuur-generator

Offline factuur-app voor Wilma Smilde in één HTML-bestand. Geen server, geen login, geen kosten: alle gegevens (klanten, facturen, instellingen) staan in `localStorage` op het eigen apparaat.

## Gebruik

Open `index.html` in Chrome (telefoon of PC), of via GitHub Pages:

```
https://hultink5611.github.io/wilma-smilde/
```

Op de telefoon: menu → **"Toevoegen aan beginscherm"** voor een app-gevoel.

## Functies

- **Nieuwe factuur** — klant kiezen of snel invullen, automatische factuurnummering (bijv. `2026-001`), regels met aantal × prijs, BTW 21% of vrijgesteld (incl. wettelijke vermelding), voorbeeld, PDF-download en print-fallback.
- **Facturen** — overzicht met zoeken, status (Concept / Verzonden / Betaald), opnieuw downloaden, bewerken, verwijderen.
- **Klanten** — klantenbeheer met zoeken, bewerken en verwijderen. Facturen bewaren een kopie van de klantgegevens van dat moment.
- **Instellingen** — bedrijfsgegevens, logo (automatisch verkleind), betalingstermijn, volgend factuurnummer, voettekst, en **backup exporteren/importeren** (JSON).

## Techniek

- Eén bestand (`index.html`), inline CSS + JS, geen build-stap of frameworks.
- PDF-export via [html2pdf.js](https://github.com/eKoopmans/html2pdf.js) (CDN, lazy geladen). Zonder verbinding valt de app terug op de afdrukweergave ("Opslaan als PDF").
- Fonts: Cormorant Garamond + Inter via Google Fonts, met systeem-fallbacks offline.
- Alle gebruikersinvoer wordt ge-escaped voor weergave (XSS-veilig).

## Deploy (GitHub Pages)

Eenmalig activeren: repo **Settings → Pages → Source: Deploy from a branch → `main` / root**. Daarna is elke push naar `main` binnen ± een minuut live.

## Belangrijk voor de gebruiker

- Gegevens staan **alleen op dit apparaat**. Maak regelmatig een backup via Instellingen → "Backup exporteren" en bewaar dat bestand veilig (het bevat klantgegevens).
- Factuurnummers horen boekhoudkundig opeenvolgend te zijn; verwijder alleen concepten die nooit verstuurd zijn.
