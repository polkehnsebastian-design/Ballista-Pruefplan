# Test-Checkliste – Ballista Prüfplan (v0.1 Beta)

Danke, dass du beim Testen hilfst! Bitte geh diese Punkte durch und trage dein Feedback direkt hier ein oder erstelle für jeden gefundenen Fehler ein eigenes GitHub Issue.

**Zum Testen liegen im Repository zwei Beispielzeichnungen bereit** (`Testzeichnung_1_Flansch.pdf` und `Testzeichnung_2_Welle.pdf`). Danach am besten mit **eigenen Zeichnungen** aus dem Arbeitsalltag weitertesten – dort zeigt sich am besten, ob die Erkennung zuverlässig funktioniert.

## 1. Installation & erster Start
- [ ] `Ballista Pruefplan.exe` (bzw. Setup) erfolgreich heruntergeladen
- [ ] Die Anwendung lässt sich per Doppelklick starten
- [ ] Bei der Windows-Warnung "Windows hat Ihren PC geschützt" konnte die App über "Weitere Informationen" → "Trotzdem ausführen" gestartet werden
- [ ] Beim ersten Start dauert es 5–15 Sekunden – die App erscheint danach normal
- [ ] Das Ballista-Logo wird oben links im Fenster und in der Taskleiste angezeigt

## 2. Datei laden
- [ ] Eine der beiden Testzeichnungen (PDF) lässt sich über "Datei laden" öffnen
- [ ] Die Zeichnung wird korrekt und scharf angezeigt
- [ ] Ein Bild (PNG/JPG) lässt sich alternativ ebenfalls laden
- [ ] Beim Laden einer neuen Datei mit bereits gesetzten Ballons erscheint die Rückfrage "Möchten Sie speichern?"

## 3. Ballons von Hand setzen
- [ ] Ein Ballon lässt sich per Linksklick auf ein Maß setzen
- [ ] Das Maß wird automatisch korrekt erkannt (z. B. Durchmesser, Gewinde, Radius, Winkel)
- [ ] Beim Klick wird das ganze zusammengehörige Maß gelesen (z. B. "Ø6 H6", nicht nur "Ø6")
- [ ] Ein Ballon lässt sich per Klick+Ziehen verschieben
- [ ] Ein Ballon lässt sich per Rechtsklick+Ziehen drehen
- [ ] Ein Ballon lässt sich mit STRG+Linksklick löschen
- [ ] Die Bereichs-Suche (Klick+Ziehen auf freier Fläche) setzt einen Ballon für den Text im aufgezogenen Bereich
- [ ] Nach dem Drehen der Zeichnung (↺ / ↻) funktioniert die Erkennung per Klick weiterhin

## 4. Auto-Stempeln
- [ ] Der Knopf "Auto-Stempeln (alle Maße)" stempelt die Maße der Testzeichnung in einem Schritt
- [ ] UMSCHALT + Ziehen stempelt nur die Maße im aufgezogenen Bereich
- [ ] Senkrecht stehende Maße werden ebenfalls erkannt
- [ ] Eine Anzahlangabe wie "4x Ø6 F9" ergibt ein Merkmal "Durchmesser 6 (4x)" mit Passung F9
- [ ] Daneben stehende Abmaße (z. B. "+0,2" / "-0,1") werden dem richtigen Maß zugeordnet
- [ ] Schriftfeld, Datum, Maßstab und Blattrand werden nicht gestempelt
- [ ] Hilfsmaße in Klammern werden nicht gestempelt
- [ ] Die Abschlussmeldung nennt die Anzahl der gestempelten Merkmale und ggf. Positionen, die zu prüfen sind
- [ ] STRG+Z macht den gesamten Auto-Stempel-Schritt auf einmal rückgängig
- [ ] Ein zweiter Durchlauf stempelt bereits gestempelte Maße nicht doppelt
- [ ] Die Ballons verdecken die Maßzahlen nicht

## 5. Form- und Lagetoleranzen
- [ ] Toleranzrahmen (z. B. Position, Ebenheit, Rundlauf) werden beim Auto-Stempeln als eigenes Merkmal erfasst
- [ ] Die Art der Toleranz wird richtig erkannt
- [ ] Ist das Symbol nicht lesbar, steht "Form-/Lagetoleranz" in der Liste und die Abschlussmeldung nennt die Position
- [ ] Die Art lässt sich per Doppelklick auf den Ballon nachträglich wählen

## 6. Scans und Bilder (Texterkennung)
Nur nötig, wenn du mit gescannten Zeichnungen arbeitest, auch gescannte PDFs zählen dazu. Voraussetzung: Tesseract-OCR ist installiert (siehe README).
- [ ] Ohne Tesseract erscheint beim Auto-Stempeln eines Scans eine verständliche Meldung, die App stürzt nicht ab
- [ ] Mit Tesseract werden Maße auf einem Scan oder Bild erkannt (Klick, Bereich und Auto-Stempeln)
- [ ] Die erste Erkennung dauert einige Sekunden, danach reagiert die App normal
- [ ] Durchmesser (Ø) werden richtig gelesen – falls nicht, bitte Beispiel melden
- [ ] Toleranzen mit ± werden richtig übernommen – falls nicht, bitte Beispiel melden

## 7. Toleranzberechnung
- [ ] Bei einem Durchmesser mit ISO-Passung (z. B. h7, H7) wird die Toleranz korrekt berechnet
- [ ] Bei einer J-Passung (z. B. J8) wird die Toleranz asymmetrisch berechnet (nicht symmetrisch wie JS8)
- [ ] Bei einem einfachen Längenmaß ohne Passung wird die ISO-2768-Allgemeintoleranz korrekt eingetragen
- [ ] Ein Längenmaß über 400 mm erhält eine Allgemeintoleranz (z. B. 500 mm, Klasse m: ±0,8)
- [ ] Eine explizit im Text vorgegebene Toleranz (z. B. "0 / -0,1", "+0,2", "-0,2") wird korrekt übernommen und NICHT überschrieben
- [ ] Eine Fase wie "2x45°" erhält die Allgemeintoleranz für Fasen (Klasse m: ±0,2), keine Passungstoleranz
- [ ] Bei einem Winkel bleibt die Toleranz leer, bis im Dialog die "Schenkellänge (mm)" eingetragen ist; danach wird sie nach ISO 2768 berechnet

## 8. Merkmalsliste (Tabelle)
- [ ] Die Merkmalsliste in der Seitenleiste zeigt alle gesetzten Ballons korrekt an
- [ ] Bei jedem Merkmal steht das Maß mit in der Typ-Spalte (z. B. "Länge 20", "Durchmesser 25")
- [ ] Werte in der Tabelle lassen sich bearbeiten (Bezeichnung, Maß)
- [ ] Die Positionsnummer lässt sich ändern, und die anderen Ballons werden automatisch neu nummeriert

## 9. Rückgängig / Wiederholen
- [ ] STRG+Z macht die letzte Aktion rückgängig
- [ ] STRG+Y stellt die Aktion wieder her

## 10. Speichern / Laden
- [ ] Ein Projekt lässt sich speichern (JSON-Datei)
- [ ] Ein gespeichertes Projekt lässt sich wieder laden, inkl. aller Ballons
- [ ] Ein Projekt aus einer älteren Version lässt sich weiterhin laden

## 11. Export
- [ ] PDF-Export funktioniert und zeigt die Ballons korrekt auf der Zeichnung
- [ ] Excel-Export erstellt eine saubere, lesbare Tabelle
- [ ] Q-DAS-Export (.dfq) lässt sich erzeugen (Format-Prüfung optional, falls du Q-DAS-Software hast)
- [ ] Falls Q-DAS-Software vorhanden: Maße werden als variable Merkmale eingelesen

## 12. Test mit eigenen Zeichnungen
- [ ] Eine reale Zeichnung aus dem eigenen Arbeitsalltag lässt sich problemlos laden
- [ ] Die Erkennung funktioniert auch bei komplexeren Zeichnungen zufriedenstellend
- [ ] Die Toleranzberechnung liefert bei bekannten Passungen die erwarteten Werte
- [ ] Wird etwas nicht oder falsch erkannt: Diagnose-Datei speichern (Projekt-Aktionen → "Diagnose: erkannten Text speichern") und dem Issue anhängen

## 13. Allgemeiner Eindruck
- Wie einfach war die Bedienung insgesamt (1 = sehr umständlich, 5 = sehr intuitiv)? ___
- Ist etwas abgestürzt? Falls ja: Die Datei `emp_editor_crash.log` (liegt neben der `.exe`) bitte anhängen
- Was hat gefehlt oder gestört?
- Was hat besonders gut funktioniert?

---

## Fehler melden
Bitte für jeden gefundenen Fehler ein eigenes [GitHub Issue](../../issues/new) mit folgenden Angaben erstellen:
1. **Was hast du versucht zu tun?**
2. **Was ist passiert?**
3. **Was hättest du erwartet?**
4. Screenshot (falls möglich)
5. Inhalt von `emp_editor_crash.log`, falls die App abgestürzt ist
6. Bei Erkennungsfehlern: die Diagnose-Datei (siehe Abschnitt 12)
7. Windows-Version (10 / 11)
