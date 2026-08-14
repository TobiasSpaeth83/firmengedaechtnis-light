# A1 — Rechnungsprüfer

**Stufe:** 1 · **Stand:** 14.08.2026 · **Status:** Entwurf, noch nicht in Betrieb

Prüft eingehende Lieferantenrechnungen gegen die zugehörige Auftragsbestätigung. Läuft im selben Durchgang wie A2 — es ist dieselbe Maschine mit einer zusätzlichen Prüfregel.

## Der eigentliche Wert

Nicht das Ablegen, sondern der **Abgleich**: Stimmt der berechnete Betrag mit dem überein, was zuletzt bestätigt wurde? Genau da entstehen die Fehler, die sonst niemand bemerkt — eine Preisanpassung nach einer Planänderung, ein doppelt berechnetes Teil, eine nicht abgezogene Anzahlung.

Deshalb der wichtigste Punkt im ganzen Ablauf: **verglichen wird gegen die *aktuellste* Auftragsbestätigung.** Bei Küchenaufträgen gibt es oft mehrere, weil sich unterwegs etwas ändert. Gegen eine veraltete zu prüfen ist schlimmer als gar nicht zu prüfen, weil es falsche Sicherheit erzeugt.

## Auslöser

Werktags 10:00 Uhr, gemeinsam mit A2. Zusätzlich, sobald eine Rechnung im Hersteller-Mailordner eintrifft (ab Stufe 2, wenn A9 läuft).

## Ablauf

1. Dokument von A2 als „Lieferantenrechnung" erkannt und einer Kommission zugeordnet.
2. **Aktuellste Auftragsbestätigung** zu dieser Kommission suchen — die mit dem jüngsten Datum. Gibt es mehrere mit gleichem Datum oder ist unklar, welche gilt → `zu_pruefen`, nicht weiterrechnen.
3. **Vergleichen:**
   - Gesamtbetrag brutto und netto
   - Artikelnummern und Anzahl, soweit auf beiden Dokumenten aufgeführt
   - berücksichtigte Anzahlungen und Nachlässe
4. **Bewerten:**
   - Abweichung 0 € → `ok`
   - Abweichung bis zur Bagatellgrenze (Vorschlag: 2 €, in `wissen/BETRIEB.md` festlegen) → `ok`, Hinweis vermerken
   - jede größere Abweichung → `abweichung`, Betrag und Richtung nennen
   - keine Auftragsbestätigung auffindbar → `zu_pruefen`
5. **Ablegen** im Kommissionsordner unter `Rechnungen`.
6. **Registerzeile** schreiben, inklusive Vergleichsergebnis.
7. **Eintrag in die Einnahmen-Ausgaben-Liste** vorbereiten — siehe Einschränkung unten.
8. Im Tagesbericht: alle Abweichungen zuerst, danach der Rest als Zahl.

## Die Einschränkung bei der Einnahmen-Ausgaben-Liste

Der Agent schreibt **nicht** direkt in die laufende Excel-Datei, während Klara oder Felix sie womöglich geöffnet haben. Zwei Programme, die gleichzeitig in dieselbe Datei schreiben, führen zu verlorenen Zeilen — und das fällt bei einer Buchhaltungsliste erst Wochen später auf.

Stattdessen: Der Agent schreibt die fertigen Zeilen in eine Datei `00-Register\Nachtrag-JJJJ-MM.xlsx`, die einmal am Tag von Hand übernommen wird (kopieren, einfügen, fertig — zwei Minuten). Wenn sich das bewährt, kann man später über eine sauberere Lösung nachdenken.

## Was der Agent nie tut

- eine Rechnung als geprüft markieren, wenn keine Auftragsbestätigung gefunden wurde
- eine Zahlung anstoßen oder vormerken
- eine Rechnung beim Lieferanten reklamieren
- eine Abweichung selbst erklären („ist wahrscheinlich der Rabatt") — die Abweichung wird genannt, nicht gedeutet

## Abnahme

- [ ] Fünf echte, bereits geprüfte Rechnungen ergeben dasselbe Ergebnis wie die manuelle Prüfung
- [ ] Ein Fall mit zwei Auftragsbestätigungen wird gegen die neuere geprüft
- [ ] Eine künstlich veränderte Rechnung (Betrag um 50 € erhöht) wird als `abweichung` erkannt
- [ ] Eine Rechnung ohne auffindbare Auftragsbestätigung landet auf `zu_pruefen`, nicht auf `ok`
- [ ] Beträge im Register sind Zahlen, nicht Text

Der dritte Punkt ist der wichtigste: Ein Prüfer, der nichts findet, sieht genauso aus wie einer, der funktioniert. Das muss man aktiv testen.

## Bekannte Schwachstellen

| Was | Wie damit umgehen |
|---|---|
| Sammelrechnungen über mehrere Kommissionen | zunächst immer `zu_pruefen` |
| Teillieferungen und Teilrechnungen | Vergleich der Summe schlägt fehl — Regel dafür erst nach den ersten echten Fällen bauen |
| Rechnung erreicht uns vor der geänderten Auftragsbestätigung | sieht wie eine Abweichung aus und ist keine — deshalb wird die Abweichung gemeldet, nicht gedeutet |
| Skonto und Rückvergütungen | in Stufe 1 nicht abgedeckt |

## Änderungen

| Datum | Was |
|---|---|
| 2026-08-14 | Steckbrief angelegt |
