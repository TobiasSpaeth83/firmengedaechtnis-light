# Agenten-Fahrplan

Wie man aus einer Wunschliste von Automatisierungen eine sinnvolle Reihenfolge macht — und welche Kandidaten regelmäßig überschätzt werden.

> Die betriebsspezifische Bewertung der eigenen Kandidatenliste gehört in die private Arbeitskopie, nicht hierher. Diese Seite enthält die Regeln, nach denen bewertet wird.

## Regel 1: Viele Agenten sind in Wahrheit einer

In fast jeder Wunschliste stehen mehrere Punkte, die unterschiedlich aussehen, aber denselben Ablauf haben:

> Ein Dokument kommt rein → lesen → Vorgang zuordnen → gegen etwas prüfen → ablegen → Register → bei Zweifel zur Prüfung legen.

Im Küchenstudio trifft das mindestens auf vier Fälle zu: Lieferantenrechnung gegen Auftragsbestätigung, Zubehörbestellung gegen Bestellung, Abladebestätigung gegen Lieferumfang, allgemeiner Scan ohne Vergleich. Unterschiedlich sind nur die **Prüfregel** und der **Zielordner**.

**Also: eine Maschine bauen, mehrfach verwenden.** Das ist der Unterschied zwischen zwei Wochen und zwei Monaten Bauzeit — und zwischen einem Ding, das man pflegt, und vieren.

## Regel 2: Nach Menge sortieren, nicht nach Einfachheit

Die naheliegende Sortierung ist „was ist am schnellsten gebaut". Die richtige ist:

```
Ersparnis pro Monat  =  Vorgänge pro Monat  ×  Minuten pro Vorgang
```

Bei einem Betrieb mit zwei bis drei Küchen im Monat fällt dabei vieles durch: Ein Agent, der pro Küche fünf Minuten spart, spart im Monat eine Viertelstunde. Das trägt keinen Bau- und keinen Wartungsaufwand — egal, wie einfach er zu bauen wäre.

Die Masse liegt fast immer bei drei Dingen:

1. **E-Mail-Eingang** — täglich, dutzende Vorgänge
2. **Scans und Dokumente** — wöchentlich zweistellig
3. **Lieferantenrechnungen** — zweistellig im Monat, und hier steckt zusätzlich Geld drin

## Regel 3: Der Schaden zählt mit, nicht nur die Zeit

Neben der Zeitersparnis gibt es eine zweite Größe: **Was kostet es, wenn der Fall vergessen wird?**

Eine falsch benannte Datei kostet zwei Minuten. Ein versäumter Bestelltermin bei 6–8 Wochen Lieferzeit kostet einen verschobenen Montagetermin, umgeplante Handwerker, einen vertrösteten Kunden und im Zweifel einen Nachlass.

Deshalb gehören **Fristen- und Terminüberwachung** meist weiter nach vorn, als sie in Wunschlisten landen — sie sparen wenig Zeit, verhindern aber die teuren Fehler. Wer eine Liste bewertet, sollte diese Spalte ausdrücklich mitführen.

## Regel 4: Die Stufen

| Stufe | Was | Warum in dieser Reihenfolge |
|---|---|---|
| 1 | Dokumentenmaschine: einlesen, zuordnen, ablegen, prüfen | höchste Menge, kein Zugriff nach außen, Fehler sind harmlos — ideal zum Vertrauen aufbauen |
| 2 | Termin- und Fristenüberwachung | verhindert die teuren Fehler; braucht nur Kalender und Aufgabenliste |
| 3 | E-Mail-Vorsortierung | größter Einzelhebel, aber sinnvoll erst, wenn Stufe 1 die erkannten Dokumente übernehmen kann |
| 4 | weitere Prüfregeln in der bestehenden Maschine | Erweiterung, kein Neubau — je etwa ein Tag |
| 5 | alles mit Zugangsdaten in fremden Portalen | aufwendigste und störanfälligste Klasse — zuletzt |

Zwischen Stufe 1 und 2 gehören **vier Wochen echter Betrieb**. Wer stattdessen weiterbaut, hat am Ende fünf Automatisierungen, denen niemand traut.

## Regel 5: Portale und Logins zuletzt

Agenten, die sich in fremden Portalen einloggen (Garantieanmeldung, Steuerberater-Upload, Lieferantenportale), sind verlockend, weil die Arbeit dort so stumpf ist. Sie sind aber die schlechteste Wahl für den Anfang:

- Ändert der Anbieter sein Formular, steht der Agent — ohne Vorwarnung.
- Es braucht hinterlegte Zugangsdaten, also die heikelste Konfiguration überhaupt.
- Ein Fehler passiert außerhalb des eigenen Systems und ist oft nicht zurückzunehmen.

Wenn doch, dann in der Form **„Agent füllt aus, Mensch klickt auf Absenden"**. Das Ausfüllen war die Arbeit, nicht der Klick.

## Regel 6: WhatsApp-Automatisierung lohnt in dieser Betriebsgröße nicht

Ein Klassiker auf jeder Wunschliste, meist mit „ganz einfach" bewertet. Das trifft nicht zu.

**WhatsApp Business (die App) hat keine Schnittstelle zur Automatisierung.** Automatisiert senden geht nur über die WhatsApp Cloud API von Meta, und die bedeutet: geschäftliche Verifizierung, einzeln genehmigte Nachrichtenvorlagen, Migration der Rufnummer aus der Business-App — die danach nicht mehr wie gewohnt funktioniert — sowie laufende Kosten pro Gespräch.

Für eine Handvoll Nachrichten im Monat ist das grob unverhältnismäßig. Drittanbieter-Werkzeuge, die WhatsApp Web fernsteuern, verstoßen gegen die Nutzungsbedingungen und riskieren die Sperrung der Nummer — bei der Nummer, über die die Kundenkommunikation läuft, ein untragbares Risiko.

**Besserer Weg, gleicher Nutzen:** Der Agent überwacht die Termine und legt morgens den **fertigen Text** hin. Ein Tippen zum Kopieren, ein Tippen zum Senden. Das Erinnern war der Aufwand, nicht das Absenden — und die Nachricht kommt weiterhin persönlich vom Inhaber, was bei Kunden, die gerade fünfstellig investieren, ohnehin besser ankommt.

Dasselbe gilt für Rückfragen bei Montage- und Auslieferpartnern.

## Regel 7: Branchensoftware gibt keine Schnittstelle her

Planungs- und Auftragsprogramme für den Möbel- und Küchenhandel bieten einem einzelnen Händler in aller Regel keine offene Schnittstelle, und ein direkter Zugriff auf die Datenbank verbietet sich schon aus Gewährleistungsgründen.

Realistischer Zuschnitt: Der Agent **erinnert** rechtzeitig, sagt, welche Dokumente gebraucht werden, prüft, was schon als PDF vorliegt, und stellt zusammen. Der Export aus der Branchensoftware bleibt Handarbeit — es sind ein paar Klicks, das Daran-Denken war das Problem.

Bevor man auf einer solchen Schnittstelle plant: beim Anbieter schriftlich nachfragen. Nicht annehmen.

## Bewertungsraster für die eigene Liste

Für jeden Kandidaten:

| Frage | |
|---|---|
| Wie oft im Monat? | |
| Minuten pro Vorgang heute? | |
| Ersparnis im Monat? | Menge × Minuten |
| Was kostet es, wenn der Fall vergessen wird? | |
| Braucht es Zugriff nach außen (Portal, Mail, Nachricht)? | wenn ja → spätere Stufe |
| Ist es dieselbe Maschine wie ein anderer Kandidat? | wenn ja → zusammen bauen |
| Was ist der Schaden, wenn der Agent es falsch macht? | wenn hoch → immer zur Freigabe |

Alles unter etwa einer Stunde Ersparnis im Monat und ohne Schadenspotenzial: auf die Liste, aber nach hinten.
