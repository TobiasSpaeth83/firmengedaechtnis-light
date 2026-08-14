# A2 — Scan-Sortierer

**Stufe:** 1 (Start) · **Stand:** 14.08.2026 · **Status:** Entwurf, noch nicht in Betrieb

Der erste Agent. Sortiert eingehende Scans und Downloads, benennt sie einheitlich und legt sie ab.

## Warum dieser zuerst

Höchste Menge (2–15 Scans die Woche), kein Zugriff nach außen, Fehler sind harmlos — eine falsch benannte Datei benennt man um. Ideal, um zu sehen, ob Claude die Dokumente des Betriebs versteht, bevor irgendetwas Wichtiges davon abhängt.

## Auslöser

Werktags 10:00 Uhr über die Windows-Aufgabenplanung. Zusätzlich jederzeit von Hand: „Sortier bitte den Eingang."

## Ablauf

1. **Neue Dateien finden** in `00-Eingang`. Für jede Datei Pfad und Prüfsumme bilden und im Register nachsehen, ob sie schon verarbeitet wurde. Wenn ja: überspringen.
2. **Dokument lesen** und einordnen, um welchen Typ es sich handelt:
   - Lieferantenrechnung · Auftragsbestätigung · Lieferschein/Abladebestätigung · Kundendokument · Behördenpost · Versicherung/Bank · Privat · Unklar
3. **Kommission zuordnen.** Kommissionsnummer im Dokument suchen. Wenn nicht vorhanden: über Kundenname und Datum versuchen. Wenn nicht eindeutig → Status `zu_pruefen`.
4. **Umbenennen** nach dem Schema:
   `JJJJ-MM-TT_Typ_Absender_Kommission.pdf`
   Beispiel: `2026-08-12_Rechnung_Beispiel-Lieferant_K-2026-041.pdf`
   Fehlt die Kommission: `_ohne-komm` statt der Nummer.
5. **Ablegen:**
   - eindeutig zugeordnet → Kommissionsordner in OneDrive
   - unklar, unleserlich, Handlungsbedarf, privat → `00-Manuell-pruefen`
6. **Registerzeile schreiben** (Felder siehe `data/dokumentenregister.csv`).
7. **Tagesbericht** nach `berichte/JJJJ-MM-TT.md`.

## Was immer nach „Manuell prüfen" geht

- unleserlich oder nur teilweise lesbar
- keine eindeutige Kommission
- als privat erkannt
- Behördenpost, insbesondere Finanzamt — **immer**, auch wenn eindeutig zuzuordnen
- Mahnungen, Fristen, Kündigungen
- alles, was der Agent nicht sicher einem der Typen zuordnen kann

Lieber eine Datei zu viel in der Prüfliste als eine falsch abgelegte.

## Was der Agent nie tut

- Dateien löschen (auch keine offensichtlichen Fehlscans — die kommen nach `00-Manuell-pruefen`)
- Dateien außerhalb der festgelegten Ordner verändern
- irgendetwas versenden
- Beträge oder Nummern erraten, um ein Feld zu füllen

## Trockenlauf vor dem Scharfschalten

Erster Lauf mit dem Zusatz: *„Verändere nichts. Sag mir für jede Datei: erkannter Typ, erkannte Kommission, geplanter neuer Name, geplanter Zielordner, Sicherheit hoch/mittel/niedrig."*

Bestanden, wenn von 10 echten Scans mindestens 8 richtig eingeordnet sind **und** die zwei falschen als „niedrige Sicherheit" markiert waren. Der zweite Teil ist der wichtigere: Ein Agent, der weiß, wann er unsicher ist, ist brauchbar. Einer, der sich sicher irrt, nicht.

## Abnahme

- [ ] Trockenlauf bestanden (siehe oben)
- [ ] Zweiter Lauf legt dieselbe Datei nicht doppelt an
- [ ] Ein unleserlicher Scan landet in `00-Manuell-pruefen`
- [ ] Ein Scan ohne Kommission landet in `00-Manuell-pruefen`
- [ ] Behördenpost landet in `00-Manuell-pruefen`, auch wenn zuordenbar
- [ ] Tagesbericht kommt an und ist verständlich

## Bekannte Schwachstellen

| Was | Wie damit umgehen |
|---|---|
| Handschriftliche Notizen auf Ausdrucken | werden oft nicht erkannt — Status `zu_pruefen` ist hier der Normalfall, kein Fehler |
| Mehrere Dokumente in einem Scan | wird zunächst nicht getrennt; solche Scans nach Möglichkeit einzeln einscannen |
| Kommissionsnummer nur auf Seite 2 | Agent liest alle Seiten, dauert aber länger — bei sehr langen PDFs ggf. nur die ersten 5 Seiten |

## Änderungen

| Datum | Was |
|---|---|
| 2026-08-14 | Steckbrief angelegt |
