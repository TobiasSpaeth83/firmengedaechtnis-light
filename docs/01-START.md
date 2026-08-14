# Start — die ersten 90 Minuten

Diese Seite ist für den allerersten Tag. Kein Vorwissen nötig. Wenn du damit durch bist, läuft ein erster Agent und du weißt, wie es weitergeht.

## Worum es geht — in vier Sätzen

Claude ist ein Assistent, der auf deinem PC Dateien lesen und schreiben darf. Du sagst ihm einmal, wie dein Betrieb arbeitet — das steht in diesem Repository. Danach kann er wiederkehrende Arbeit selbst erledigen: Rechnungen prüfen, Scans einsortieren, Post vorsortieren. Was er nicht sicher weiß, legt er dir zur Prüfung hin, statt zu raten.

## Was sich dadurch ändern soll

Dein Engpass ist nicht der Verkauf, sondern die Verwaltung. 10–15 Lieferantenrechnungen im Monat, 2–15 Scans die Woche, täglich Post im Thunderbird — das kostet dich und Klara Stunden, die keine Küche verkaufen. Genau diese Masse ist das Ziel. Nicht die schicken Sachen wie WhatsApp-Bots.

## Die vier Bausteine

| Baustein | Was es ist | Wo |
|---|---|---|
| **Das Gedächtnis** | Regeln und Betriebswissen, die Claude automatisch kennt | dieses Repository |
| **Die Ablage** | deine echten Dokumente | OneDrive, wie bisher |
| **Das Register** | eine Tabelle: welches Dokument wurde wann wie verarbeitet | Excel/Calc, Vorlage in `data/` |
| **Die Routine** | der Auslöser, der Claude täglich weckt | Windows-Aufgabenplanung |

Wichtig: **An deiner Ablage ändert sich nichts.** OneDrive bleibt OneDrive, Notion bleibt Notion. Es kommt nur ein Assistent dazu, der hineinschaut.

## Ablauf des ersten Tages

### Schritt 1 — Repository privat stellen und klonen (10 Min)

Anleitung: [02-EINRICHTUNG.md](02-EINRICHTUNG.md), Schritt 1.

Warum privat: Hier stehen deine Lieferanten, deine Abläufe, deine Entscheidungen. Das geht niemanden etwas an.

### Schritt 2 — Betriebsprofil ausfüllen (30 Min)

`wissen/BETRIEB.md` öffnen und die Lücken füllen: Ordnerpfade, welche Hersteller, wie deine Kommissionsnummern aussehen. Das ist die wichtigste halbe Stunde des ganzen Projekts — alles, was hier fehlt, muss Claude später raten.

Am schnellsten geht das im Gespräch: Claude starten und sagen „Geh mit mir `wissen/BETRIEB.md` durch und stell mir die Fragen einzeln."

### Schritt 3 — Ersten Agenten testen, ohne dass er etwas verändert (30 Min)

Wir fangen mit dem **Scan-Sortierer** an (`agenten/A2-scan-sortierer.md`), im Trockenlauf: Claude schaut sich 10 echte Scans an und sagt dir, wie er sie benennen und einsortieren *würde* — ohne eine Datei anzufassen.

Du siehst sofort, ob er deine Dokumente versteht. Und es kann nichts kaputtgehen.

### Schritt 4 — Erst dann scharf schalten (20 Min)

Wenn der Trockenlauf passt: Ablage erlauben und die tägliche Routine einrichten ([03-ROUTINEN-EINRICHTEN.md](03-ROUTINEN-EINRICHTEN.md)).

## Danach: vier Wochen mitlaufen lassen

Nicht sofort den nächsten Agenten bauen. Erst vier Wochen mit einem laufen, jeden Morgen zwei Minuten die „zu prüfen"-Zeilen anschauen. Was dabei schiefgeht, kommt ins Logbuch — und macht den zweiten Agenten besser.

Der häufigste Fehler in solchen Projekten ist, fünf Automatisierungen gleichzeitig zu starten und dann keiner mehr zu trauen.

## Was du wissen solltest, bevor du anfängst

- **Die ersten Wochen musst du gegenlesen.** Beim Lesen von Scans passieren Fehler. Das wird schnell besser, aber am Anfang ist Kontrolle Pflicht.
- **Standardisierte Dokumente sind einfach, handschriftliche schwer.** Eine Herstellerrechnung: kein Problem. Ein handschriftlicher Zettel vom Montageteam: eher nicht.
- **Es ersetzt kein Warenwirtschaftssystem.** Es nimmt dir Handgriffe ab, es führt nicht deinen Betrieb.
- **Rechne mit Nacharbeit.** Ein Agent ist nach dem ersten Bauen zu 80 % fertig. Die letzten 20 % kommen aus dem echten Betrieb.

## Wenn du nicht weiterkommst

Claude starten und fragen. Er kennt dieses Repository. Formulierungen wie „Ich verstehe Schritt 3 nicht, erklär's mir nochmal anders" funktionieren — er weiß aus `CLAUDE.md`, dass er ohne Fachchinesisch antworten soll.
