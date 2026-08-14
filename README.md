# Firmengedächtnis light — Küchenstudio

Eine schlanke Vorlage, mit der ein kleiner Handwerks- oder Handelsbetrieb sein Betriebswissen festhält und Schritt für Schritt Routineaufgaben an Claude abgibt.

Zugeschnitten auf ein Küchenstudio mit Inhaber, Bürokraft und Montage-Subunternehmern — übertragbar auf ähnlich aufgestellte Betriebe.

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

## Wichtig: diese Vorlage ist öffentlich

Dieses Repository ist für alle sichtbar. Es enthält **keine** Kundendaten, Namen von Mitarbeitern oder Partnerbetrieben, Belege, Zugangsdaten oder Links in private Ablagen — nur Anleitungen, Strukturen und erfundene Beispiele. Deshalb ist überall von „dem Inhaber" und „der Bürokraft" die Rede statt von Namen.

**Die eigene Arbeitskopie muss privat sein.** Erst dort dürfen echte Betriebsdaten stehen. Wie das geht, steht in [docs/02-EINRICHTUNG.md](docs/02-EINRICHTUNG.md), Schritt 1.

## Zielprozess der ersten Ausbaustufe

`Dokument kommt rein` → `Claude liest es` → `Kommission zuordnen` → `gegen Auftragsbestätigung prüfen` → `Register + Ablage` → `Tagesbericht`

Unklare Fälle gehen nie durch, sondern nach „Manuell prüfen".
