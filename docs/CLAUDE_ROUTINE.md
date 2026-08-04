# Claude-Routine für Felix

Diese Anleitung dient als Gesprächsgrundlage, wenn Felix seinen lokalen Claude mit dem Aufbau der Automatisierung beauftragt.

## Rolle

Claude unterstützt bei Planung, Einrichtung, Test und laufender Kontrolle. Er darf keine Buchungen oder Zahlungen auslösen und keine vertraulichen Originaldaten in dieses öffentliche Repository schreiben.

## Arbeitsauftrag für den lokalen Claude

> Richte mit mir eine tägliche Dokumentenroutine ein. Sie soll um 10 Uhr neue Dateien aus meinem Google-Drive-Eingangsordner erkennen, OCR ausführen, die vereinbarten Felder auslesen und eine Zeile in meinem Dokumentenregister anlegen. Plane zuerst die benötigten Zugriffe, zeige mir jeden Einrichtungsschritt, teste mit anonymisierten Beispieldateien und führe keine irreversible Aktion ohne meine Bestätigung aus. Unklare Werte markierst du zur manuellen Prüfung.

## Abnahme vor dem Echtbetrieb

- Der Test verarbeitet eine Beispiel-PDF und ein Bild.
- Eine Datei wird beim zweiten Lauf nicht doppelt angelegt.
- Unlesbare Dokumente landen in der Fehlerliste.
- Die Tabelle enthält Quelle, Status und Prüfhinweis.
- Felix erhält nach jedem Lauf eine kurze Zusammenfassung.

## Betriebsroutine

Wenn die Routine läuft, kontrolliert Felix täglich die Einträge mit Status „zu prüfen“ und wöchentlich die Fehlerliste. Änderungen am Ablauf werden als Entscheidung in diesem Repository dokumentiert, ohne Kundendaten zu hinterlegen.
