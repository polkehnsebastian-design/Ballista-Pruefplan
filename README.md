# Ballista Prüfplan

**Ballonierung und automatische Toleranzberechnung für technische Zeichnungen.**

Werkzeug zur schnellen Erstellung von Erstmusterprüfberichten (EMPB / PPAP / VDA) aus PDF- oder Bildzeichnungen – mit integrierter Toleranzberechnung nach ISO 286 und ISO 2768.

---

## Für wen ist Ballista Prüfplan?

- Qualitätsmanager, Messtechniker und Konstrukteure
- Erstmusterprüfer in Automotive, Maschinenbau und Zulieferindustrie
- Alle, die aus Zeichnungen strukturierte Prüfpläne erzeugen müssen

## Funktionen

- PDF- und Bildzeichnungen laden und mit nummerierten Prüfmerkmalen (Ballons) versehen
- **Auto-Stempeln:** alle Maße der Zeichnung in einem Schritt stempeln – per Knopf für die ganze Zeichnung oder mit UMSCHALT + Ziehen für einen Bereich
- Automatische Erkennung von Durchmesser, Gewinde, Winkel, Radius, Fase, Rauheit, Toleranzen und Passungen – bei CAD-PDFs direkt aus der Textebene, bei Scans und Bildern per Texterkennung (OCR)
- Erkennung von Form- und Lagetoleranzen (Toleranzrahmen) sowie Anzahlangaben wie „4x Ø6"
- Normkonforme Toleranzberechnung nach ISO 286 (Passungen) und ISO 2768 (Allgemeintoleranzen, Längen bis 4000 mm)
- Undo / Redo für sicheres Arbeiten
- Export als PDF (mit Ballons), Excel (VDA / PPAP) und Q-DAS (.dfq)
- Diagnose-Export: zeigt, welchen Text Ballista auf einer Zeichnung liest
- 46 automatisierte Tests sichern die Toleranzberechnung gegen bekannte Normwerte ab

### Neu in dieser Version

- Auto-Stempeln für die ganze Zeichnung oder einen Bereich
- Texterkennung für gescannte Zeichnungen und Bilder (benötigt Tesseract-OCR, siehe unten)
- Form- und Lagetoleranzen werden erkannt; ist das Symbol nicht lesbar, wird „Form-/Lagetoleranz" eingetragen und die Art von Hand gewählt
- Durchmesser- und Gradzeichen werden in allen gängigen Schreibweisen erkannt (Ø, ⌀, ∅, Φ bzw. °, º)
- Ein Klick auf ein Maß liest das ganze zusammengehörige Textstück (z. B. „Ø20 H7")
- Korrekturen an der Toleranzberechnung:
  - ISO 2768: Längen über 400 mm, Fasen und Radien in Klasse v
  - ISO 286: Passungen k, K und N, Nennmaße bis 3 mm, Toleranzgrad IT18
  - Maße wie „2x45°" werden nicht mehr als Passung gelesen
- Winkel: Die Allgemeintoleranz nach ISO 2768 richtet sich nach der Länge des kürzeren Schenkels. Dafür gibt es im Merkmal-Dialog das neue Feld „Schenkellänge (mm)". Ohne Angabe bleibt die Toleranz leer.
- Q-DAS-Export: Merkmalsart (K2004) korrigiert
- Die Erkennung funktioniert auch nach dem Drehen der Zeichnung

### Hinweise zur automatischen Erkennung

- Die automatische Erkennung ist ein Vorschlag. Bitte jedes Merkmal gegen die Zeichnung prüfen, bevor ein Prüfbericht erstellt wird.
- Bei Scans kann die Texterkennung Zeichen verwechseln, zum Beispiel Ø als 8 oder ± als +. Nach dem Auto-Stempeln nennt Ballista die Positionen, bei denen eine Toleranz möglicherweise unvollständig erkannt wurde.
- Hilfsmaße in Klammern werden nicht automatisch gestempelt.
- Es wird die erste Seite einer PDF verarbeitet.

---

## Download & Installation

Die aktuelle Version findest du im Bereich **[Releases](../../releases)** rechts.

**So gehts:**

1. Rechts auf **Releases** klicken
2. Bei der neuesten Version den Download **`Ballista Pruefplan.exe`** (bzw. das Setup) herunterladen
3. Ausführen – keine Installation von Python nötig

**Hinweis zum ersten Start:** Windows kann bei nicht signierten Anwendungen die Meldung „Windows hat Ihren PC geschützt" anzeigen. Auf **„Weitere Informationen"** klicken und dann auf **„Trotzdem ausführen"**. Das ist bei Beta-Software normal.

### Optional: Texterkennung für Scans und Bilder

Für PDFs direkt aus dem CAD ist nichts weiter nötig. Nur für gescannte Zeichnungen und Bilder (PNG/JPG) braucht Ballista das kostenlose Programm **Tesseract-OCR**:

1. Den Windows-Installer von der [UB Mannheim](https://github.com/UB-Mannheim/tesseract/wiki) herunterladen (64-Bit)
2. Installieren und den vorgeschlagenen Ordner `C:\Program Files\Tesseract-OCR` beibehalten
3. Bei den Sprachdaten zusätzlich **German** auswählen
4. Ballista neu starten

Fehlt Tesseract, funktioniert alles andere wie gewohnt; Ballista weist beim Auto-Stempeln eines Scans mit einer Meldung darauf hin.

## Beta-Test

Diese Version wird aktuell zur unabhängigen Erprobung bereitgestellt. Feedback ist ausdrücklich erwünscht:

- **Fehler oder Verbesserungsvorschläge** bitte über [Issues](../../issues) melden
- Test-Checkliste zum Abarbeiten: [`Test-Checkliste.md`](Test-Checkliste.md)
- Beispielzeichnungen zum Ausprobieren liegen im Repository: [`Testzeichnung_1_Flansch.pdf`](Testzeichnung_1_Flansch.pdf) und [`Testzeichnung_2_Welle.pdf`](Testzeichnung_2_Welle.pdf)
- Wird auf einer Zeichnung etwas nicht oder falsch erkannt, hilft die Diagnose-Datei: Menü **Projekt-Aktionen → Diagnose: erkannten Text speichern**. Sie enthält nur Texte und Positionen, keine Geometrie.

## Systemvoraussetzungen

- Windows 10 oder 11 (64-Bit)
- Ca. 200 MB freier Speicherplatz
- Optional: Tesseract-OCR für die Texterkennung bei Scans und Bildern

---

## Autor / Kontakt

**Sebastian Polkehn**
E-Mail: polkehn.sebastian@googlemail.com

## Lizenz

Copyright (c) 2026 Sebastian Polkehn. Alle Rechte vorbehalten.

Proprietäre Software – siehe [LICENSE.txt](LICENSE.txt).
Die Software darf ohne ausdrückliche schriftliche Zustimmung des Rechteinhabers weder kopiert, verändert, verbreitet noch kommerziell verwertet werden.
