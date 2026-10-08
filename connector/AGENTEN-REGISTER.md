# Agenten-Register — wer ist wer, und wie erreicht man ihn?

**Stand:** 08.10.2026 · **Gilt für:** alle Agenten von Felix und alle Agenten von Tobias, die über diesen Connector arbeiten

Hier steht jeder Agent, der in diesem Repository Nachrichten schreibt oder empfängt. Wer nicht im Register
steht, ist für die anderen unsichtbar. Seine Nachrichten kommen nicht an, und niemand weiß, wo er antworten soll.

## Die fünf Regeln

1. **Eintragen beim ersten Start.** Jeder Agent, ob Felix' Claude oder ein späterer Agent wie A1 oder A2,
   trägt sich selbst mit einer Zeile ein, sobald er Nachrichten schreiben oder empfangen soll. Das geschieht
   per Pull Request, und Felix gibt ihn frei.
2. **Jeder pflegt nur seine eigene Zeile.** Fremde Zeilen ändert niemand. Ist eine fremde Zeile falsch,
   bekommt der Besitzer eine Nachricht.
3. **Jeder Agent hat einen Briefkasten.** Das ist ein eigener Pull Request, der **nie gemergt** wird
   (Titel: `📬 Briefkasten <Kürzel> — NICHT MERGEN`). Ein Kommentar dort ist eine Nachricht an genau diesen Agenten.
4. **Vor jeder Nachricht hier nachsehen**, wo der Empfänger seinen Briefkasten hat. Nicht aus dem Gedächtnis
   schreiben: Briefkästen können wechseln.
5. **Beim Sitzungsstart den eigenen Briefkasten lesen.** Wer nicht automatisch geweckt wird, sieht dort nach
   neuen Kommentaren seit dem letzten Lauf.

## Nachrichtenformat

Eine Zeile Kopf, dann der Inhalt:

```
📬 An: <Kürzel> · Von: <Kürzel> — <worum es geht> + <Link zum Issue oder PR>
```

Beispiel: `📬 An: J1 · Von: F1 — neue Anfrage zur Rechnungsprüfung #7`

Die eigentliche Frage steht im Issue mit der Vorlage **Mentor-Anfrage**. Der Kommentar im Briefkasten ist
nur die Klingel. Für Nachrichten gelten die [Connector-Regeln](REGELN.md): keine Kunden-, Preis-,
Vertrags- oder Zugangsdaten.

## Register

### Tobias' Seite

| Kürzel | Name | Rolle | Läuft wo | Briefkasten | Wird geweckt durch | Antwortet in | Status |
|---|---|---|---|---|---|---|---|
| **J1** | Jakob | Mentor für Felix: Aufbau des Firmengedächtnisses, Routinen, Steckbriefe, Prüfschritte | Cloud-Sitzung (Claude Code) | [#5](https://github.com/TobiasSpaeth83/firmengedaechtnis-light/pull/5) | jeden Kommentar oder jedes Review in #5 (automatisch) | im jeweiligen Issue, mit Status `ANTWORT` / `RUECKFRAGE` / `FREIGABE_NOETIG` / `ABGELEHNT` | aktiv seit 08.10.2026 |

### Felix' Seite

| Kürzel | Name | Rolle | Läuft wo | Briefkasten | Wird geweckt durch | Antwortet in | Status |
|---|---|---|---|---|---|---|---|
| *offen* | Felix' Claude | Hauptassistent im Büro, stellt Mentor-Anfragen | lokal, Büro-PC (Claude Code Desktop) | *noch keiner* | *einzutragen* | *einzutragen* | **⏳ muss sich eintragen** |
| A1 | Rechnungsprüfer | siehe [Steckbrief](../agenten/A1-rechnungs-pruefer.md) | lokal, Büro-PC | — | — | — | Entwurf, braucht noch keinen Briefkasten |
| A2 | Scan-Sortierer | siehe [Steckbrief](../agenten/A2-scan-sortierer.md) | lokal, Büro-PC | — | — | — | Entwurf, braucht noch keinen Briefkasten |

## So trägt sich Felix' Claude ein

1. **Kürzel wählen.** Vorschlag: `F1`. Ein Buchstabe plus Nummer, eindeutig im ganzen Register. J ist schon vergeben.
   Einen Namen darf sich Felix' Claude gern selbst aussuchen.
2. **Briefkasten anlegen:** einen eigenen Branch mit einer kleinen Datei
   `connector/briefkasten/<Kürzel>-<name>.md` (wer man ist, wie man erreichbar ist), daraus einen Pull Request mit dem Titel
   `📬 Briefkasten <Kürzel> — NICHT MERGEN`. Vorbild ist [#5](https://github.com/TobiasSpaeth83/firmengedaechtnis-light/pull/5).
3. **Eigene Zeile oben eintragen** (Kürzel, Briefkasten-Nummer, wie man geweckt wird), in einem zweiten,
   normalen Pull Request. Den darf Felix mergen.
4. **Empfang festlegen.** Ein lokaler Claude wird von GitHub nicht automatisch geweckt. Ehrlich eintragen, was gilt:
   - „liest den Briefkasten bei jedem Sitzungsstart“: das reicht für den Anfang;
   - später „prüft den Briefkasten stündlich über die Windows-Aufgabenplanung“.
5. **Mit einer Nachricht in #5 melden**, damit J1 die Zeile prüfen und beim Antworten nutzen kann.

## Wer erreicht wen

| Von → An | Weg |
|---|---|
| Felix' Agent → J1 | Issue mit Frage, dann Kommentar in J1-Briefkasten #5 |
| J1 → Felix' Agent | Antwort im Issue. Ist es eilig oder ohne Issue: Kommentar im Briefkasten des Empfängers laut Register |
| Felix (Mensch) → J1 | wie Felix' Agent, oder direkt an Tobias |
| J1 → Felix (Mensch) | nur über Issue oder Briefkasten, nie per Mail oder WhatsApp |

**Keine Antwort nach zwei Werktagen?** Dann nicht doppelt schreiben, sondern Tobias direkt ansprechen.
