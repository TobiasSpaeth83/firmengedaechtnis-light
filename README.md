# Firmengedächtnis light — FS Kreativ Küchen

Eine schlanke Grundlage, mit der das Küchenstudio sein Betriebswissen festhält und Schritt für Schritt Routineaufgaben an Claude abgibt.

> ⚠️ **Dieses Repository muss noch auf privat gestellt werden.** Es enthält Betriebswissen, Namen von Mitarbeitern und Partnerbetrieben sowie die Lieferantenstruktur. Solange es öffentlich ist, keine Kundennamen, Beträge, Belege oder Zugangsdaten ergänzen. *(GitHub → Settings → General → Danger Zone → Change visibility)*

## Zwei Dinge in einem

1. **Gedächtnis** — wie der Betrieb arbeitet, welche Regeln gelten, was entschieden wurde. Damit Claude nicht bei jedem Gespräch bei null anfängt.
2. **Fahrplan für Agenten** — welche Routineaufgaben in welcher Reihenfolge automatisiert werden, mit ehrlicher Einschätzung von Aufwand und Nutzen.

Beides gehört zusammen: Eine Automatisierung ohne Gedächtnis muss man jedes Mal neu erklären.

## Start hier

| Wenn du … | dann lies … |
|---|---|
| das Ganze zum ersten Mal siehst | [docs/01-START.md](docs/01-START.md) |
| es technisch einrichten willst | [docs/02-EINRICHTUNG.md](docs/02-EINRICHTUNG.md) |
| wissen willst, wie „täglich um 10 Uhr" real wird | [docs/03-ROUTINEN-EINRICHTEN.md](docs/03-ROUTINEN-EINRICHTEN.md) |
| wissen willst, was wann automatisiert wird | [docs/04-AGENTEN-FAHRPLAN.md](docs/04-AGENTEN-FAHRPLAN.md) |
| wissen willst, was Claude allein darf | [docs/05-SPIELREGELN.md](docs/05-SPIELREGELN.md) |

## Aufbau

```
CLAUDE.md          Arbeitsanweisung — liest Claude bei jedem Start automatisch
docs/              Anleitung, Fahrplan, Spielregeln, Logbuch
agenten/           Steckbriefe der einzelnen Agenten (einer pro Aufgabe)
wissen/            Betriebsprofil, Glossar, Lieferanten und Portale
data/              Struktur des Dokumentenregisters (nur anonyme Beispiele)
```

## Was hier nicht hineingehört

Kaufverträge, Rechnungen, Scans, Kundendaten und Zugangsdaten. Die bleiben in OneDrive, Notion und im Passwortmanager. Hier stehen nur Regeln, Strukturen und erfundene Beispiele — auch nachdem das Repository privat ist.

## Zielprozess der ersten Ausbaustufe

`Dokument kommt rein` → `Claude liest es` → `Kommission zuordnen` → `gegen Auftragsbestätigung prüfen` → `Register + Ablage` → `Tagesbericht`

Unklare Fälle gehen nie durch, sondern nach „Manuell prüfen".

## Nächster offener Punkt

Das Betriebsprofil in [wissen/BETRIEB.md](wissen/BETRIEB.md) ausfüllen — vor allem der **Aufbau der Kommissionsnummern**. Ohne das kann kein Agent ein Dokument zuordnen.
