# Logbuch — Entscheidungen und Fehler

Zwei Tabellen, ein Zweck: In sechs Monaten soll nachvollziehbar sein, warum etwas so ist wie es ist — und was schon einmal schiefgegangen ist.

**Regel:** Neue Zeilen kommen oben unter die Überschrift, alte werden nicht überschrieben. Keine Kundennamen, keine Beträge, keine Zugangsdaten.

---

## Entscheidungen

Was am Ablauf geändert wurde und warum. Die ersten Zeilen sind die Grundentscheidungen der Vorlage — sie erklären, warum die Anleitung so aussieht, wie sie aussieht.

| Datum | Entscheidung | Grund |
|---|---|---|
| 2026-10-08 | Agenten-Register `connector/AGENTEN-REGISTER.md` eingeführt; jeder Agent trägt sich ein und hat einen eigenen Briefkasten-PR (nie gemergt). Mentor heißt Jakob (J1), Briefkasten #5 | Anfragen vom 02.10. und 07.10. blieben liegen, weil ein Issue niemanden weckt und unklar war, wer wo erreichbar ist |
| 2026-09-22 | `firmengedaechtnis-light` erhält einen getrennten Mentor-Connector für den Austausch zwischen Felix und Tobias' Agentensystem | Felix kann erprobte Routinen und Betriebswissen erfragen, ohne Zugriff auf Tobias' vollständiges Firmengedächtnis oder dessen Zugangsdaten zu erhalten; der Start erfolgt manuell und ohne gespeicherte Agenten-Secrets |
| 2026-08-14 | Claude läuft lokal auf dem Büro-PC, nicht als Cloud-Sitzung | Eine Cloud-Sitzung sieht weder OneDrive noch das Mailprogramm noch den Scan-Ordner |
| 2026-08-14 | Auslöser der Routinen ist die Windows-Aufgabenplanung | einzige Variante, die ohne zusätzliche Dienste auskommt und auf dem Rechner läuft, auf dem die Dateien liegen |
| 2026-08-14 | WhatsApp-Versand wird nicht automatisiert; der Agent legt stattdessen fertige Texte zur Freigabe vor | WhatsApp Business hat keine Schnittstelle; die Cloud API von Meta wäre für wenige Nachrichten im Monat unverhältnismäßig und würde die gewohnte Nutzung der Rufnummer verändern |
| 2026-08-14 | Register wird als Excel-Datei geführt, nicht als CSV | Deutsches Excel/Calc verfälscht Beträge und Datumsangaben beim CSV-Import |
| 2026-08-14 | Kein separates OCR-Werkzeug in Stufe 1 | Claude liest PDFs und Bilder direkt; ein Bauteil weniger, das ausfallen kann |
| 2026-08-14 | Zugriff auf Mails per IMAP statt über die Dateien des Mailprogramms | ein Mailprogramm ist ein Anzeigeprogramm; Zugriff auf seine laufenden Datenbanken ist fehleranfällig |
| 2026-08-14 | Rechnungsprüfung, Scan-Sortierung, Zubehör- und Lieferprüfung werden als **eine** Maschine gebaut | identischer Ablauf, nur andere Prüfregel und Zielordner |
| 2026-08-14 | Repository enthält die konkreten Betriebsangaben und wird dafür auf privat gestellt | ein Gedächtnis ohne echte Namen, Lieferanten und Pfade ist nur eine Anleitung; Tobias-Entscheid 14.08. — **Umstellung auf privat steht noch aus** |
| 2026-08-04 | Grundstruktur angelegt | gemeinsame Vorlage für Betriebswissen und Automatisierung |

---

## Fehler und was daraus wurde

Jeder Fehler, der im Betrieb auffällt. Auch die kleinen — die Häufung zeigt, wo eine Regel fehlt.

| Datum | Was passiert ist | Ursache | Was geändert wurde |
|---|---|---|---|
| — | *(noch keine Einträge — hier kommt der erste echte Betriebsfehler hinein)* | | |

**Anleitung für den Eintrag:** Was ist passiert (ohne Kundennamen), was war die Ursache, was wurde geändert. Wenn noch nichts geändert wurde, bleibt die letzte Spalte leer — dann ist der Fehler offen und gehört in den Wochenrückblick.

---

## Offene Fragen an Felix

Fragen, die den Ablauf blockieren, bis sie beantwortet sind.

| Seit | Frage | Warum es wichtig ist |
|---|---|---|
| 2026-08-14 | **Fristen-Wächter vorziehen?** Im Mai war das Kernproblem wörtlich „pünktlich bestellen, was 6–8 Wochen Lieferzeit hat" — in der Kandidatenliste steht es unter „später". | ein versäumter Bestelltermin kostet mehr als alle anderen Kandidaten zusammen einsparen |
| 2026-08-14 | Wie sind die Kommissionsnummern aufgebaut? | ohne dieses Muster kann kein Dokument sicher zugeordnet werden |
| 2026-08-14 | Läuft der Büro-PC werktags vormittags zuverlässig? | bestimmt, wann die Routine feuern kann |
| 2026-08-14 | Ab welcher Abweichung soll eine Rechnung als auffällig gelten? | Vorschlag 2 €, gehört nach `wissen/BETRIEB.md` |
| 2026-08-14 | Wer bekommt den Tagesbericht — Felix, Klara oder beide? | |
| 2026-08-14 | Gibt Cyncly eine Schnittstelle zu CompuSoft Winner her? | schriftlich anfragen, bevor A11 verplant wird |
