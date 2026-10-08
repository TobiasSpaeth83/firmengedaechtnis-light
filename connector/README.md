# Mentor-Connector

Dieser Bereich ist der gemeinsame, nachvollziehbare Austauschkanal zwischen
Felix und Tobias' Mentor-Agenten. Er ermöglicht Fragen zu Automatisierung,
Routinen und Betriebsorganisation, ohne Tobias' vollständiges Firmengedächtnis
für Felix freizugeben.

## So funktioniert eine Anfrage

1. Felix eröffnet über die Vorlage **Mentor-Anfrage** ein GitHub-Issue.
2. Felix' Claude schreibt danach einen Kommentar in den Briefkasten des Mentors
   (`📬 An: J1 · Von: <Kürzel> — neue Anfrage #<Nummer>`). Wo der Briefkasten liegt, steht im
   [Agenten-Register](AGENTEN-REGISTER.md). Erst dieser Kommentar weckt den Mentor.
3. Tobias' Mentor-Agent Jakob (J1) prüft die Anfrage und schlägt intern nach.
4. Die Antwort wird auf vertrauliche Angaben geprüft und im Issue veröffentlicht.
5. Wiederverwendbare Vorlagen kommen als Pull Request in `connector/vorlagen/`.
6. Felix entscheidet selbst, ob und wie er die Empfehlung in seinem Betrieb
   übernimmt.

Ein GitHub-Issue allein startet keinen Agenten. Geweckt wird über den
Briefkasten-PR des Empfängers (siehe Register). Eine spätere Oswald-/Hermes-Anbindung muss den gleichen
Regeln folgen und erhält keine Zugangsdaten in diesem Repository.

## Was der Connector kann

- Fragen und Antworten dauerhaft dokumentieren
- Routinen und Vorgehensweisen erklären
- bereinigte Checklisten und Vorlagen teilen
- Änderungen über Pull Requests gemeinsam prüfen
- Entscheidungen und offene Punkte nachvollziehbar halten

## Was der Connector nicht kann

- Tobias' vollständiges Firmengedächtnis sichtbar machen
- Kundendaten oder interne Dokumente zwischen Betrieben übertragen
- Claude-, GitHub-, Hermes- oder andere Zugangsdaten teilen
- allein durch eine Nachricht Änderungen an Systemen ausführen
- eine fachliche, rechtliche oder finanzielle Freigabe ersetzen

Verbindlich sind die [Connector-Regeln](REGELN.md). Eine unverfängliche
Beispielanfrage steht in [BEISPIEL-ANFRAGE.md](BEISPIEL-ANFRAGE.md).

## Ordner

- `AGENTEN-REGISTER.md` – wer ist wer, Briefkästen, wie man sich einträgt
- `briefkasten/` – Kurzbeschreibung je Briefkasten (liegt auf dem jeweiligen Briefkasten-Branch)
- `antworten/` – dauerhafte, bereinigte Antworten mit allgemeinem Nutzen
- `vorlagen/` – gemeinsam geprüfte Checklisten, Prompts und Routinevorlagen

Einzelne Gespräche bleiben als Issues bestehen. Nicht jede Antwort muss deshalb
zusätzlich als Datei abgelegt werden.
