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
- Mehrere Merkmale auf einmal markieren und löschen (STRG + Ziehen, dann ENTF)
- Undo / Redo für sicheres Arbeiten
- Export als PDF (mit Ballons), Excel (VDA / PPAP) und Q-DAS (.dfq)
- Diagnose-Export: zeigt, welchen Text Ballista auf einer Zeichnung liest

### Neu in dieser Version

- Auto-Stempeln für die ganze Zeichnung oder einen Bereich
- Texterkennung für gescannte Zeichnungen und Bilder (benötigt Tesseract-OCR, siehe unten) – auch für schräg stehende Maße, mit Erkennung des Durchmesserzeichens an seiner Form und von Toleranzrahmen
- Mehrere Merkmale markieren und gemeinsam löschen: STRG + Ziehen, dann ENTF (ESC hebt die Markierung auf)
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
- Neue PDF-Grundlage: Anzeige, Texterkennung und PDF-Export laufen über frei lizenzierte Bibliotheken. Der PDF-Export übernimmt jetzt auch Kommentare und Abdeckungen aus der Original-PDF an der richtigen Stelle, auch bei gedrehter Zeichnung.
- Auslieferung als ZIP-Datei mit Programmordner statt einer einzelnen `.exe`
- Absturz beim Öffnen einer weiteren Zeichnung behoben; Fehler und Abstürze werden in Log-Dateien protokolliert

### Hinweise zur automatischen Erkennung

- Die automatische Erkennung ist ein Vorschlag. Bitte jedes Merkmal gegen die Zeichnung prüfen, bevor ein Prüfbericht erstellt wird.
- Bei Scans kann die Texterkennung Zeichen verwechseln, zum Beispiel Ø als 8 oder ± als +. Nach dem Auto-Stempeln nennt Ballista die Positionen, bei denen eine Toleranz möglicherweise unvollständig erkannt wurde.
- Bei Scans dauert das Auto-Stempeln je nach PC etwa 5 bis 15 Sekunden.
- Bekannte Schwäche bei Scans: senkrecht stehende Durchmesserangaben und sehr kleine, gestapelte Abmaße werden noch nicht immer richtig gelesen.
- Hilfsmaße in Klammern werden nicht automatisch gestempelt.
- Es wird die erste Seite einer PDF verarbeitet.

---

## Download & Installation

Die aktuelle Version findest du im Bereich **[Releases](../../releases)** rechts.

**So gehts:**

1. Rechts auf **Releases** klicken
2. Bei der neuesten Version **`Ballista_Pruefplan.zip`** herunterladen
3. Die ZIP-Datei entpacken (Rechtsklick → **„Alle extrahieren…"**). Bitte nicht direkt aus der ZIP-Datei heraus starten.
4. Im entpackten Ordner **`Ballista Pruefplan.exe`** starten – keine Installation von Python nötig

Der Unterordner `_internal` gehört zum Programm und muss neben der `.exe` bleiben. Für den schnellen Start kannst du eine Verknüpfung zur `.exe` auf den Desktop legen (Rechtsklick → „Senden an" → „Desktop").

**Hinweis zum ersten Start:** Windows kann bei nicht signierten Anwendungen die Meldung „Windows hat Ihren PC geschützt" anzeigen. Auf **„Weitere Informationen"** klicken und dann auf **„Trotzdem ausführen"**. Das ist bei Beta-Software normal.

### Optional: Texterkennung für Scans und Bilder

Ob du Tesseract brauchst, hängt davon ab, wie die Zeichnung entstanden ist, nicht vom Dateiformat:

- **PDF direkt aus dem CAD**: nichts weiter nötig. Ballista liest die Maße direkt aus der Datei.
- **Gescannte PDF** sowie **Bilder (PNG/JPG)**: Ballista braucht das kostenlose Programm **Tesseract-OCR**. Auch eine PDF kann ein Scan sein, etwa eine eingescannte Papierzeichnung.

**So erkennst du den Unterschied:** Öffne die PDF in einem PDF-Viewer und versuche, eine Maßzahl mit der Maus zu markieren. Lässt sich der Text markieren, stammt die PDF aus dem CAD. Lässt er sich nicht markieren, ist es ein Scan.

Installation von Tesseract-OCR:

1. Den Windows-Installer von der [UB Mannheim](https://github.com/UB-Mannheim/tesseract/wiki) herunterladen (64-Bit)
2. Installieren und den vorgeschlagenen Ordner `C:\Program Files\Tesseract-OCR` beibehalten
3. Bei den Sprachdaten zusätzlich **German** auswählen
4. Ballista neu starten

Fehlt Tesseract, funktioniert alles andere wie gewohnt; Ballista weist beim Auto-Stempeln eines Scans mit einer Meldung darauf hin.

## Beta-Test

Diese Version wird aktuell zur unabhängigen Erprobung bereitgestellt. Alle dürfen sie kostenlos testen.

**Ablaufdatum:** Jede Beta-Version läuft drei Monate nach ihrer Veröffentlichung ab. Das Datum steht in der Titelleiste, zwei Wochen vorher erinnert Ballista beim Start daran. Danach einfach die neueste Version unter [Releases](../../releases) herunterladen – gespeicherte Projekte lassen sich weiter öffnen.

Feedback ist ausdrücklich erwünscht:

- **Fehler oder Verbesserungsvorschläge** bitte über [Issues](../../issues) melden
- Test-Checkliste zum Abarbeiten: [`Test-Checkliste.md`](Test-Checkliste.md)
- Beispielzeichnungen zum Ausprobieren liegen im Repository:
  - [`Testzeichnung_1_Flansch.pdf`](Testzeichnung_1_Flansch.pdf) und [`Testzeichnung_2_Welle.pdf`](Testzeichnung_2_Welle.pdf)
  - [`Testzeichnung_3_Antriebswelle.pdf`](Testzeichnung_3_Antriebswelle.pdf): Durchmesser mit Passungen, Gewinde, Fase, Radius, Rundlauf und Zylinderform
  - [`Testzeichnung_4_Lagerflansch.pdf`](Testzeichnung_4_Lagerflansch.pdf): Lochkreis, Winkel, Position, Ebenheit und Parallelität
  - [`Testzeichnung_5_Halter_schraeg.pdf`](Testzeichnung_5_Halter_schraeg.pdf): schräge Maße, Winkel und Rechtwinkligkeit
- Wird auf einer Zeichnung etwas nicht oder falsch erkannt, hilft die Diagnose-Datei: Menü **Projekt-Aktionen → Diagnose: erkannten Text speichern**. Sie enthält nur Texte und Positionen, keine Geometrie.

## Systemvoraussetzungen

- Windows 10 oder 11 (64-Bit)
- Ca. 500 MB freier Speicherplatz
- Optional: Tesseract-OCR für die Texterkennung bei gescannten PDFs und Bildern

---

## Autor / Kontakt

**Sebastian Polkehn**
E-Mail: polkehn.sebastian@googlemail.com

## Lizenz

Copyright (c) 2026 Sebastian Polkehn. Alle Rechte vorbehalten.

Proprietäre Software – siehe [LICENSE.txt](LICENSE.txt).
Die Software darf ohne ausdrückliche schriftliche Zustimmung des Rechteinhabers weder kopiert, verändert, verbreitet noch kommerziell verwertet werden.

### Komponenten von Drittanbietern

Ballista Prüfplan enthält Open-Source-Bibliotheken, die unter ihren eigenen Lizenzen stehen, darunter PySide6/Qt (LGPL v3), pypdfium2/PDFium (Apache-2.0 / BSD-3-Clause), pypdf (BSD-3-Clause), OpenCV und NumPy (Apache-2.0 / BSD-3-Clause), Pillow, openpyxl und pytesseract. Eine Übersicht steht in der Datei `DRITTANBIETER-LIZENZEN.txt`, die vollständigen Lizenztexte im Ordner `Lizenzen` – beides liegt im Programmordner.
