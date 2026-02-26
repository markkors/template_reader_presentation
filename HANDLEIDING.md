# Handleiding: Digitale Reader aanmaken 

## Wat is dit systeem?

Je maakt een digitale webpagina (reader + presentaties) die automatisch online staat via GitHub. Je schrijft je inhoud in eenvoudige tekstbestanden (Markdown), en GitHub zet dat automatisch om naar een mooie website. **Je hoeft niets op je computer te installeren.**

---

## Stap 1 – Maak een GitHub-account aan

1. Ga naar [github.com](https://github.com)
2. Klik op **Sign up** (rechtsboven)
3. Kies een gebruikersnaam (bijv. `janneke-docent`), vul je e-mail en wachtwoord in
4. Bevestig je e-mailadres via de mail die je krijgt
5. Log in op GitHub

---

## Stap 2 – Kopieer het sjabloon via Fork

De template staat op:
`https://github.com/markkors/template_reader_presentation`

1. Ga naar die pagina
2. Klik rechtsboven op **"Fork"** (naast de ster-knop)
3. Kies **"Create a new fork"**
4. Geef je repository een naam, bijv. `javascript-reader` of `python-reader`
5. Laat de instelling op **Public** staan (nodig voor gratis hosting)
6. Klik op **"Create fork"**

> Je hebt nu je eigen kopie van het sjabloon.

---

## Stap 3 – Activeer de gratis website (GitHub Pages)

1. Ga naar je repository
2. Klik bovenaan op **Settings** (tandwiel-icoon)
3. Klik in het linkermenu op **Pages**
4. Onder "Source": kies **GitHub Actions**
5. Klik op **Save**

> De eerste keer duurt het 2–5 minuten voordat de site live is.
> Je websiteadres wordt: `https://jouw-gebruikersnaam.github.io/naam-van-je-repo/`

---

## Stap 4 – Pas de basisinformatie aan

1. Klik in je repository op het bestand **`_config.yml`**
2. Klik op het potlood-icoon (rechtsboven in het bestand) om te bewerken
3. Pas de volgende regels aan:

```yaml
title: JavaScript Fundamentals          # Naam van je reader
description: Introductie tot JavaScript # Korte beschrijving
author: Janneke de Vries                # Jouw naam
baseurl: "/javascript-reader"           # Exacte naam van je repository
repository: janneke-docent/javascript-reader  # gebruikersnaam/reponaam
```

4. Scroll naar beneden, klik **"Commit changes"** → **"Commit directly to main"**

---

## Stap 5 – Schrijf je eerste reader-hoofdstuk

1. Klik op het bestand **`Reader_example.md`**
2. Klik op het potlood-icoon om te bewerken
3. Pas bovenaan de "frontmatter" aan:

```yaml
---
layout: default
title: Hoofdstuk 1 – Introductie JavaScript
author: Janneke de Vries
version: "1.0"
chapter: "1"
---
```

4. Schrijf daarna je inhoud in Markdown (zie tips hieronder)
5. Sla op met **"Commit changes"**

> **Tip Markdown-opmaak:**
> - `## Kopje` = grote kop
> - `**vet**` = **vet**
> - `- item` = opsommingspunt
> - ` ```html ... ``` ` = codeblok

---

## Stap 6 – Koppel het hoofdstuk aan de homepage

1. Open het bestand **`index.html`**
2. Klik op het potlood-icoon om te bewerken
3. Zoek de bestaande tile en pas de tekst en bestandsnaam aan:

```html
<a href="{{ '/Reader_example.html' | relative_url }}" class="reader-link">
  1. Reader voorbeeld
</a>
```

Verander dit naar jouw hoofdstuk, bijv.:

```html
<a href="{{ '/Hoofdstuk_1.html' | relative_url }}" class="reader-link">
  1. Introductie JavaScript
</a>
```

4. Sla op met **"Commit changes"**

---

## Stap 7 – Bekijk je website

Na elke wijziging bouwt GitHub automatisch de site opnieuw. Dit duurt 1–3 minuten.

- Ga naar **Settings → Pages** om je websiteadres te zien
- Of ga direct naar: `https://jouw-gebruikersnaam.github.io/naam-van-je-repo/`

Je kunt de voortgang van het bouwen zien via het tabblad **Actions** in je repository.

---

## Nieuwe hoofdstukken toevoegen

Voor elk nieuw hoofdstuk:

1. Klik in je repository op **"Add file" → "Create new file"**
2. Geef het bestand een naam, bijv. `Hoofdstuk_2.md`
3. Kopieer de inhoud van `Reader_example.md` als startpunt
4. Schrijf je inhoud en sla op met **"Commit changes"**
5. Voeg een nieuwe tile toe in `index.html` die verwijst naar `Hoofdstuk_2.html`

---

## Veelgestelde vragen

| Probleem | Oplossing |
|----------|-----------|
| Site is niet zichtbaar | Wacht 5 min, controleer **Actions** tab op fouten |
| Opmaak klopt niet | Controleer of de frontmatter (`---`) bovenaan staat |
| Wijziging niet zichtbaar | Lege de browsercache (Ctrl+Shift+R) |
| Afbeelding werkt niet | Upload afbeelding naar de map `Attachments/` en verwijs er naar |

---

## Samenvatting: de workflow

```
Bestand bewerken in GitHub → Commit → GitHub bouwt automatisch → Website is live
```

Geen software nodig. Geen installaties. Alles via de browser.

---

## Lokaal testen (optioneel)

Wil je wijzigingen bekijken **zonder elke keer naar GitHub te pushen**? Dan kun je Jekyll lokaal installeren en de site op je eigen computer draaien.

Zie hiervoor: [Yekill.md](Yekill.md)

---

Vragen? 
Mark Kors, ROC ICA, 2026