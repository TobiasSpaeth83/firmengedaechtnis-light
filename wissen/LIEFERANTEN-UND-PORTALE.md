# Lieferanten und Portale

Der Agent braucht das, um Absender zu erkennen, Rechnungen zuzuordnen und zu wissen, welche Dokumente von wem in welcher Form kommen.

Vorausgefüllt ist, was aus der Kandidatenliste bekannt ist. **`??` muss Felix ergänzen.**

**Hier stehen keine Zugangsdaten.** Passwörter gehören in den Passwortmanager, technische Zugänge in die `.env`-Datei. In dieser Tabelle steht nur, *dass* es einen Zugang gibt.

---

## Hersteller und Lieferanten

| Lieferant | Was | Absender-Adressen der Mails | Dokumente von dort | Besonderheiten |
|---|---|---|---|---|
| Häcker | Küchenmöbel | ?? | Auftragsbestätigung, Rechnung, **Abladebestätigung** | Bestellung über Häcker Extranet. Abladebestätigung ist Auslöser für A6 (Fehlteilprüfung) |
| Bosch / Neff | Elektrogeräte | ?? | Auftragsbestätigung, Rechnung | Bestellung über Trade Place |
| ?? | Arbeitsplatten | ?? | | |
| ?? | Zubehör, Stühle, Armaturen | ?? | Bestellung + Auftragsbestätigung | Auslöser für A5 (Preis- und Artikelnummernprüfung) |

**Wozu die Absenderadressen:** Damit der Mail-Vorsortierer und die Dokumentenzuordnung sicher erkennen, von wem ein Dokument stammt — auch wenn im Dateinamen nichts steht. In Thunderbird bestehen bereits Ordnerfilter je Hersteller; die Adressen lassen sich dort ablesen.

## Portale

| Portal | Wofür | Zugang | Automatisierung |
|---|---|---|---|
| Häcker Extranet | Bestellungen Küchenmöbel | Händlerlogin | nein — Stufe 4 |
| Trade Place | Bestellungen Bosch/Neff | Händlerlogin | nein — Stufe 4 |
| G4U / GFM | Garantieanmeldung: Artikelnummern, Anzahl, Hersteller, Kategorie eintragen | Händlerlogin, Formular | Stufe 4, dann als „Agent füllt aus, Felix sendet" |
| GarantieMax | Garantieanmeldung per E-Mail (Kaufvertrag + Kundendaten + Liefer-KW) und Portal | ?? | Entwurf vorbereiten, **Versand durch Felix** |
| Agenda | monatlicher Beleg-Upload an den Steuerberater | browserbasiert | nein — Stufe 4, heikelste Klasse |

Alle Portale stehen in Stufe 4 des Fahrplans. Begründung: `docs/04-AGENTEN-FAHRPLAN.md`.

## Montage und Auslieferung

| Partner | Leistung | Kontaktweg | Vorlauf für Terminabsprache |
|---|---|---|---|
| René (mit Thomas) | Montage, Hauptteam | WhatsApp | ?? |
| Robert (mit wechselnden Söhnen) | Montage | WhatsApp | ?? |
| Manfred / Umzüge Simon | Auslieferung | WhatsApp | ?? |
| F+V Dienstleistungen | Auslieferung | ?? | ?? |

Kontakt läuft über Nachrichten, die **Felix** abschickt — nie automatisiert (`docs/05-SPIELREGELN.md`, Stufe B). Der Agent bereitet den Text vor und erinnert an die Frist.

## Wiederkehrende Dokumenttypen

Was regelmäßig hereinkommt, damit der Sortierer es zuordnen kann:

| Dokumenttyp | Kommt von | Format | Menge |
|---|---|---|---|
| Lieferantenrechnung | Hersteller | PDF per Mail | 10–15/Monat |
| Auftragsbestätigung | Hersteller, Zubehörlieferanten | PDF per Mail | mehrere je Küche |
| Abladebestätigung | Häcker | PDF per Mail | 1 je Küche |
| Behördenpost, Finanzamt | | Scan | **immer zur Prüfung, nie automatisch ablegen** |
| Versicherung, Bank | | Scan | |
| Privatpost | | Scan | zur Prüfung, nicht einsortieren |

Scanaufkommen insgesamt: 2–15 pro Woche, stark schwankend, inhaltlich sehr gemischt.
