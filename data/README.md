# Dokumentenregister — Aufbau

`dokumentenregister.csv` ist die **Strukturvorlage**, nicht die Arbeitsdatei. Die Arbeitsdatei ist eine Excel-Datei im OneDrive (Begründung: `docs/02-EINRICHTUNG.md`, Schritt 5).

Die drei Beispielzeilen sind erfunden und zeigen die drei Fälle, die vorkommen: sauber durchgelaufen, Abweichung erkannt, nicht zuzuordnen.

## Spalten

| Spalte | Inhalt | Pflicht |
|---|---|---|
| `datei_id` | Prüfsumme der Datei. Verhindert Doppelverarbeitung. | ja |
| `dateiname` | Name nach dem Umbenennen | ja |
| `quelle` | `scan` · `mail` · `download` · `manuell` | ja |
| `eingang_am` | wann die Datei im Eingang lag (JJJJ-MM-TT) | ja |
| `verarbeitet_am` | wann der Agent sie bearbeitet hat | ja |
| `dokumenttyp` | `Rechnung` · `Auftragsbestaetigung` · `Lieferschein` · `Abladebestaetigung` · `Kundendokument` · `Behoerde` · `Versicherung` · `privat` · `unklar` | ja |
| `dokumentdatum` | Datum **auf** dem Dokument | wenn lesbar |
| `absender` | Lieferant, Behörde, Absender | wenn lesbar |
| `kommission` | Kommissionsnummer — die zentrale Ordnungsgröße | wenn zuzuordnen |
| `betrag_netto` | Zahl mit Punkt als Dezimaltrennzeichen | bei Rechnungen |
| `betrag_brutto` | Zahl mit Punkt als Dezimaltrennzeichen | bei Rechnungen |
| `referenz` | Rechnungs- oder Belegnummer | wenn vorhanden |
| `verglichen_mit` | wogegen geprüft wurde, mit Datum | bei Prüfung |
| `vergleich_ergebnis` | `ok` · `abweichung` · `nicht_moeglich` | bei Prüfung |
| `abweichung` | Betrag der Abweichung, positiv wenn die Rechnung höher ist | bei Abweichung |
| `status` | `ok` · `abweichung` · `zu_pruefen` · `fehler` | ja |
| `pruefhinweis` | Klartext, was zu prüfen ist. Bei `zu_pruefen` **immer** gefüllt. | bei Bedarf |
| `abgelegt_unter` | wohin die Datei gelegt wurde | ja |

## Regeln

- **Kein Feld wird geraten.** Nicht lesbar heißt leer plus `status: zu_pruefen` plus Prüfhinweis.
- **Beträge sind Zahlen**, nicht Text. Dezimaltrennzeichen ist der Punkt.
- **Eine Zeile pro Datei**, nie zwei. Vor dem Schreiben prüfen, ob `datei_id` schon existiert.
- **Nichts nachträglich überschreiben.** Korrekturen kommen als neue Zeile mit Verweis im Prüfhinweis.
- Der Status `zu_pruefen` ist kein Fehler des Agenten, sondern sein bestimmungsgemäßes Verhalten.
