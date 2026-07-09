# Test-Checkliste – Ballista Prüfplan (v0.1 Beta)

Danke, dass du beim Testen hilfst! Bitte geh diese Punkte durch und trage dein Feedback direkt hier ein oder erstelle für jeden gefundenen Fehler ein eigenes GitHub Issue.

## 1. Installation & erster Start
- [ ] `Ballista Pruefplan.exe` (bzw. Setup) erfolgreich heruntergeladen
- [ ] Die Anwendung lässt sich per Doppelklick starten
- [ ] Bei der Windows-Warnung "Windows hat Ihren PC geschützt" konnte die App über "Weitere Informationen" → "Trotzdem ausführen" gestartet werden
- [ ] Beim ersten Start dauert es 5–15 Sekunden – die App erscheint danach normal
- [ ] Das Ballista-Logo wird oben links im Fenster und in der Taskleiste angezeigt

## 2. Datei laden
- [ ] Eine der mitgelieferten Testzeichnungen (PDF) lässt sich über "Datei laden" öffnen
- [ ] Die Zeichnung wird korrekt und scharf angezeigt
- [ ] Ein Bild (PNG/JPG) lässt sich alternativ ebenfalls laden
- [ ] Beim Laden einer neuen Datei mit bereits gesetzten Ballons erscheint die Rückfrage "Möchten Sie speichern?"

## 3. Ballons setzen
- [ ] Ein Ballon lässt sich per Linksklick auf ein Maß setzen
- [ ] Das Maß wird automatisch korrekt erkannt (z. B. Durchmesser, Gewinde, Radius, Winkel)
- [ ] Ein Ballon lässt sich per Klick+Ziehen verschieben
- [ ] Ein Ballon lässt sich per Rechtsklick+Ziehen drehen
- [ ] Ein Ballon lässt sich mit STRG+Linksklick löschen
- [ ] Die Bereichs-Suche (Klick+Ziehen aufziehen) erkennt mehrere Ballons auf einmal korrekt

## 4. Toleranzberechnung
- [ ] Bei einem Durchmesser mit ISO-Passung (z. B. h7, H7) wird die Toleranz korrekt berechnet
- [ ] Bei einer J-Passung (z. B. J8) wird die Toleranz asymmetrisch berechnet (nicht symmetrisch wie JS8)
- [ ] Bei einem einfachen Längenmaß ohne Passung wird die ISO-2768-Allgemeintoleranz korrekt eingetragen
- [ ] Eine explizit im Text vorgegebene Toleranz (z. B. "0 / -0,1", "+0,2", "-0,2") wird korrekt übernommen und NICHT überschrieben

## 5. Merkmalsliste (Tabelle)
- [ ] Die Merkmalsliste in der Seitenleiste zeigt alle gesetzten Ballons korrekt an
- [ ] Bei jedem Merkmal steht das Maß mit in der Typ-Spalte (z. B. "Länge 20", "Durchmesser 25")
- [ ] Werte in der Tabelle lassen sich bearbeiten (Bezeichnung, Maß)
- [ ] Die Positionsnummer lässt sich ändern, und die anderen Ballons werden automatisch neu nummeriert

## 6. Rückgängig / Wiederholen
- [ ] STRG+Z macht die letzte Aktion rückgängig
- [ ] STRG+Y stellt die Aktion wieder her

## 7. Speichern / Laden
- [ ] Ein Projekt lässt sich speichern (JSON-Datei)
- [ ] Ein gespeichertes Projekt lässt sich wieder laden, inkl. aller Ballons

## 8. Export
- [ ] PDF-Export funktioniert und zeigt die Ballons korrekt auf der Zeichnung
- [ ] Excel-Export erstellt eine saubere, lesbare Tabelle
- [ ] Q-DAS-Export (.dfq) lässt sich erzeugen (Format-Prüfung optional, falls du Q-DAS-Software hast)

## 9. Allgemeiner Eindruck
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
6. Windows-Version (10 / 11)
