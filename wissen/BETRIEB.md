# Betriebsprofil FS Kreativ Küchen

Das ist die wichtigste Datei des ganzen Repositorys. Alles, was hier fehlt, muss Claude bei jedem Dokument neu erraten. Eine halbe Stunde Ausfüllen spart Wochen an Rückfragen.

Vorausgefüllt ist, was aus der Kandidatenliste bekannt ist. **Felder mit `??` muss Felix ergänzen.**

Am schnellsten im Gespräch: Claude starten und sagen *„Geh mit mir das Betriebsprofil durch und stell mir die offenen Fragen einzeln."*

---

## 1. Betrieb

| Feld | Wert |
|---|---|
| Firmierung | FS Kreativ Küchen |
| Ort | Oberhaid bei Bamberg |
| Inhaber | Felix, Vollzeit |
| Verwaltung | Klara, Minijob ca. 25 Std./Woche — Verwaltung + Social-Media-Videoschnitt |
| Montage | René (mit Thomas) Hauptteam, Robert (mit wechselnden Söhnen) — Subunternehmer |
| Auslieferung | Manfred / Umzüge Simon, F+V Dienstleistungen — Subunternehmer |
| Anfragen | ca. 2–3 pro Monat |
| Küchen pro Monat | ca. 2–3 |
| Typischer Auftragswert | ?? |
| Engpass | **nicht** Beratung/Verkauf, sondern administrative Kapazität |

## 2. Kommissionen — das Wichtigste

Eine Kommission ist ein Küchenauftrag. Jedes Dokument gehört zu genau einer. Die OneDrive-Ablage ist danach strukturiert.

| Feld | Wert |
|---|---|
| Aufbau der Kommissionsnummer | **??** — echtes Muster eintragen, z. B. `K-2026-041` |
| Wo steht sie auf Lieferantenrechnungen? | ?? |
| Wo steht sie auf Auftragsbestätigungen? | ?? |
| Vergibt sie der Betrieb oder der Hersteller? | ?? |
| Wenn ein Dokument keine hat | über Kundenname + Datum versuchen, sonst nach „Manuell prüfen" |

**Ohne dieses Muster kann kein Agent ein Dokument sicher zuordnen.** Das ist die erste Frage, die beantwortet sein muss.

## 3. Ablage (OneDrive)

Bestehende Struktur ist pro Kommission organisiert und bleibt unverändert. Neu kommen drei Sammelordner dazu.

| Ordner | Pfad |
|---|---|
| Wurzel der Kommissionsordner | ?? |
| Eingang für neue Dokumente | `00-Eingang` |
| Manuell prüfen | `00-Manuell-pruefen` |
| Register | `00-Register` |
| Scan-Ordner des Druckers | ?? |

Sync mit Klaras PC läuft über Synchting — an dieser Einrichtung ändert sich nichts.

**Unterordner je Kommission** (bestehende Struktur eintragen, damit der Agent richtig ablegt):

```
Kommission/
├── ?? Rechnungen
├── ?? Auftragsbestaetigungen
├── ?? Lieferscheine
├── ?? Planung
└── ?? Bilder
```

## 4. Werkzeuge

| Zweck | Programm | Zugang für den Agenten |
|---|---|---|
| Mail | Thunderbird, Provider Manitu — Ordnerfilter je Hersteller bestehen bereits | **IMAP direkt bei Manitu**, nicht über Thunderbird-Dateien. Zugangsdaten in `.env` |
| Kalender | Google Kalender | API, später für den Fristen-Wächter |
| Aufgaben/Wissen je Kunde | Notion — pro Kunde eine Seite mit To-Do-, Warte-auf-Rückmeldung-, Nachverkauf- und Vor-Auslieferung-Listen | API |
| Dateiablage | OneDrive, Sync via Synchting | lokaler Dateizugriff auf dem Büro-PC |
| Planung/Auftrag/Rechnung | CompuSoft Winner (Cyncly) — Bestellungen, Rechnungen, Kaufverträge | **vermutlich keine Schnittstelle.** Vor Planung schriftlich bei Cyncly anfragen. Siehe `docs/04-AGENTEN-FAHRPLAN.md` |
| Einnahmen-Ausgaben-Liste | Excel / OpenOffice Calc | Agent schreibt **nur** in die Nachtragsdatei, nie direkt |
| Auftragsliste | Excel / OpenOffice Calc | lesend |
| Kundenkommunikation | WhatsApp Business | **kein automatisierter Versand** — Agent bereitet Texte vor |
| Bildbearbeitung | GIMP | für Wasserzeichen später als Skript |
| Video | CapCut | nicht automatisiert |

## 5. Lieferanten und Portale

Siehe `wissen/LIEFERANTEN-UND-PORTALE.md`.

## 6. Fristen, Schwellen, Regeln

Diese Tabelle ist die Grundlage für den Fristen-Wächter. Was hier steht, kann überwacht werden — was fehlt, nicht.

| Regel | Wert |
|---|---|
| Bagatellgrenze bei Rechnungsabweichung | Vorschlag 2 € — **Felix bestätigen** |
| Übliche Lieferzeit Küche | 6–8 Wochen |
| Bestellung muss spätestens erfolgen | ?? Wochen vor Auslieferung |
| Aufmaß muss erfolgt sein | ?? Wochen vor Bestellung |
| Auslieferungsart klären | ca. 4 Wochen vorher (aus Notion-Praxis) |
| Anzahlung fällig | ?? |
| Restzahlung fällig | ?? |
| Erinnerung an Kunden vor Auslieferung | ?? Tage vorher |
| Rückfrage bei Montage-/Auslieferpartner | ?? Tage vorher |
| Garantie-Anmeldung | bei 50–70 % der Küchen — Kriterium: ?? |

## 7. Wer bekommt was

| Was | An wen |
|---|---|
| Tagesbericht der Dokumentenroutine | ?? Felix, Klara oder beide |
| Meldung bei Rechnungsabweichung | ?? |
| Wochenrückblick | ?? |

## 8. Was bewusst nicht automatisiert wird

Damit niemand später auf die Idee kommt, es doch zu bauen — Felix' eigene Begründungen:

| Was | Warum nicht |
|---|---|
| Küchen-Auftragsbestätigung mit ~25 Einzelteilen Position für Position prüfen | zu hohes Fehlerpotenzial, erfordert Fachwissen |
| Nachfassen nach einem Angebot | zu beziehungsabhängig, individuell |
| Anruf nach der Montage beim Kunden | bewusste persönliche Fürsorge |
| Lager-Fotos und Videos für Auslieferer | situativ vor Ort |
| Kommentieren auf Instagram/TikTok für Sichtbarkeit | wirkt automatisiert unauthentisch |
