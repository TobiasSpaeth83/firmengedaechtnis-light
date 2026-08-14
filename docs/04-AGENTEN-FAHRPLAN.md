# Agenten-Fahrplan

Bewertung der elf Kandidaten aus Felix' Liste, sortiert nach dem, was tatsächlich Zeit spart. Mit ehrlicher Einschätzung, wo es technisch klemmt.

## Der wichtigste Befund: vier Agenten sind in Wahrheit einer

Die Kandidaten 1, 2, 5 und 6 sehen unterschiedlich aus, machen aber dasselbe:

> Ein Dokument kommt rein → lesen → Kommission zuordnen → gegen etwas prüfen → ablegen → Register → bei Zweifel zur Prüfung legen.

Der Unterschied liegt nur darin, **womit** verglichen wird (Rechnung gegen Auftragsbestätigung, Zubehörbestellung gegen Bestellung, Abladebestätigung gegen Lieferumfang) und **wohin** abgelegt wird.

Daraus folgt: **eine Maschine bauen, vier Mal verwenden.** Nicht vier Agenten nacheinander bauen. Das ist der Unterschied zwischen einer Woche und zwei Monaten Bauzeit — und zwischen einem Ding, das gepflegt wird, und vieren.

## Nach Menge sortiert, nicht nach Einfachheit

Felix' Liste ist nach „schnelle Gewinne" sortiert, wobei die Einfachheit den Ausschlag gab. Bei 2–3 Küchen im Monat ist aber nicht die Einfachheit die entscheidende Größe, sondern **wie oft der Fall vorkommt**:

| Agent | Vorgänge/Monat | Zeit pro Vorgang | Ersparnis/Monat |
|---|---|---|---|
| 9 · E-Mail-Vorsortierer | täglich, dutzende Mails | Minuten | **hoch** |
| 2 · Scan-Sortierer | ca. 8–60 | 1–3 Min | **hoch** |
| 1 · Rechnungsprüfer | 10–15 | 3–5 Min | **hoch**, plus Geldfund |
| 5 · Zubehör-Prüfung | mehrere je Küche | 2–3 Min | mittel |
| 6 · Abladebestätigung | 2–3 | 3–5 Min | gering |
| 3 · Garantie-Anmeldung | 1–2 | 3–9 Min | **~10 Min gesamt** |
| 4 · Kundenerinnerung | 2–3 | 2 Min | ~6 Min gesamt |
| 8 · Rückfrage Auslieferer | 2–3 | 2 Min | ~6 Min gesamt |
| 10 · Logo-Wasserzeichen | 2–3 | 5 Min | ~15 Min gesamt |

Die Agenten 3, 4, 8 und 10 sind einfach zu bauen — sparen aber zusammen etwa **eine halbe Stunde im Monat**. Das rechtfertigt keinen Bau- und Wartungsaufwand, solange 1, 2 und 9 nicht laufen. Sie bleiben auf der Liste, aber weiter hinten.

## Die Stufen

### Stufe 1 — die Dokumentenmaschine (Start hier)

**A2 Scan-Sortierer** und **A1 Rechnungsprüfer**, gemeinsam gebaut.

Warum diese zuerst: höchste Menge, kein Zugriff nach außen nötig, Fehler sind harmlos (eine falsch benannte Datei benennt man um). Ideal zum Vertrauen aufbauen.

Steckbriefe: `agenten/A2-scan-sortierer.md`, `agenten/A1-rechnungs-pruefer.md`

**Vier Wochen laufen lassen, bevor es weitergeht.**

### Stufe 2 — der Posteingang

**A9 E-Mail-Vorsortierer.** Der größte Einzelhebel, aber erst sinnvoll, wenn Stufe 1 zuverlässig läuft — denn der Vorsortierer speist Rechnungen und Auftragsbestätigungen direkt in die Dokumentenmaschine ein. Ohne sie hat er niemanden, dem er etwas übergibt.

Technisch: **nicht** über Thunderbird, sondern direkt per IMAP über Manitu. Thunderbird ist ein Anzeigeprogramm; an seine lokalen Datenbanken heranzugehen, während es läuft, ist fehleranfällig. Über IMAP sieht Claude dieselben Mails und dieselben Ordner, die Felix schon nach Herstellern gefiltert hat — und Thunderbird bekommt die Änderungen automatisch mit.

**Grenze:** Der Vorsortierer verschiebt und markiert. Er löscht nichts endgültig und antwortet nie.

### Stufe 3 — Erweiterungen der Maschine

**A5 Zubehör-Prüfung** und **A6 Abladebestätigung**. Beides ist im Kern nur eine neue Prüfregel in der bestehenden Maschine, kein neuer Agent. Aufwand jeweils ein knapper Tag.

### Stufe 4 — alles mit Zugangsdaten nach außen

**A3 Garantie-Anmeldung** (G4U/GFM, GarantieMax), **A7 Agenda-Upload**, teilweise **A11 Dokumenten-Export**.

Diese Agenten müssen sich irgendwo einloggen und in fremden Portalen klicken. Das ist die aufwendigste und störanfälligste Klasse: Ändert der Anbieter sein Formular, steht der Agent — ohne Vorwarnung. Dazu kommt die Frage, wo die Zugangsdaten liegen.

Ehrliche Empfehlung: **erst dann, wenn Stufe 1–3 seit Monaten stabil läuft** — und selbst dann eher als „Agent füllt aus, Felix klickt auf Absenden".

### Nicht bauen, sondern anders lösen

**A4 Kundenerinnerung** und **A8 Rückfrage beim Auslieferer** — siehe nächster Abschnitt.

**A10 Logo-Wasserzeichen** — dafür braucht es keinen Agenten. Ein kleines Skript, das man auf einen Ordner zieht, reicht (helles Logo bei dunklen Küchen, dunkles bei hellen). Halber Tag, dann nie wieder anfassen.

## Zwei Punkte, die in der Kandidatenliste zu optimistisch bewertet sind

### WhatsApp ist nicht 5/5 einfach

A4 und A8 sind mit Einfachheit 5/5 bewertet. Das trifft nicht zu. **WhatsApp Business — die App, die Felix nutzt — hat keine Schnittstelle zur Automatisierung.** Automatisiert senden geht nur über die WhatsApp Cloud API von Meta, und die bedeutet:

- geschäftliche Verifizierung bei Meta,
- Vorlagen für ausgehende Nachrichten müssen einzeln genehmigt werden,
- die Rufnummer muss aus der Business-App migriert werden — danach funktioniert die gewohnte App auf dem Handy nicht mehr wie bisher,
- laufende Kosten pro Gespräch.

Für zwei bis drei Erinnerungen im Monat ist das grob unverhältnismäßig. Werkzeuge von Drittanbietern, die WhatsApp Web fernsteuern, verstoßen gegen die Nutzungsbedingungen und riskieren die Sperrung der Nummer — bei der Nummer, über die die Kundenkommunikation läuft, ein untragbares Risiko.

**Besserer Weg, gleicher Nutzen:** Der Agent überwacht die Termine und legt Felix morgens den **fertigen Text** hin — „Für Familie Beispiel steht Donnerstag die Auslieferung an, hier ist die Erinnerung." Ein Tippen zum Kopieren, ein Tippen zum Senden. Das Erinnern war der Aufwand, nicht das Absenden. Und die Nachricht kommt weiterhin persönlich von Felix — was bei Kunden, die gerade fünfstellig investieren, ohnehin besser ankommt.

Dasselbe für die Rückfrage bei René und Robert.

### Der Zugriff auf CompuSoft Winner ist realistisch nicht zu erwarten

A11 ist bereits als „technisch zu prüfen" markiert — das ist richtig. Die Einschätzung vorweg: Für eine Branchenlösung dieser Größenordnung gibt es für einen einzelnen Händler in aller Regel keine offene Schnittstelle, und ein direkter Zugriff auf die Datenbank verbietet sich schon aus Gewährleistungsgründen.

**Realistischer Zuschnitt für A11:** Der Agent erinnert eine Woche vor Auslieferung, sagt, welche Dokumente gebraucht werden, prüft den Anzahlungsstand aus der Einnahmen-Ausgaben-Liste und stellt zusammen, was schon als PDF vorliegt. Das Exportieren aus Winner bleibt Handarbeit — es sind ein paar Klicks, das Daran-Denken war das Problem.

**Vor weiterer Planung schriftlich bei Cyncly anfragen.** Nicht annehmen.

## Was in der Liste fehlt: die Fristen

Im Mai war Felix' eigenes Kernproblem ein anderes als Dokumentenablage:

> „Selber darauf achten, pünktlich zu bestellen alles was Lieferzeit hat. Also Küche z. B. 6–8 Wochen. Und davor noch Erinnerung, ob bereits gemessen wurde. […] Verschiedene Parameter, die ich aktuell alle selber checken und im Auge behalten muss. Bei jedem einzelnen Auftrag."

In der aktuellen Liste steht das nur noch unter „Noch offen" als Notion-Fristen-Wächter. Das ist vermutlich die falsche Einstufung: **Ein vergessener Bestelltermin bei 6–8 Wochen Lieferzeit kostet mehr als alle anderen Kandidaten zusammen einsparen.** Eine verschobene Küchenmontage bedeutet Handwerker umplanen, Kunde vertrösten, im Zweifel Nachlass.

Vorschlag: Das gehört als eigener Punkt bewertet und nicht unter „später" abgelegt. Fachlich ist es machbar, weil die Termine schon in Notion und Google Kalender stehen — es braucht keinen Zugriff auf Winner, sondern eine Liste von Regeln der Form „X Wochen vor Auslieferung muss Y erledigt sein". Die Regeln stehen in `wissen/BETRIEB.md`, Abschnitt 6.

Das sollte mit Felix besprochen werden, bevor die Reihenfolge festgezurrt wird — es kann sein, dass er es bewusst zurückgestellt hat, weil das manuelle Wiedervorlagesystem für ihn gut genug funktioniert.

## Zusammengefasst

| Reihenfolge | Was | Aufwand | Warum |
|---|---|---|---|
| 1 | Dokumentenmaschine (A2 + A1) | ~1 Woche | höchste Menge, risikoarm |
| 2 | *offen:* Fristen-Wächter | ~1 Woche | höchster Schaden bei Versäumnis — mit Felix klären |
| 3 | E-Mail-Vorsortierer (A9) | ~3 Tage | größter Einzelhebel, braucht Stufe 1 |
| 4 | Prüfregeln A5, A6 | je ~1 Tag | Erweiterung, kein Neubau |
| 5 | Wasserzeichen (A10) | ~½ Tag | Skript, kein Agent |
| 6 | Portale A3, A7, A11 | offen | erst bei stabilem Betrieb |
| — | A4, A8 als Textvorlage statt Versand | im Fristen-Wächter enthalten | WhatsApp-Automatisierung lohnt nicht |

## Ausgeschlossen — und warum das richtig ist

Felix hat fünf Kandidaten selbst ausgeschlossen. Die Begründungen tragen und sollten nicht wieder aufgemacht werden:

| Was | Warum nicht |
|---|---|
| Küchen-Auftragsbestätigung mit ~25 Einzelteilen prüfen | zu hohes Fehlerpotenzial, erfordert Fachwissen |
| Nachfassen nach Angebot | beziehungsabhängig, gehört zum Verkauf |
| Anruf nach der Montage | bewusste persönliche Fürsorge |
| Lager-Fotos für Auslieferer | situativ vor Ort |
| Kommentieren in sozialen Medien | wirkt automatisiert unecht |
