# DJ Tomekk — Mentoring Website

Offizielle Mentoring- und Buchungsseite von DJ Tomekk.
Live unter: **mentoring.djtomekk.com** (bzw. GitHub Pages waehrend der Entwicklung)

---

## Projektstruktur

```
dj-tomekk/
├── index.html          <- die komplette Website (eine Datei)
├── impressum.html      <- Impressum (B.D.B. Media GmbH)
├── datenschutz.html    <- Datenschutzerklaerung (DSGVO)
├── agb.html            <- Allgemeine Geschaeftsbedingungen
├── widerruf.html       <- Widerrufsbelehrung
├── legal.css           <- Styling fuer alle Rechtstext-Seiten
├── images/             <- alle Bilder der Website
│   ├── LOGO.png            (DJ Tomekk Logo — dreht sich auf der Schallplatte)
│   ├── tomekk-portrait.jpg (Portraet im Vita-Bereich)
│   ├── gallery-1.png       (Galerie: Dr. Dre & Tomekk)
│   ├── gallery-2.jpg       (Galerie: Lil' Kim & Tomekk)
│   ├── gallery-3.jpg       (Galerie: Tomekk & Coolio)
│   └── gallery-1org.jpg    (Original-Backup, wird nicht angezeigt)
├── .gitignore
└── README.md           <- diese Datei
```

---

## Lokal bearbeiten

1. Ordner in **VS Code** oeffnen (`File -> Open Folder`)
2. Extension **"Live Server"** (von Ritwick Dey) installieren
3. Rechtsklick auf `index.html` -> **"Open with Live Server"**
4. Die Seite oeffnet sich im Browser und laedt bei jeder Speicherung automatisch neu

---

## Auf GitHub hochladen (Deploy)

Nach jeder Aenderung:
1. Auf **github.com** ins Repo einloggen
2. `Add file -> Upload files`
3. Den kompletten Inhalt des `dj-tomekk/`-Ordners reinziehen
4. `Commit changes` klicken

GitHub Pages deployt automatisch — nach ca. 1-2 Minuten ist die Seite live.

---

## Sprachen

Die Seite hat einen **DE / EN / PL Toggle** oben rechts in der Navigation.

Alle Texte sind direkt in `index.html` mit `data-de`, `data-en` und `data-pl` Attributen gekennzeichnet:

```html
<span data-de>Deutscher Text</span>
<span data-en>English text</span>
<span data-pl>Tekst po polsku</span>
```

Beim Hinzufuegen neuer Texte immer **alle drei Sprachen** eintragen, sonst bleibt der Block beim Umschalten leer.

---

## Buchungs-Links (Cal.com)

Alle Buchungen laufen ueber **Cal.com** — Account: `djtomekk`

| Session | Cal.com-Link |
|---|---|
| Quick Call (30 Min) | https://cal.eu/djtomekk/30min |
| Artist Strategy (60 Min) | https://cal.eu/djtomekk/60min |
| VIP Mentoring (90 Min) | https://cal.eu/djtomekk/vip-mentoring |
| Elite Mentoring (4 Wochen) | https://cal.eu/djtomekk/elite-mentoring |

Die Links sind in `index.html` direkt bei den jeweiligen Buttons eingetragen. Wenn ein neuer Session-Typ auf Cal.com angelegt wird, einfach den neuen Link als `href` beim entsprechenden Button eintragen.

**Instagram Posts (C1)** laufen per E-Mail — kein Cal.com-Link, Button oeffnet: `mailto:impressum@djtomekk.com`

---

## Bilder austauschen / hinzufuegen

Bilder einfach in den `images/`-Ordner legen mit dem richtigen Dateinamen — sie erscheinen automatisch ohne Code-Aenderung:

| Dateiname | Wo auf der Seite |
|---|---|
| `tomekk-portrait.jpg` | Vita-Bereich (Portraet) |
| `gallery-1.png` | Galerie, Bild 1 |
| `gallery-2.jpg` | Galerie, Bild 2 |
| `gallery-3.jpg` | Galerie, Bild 3 |
| `LOGO.png` | Schallplatten-Label (dreht sich) |

Solange ein Bild fehlt, zeigt die Seite einen markierten Platzhalter mit dem erwarteten Dateinamen.

---

## Preise aendern

Preise stehen an zwei Stellen in `index.html` — immer beide updaten:

1. **Tracklist** (aufklappbare Zeilen) — Attribut `data-price="... EUR"` im `<button>`-Tag
2. **Booking-Cards** (die Karten weiter unten) — im `<span class="bc-price">` Tag

---

## Rechtstexte aktualisieren

Die vier Rechtstext-Seiten sind eigenstaendige HTML-Dateien und koennen direkt bearbeitet werden. Alle nutzen `legal.css` fuer das Styling.

Betreiber ist die **B.D.B. Media GmbH**, Kronenstrasse 18, 10117 Berlin (GF: Tomasz Kuklicz, HRB 177225, AG Charlottenburg).

---

## Zahlung

Laeuft ueber **PayPal** — verbunden mit dem Cal.com-Account. Kein eigener Checkout-Code auf der Website. Bei Problemen mit der Zahlungsanbindung: Cal.com-Einstellungen -> Apps -> PayPal.

---

## Technisches

- **Kein Build-System** — reine HTML/CSS/JS-Datei, keine Dependencies, kein npm
- **Kein Tracking** — kein Google Analytics, kein Cookie-Banner noetig
- **Fonts** — Google Fonts (Archivo, Inter, Space Mono), werden von Google geladen
- **Hosting** — GitHub Pages (kostenlos, auto-deploy bei jedem Commit)
- **Domain** — mentoring.djtomekk.com (DNS bei Strato)
