# Logbuch — Entscheidungen und Fehler

Zwei Tabellen, ein Zweck: In sechs Monaten soll nachvollziehbar sein, warum etwas so ist wie es ist — und was schon einmal schiefgegangen ist.

**Regel:** Neue Zeilen kommen oben unter die Überschrift, alte werden nicht überschrieben. Keine Kundennamen, keine Beträge, keine Zugangsdaten.

---

## Entscheidungen

Was am Ablauf geändert wurde und warum. Die ersten Zeilen sind die Grundentscheidungen der Vorlage — sie erklären, warum die Anleitung so aussieht, wie sie aussieht.

| Datum | Entscheidung | Grund |
|---|---|---|
| 2026-08-14 | Claude läuft lokal auf dem Büro-PC, nicht als Cloud-Sitzung | Eine Cloud-Sitzung sieht weder OneDrive noch das Mailprogramm noch den Scan-Ordner |
| 2026-08-14 | Auslöser der Routinen ist die Windows-Aufgabenplanung | einzige Variante, die ohne zusätzliche Dienste auskommt und auf dem Rechner läuft, auf dem die Dateien liegen |
| 2026-08-14 | WhatsApp-Versand wird nicht automatisiert; der Agent legt stattdessen fertige Texte zur Freigabe vor | WhatsApp Business hat keine Schnittstelle; die Cloud API von Meta wäre für wenige Nachrichten im Monat unverhältnismäßig und würde die gewohnte Nutzung der Rufnummer verändern |
| 2026-08-14 | Register wird als Excel-Datei geführt, nicht als CSV | Deutsches Excel/Calc verfälscht Beträge und Datumsangaben beim CSV-Import |
| 2026-08-14 | Kein separates OCR-Werkzeug in Stufe 1 | Claude liest PDFs und Bilder direkt; ein Bauteil weniger, das ausfallen kann |
| 2026-08-14 | Zugriff auf Mails per IMAP statt über die Dateien des Mailprogramms | ein Mailprogramm ist ein Anzeigeprogramm; Zugriff auf seine laufenden Datenbanken ist fehleranfällig |
| 2026-08-14 | Rechnungsprüfung, Scan-Sortierung, Zubehör- und Lieferprüfung werden als **eine** Maschine gebaut | identischer Ablauf, nur andere Prüfregel und Zielordner |
| 2026-08-14 | Arbeitskopie des Firmengedächtnisses muss privat sein; die Vorlage bleibt namensfrei | echtes Betriebswissen und Personennamen gehören nicht in ein öffentliches Repository |
| 2026-08-04 | Grundstruktur angelegt | gemeinsame Vorlage für Betriebswissen und Automatisierung |

---

## Fehler und was daraus wurde

Jeder Fehler, der im Betrieb auffällt. Auch die kleinen — die Häufung zeigt, wo eine Regel fehlt.

| Datum | Was passiert ist | Ursache | Was geändert wurde |
|---|---|---|---|
| — | *(noch keine Einträge — hier kommt der erste echte Betriebsfehler hinein)* | | |

**Anleitung für den Eintrag:** Was ist passiert (ohne Kundennamen), was war die Ursache, was wurde geändert. Wenn noch nichts geändert wurde, bleibt die letzte Spalte leer — dann ist der Fehler offen und gehört in den Wochenrückblick.

---

## Offene Fragen an den Inhaber

Fragen, die den Ablauf blockieren, bis sie beantwortet sind.

| Seit | Frage | Warum es wichtig ist |
|---|---|---|
| 2026-08-14 | Wie sind die Kommissionsnummern aufgebaut? | ohne dieses Muster kann kein Dokument sicher zugeordnet werden |
| 2026-08-14 | Läuft der Büro-PC werktags vormittags zuverlässig? | bestimmt, wann die Routine feuern kann |
| 2026-08-14 | Ab welcher Abweichung soll eine Rechnung als auffällig gelten? | Vorschlag 2 €, gehört nach `wissen/BETRIEB.md` |
