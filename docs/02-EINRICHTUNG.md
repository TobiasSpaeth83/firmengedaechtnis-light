# Einrichtung

Technische Einrichtung, Schritt für Schritt. Rechne mit einem halben bis ganzen Tag für Schritt 1–5.

## Grundentscheidung: Claude läuft lokal auf dem Windows-PC

Das ist keine Geschmacksfrage, sondern ergibt sich aus dem Betrieb: Die Dokumente liegen in **OneDrive**, die Mails in **Thunderbird**, die Scans auf einem lokalen Ordner. Eine Cloud-Sitzung (Claude im Browser) kommt an keine dieser Dateien heran. Also: **Claude Code auf dem Rechner, auf dem OneDrive synchronisiert.**

Das hat eine Konsequenz, die man wissen muss: **Der Rechner muss laufen, wenn die Routine feuern soll.** Wenn der Bürorechner abends aus ist, läuft nachts nichts. Deshalb legen wir die Routinen auf die Bürozeit (Vorschlag: 10:00 Uhr).

## Schritt 1 — Eigene private Kopie anlegen

Diese Vorlage ist öffentlich. Die Arbeitskopie darf es nicht sein.

1. Auf GitHub ein **neues privates Repository** anlegen, z. B. `fs-kreativ-firmengedaechtnis`.
2. Inhalt dieser Vorlage hineinkopieren (Download als ZIP reicht — kein Fork, ein Fork eines öffentlichen Repos kann nicht privat gestellt werden).
3. Auf dem Büro-PC in einen Ordner klonen, z. B. `C:\Firmengedaechtnis\`.

Der Ordner sollte **nicht** in OneDrive liegen — OneDrive und Git kommen sich beim Synchronisieren in die Quere.

## Schritt 2 — Claude Code installieren

Auf dem Büro-PC installieren und mit dem Anthropic-Abo anmelden. Danach im Repository-Ordner starten:

```
cd C:\Firmengedaechtnis
claude
```

Beim Start liest Claude automatisch `CLAUDE.md`. Testfrage zum Prüfen, ob das geklappt hat: *„Was sind hier die Regeln zu Kommissionsnummern?"* — kommt eine sinnvolle Antwort, sitzt es.

## Schritt 3 — Betriebsprofil ausfüllen

`wissen/BETRIEB.md`, `wissen/GLOSSAR.md` und `wissen/LIEFERANTEN-UND-PORTALE.md` ausfüllen. Am schnellsten im Dialog: Claude bitten, die Fragen einzeln zu stellen.

Ohne diesen Schritt rät Claude bei jedem Dokument neu, was eine Kommission ist und wie eure Ordner heißen.

## Schritt 4 — Ordner festlegen

Drei Ordner in OneDrive, parallel zur bestehenden Struktur:

| Ordner | Zweck |
|---|---|
| `00-Eingang` | Hier landen neue Scans und Downloads. Der Agent schaut nur hier hinein. |
| `00-Manuell-pruefen` | Alles, was der Agent nicht sicher zuordnen konnte. |
| `00-Verarbeitet` | Ablage-Kopien, falls der Zielordner unklar war. |

Die bestehende Struktur pro Kommission bleibt unverändert — dorthin sortiert der Agent am Ende ein.

## Schritt 5 — Register anlegen

`data/dokumentenregister.csv` als Vorlage nehmen und als **Excel-Datei** (nicht CSV) im OneDrive anlegen, z. B. `00-Register\Dokumentenregister.xlsx`.

**Warum nicht CSV:** Deutsches Excel und OpenOffice Calc interpretieren CSV-Dateien je nach Einstellung unterschiedlich — vor allem bei Beträgen (`1250.00` wird schnell zu `125000`) und Datumsangaben. Bei einer Datei, in der Rechnungsbeträge stehen, ist das ein echtes Risiko. Als `.xlsx` gibt es das Problem nicht.

Spalten siehe `data/dokumentenregister.csv`. Beträge im Register immer mit Punkt als Dezimaltrennzeichen speichern und als Zahl formatieren.

## Schritt 6 — OCR? Meistens nicht nötig

Die ursprüngliche Planung sah einen eigenen OCR-Dienst vor. Das kann man sich in den meisten Fällen sparen: **Claude liest PDFs und Bilder direkt**, auch eingescannte. Ein zusätzliches OCR-Werkzeug lohnt erst, wenn sich zeigt, dass die Scan-Qualität nicht reicht.

Vorgehen: erst ohne OCR testen, dann entscheiden. Ein Werkzeug, das man nicht braucht, ist ein Werkzeug, das kaputtgehen kann.

## Schritt 7 — Zugangsdaten

Alles, was ein Passwort braucht (Mailpostfach, später Lieferanten- und Steuerberaterportale), kommt in eine Datei `.env` im Repository-Ordner. Die steht in `.gitignore` und wird nie mit hochgeladen.

```
MAIL_IMAP_HOST=...
MAIL_IMAP_USER=...
MAIL_IMAP_PASS=...
```

Passwörter niemals in eine `.md`-Datei schreiben und niemals in den Chat tippen.

## Schritt 8 — Erst Trockenlauf, dann scharf

Bevor ein Agent Dateien verschiebt oder umbenennt, läuft er im Trockenlauf: Er sagt, was er tun *würde*. Erst wenn das an 10 echten Dokumenten stimmt, bekommt er Schreibrechte. Details je Agent im jeweiligen Steckbrief in `agenten/`.

## Abnahme vor dem Echtbetrieb

- [ ] Eine Beispiel-PDF und ein Foto werden korrekt erkannt.
- [ ] Ein zweiter Lauf legt dieselbe Datei **nicht** noch einmal an.
- [ ] Ein unleserliches Dokument landet in `00-Manuell-pruefen` und nicht im Register als „fertig".
- [ ] Ein Dokument ohne erkennbare Kommission landet in `00-Manuell-pruefen`.
- [ ] Das Register enthält Quelle, Status und Prüfhinweis.
- [ ] Nach jedem Lauf kommt eine kurze Zusammenfassung an.
- [ ] Beträge stehen in der Tabelle als Zahl, nicht als Text.

Erst wenn alle sieben Haken sitzen, geht der Agent in Betrieb.

## Laufende Kosten

| Posten | ca. |
|---|---|
| Anthropic-Abo | 20–100 €/Monat je nach Nutzung |
| Rest | 0 € — OneDrive, Excel, Thunderbird sind vorhanden |

Kein zusätzliches SaaS nötig für die erste Ausbaustufe.
