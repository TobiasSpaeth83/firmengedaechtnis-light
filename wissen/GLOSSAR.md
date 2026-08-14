# Glossar

Zwei Sorten Begriffe: die aus dem Küchenhandel (die Claude kennen muss) und die aus der Technik (die der Betrieb verstehen soll). Wenn in einem Gespräch ein Wort fällt, das hier nicht steht und erklärungsbedürftig war — hier ergänzen.

## Aus dem Betrieb

| Begriff | Bedeutung |
|---|---|
| **Kommission** | Ein Küchenauftrag von der Bestellung bis zur Abnahme. Die Kommissionsnummer ist die zentrale Ordnungsgröße: Jedes Dokument gehört zu genau einer Kommission. |
| **Auftragsbestätigung (AB)** | Bestätigung des Herstellers über Umfang und Preis. Es kann mehrere je Kommission geben, wenn sich unterwegs etwas ändert — **maßgeblich ist immer die neueste.** |
| **Abladebestätigung** | Beleg des Herstellers, dass die Küche geliefert und abgeladen wurde. Wird auf Fehlteile geprüft. |
| **Fehlteil** | Ein bestelltes, aber nicht geliefertes oder beschädigtes Teil. Muss nachbestellt werden und ist häufig der Grund, warum eine Montage nicht abgeschlossen werden kann. |
| **Aufmaß** | Das genaue Vermessen vor Ort. Muss vor der Bestellung erfolgen — sonst wird eine Küche bestellt, die nicht passt. |
| **Liefer-KW** | Kalenderwoche der Lieferung. Achtung: Wochenangabe und Datumsangabe können in verschiedenen Systemen auseinanderlaufen — bei Abweichung immer nachfragen. |
| **Anzahlung / Restzahlung** | Übliche Zahlungsaufteilung. Für die Rechnungsprüfung wichtig, weil Anzahlungen auf der Schlussrechnung abgezogen sein müssen. |
| **Zubehör** | Stühle, Armaturen, Kleinteile — meist bei anderen Lieferanten als der Küche selbst bestellt, mit eigenen Auftragsbestätigungen. |

## Aus der Technik

| Begriff | Bedeutung |
|---|---|
| **Agent** | Eine festgelegte Aufgabe, die Claude wiederholt und gleich abarbeitet. Beschrieben in einem Steckbrief unter `agenten/`. |
| **Routine** | Der Zeitplan, der einen Agenten weckt. Bei uns: die Windows-Aufgabenplanung. |
| **Trockenlauf** | Ein Probelauf, bei dem der Agent nur sagt, was er tun würde, ohne etwas zu verändern. Immer der erste Schritt. |
| **Register** | Die Tabelle, in der jedes verarbeitete Dokument eine Zeile bekommt. Damit ist nachvollziehbar, was der Agent getan hat. |
| **Repository (kurz: Repo)** | Der Ordner mit diesem Firmengedächtnis, dessen Änderungen nachvollziehbar gespeichert werden. |
| **Prüfsumme** | Ein Zahlenwert, der aus dem Inhalt einer Datei berechnet wird. Zwei Dateien mit derselben Prüfsumme sind identisch — so erkennt der Agent, dass er ein Dokument schon verarbeitet hat. |
| **IMAP** | Das Verfahren, mit dem Mailprogramme Mails vom Anbieter abrufen. Der Agent nutzt denselben Weg und sieht dieselben Ordner. |
| **Schnittstelle (API)** | Ein offizieller Weg, mit dem ein Programm ein anderes fernsteuern kann. Gibt es nicht für jedes Programm — deshalb ist manches nicht automatisierbar. |
| **`.env`** | Eine Datei mit Zugangsdaten, die absichtlich nie mit hochgeladen wird. |
| **Status `zu_pruefen`** | Der Agent war sich nicht sicher. Kein Fehler, sondern das erwünschte Verhalten. |
