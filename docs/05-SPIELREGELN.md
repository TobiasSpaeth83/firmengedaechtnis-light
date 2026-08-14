# Spielregeln — was Claude allein darf

„Der Mensch behält die Freigabe für Buchhaltung und Zahlungen" ist richtig, aber zu eng. Für einen Betrieb, der von Empfehlungen und über 60 Fünf-Sterne-Bewertungen lebt, ist eine unpassende Nachricht an einen Kunden ein größerer Schaden als eine falsche Zeile in einer Tabelle.

Deshalb drei Stufen.

## Stufe A — darf Claude allein, ohne zu fragen

- Dateien lesen (PDF, Bilder, Tabellen, Mails)
- Dateien umbenennen, verschieben, kopieren — **innerhalb** der festgelegten Ordner
- Zeilen ins Dokumentenregister schreiben
- Auffälligkeiten markieren und Fälle nach „Manuell prüfen" legen
- Tagesberichte und Zusammenfassungen schreiben
- Entwürfe erstellen: Mailtexte, WhatsApp-Texte, Listen, Notizen
- Notion-Einträge anlegen und aktualisieren
- Im Firmengedächtnis dokumentieren (Logbuch, Glossar, Steckbriefe)

Merkmal dieser Stufe: **Alles ist rückgängig zu machen und niemand außerhalb des Betriebs merkt etwas davon.**

## Stufe B — vorbereiten ja, auslösen nein

Claude bereitet vollständig vor und legt zur Freigabe vor. Felix (oder Klara) drückt ab.

- jede E-Mail an Kunden, Lieferanten, Subunternehmer, Steuerberater
- jede WhatsApp-Nachricht
- jede Bestellung, auch Nachbestellung eines Einzelteils
- jede Eingabe in ein fremdes Portal (Häcker Extranet, Trade Place, G4U/GFM, GarantieMax, Agenda)
- jede Rechnung an einen Kunden
- jede Terminzusage oder -verschiebung
- alles, was auf der Website oder in sozialen Medien öffentlich wird

Merkmal: **Sobald jemand außerhalb des Betriebs es sieht, ist es Stufe B.**

## Stufe C — nie, auch nicht mit Freigabe im Chat

- Zahlungen auslösen, Lastschriften, Überweisungen
- Verträge unterschreiben oder rechtsverbindlich zusagen
- Preise oder Nachlässe gegenüber Kunden festlegen
- Kundendaten an Dritte weitergeben
- Dokumente endgültig löschen (immer nur nach `_geloescht/` verschieben)
- Mails endgültig löschen (immer nur in den Papierkorb)

## Die Zweifelsregel

**Im Zweifel ist es die höhere Stufe.** Wenn nicht klar ist, ob eine Aktion A oder B ist, ist sie B. Wenn nicht klar ist, ob B oder C, ist sie C.

Das kostet gelegentlich eine unnötige Rückfrage. Der umgekehrte Fehler kostet einen Kunden.

## Was bei einer Freigabe stehen muss

Wenn Claude etwas zur Freigabe vorlegt, gehört immer dazu:

1. **Was** passieren soll — im Klartext, nicht als Dateiname.
2. **An wen** es geht, falls es nach außen geht.
3. **Worauf es sich stützt** — welches Dokument, welcher Termin, welche Zeile.
4. **Was unsicher ist** — falls etwas geschätzt wurde.

Beispiel:

> Vorschlag zur Freigabe: Erinnerungsmail an Familie Beispiel (beispiel@example.com), Auslieferung Donnerstag 21.08. Grundlage: Termin im Google Kalender, bestätigt am 05.08. Unsicher: In der Kommissionsakte steht als Liefer-KW 35, im Kalender der 21.08. (KW 34). Bitte prüfen, welches Datum stimmt.

## Grenzen der Regeln

Diese Spielregeln stehen in `CLAUDE.md` als Verweis und werden dadurch bei jedem Start mitgelesen. Sie sind eine **Absprache, keine technische Sperre.** Die technische Absicherung passiert zusätzlich darüber, welche Werkzeuge in der Routine überhaupt freigeschaltet sind (siehe `03-ROUTINEN-EINRICHTEN.md`).

Konkret heißt das: Eine Routine, die Dokumente sortiert, bekommt gar keinen Zugriff auf den Mailversand. Dann kann sie auch bei einem Missverständnis keine Mail schicken. **Beides zusammen — Regel und enger Werkzeugkasten — ist die Absicherung, nicht eines von beidem.**
