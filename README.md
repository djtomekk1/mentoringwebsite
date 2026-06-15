# DJ Tomekk — Website

Statische Landingpage für die 1:1-Sessions (Mentoring/Strategie) inkl.
Buchungs-/Bezahlbereich. Lokal in VS Code bearbeitbar, später als Ordner
ins GitHub-Repo → Cloudflare Pages.

## Ordnerstruktur

```
dj-tomekk/
├── index.html          ← die Seite (alles drin: Struktur, Styles, Skripte)
├── impressum.html      ← Rechtstext (Vorlage, ausfüllen)
├── datenschutz.html    ← Rechtstext (Vorlage, ausfüllen)
├── agb.html            ← Rechtstext (Vorlage, ausfüllen)
├── widerruf.html       ← Rechtstext (Vorlage, ausfüllen)
├── legal.css           ← Styles der Rechtstext-Seiten
├── images/             ← hier deine Fotos ablegen (siehe images/README.txt)
├── .gitignore
└── README.md           ← diese Datei
```

## 1 · Lokal anschauen / bearbeiten

Am einfachsten in **VS Code mit der Extension „Live Server"**:
1. Ordner in VS Code öffnen (`File → Open Folder…`).
2. Extension „Live Server" installieren (von Ritwick Dey).
3. Rechtsklick auf `index.html` → **„Open with Live Server"**.
   Die Seite öffnet sich im Browser und lädt bei jeder Speicherung neu.

Alternativ reicht ein Doppelklick auf `index.html` (öffnet sie im Browser),
dann musst du aber nach Änderungen manuell neu laden.

## 2 · Fotos einbauen

Lege deine Bilder in den Ordner `images/` mit genau diesen Namen:

- `tomekk-portrait.jpg` → Vita-Bereich
- `gallery-1.jpg` … `gallery-4.jpg` → Galerie

Sie erscheinen dann automatisch — kein Code-Eingriff nötig. Solange ein
Bild fehlt, steht an der Stelle ein markierter Platzhalter. Details und
Format-Tipps: `images/README.txt`. Der Hero oben ist bewusst die
Vinyl-Grafik und braucht kein Foto.

## 3 · Buchung + Zahlung funktionsfähig machen (Cal.com + Stripe)

Der Bereich „Termin & Bezahlung" ist aktuell eine **Vorschau (Mockup)**.
So wird er echt:

1. **Cal.com**-Account anlegen → Google-Kalender verbinden.
2. Drei Event-Typen erstellen: 30 Min / 149 €, 60 Min / 299 €, 90 Min / 499 €.
3. **Stripe**-Account erstellen (auf den Namen dessen, der verkauft) und in
   Cal.com verbinden (optional PayPal). „Zahlung vor Buchung erforderlich"
   aktivieren.
4. In Cal.com den **HTML-Embed-Snippet** kopieren.
5. In `index.html` den Block `<div class="booking-body"> … </div>` durch den
   Snippet ersetzen — die Stelle ist im Code mit einem Kommentar markiert
   (Suche nach „Cal.com-Embed hier einsetzen").

Stripe-Gebühren EU: 1,5 % + 0,25 € pro Buchung, keine Fixkosten.

## 4 · Rechtstexte

`impressum.html`, `datenschutz.html`, `agb.html`, `widerruf.html` sind
**Vorlagen mit Platzhaltern**. Vor dem Öffentlich-Schalten mit echten
Inhalten füllen. Zentrale Frage vorab: **Wer ist Verkäufer/Betreiber —
DJ Tomekk oder du?** Davon hängen Impressum, Stripe-Konto, Rechnungen und
Umsatzsteuer ab.

## 5 · Später live schalten (wenn alles fertig ist)

1. `git init` im Projektordner, committen.
2. Repo auf GitHub anlegen und pushen.
3. Cloudflare → Pages → Repo verbinden → deployen (Build-Befehl leer,
   Output-Verzeichnis `/`). Du bekommst eine `…pages.dev`-URL.
4. Eigene Domain unter „Custom domains" verbinden (z. B.
   `tomekk.cubadunn.com` oder `djtomekk.de`).
5. Komplette Test-Buchung im Stripe-Testmodus durchklicken, dann auf
   Live umstellen.

Ab Schritt 3 deployt jeder Git-Push automatisch neu.
