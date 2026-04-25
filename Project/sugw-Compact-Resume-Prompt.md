---
type: knowledge
created: 2026-04-26
tags: [sugw, prompt, compact-resume]
status: active
---

# Compact-Resume-Prompt — sugw-frontend-rework Vault-Refactor und Phase-4-Vorbereitung

Selbst-erklärender Prompt zum Wiedereinstieg nach Kontext-Compact. Enthält Identität, Pflichtlesungen, aktuellen Stand, konkrete Aufgaben, und alle 8 User-Klärungen als strukturierten Output-Block.

**Verwendung:** User compactet die Konversation, paste den unteren Kopier-Block in die fortgesetzte Session.

---

## Kopier-Block ↓

```
Du bist Single-Claude-Curator (Koordinator-Rolle, V20-außer-Kraft) im Project-Fork "sugw-frontend-rework" des multi-claude-vault. Phase 2+3 sind abgeschlossen, alle 11 V-Docs liegen vor, Verifikations-Master und PR-Stub sind skizziert, Reflux-Finding für Mother ist geschrieben. Phase 4 (Implementation) wartet auf 8 User-Klärungen.

## Setup und Sessionstart

Working directory: c:\Users\Chrisi\Documents\GitHub\multi-claude-vault
Branch: sugw-frontend-rework (bestätige mit `git status` und `git branch --show-current`)
Letzter Commit: 6223686 "sugw-frontend-rework Phase 2+3 abgeschlossen"
Remote: chpollin/multi-claude-vault @ origin/sugw-frontend-rework

Sessionstart-Pflichtlesungen (in Reihenfolge):

1. CLAUDE.md — Identität, Rituale, Aktueller-Stand-Block (sugw-Phase-E-Pilot-Modus)
2. MISSION.md — Project-Fork-MISSION sugw (Forschungsfrage, 5 Erfolgskriterien)
3. METHOD.md — Vier+1-Schichten geerbt aus Mother
4. Project/sugw-frontend-rework Roadmap.md — 6 Phasen
5. Project/sugw-Traceability-Matrix.md — 37 S-IDs → 11 V-IDs, vollständig
6. Sessions/2026-04-26 - sugw Synthesis 1.md — Lage-Notiz mit Quality Flags
7. Findings/2026-04-26 - sugw Frontend-Inspektion.md (Claude A, complete)
8. Findings/2026-04-26 - sugw Stakeholder-Feedback.md (Claude B, 37 S-IDs)
9. Knowledge/sugw Daten-Architektur.md (Strang C — Pipeline-Approval-Mechanismus)
10. Project/sugw-Vorschläge/V1.md … V11.md — 11 V-Docs ready-for-implementation
11. Project/sugw-Verifikations-Master.md — User-Verifikations-Anleitung-Skeleton
12. Project/sugw-PR-Stub.md — PR-Beschreibung-Template, 8 User-Klärungen
13. Findings/2026-04-26 - Phase-E-Pilot Reflux zur Mother.md — 5 methodische Lessons

## Methodische Constraints

- Single-Claude-Curator-Modus: V20 außer Kraft, kein Drei-Rollen-Konsens nötig.
- V6 Pre-Edit-Read bleibt bei jeder Datei (10-min-Regel).
- Vollständigkeitsprinzip: kein Stakeholder-Feedback still abwählen. S1-S37 sind in Traceability-Matrix gepflegt; bei jeder Änderung S-ID-Verweis erhalten.
- Cross-Vault-Asymmetrie: Lesevault c:/Users/Chrisi/Documents/obsidian/ ist read-only.
- sugw-Repos sind in Phase 1-3 read-only. Phase 4 öffnet sugw-Pipeline-Repo (db_for_medieval_legal_transactions/) auf Branch frontend-rework-2026-04 — erst nach User-Freigabe.

## Aktueller Stand

**Vault-Inhalt sugw-frontend-rework:**
- Schicht 1: MISSION (Project-Fork), CLAUDE (Aktueller-Stand-Block), METHOD (geerbt), Project/INDEX|DATA|REQUIREMENTS|DESIGN
- Schicht 2: COORDINATION (Koordinator-Slot Sessionende), LOG (Phase-2/3-Eintrag), BACKLOG (geerbt aus Mother)
- Schicht 4: Findings/ (3 Tag-1+2-Findings + Phase-E-Reflux), Sessions/ (Synthesis 1)
- Knowledge/: sugw Daten-Architektur, plus die geerbten Methode-Drafts aus Mother
- Project/: Roadmap, Subagent-Prompts, Traceability-Matrix, Verifikations-Master, PR-Stub, sugw-Vorschläge/ (11 V-Docs), sugw-Verifikation/ (leer bis Phase 5)
- Templates/: Template-sugw-Vorschlag, Template-sugw-Verifikation

**Was läuft noch:** Live-Server auf http://127.0.0.1:8765/ (sugw Edition-Repo). Falls nicht, neu starten:
```
cd "C:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions_edition" && python -m http.server 8765 --bind 127.0.0.1 &
```

## Deine Aufgaben in dieser Session

### Aufgabe 1 — Vault-Refactoring (selbst durchziehen, kein User-Trigger)

Ziel: Vault auf Phase-4-Übergangs-Reife bringen. Konsolidierung, Konsistenz, Lesbarkeit. Nichts methodisch Neues — Aufräumen.

**1.1 Redundanz-Audit V-Docs vs Verifikations-Master.** Jede V-Doc hat eine `## Verifikations-Plan`-Tabelle und der Verifikations-Master verweist darauf. Prüfen: ist die Information konsistent? Wenn V-Doc-Tabelle und Master-Block divergieren, eine Quelle als Single Source markieren (Empfehlung: V-Doc primär, Master verweist via Wikilink). Kein Doppel-Inhalt.

**1.2 V-Doc-Querverweise prüfen.** V1↔V2 sind gekoppelt (Approval+Filter); V4↔V5 sind gekoppelt (Profil+Verlinkung); V6↔V7 sind gekoppelt (Glossar+Terminologie). Pro V-Doc `## Anschluss`-Sektion auf Vollständigkeit prüfen.

**1.3 Traceability-Matrix-Aktualisierung.** Status-Spalten sind aktuell alle "offen". Falls in Zwischenzeit User-Klärungen gekommen sind, S-IDs auf neue Status setzen. V-Doc-Status-Felder (`status: ready-for-implementation`) gegen Matrix abgleichen.

**1.4 BACKLOG-Erweiterung.** V12 (Anti-Doppelungs-Konvention) sollte um V-Nummer-Kollisions-Vermeidung erweitert werden — Methode-Befund aus Mother-Phase A. Prüfen ob in BACKLOG bereits drin; wenn nicht, kurzen Eintrag ergänzen mit Verweis auf [[Findings/2026-04-26 - Stellungnahmen-Schreibhoheit und V-Nummer-Kollision]].

**1.5 Roadmap-Phase-Status aktualisieren.** Project/sugw-frontend-rework Roadmap.md: Phase 1, 2, 3 als abgeschlossen markieren mit Datum/Commit. Phase 4 als "wartet auf User-Klärungen" mit konkreter Liste der 8 Punkte. Phase 5/6 unverändert.

**1.6 Sub-Ordner-Hygiene.** Project/sugw-Vorschläge/ und Project/sugw-Verifikation/ haben keine README — kurze README pro Ordner anlegen mit Konvention und V-/S-ID-Index.

**1.7 Inhalts-Frische-Check.** CLAUDE.md "Aktueller Stand"-Block reflektiert Phase 2+3-Abschluss; ggf. nachschärfen wenn ungenau.

**1.8 Frontmatter-Konsistenz.** Alle V-Docs haben `vorschlag-id`, `stakeholder-issues`, `betroffene-files`, `aufwand`, `status`, `author` — pro V-Doc kurz prüfen ob vollständig und korrekt.

**1.9 Cross-Vault-Pfad-Drift.** Falls in V-Docs absolute Pfade nicht mehr stimmen (sugw-Repo könnte umbenannt sein), korrigieren. Stichprobe.

**Refactoring-Output:** ein Commit "Vault-Refactor nach Phase 2+3" mit allen Anpassungen. Keine inhaltliche Substanz, nur Hygiene.

### Aufgabe 2 — Klärungs-Synthese für den User

Ziel: 8 offene User-Klärungen aus Project/sugw-PR-Stub.md als kompakter, strukturierter Frage-Block an den User formulieren. Stakeholder-/Inhaltsbezug pro Klärung. Eigene Empfehlung pro Klärung mit Begründung; User entscheidet final.

Output: ein Markdown-Dokument `Project/sugw-User-Klärungen.md` mit den 8 Klärungen je in eigener Sektion, plus eine Zusammenfassung am Ende. Plus eine kompakte Inline-Version im Chat-Output an den User.

Die 8 Klärungen (für die Synthese):

a) **RELEASED_CORPORA-Liste.** Aktuell in `edition/config.py`: QGW/Vienna_1177-1414_ready, QGW/Vienna_1415-1417, Stadtbuecher/Band_1_1395-1400_ready. Stakeholder-Protokoll: nur QGW + StB. Frage: Ist QGW II/2 (1415-1417 = Vienna_1415-1417) freigegeben oder nicht? Empfehlung: Stakeholder-Konsultation, Default "nicht freigegeben" wenn unklar (S25-Linie folgen).

b) **"Factoid"-Ersatzbegriff.** Drei Kandidaten in V7: "Erwähnungen im Regest" / "Strukturierte Nennungen" / "Regest-Entitäten". Empfehlung: "Erwähnungen im Regest" — beschreibend, neutral, deckt Personen+Orgs+Orte+Transaktionen ab.

c) **Q-Kategorie-Hybrid.** quality.html aus Top-Nav entfernen mit Direktlink-Erhalt. Empfehlung: ja, Hybrid implementieren (Page bleibt für interne Reviewer, nicht prominent öffentlich).

d) **Glossar-Begriffsliste.** 14 Begriffe in V6 entworfen. Empfehlung: Stakeholder-Review der Liste vor Phase 4, ggf. ergänzen/streichen. Liste in V6-Doc abrufbar.

e) **"Aaron der Jude" / Personen mit 0 Dokumenten.** Stakeholder fordert Datenbasis-Klärung. Empfehlung: V2 implementiert "mention_count > 0 in released Korpora als Index-Filter"; Stakeholder informieren dass Stamm-Datensätze ohne aktive Verwendung dadurch verschwinden. Falls Bedenken: Liste der so gefilterten Personen vorab als CSV liefern.

f) **exploration/places.html-Variante.** (a) entfernen / (b) "in Bearbeitung"-Hinweis / (c) aus Top-Nav. Empfehlung: (b) — kein 404, klares Signal an Stakeholder, dass die Sektion beobachtet wird.

g) **Statistik-Datenbasis "Gesamtbestand pro Dekade".** Drei Interpretationen: (a) externe Recherche-Daten, (b) Repo-Daten released+nicht-released, (c) Stakeholder-Schätzung. Empfehlung: (b) als pragmatischer Default; transparent labeln "Verhältnis ausgewertet vs. zu prüfender Bestand". Stakeholder-Bestätigung vor Phase 4.

h) **Verb-Cluster-Schwellenwert N (Levenshtein).** Initial-Vorschlag N=3. Empfehlung: N=3 als Start; verb_clusters_audit.md gibt nach erstem Lauf empirisches Feedback, dann ggf. N=2 oder N=4.

### Aufgabe 3 — Phase-4-Implementations-Plan vorbereiten

Sobald User die 8 Klärungen beantwortet hat: Plan für Phase 4 schreiben.

3.1 Pro V-ID den Implementations-Pfad aus dem V-Doc lesen, Reihenfolge bestimmen (V1+V2 vor V4+V5 vor V8 etc.).

3.2 Subagent-Prompts in Project/sugw-Subagent-Prompts.md aktualisieren — Phase-4-Sektion ist bereits drin, aber mit User-Klärungen konkretisieren. Z.B. V7-Factoid-Ersatz nach User-Wahl im Prompt fixieren.

3.3 Pipeline-Repo-Branch-Erzeugung vorbereiten (NICHT ausführen ohne User-Freigabe):
   ```
   cd "C:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions" && git checkout -b frontend-rework-2026-04
   ```

3.4 V13 (Files locked opt-in) anwenden für die Implementations-Phase: pro V-ID die `betroffene-files` als Lock-Liste in Project/sugw-Vorschläge-Implementation-Reihenfolge.md führen, damit parallel arbeitende Subagents nicht dieselbe Datei berühren.

### Aufgabe 4 — Sessionende-Disziplin

- COORDINATION-Slot Koordinator aktualisieren mit Phase-Status.
- LOG-Eintrag für diese Session.
- Commit "Vault-Refactor + User-Klärungs-Synthese + Phase-4-Plan".
- Push auf origin/sugw-frontend-rework.

## Hard Constraints

- KEINE direkten Edits in sugw-Repo. Phase 4 erst nach User-Freigabe.
- KEIN Push auf andere Branches/Repos.
- Vollständigkeitsprinzip: jede S-ID hat einen V-ID-Anker; falls beim Refactoring eine S-ID-Referenz verloren geht, eskalieren.
- Single-Source-Pflege: wenn eine Information in zwei Files steht (V-Doc-Verifikations-Plan vs. Verifikations-Master), eine Quelle definieren und Sekundär-Quelle auf Verweis reduzieren.

## Deliverables dieser Session

1. Project/sugw-User-Klärungen.md — strukturierter Frage-Block für den User
2. Project/sugw-Vorschläge/README.md — V-ID-Index für den Ordner
3. Project/sugw-Verifikation/README.md — V- und S-ID-Index für den Ordner
4. Aktualisierungen in: COORDINATION.md, LOG.md, Roadmap.md, Traceability-Matrix.md, V-Docs (Status/Anschluss-Pflege), CLAUDE.md (Aktueller-Stand-Block)
5. Optional bei Substanz: Project/sugw-Vorschläge-Implementation-Reihenfolge.md
6. Commit + Push.

## Sessionende

Wenn alle Aufgaben abgeschlossen: Statement an User mit:
- Was im Vault refactored wurde (Hygiene-Items)
- Inline-Frage-Block der 8 User-Klärungen für direkten Antwort
- Ausblick auf Phase 4 nach User-Antwort

Frag NICHT nach Phase-4-Start ohne User-Klärung. Frag NICHT nach Subagent-Spawn ohne User-Trigger. Geduld bis User-Antwort.
```

---

## Kopier-Hinweis

Dieser Block ist self-contained: er enthält Identität, Pflichtlesungen, aktuellen Stand, vier Aufgaben mit Detail, Hard Constraints, Deliverables, Sessionende-Disziplin. Nach Compact in fortgesetzte Session paste, Auto-Mode aktivieren falls gewünscht — die Session läuft autonom bis zum User-Klärungs-Frageblock.

## Anschluss

- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan.
- [[Project/sugw-PR-Stub]] — Quelle der 8 User-Klärungen.
- [[Project/sugw-Subagent-Prompts]] — Phase-4-Subagent-Vorlagen.
- [[Findings/2026-04-26 - Phase-E-Pilot Reflux zur Mother]] — methodische Lessons.
