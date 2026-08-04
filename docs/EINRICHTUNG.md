# Einrichtung der Dokumentenautomatisierung

## Ziel

Neue PDF-, Bild- und Scan-Dokumente aus einem Google-Drive-Eingangsordner werden täglich erkannt, per OCR in Text umgewandelt und als Zeile in einem Dokumentenregister erfasst.

## Benötigt

- einen Google-Drive-Eingangsordner, beispielsweise „Eingang Dokumente“;
- einen separaten Archivordner und einen Ordner „Manuell prüfen“;
- eine Google-Tabelle oder Excel-Datei nach dem Muster in `data/dokumentenregister.csv`;
- einen OCR-Dienst oder ein lokales OCR-Werkzeug;
- eine Automatisierungsumgebung mit Zugriff auf Drive, OCR und Tabelle.

## Täglicher Ablauf um 10 Uhr

1. Suche im Eingangsordner nach neuen, noch nicht registrierten Dateien.
2. Prüfe Dateityp und Lesbarkeit.
3. Führe OCR aus und speichere den extrahierten Text nur im geschützten System, nicht im öffentlichen Repository.
4. Extrahiere Dokumentdatum, Absender, Dokumenttyp, Betrag und Referenznummer, sofern vorhanden.
5. Ergänze eine Zeile im Dokumentenregister.
6. Verschiebe erfolgreiche Dateien ins Archiv; unklare oder fehlerhafte Fälle nach „Manuell prüfen“.
7. Erstelle eine kurze Tageszusammenfassung: verarbeitet, offen, Fehler.

## Wichtige Regeln

- Keine Datei zweimal registrieren: Drive-Datei-ID oder Prüfsumme als eindeutige Kennung nutzen.
- Felder mit geringer Sicherheit als „zu prüfen“ markieren, nicht raten.
- Zugangsdaten ausschließlich in der Automatisierungsumgebung speichern.
- Der Mensch behält die Freigabe für Buchhaltung und Zahlungen.
