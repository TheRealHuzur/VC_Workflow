# Git Workflow Helper – README

Ein kleiner **Workflow-Guide + Command-Generator** für einen einfachen Git-Flow:
**Branch starten → testen → committen → pushen → nach Merge aufräumen**.

Die Seite hilft dir, wiederholbare Schritte sauber abzuarbeiten und liefert pro Schritt **kopierfertige Terminal-Befehle**.

---

## Inhalt

- [Was ist das?](#was-ist-das)
- [Funktionen](#funktionen)
- [So benutzt du die Seite](#so-benutzt-du-die-seite)
- [Workflow Schritt für Schritt (1–5)](#workflow-schritt-für-schritt-15)
- [Checkliste: Testen & Prüfen](#checkliste-testen--prüfen)
- [Tipps & Troubleshooting](#tipps--troubleshooting)

---

## Was ist das?

Der **Git Workflow Helper** ist eine Ein-Seiten-Hilfe, die dich durch einen typischen Feature-/Ticket-Workflow führt.
Du gibst nur **Branch Name** und **Commit Message** ein und bekommst passende Commands für jeden Schritt.

---

## Funktionen

### 1) Workflow-Tracker (1–5)
- Zeigt den aktuellen Fortschritt über **5 Schritte**
- Kann auf „Neues Ticket“ / Reset zurückgesetzt werden

### 2) Terminal-Modus (&& / ;)
- Unterstützt unterschiedliche Shells:
  - **Git Bash / CMD / macOS Terminal**: nutzt `&&`
  - **Windows PowerShell**: nutzt `;`
- Hintergrund: `&&` stoppt bei Fehlern, `;` führt Befehle eher „nacheinander“ aus – deshalb Ausgabe prüfen.

### 3) Eingabefelder
- **Branch Name** (wird in `git checkout -b ...` und beim Push verwendet)
- **Commit Message** (wird beim Commit verwendet)

### 4) Kopier-Buttons
- Jeder Schritt hat einen **KOPIEREN**-Button, um die Commands direkt in die Zwischenablage zu übernehmen.

### 5) Test-Checkliste (Schritt 2)
- Eine kurze UI-/Frontend-Checkliste (Navigation, Layout, Konsole etc.)
- Button „✓ Checkliste erledigt“

---

## So benutzt du die Seite

1. **Terminal-Modus prüfen** (&& oder ;)  
2. **Branch Name** eintragen (z. B. `feature/login-fix`)  
3. **Commit Message** eintragen (z. B. `Fix login menu in sidebar`)  
4. Schrittweise vorgehen: **1 → 2 → 3 → 4 → 5**  
5. Pro Schritt: **Commands kopieren → im Terminal ausführen**

---

## Workflow Schritt für Schritt (1–5)

### Schritt 1 – Start: Arbeitsstand vorbereiten
Ziel: Auf aktuellem `main` starten und den Feature-Branch anlegen.

Typischer Inhalt:
- auf `main` wechseln
- Updates ziehen (`pull`)
- neuen Branch erstellen (aus Branch Name)

---

### Schritt 2 – Checkliste: Testen & Prüfen
Ziel: Vor dem Commit kurz prüfen, ob die Änderung sauber funktioniert.

Du testest manuell (siehe Checkliste unten) und markierst den Schritt als erledigt.

---

### Schritt 3 – Änderungen versionieren (Commit)
Ziel: Änderungen stage’n und committen.

Wichtig:
- **Vorher `git status` prüfen**
- Die Seite kann ggf. „meinungsstark“ sein (z. B. bestimmte Dateien wie `index.html` und `db.js` stage’n).
  Wenn du andere Dateien geändert hast: staging entsprechend anpassen.

---

### Schritt 4 – Push nach GitHub
Ziel: Deinen Branch ins Remote pushen.

Danach:
- Auf GitHub einen **Pull Request (PR)** erstellen
- Review/Checks abwarten, dann mergen

---

### Schritt 5 – Aufräumen (nach dem Merge)
Ziel: Lokal wieder sauber werden.

Typischer Inhalt:
- zurück auf `main`
- Updates ziehen
- Feature-Branch lokal löschen

Voraussetzung:
- Der Branch wurde wirklich gemerged und du brauchst ihn lokal nicht mehr.

---

## Checkliste: Testen & Prüfen

(Orientiert an typischen Frontend/UI-Checks)

- Navigation klickbar, keine toten Links
- Aktive Markierung funktioniert (Menü/Sidebar)
- Login-Menü / Dropdown funktioniert
- Scroll-Verhalten ok (keine Sprünge, keine „festhängenden“ Bereiche)
- Layout stimmt in Standard-Auflösung
- DevTools-Konsole: keine relevanten Errors/Warnings

---

## Tipps & Troubleshooting

### PowerShell: „läuft weiter“ trotz Fehler
Wenn du im PowerShell-Modus (`;`) arbeitest:
- Lies die Ausgabe genau und stoppe bei Fehlern manuell
- Im Zweifel Befehle einzeln ausführen statt als Kette

### Branch Name
- keine Leerzeichen
- am besten `feature/...`, `fix/...`, `chore/...` etc.
- Beispiel: `fix/navbar-scroll`

### Commit Message
- kurz, klar, im Imperativ
- Beispiel: `Fix sidebar active state`

### Immer prüfen
- `git status` vor Commit
- `git diff` wenn du unsicher bist, was genau geändert wurde

---

## Lizenz / Nutzung

Dieses Repo/Projekt kann frei als persönlicher Workflow-Helper genutzt und angepasst werden.
(Wenn du eine konkrete Lizenz nutzt: z. B. MIT – dann hier ergänzen.)
