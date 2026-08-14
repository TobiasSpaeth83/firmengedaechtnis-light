# Routinen einrichten — wie „täglich um 10 Uhr" real wird

In der ersten Fassung stand „Täglicher Ablauf um 10 Uhr", aber nicht, **wodurch** er ausgelöst wird. Genau daran scheitern solche Projekte. Diese Seite schließt die Lücke.

## Das Grundprinzip

Claude wacht nicht von selbst auf. Es braucht etwas, das ihn weckt. Dieses Etwas ist bei uns die **Windows-Aufgabenplanung** — das eingebaute Windows-Werkzeug, das auch Backups oder Updates startet.

```
Windows-Aufgabenplanung  →  startet claude mit einem festen Auftrag
                         →  Claude arbeitet die Routine ab
                         →  Ergebnis landet im Register + als Tagesbericht
```

## Warum nicht die Cloud-Variante

Claude kann auch im Browser nach Zeitplan laufen. Für diesen Betrieb geht das nicht: Eine Cloud-Sitzung sieht weder OneDrive noch Thunderbird noch den Scan-Ordner. Für Aufgaben, die nur im Web stattfinden (später z. B. Portal-Abfragen), kann man darauf zurückkommen — für alles, was Dateien anfasst, muss es lokal laufen.

## Einrichtung in drei Schritten

### 1. Auftragsdatei anlegen

Der Auftrag steht in einer Datei, nicht im Aufgabenplaner. So kann man ihn ändern, ohne die Windows-Einstellungen anzufassen.

`routinen/taeglich-dokumente.txt`:

```
Führe die tägliche Dokumentenroutine aus.

Lies zuerst CLAUDE.md, wissen/BETRIEB.md und agenten/A2-scan-sortierer.md.
Arbeite dann exakt nach dem Ablauf im Steckbrief.

Wichtig:
- Nichts raten. Unsichere Fälle nach 00-Manuell-pruefen.
- Nichts nach außen senden.
- Am Ende Tagesbericht schreiben nach berichte/JJJJ-MM-TT.md.
```

### 2. Startskript anlegen

`routinen/taeglich-dokumente.cmd`:

```bat
cd /d C:\Firmengedaechtnis
claude -p "%CD%\routinen\taeglich-dokumente.txt" >> routinen\log.txt 2>&1
```

`claude -p` ist der Modus ohne Rückfragen ("headless"): Claude arbeitet den Auftrag ab und beendet sich.

**Beim ersten Einrichten prüfen:** `claude --help` zeigt die aktuellen Schalter. Für einen unbeaufsichtigten Lauf braucht es zusätzlich eine Angabe, welche Werkzeuge ohne Nachfrage erlaubt sind — sonst bleibt der Lauf bei der ersten Rückfrage stehen, und niemand sitzt davor. Diesen Schalter beim Setup gemeinsam festlegen und **so eng wie möglich** halten: Lesen und Dateien verschieben ja, Mailversand nein.

### 3. Aufgabe in Windows anlegen

Aufgabenplanung öffnen → *Einfache Aufgabe erstellen*:

| Feld | Wert |
|---|---|
| Name | `Claude – Dokumentenroutine` |
| Auslöser | Täglich, 10:00 Uhr |
| Aktion | Programm starten: `C:\Firmengedaechtnis\routinen\taeglich-dokumente.cmd` |
| Einstellungen | „Aufgabe so schnell wie möglich nachholen, wenn Start verpasst wurde" aktivieren |

Der Haken beim Nachholen ist wichtig: Ist der Rechner um 10 Uhr aus, läuft die Routine beim nächsten Hochfahren.

## Prüfen, ob es läuft

Die ersten Tage nicht darauf vertrauen, dass es läuft, sondern nachsehen:

1. `routinen\log.txt` — ist heute etwas passiert?
2. `berichte\` — gibt es den Tagesbericht von heute?
3. Register — sind neue Zeilen dazugekommen?

**Merke:** Eine Routine, die still nicht läuft, ist schlimmer als gar keine — man verlässt sich darauf. Deshalb: Wenn an einem Werktag kein Tagesbericht da ist, ist das ein Fehler und gehört ins Logbuch.

## Empfohlener Takt

| Routine | Wann | Warum |
|---|---|---|
| Dokumente/Scans | werktags 10:00 | vormittags, damit Rückfragen am selben Tag geklärt werden |
| Rechnungsprüfung | werktags 10:00 (gleicher Lauf) | dieselben Dokumente, ein Aufwasch |
| Wochenrückblick | freitags 15:00 | offene „zu prüfen"-Fälle, Fehler der Woche |

Mehr Routinen heißen nicht mehr Nutzen. Ein Lauf am Tag, der zuverlässig durchläuft, ist mehr wert als vier, die niemand kontrolliert.

## Wenn eine Routine hängt

Sie läuft nicht endlos weiter, sondern bricht ab. Dann:

1. `routinen\log.txt` ansehen — meistens steht die Ursache in den letzten Zeilen.
2. Unverarbeitete Dateien bleiben im Eingang liegen. Nichts geht verloren.
3. Ursache ins Logbuch, dann die Regel oder den Auftragstext nachschärfen.
