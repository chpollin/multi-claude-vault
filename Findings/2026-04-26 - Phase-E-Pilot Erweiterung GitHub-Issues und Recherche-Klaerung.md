---
type: finding
created: 2026-04-26
tags: [methode, phase-e, v21, v22, reflux, github-issues]
status: complete
author: Koordinator (Single-Curator)
reflux-target: main@multi-claude-vault
reflux-status: pending
---

# Finding 2026-04-26 — Phase-E-Pilot-Erweiterung: GitHub-Issues und Recherche-statt-Klärung

Zwei zusätzliche methodische Lessons aus dem fortgesetzten Phase-E-Pilot (sugw-frontend-rework, Branch von Mother@e355bac), die vor Phase 4 entstanden sind. Geschrieben als Reflux-Erweiterung des bestehenden [[Findings/2026-04-26 - Phase-E-Pilot Reflux zur Mother]].

## Zusammenfassung

Zwei pragmatische Befunde aus der Übergangsphase Phase-3-zu-Phase-4 mit dem User:

1. **V21 — GitHub-Issues als operativer Spiegel der V-Docs.** Tracking auf Implementation-Ebene gehört nicht in den Vault-internen Status, sondern in das Issue-Tracker-System des Code-Repos — sichtbar für Stakeholder, verlinkbar in PRs, mit nativem Branch-Workflow.
2. **V22 — Recherche statt Klärung.** Pendente "User-Klärungen" sind oft nicht User-Klärungen sondern Recherche-Lücken: Code-Lektüre, Daten-Stichproben oder erneute Original-Quellen-Lektüre beantworten sie. Stakeholder-Bestätigung erfolgt rückwirkend bei Verifikation, nicht vorab.

## Befund V21 — GitHub-Issues als operativer Spiegel der V-Docs

### Beobachtung

In Phase 3 wurden 11 V-Docs als `Project/sugw-Vorschläge/V<n>.md` erstellt mit Frontmatter (vorschlag-id, stakeholder-issues, betroffene-files, aufwand, status). Status `ready-for-implementation` war Vault-intern dokumentiert. Dann fragte der User: *"Kannst du alle Vorschläge als GitHub Issues anlegen?"* — die Antwort ist offensichtlich Ja, mit drei nicht-trivialen Begründungen:

1. **Sichtbarkeit.** Stakeholder können Issues lesen, kommentieren, abonnieren. Vault-interne Markdown-Files sind technisch sichtbar (chpollin/multi-claude-vault ist public), praktisch aber für Nicht-Vault-Nutzer unzugänglich.
2. **Branch-Integration.** Issue-Nummer in Commit-Messages (`Closes #3`) ergibt automatische Verlinkung zur PR-Beschreibung. PR-Branch-Name kann `v3-suche-diakritika` heißen, GitHub zeigt die Verbindung.
3. **Status-Lifecycle nativ.** Open/Closed/Milestone sind Issue-Tracker-Domäne. V-Doc-Status wird zur **abgeleiteten** Größe, nicht zur primären.

### Pragmatik der Repo-Wahl

Die Issues kommen ins **Edition-Repo** (Build-Output) statt ins Pipeline-Repo (Code), obwohl die Implementation im Pipeline-Repo passiert. Begründung: Aus Stakeholder-Sicht ist "Frontend = Edition-Site = Edition-Repo". Issue-Bodies enthalten expliziten Hinweis "Code-Implementation passiert im Pipeline-Repo, Branch `frontend-rework-2026-04`". Das ist ein methodisch interessanter Trade-off: Issue-Lokation = User-mentale-Karte, nicht Code-Lokation.

### V-Doc bleibt Source of Truth

Issue-Bodies sind **kompakte Spiegel** der V-Docs — Akzeptanzkriterien, Verifikations-Tabelle, Code-Lokus, Quelldokumentations-Links. Inhaltliche Änderungen erfolgen weiter im V-Doc, der Issue-Body wird bei Bedarf nachgezogen. Single-Source-Verletzung droht nur bei häufigen Änderungen — daher V-Doc-Frontmatter-Feld `github-issue: <n>` als Pointer plus konvention "bei substantieller Änderung Issue-Body manuell synchen oder Hinweis im Issue-Kommentar".

### Methodischer Ertrag

V21 ist eine **operative Komplementärschicht** zu V15 (Subagent-Integration) und V18 (Project-Fork-Topologie). Sie greift, sobald ein Project-Fork eine Implementation-Phase erreicht und ein Code-Repo mit Issue-Tracker als Anker existiert.

### Mother-METHOD-Konsequenz

V21 in METHOD aufnehmen mit Konvention:
- "Wenn ein Project-Fork eine Implementations-Phase erreicht und das Code-Repo Issue-Tracker hat: V-Docs als GitHub-Issues spiegeln. V-Doc bleibt Source of Truth, Issue ist operativer Spiegel mit Tracking-Funktion."
- "Issue-Repo-Wahl folgt der User-mentalen-Karte (z.B. Edition-Repo bei Frontend-Sicht), nicht zwingend dem Code-Repo. Issue-Body enthält expliziten Code-Lokus-Hinweis."
- "Ein Tracking-Übersichts-Issue als Single-Page-View aller V-IDs, mit Implementations-Reihenfolge und Vollständigkeits-Audit."
- "V-Doc-Frontmatter-Feld `github-issue: <n>` als Pointer."

## Befund V22 — Recherche statt Klärung

### Beobachtung

In Phase 3 wurden 8 "User-Klärungen" als pendent dokumentiert ([[Project/sugw-PR-Stub#User-Klärungen pendent (vor Merge)]]). Beispiele:

- (a) Ist QGW II/2 freigegeben?
- (b) Welcher Ersatz für "Factoid"?
- (e) Wie ist mit "Aaron der Jude" umzugehen?
- (g) Wie ist "Gesamtbestand pro Dekade" zu definieren?

Auf User-Frage *"Wie kannst du die acht User-Klärungen abklären? Indem du in die Daten schaust oder ins Frontend schaust, am besten in die ursprünglichen Dokumente oder begründete Lösungen überlegst?"* zeigte sich:

- (a) ist eine **Code-Lektüre-Frage** — `RELEASED_CORPORA` in `edition/config.py` ist Single Source, listet QGW II/2 explizit als released.
- (b) ist eine **Original-Quellen-Lektüre-Frage** — Protokoll-Wortlaut "Liste von im Regest vorkommenden Personen, Organisationen" gibt den Ersatzbegriff vor: "Erwähnungen im Regest".
- (e) ist eine **Daten-Stichproben-Frage** — `persons_search.json` zeigt empirisch, dass 47% der Personen `dc=0` haben, "Aaron der Jude" gehört dazu, V2-Filter (`dc>0` nach released-Filterung) erledigt ihn automatisch.
- (g) ist eine **begründete-Default-Frage** — Variante (b) "Bestand der Edition" ist pragmatisch im Repo ableitbar, wissenschaftlich sauber genug, transparent gegenüber Stakeholder.

Sechs der acht Klärungen waren **keine** Stakeholder-Klärungen sondern Recherche-Lücken im Koordinator-Prozess.

### Methodischer Ertrag

Voreilig dokumentierte "User-Klärungen" sind ein Anti-Pattern: sie verlagern Kognition vom Koordinator auf den User und blockieren Phase-4-Start. **Recherche-First-Disziplin** heißt: vor jeder dokumentierten Klärung erst prüfen, ob sie durch Code-/Daten-/Original-Lektüre oder begründeten Default beantwortbar ist. Nur echte Stakeholder-Wertentscheidungen (nicht Code-Fakten oder Recherche-Lücken) bleiben als pendente Klärung.

Stakeholder-Bestätigung erfolgt **rückwirkend in Phase 5** durch Verifikation am Frontend mit konkreten Stichproben — nicht vorab durch abstrakte Mehrfach-Choice-Fragen. Das ist näher am Stakeholder-Erlebnis (Stakeholder sieht das Ergebnis und bestätigt) und schneller (kein Vorab-Theater).

### Anti-Pattern

"Soft-Default mit User-Bestätigungs-Aufruf" — der Koordinator wählt eine Default-Variante, fragt aber trotzdem den User vor Phase 4. Resultiert in Latenz ohne Mehrwert: User wird gebeten, eine Default-Wahl zu bestätigen, die er nicht selbst getroffen hat und nicht beurteilen kann ohne das Ergebnis zu sehen.

### Mother-METHOD-Konsequenz

V22 in METHOD aufnehmen mit Konvention:
- "Pendente Klärungen erst dokumentieren, nachdem Code-/Daten-/Original-Recherche durchgeführt wurde. Klassifizieren: ist das eine Recherche-Lücke oder eine Stakeholder-Wertentscheidung?"
- "Stakeholder-Bestätigung erfolgt rückwirkend bei Verifikation am Ergebnis, nicht vorab durch abstrakte Multiple-Choice. Falls Stakeholder bei Verifikation anders entscheidet: Folge-Iteration im V-Doc + Issue."
- "Recherche-Antworten in eigenem Doc `Project/<projekt>-User-Klärungen.md` mit Frontmatter `status: resolved-by-research`, plus Beleg pro Antwort (Code-Stelle, Daten-Stichprobe, Quellen-Wortlaut)."

## Quality Flags

Phase-E-Pilot-Erweiterung gegen MISSION-Erfolgskriterien:

- **Methodische Lessons (für Mother):** ✓ Validiert (V21 + V22 als ergänzende V-Items zu V15/V18/V20 + bestehender Reflux).
- **Werkzeug-Integration GitHub-Issues:** ✓ funktional (12 Issues angelegt, Milestone, Labels).
- **Schreibhoheit-Erhalt im Vault-Strang:** ✓ V-Docs bleiben Source of Truth.

## Reflux-Aktion

Diese Lessons werden zusammen mit dem bestehenden Phase-E-Reflux-Finding in den Mother-Branch `main` als ein Reflux-PR eingebracht. V21 und V22 bekommen eigene BACKLOG-Einträge.

## Anschluss

- [[Findings/2026-04-26 - Phase-E-Pilot Reflux zur Mother]] — Originale 5 Lessons (V15, V18, V20, Subagent-Briefing, Vollständigkeitsprinzip).
- [[Project/sugw-User-Klärungen]] — Anwendungsbeispiel V22.
- [[Project/sugw-Vorschläge/README]] — Anwendungsbeispiel V21 (Issue-Index).
- [[METHOD]] — Mother-METHOD (V21, V22 ergänzen).
- [[BACKLOG]] — V21, V22 ergänzen.
