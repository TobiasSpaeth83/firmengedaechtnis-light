# 07 — Git-Arbeitsweise: immer vom neuesten Stand, nie direkt auf main

**Stand:** 08.10.2026 · **Gilt für:** Felix' Claude und alle späteren Agenten in diesem Repository

Dieses Repository ist das Gedächtnis des Betriebs. Es funktioniert nur, wenn alle mit **demselben, neuesten Stand**
arbeiten. Sonst übersieht Claude eine Regel, die gestern geändert wurde, oder eine Antwort des Mentors. Er schreibt
dann gegen eine alte Fassung und erzeugt Konflikte.

Die Arbeitsweise ist dieselbe wie in Tobias' Firmengedächtnis. Dort läuft sie mit über zwanzig Agenten
seit Monaten. Hier ist sie auf euren Betrieb zugeschnitten.

## Die vier Grundregeln

1. **Jede Sitzung beginnt mit dem neuesten Stand von `main`.** Ohne Ausnahme, auch wenn gestern alles aktuell war.
2. **Nie direkt auf `main` schreiben.** Jede Änderung läuft über einen eigenen Branch und einen Pull Request (PR).
3. **Ein PR je fertigem Arbeitsschritt, nicht je Datei.** Mehrere Commits auf einem Branch sind erwünscht.
   Ein PR entsteht erst, wenn ein zusammenhängendes Stück Arbeit fertig ist.
4. **Keine Sitzung endet mit offener Arbeit.** Am Ende ist alles committet und gemergt, oder es ist bewusst als
   offen vermerkt (siehe unten).

## Ablauf in Befehlen

```bash
# SITZUNGSSTART — immer
git checkout main
git pull --rebase origin main

# ARBEIT — für jeden zusammenhängenden Arbeitsschritt
git checkout -b <art>/<kurzer-name>       # z. B. docs/logbuch-oktober, new/steckbrief-a3, fix/register-zeile
# … arbeiten …
git add <geänderte-dateien>
git commit -m "<Art>: <kurz, was und warum>"
git push -u origin <art>/<kurzer-name>
# PR öffnen (GitHub-Webseite oder, falls installiert: gh pr create)

# NACH DEM MERGE — zurück auf den neuesten Stand
git checkout main
git pull --rebase origin main
```

**Arten** für Branch und Commit: `Docs:` (Dokumentation), `New:` (neue Datei/neuer Steckbrief), `Update:`
(Änderung), `Fix:` (Fehler behoben), `Cleanup:` (Aufräumen).

## Wer merged?

In Tobias' System merged der Agent seinen eigenen PR selbst. Ein Mensch prüft keinen Diff. Für euch gilt
wegen der [Spielregeln](05-SPIELREGELN.md) eine Stufe vorsichtiger:

| Was der PR ändert | Wer merged |
|---|---|
| Wissen, Logbuch, Glossar, eigene Register-Zeile, Tagesberichte | **Claude selbst**, sobald der Schritt fertig ist |
| Spielregeln, `CLAUDE.md`, Steckbriefe, Routinen, Schwellen | **Claude bereitet vor, Felix gibt kurz frei** („passt"), dann merged Claude |
| `connector/` (Regeln, Register-Kopf, Vorlagen) | wie oben. Gehört der Connector Tobias (CODEOWNERS), kann seine Bestätigung nötig sein. |

Felix muss dafür keinen Code lesen. Claude schreibt in den PR in zwei, drei Sätzen, **was** sich ändert und **warum**.

## Besonderheiten

- **Briefkasten-PRs werden nie gemergt.** Sie haben im Titel `NICHT MERGEN` (siehe
  [Agenten-Register](../connector/AGENTEN-REGISTER.md)). Wer etwas am Register ändert, nimmt dafür **einen eigenen
  Branch**, nie den Briefkasten-Branch. Sonst schließt der Merge den Briefkasten.
- **Vor dem Mergen noch einmal `main` holen**, wenn der Branch schon länger offen ist:
  `git pull --rebase origin main` auf dem Branch, dann pushen. So entstehen keine Konflikte mit Änderungen, die
  inzwischen dazugekommen sind.
- **Konflikt?** Nicht raten, welche Seite gilt. Bei Regeln oder Zahlen Felix fragen, bei Formatfragen die neuere
  Fassung behalten und den Fall im Logbuch notieren.
- **Kein `git push --force` auf `main`**, kein Löschen fremder Branches.
- **Nichts Vertrauliches committen.** `.env`, Zugangsdaten, Belege und Scans stehen in `.gitignore`. Neue Datei mit
  Passwort? Erst `.gitignore` ergänzen, dann committen.
- **Repository nicht in OneDrive** (siehe [Einrichtung](02-EINRICHTUNG.md)): OneDrive und Git stören sich gegenseitig.

## Sitzungsende — Prüfliste

- [ ] Alles committet und gepusht
- [ ] Fertige Arbeitsschritte gemergt. Was auf Felix' Freigabe wartet, steht im Tagesbericht unter „was Felix tun muss“.
- [ ] Logbuch ergänzt, falls eine Regel oder ein Ablauf geändert wurde
- [ ] Eigenen Briefkasten gelesen und beantwortet
- [ ] Wieder auf `main` und `git pull --rebase origin main` ausgeführt
