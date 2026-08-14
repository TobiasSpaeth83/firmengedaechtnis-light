# Betriebsprofil

**Zum Ausfüllen in der privaten Arbeitskopie.** In der öffentlichen Vorlage bleiben die Felder leer.

Das ist die wichtigste Datei des ganzen Repositorys. Alles, was hier fehlt, muss Claude bei jedem Dokument neu erraten. Eine halbe Stunde hier spart Wochen an Rückfragen.

Am schnellsten im Gespräch ausfüllen: Claude starten und sagen *„Geh mit mir das Betriebsprofil durch und stell mir die Fragen einzeln."*

---

## 1. Betrieb

| Feld | Wert |
|---|---|
| Firmierung | |
| Ort | |
| Inhaber | |
| Weitere Mitarbeiter und Aufgaben | |
| Küchen pro Jahr (ungefähr) | |
| Typischer Auftragswert | |

## 2. Kommissionen — das Wichtigste

Eine Kommission ist ein Küchenauftrag. Jedes Dokument gehört zu genau einer.

| Feld | Wert |
|---|---|
| Aufbau der Kommissionsnummer | z. B. `K-2026-041` — **echtes Muster hier eintragen** |
| Wo steht sie auf Lieferantenrechnungen? | |
| Wo steht sie auf Auftragsbestätigungen? | |
| Vergibt sie der Betrieb oder der Hersteller? | |
| Was gilt, wenn ein Dokument keine hat? | Vorschlag: nach „Manuell prüfen" |

## 3. Ablage

| Ordner | Pfad |
|---|---|
| Wurzel der Kommissionsordner | |
| Eingang für neue Dokumente | |
| Manuell prüfen | |
| Register | |
| Scan-Ordner des Druckers | |

**Unterordner je Kommission** (bestehende Struktur eintragen, damit der Agent richtig ablegt):

```
Kommission/
├── ...
├── ...
└── ...
```

## 4. Werkzeuge

| Zweck | Programm | Zugang für den Agenten |
|---|---|---|
| Mail | | IMAP über den Provider, Zugangsdaten in `.env` |
| Kalender | | |
| Aufgaben/Wissen je Kunde | | |
| Dateiablage | | |
| Planung/Auftrag/Rechnung | | vermutlich keine Schnittstelle — siehe `docs/04-AGENTEN-FAHRPLAN.md`, Regel 7 |
| Einnahmen-Ausgaben-Liste | | Agent schreibt nur in die Nachtragsdatei |
| Kundenkommunikation | | kein automatisierter Versand |

## 5. Lieferanten und Hersteller

Siehe `wissen/LIEFERANTEN-UND-PORTALE.md`.

## 6. Schwellen und Regeln

| Regel | Wert |
|---|---|
| Bagatellgrenze bei Rechnungsabweichung | Vorschlag: 2 € |
| Übliche Lieferzeit Küche | |
| Bestellung muss spätestens erfolgen | Wochen vor Auslieferung: |
| Aufmaß muss erfolgt sein | Wochen vor Bestellung: |
| Anzahlung fällig | |
| Restzahlung fällig | |
| Erinnerung an Kunden vor Auslieferung | Tage vorher: |
| Rückfrage bei Montage-/Auslieferpartner | Tage vorher: |

Diese Tabelle ist die Grundlage für die Fristenüberwachung. Was hier steht, kann überwacht werden — was fehlt, nicht.

## 7. Was der Betrieb bewusst nicht automatisiert

Damit niemand später auf die Idee kommt, es doch zu bauen — mit Begründung:

| Was | Warum nicht |
|---|---|
| Prüfung der Küchen-Auftragsbestätigung Position für Position | zu viele Einzelteile, erfordert Fachwissen, Fehler wären teuer |
| Nachfassen nach einem Angebot | beziehungsabhängig, gehört zum Verkauf |
| Anruf nach der Montage | bewusste persönliche Fürsorge |
| Kommentieren in sozialen Medien | wirkt automatisiert unecht |
| | |
