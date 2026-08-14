# Lieferanten und Portale

**Zum Ausfüllen in der privaten Arbeitskopie.**

Der Agent braucht das, um Absender zu erkennen, Rechnungen zuzuordnen und zu wissen, welche Dokumente von wem in welcher Form kommen.

**Hier stehen keine Zugangsdaten.** Passwörter gehören in den Passwortmanager, technische Zugänge in die `.env`-Datei. In dieser Tabelle steht nur, *dass* es einen Zugang gibt und wer ihn hat.

---

## Hersteller und Lieferanten

| Lieferant | Was | Absender-Adressen der Mails | Dokumente, die von dort kommen | Besonderheiten |
|---|---|---|---|---|
| | Küchenmöbel | | Auftragsbestätigung, Rechnung, Abladebestätigung | |
| | Elektrogeräte | | Auftragsbestätigung, Rechnung | |
| | Arbeitsplatten | | | |
| | Zubehör, Stühle, Armaturen | | | |

**Wozu die Absenderadressen:** Damit der Mail-Vorsortierer und die Dokumentenzuordnung sicher erkennen, von wem ein Dokument stammt — auch wenn im Dateinamen nichts steht.

## Portale

| Portal | Wofür | Zugang bei | Automatisierung |
|---|---|---|---|
| | Bestellungen Küchenmöbel | | nein — Stufe 5 |
| | Bestellungen Geräte | | nein — Stufe 5 |
| | Garantieanmeldung | | nein — Stufe 5, ggf. „ausfüllen, Mensch sendet" |
| | Garantieanmeldung per Mail | | Entwurf vorbereiten, Versand durch Menschen |
| | Belege an den Steuerberater | | nein — Stufe 5 |

Alle Portale stehen in Stufe 5 des Fahrplans. Begründung: `docs/04-AGENTEN-FAHRPLAN.md`, Regel 5.

## Montage und Auslieferung

| Partner | Leistung | Kontaktweg | Vorlaufzeit für Terminabsprache |
|---|---|---|---|
| | Montage | | |
| | Auslieferung | | |

Kontakt läuft über Nachrichten, die ein Mensch abschickt — nie automatisiert (`docs/05-SPIELREGELN.md`, Stufe B).

## Wiederkehrende Dokumenttypen

Was regelmäßig hereinkommt, damit der Sortierer es zuordnen kann:

| Dokumenttyp | Kommt von | Format | Erkennungsmerkmal |
|---|---|---|---|
| Lieferantenrechnung | Hersteller | PDF per Mail | |
| Auftragsbestätigung | Hersteller | PDF per Mail | |
| Abladebestätigung | Möbelhersteller | PDF per Mail | |
| Behördenpost | Finanzamt, Kammer | Scan | **immer zur Prüfung, nie automatisch ablegen** |
| Versicherung, Bank | | Scan | |
| Privatpost | | Scan | zur Prüfung |
