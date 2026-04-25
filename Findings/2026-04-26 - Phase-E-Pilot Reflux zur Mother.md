---
type: finding
created: 2026-04-26
tags: [methode, phase-e, v15-pilot, v18-pilot, reflux]
status: complete
author: Koordinator (Single-Curator)
reflux-target: main@multi-claude-vault
reflux-status: pending
---

# Finding 2026-04-26 — Phase-E-Pilot Reflux zur Mother

Methodische Lessons aus dem ersten Project-Fork-Pilot (sugw-frontend-rework, Branch von Mother@e355bac). Geschrieben als Reflux-Finding für die Mother-METHOD-Erweiterung; `reflux-target: main@multi-claude-vault` in Frontmatter.

## Zusammenfassung

Erster Phase-E-Lauf der Methode an einem realen Projekt (sugw-Frontend-Refactoring auf Stakeholder-Feedback). Drei-Rollen-Aufstellung: Koordinator (Single-Curator), Claude A (Tech), Claude B (Inhalt). V15-Pilot mit zwei Subagents lief erfolgreich; V20 hielt unter Druck; V18-Mother-Fork-Topologie funktionierte als Branch-basierter Light-Mode. Vier methodische Befunde mit Konsequenzen für METHOD-Erweiterungen.

## Befund 1 — V15 No-shared-write-Klausel hat unter Realbedingungen getragen

### Beobachtung

Zwei Subagents (Claude A Frontend-Inspektor; Claude B Stakeholder-Feedback-Analyst) liefen parallel in eigenen Conversations über den Vault-File-System-Channel. Beide hielten die No-shared-write-Klausel ein: jeder schrieb ausschließlich seine eine Findings-Datei (`Findings/2026-04-26 - sugw Frontend-Inspektion.md` und `Findings/2026-04-26 - sugw Stakeholder-Feedback.md`). Keine Race Conditions zwischen den beiden, keine Schicht-2-Edits.

Re-Entry-Logik wurde nicht aktiv getestet — beide Subagents schlossen Phase 1 in einer Session ab. Multi-Session-Re-Entry-Pattern ist noch unvalidiert.

### Methodischer Ertrag

V15 ist konsensreif in Mother-METHOD und wurde im Phase-E-Lauf empirisch validiert. Reif für Vollratifizierung in nächster Methodenwelle. Konvention "ein Subagent = eine Output-Datei" hat als pragmatischer Default getragen.

### Mother-METHOD-Konsequenz

V15 in METHOD aufnehmen mit Konkretisierung: "Pro Subagent eine kanonische Output-Datei mit klar definierter Frontmatter (`status`, `author`). Re-Entry über Vault-File-Lesen, nicht über Übergabe-System. No-shared-write strikt: weder Schicht 1 noch Schicht 2, auch nicht Sister-Findings."

## Befund 2 — V20 Stellungnahmen-Schreibhoheit auch für externe Stakeholder-Aussagen tragfähig

### Beobachtung

Claude B's Auftrag explizit: "Stakeholder-Aussagen NIEMALS in fremdem Namen formulieren oder ausschmücken. Bleib so nah am Originalwortlaut wie möglich." Output bestätigt: Claude B hat 37 S-IDs jeweils mit wörtlichem Quellen-Auszug und expliziter Quellen-Referenz dokumentiert; eigene Einschätzungen (Schweregrad, Lösungsrichtung) sind als solche getrennt.

Methodisch wichtig: V20 wurde ursprünglich aus Multi-Claude-Stellungnahmen-Anti-Pattern abgeleitet (Strukturarbeiter hatte Stellungnahme im Inhalts-Namen vorbereitet). Der Phase-E-Lauf zeigt, dass das Prinzip auch auf **externe Quellen-Aussagen** trägt: Stakeholder-Aussagen (Protokoll, Slides) sind Identitätsakte der Stakeholder, nicht der Subagents. Das ist eine semantische Erweiterung der Konvention.

### Methodischer Ertrag

V20 ist konsensreif in Mother und durch Phase E erweitert validiert. Für externe Quellen besonders kritisch — Stakeholder können Diskursverletzungen am leichtesten erkennen (sie wissen, was sie gesagt haben).

### Mother-METHOD-Konsequenz

V20 in METHOD aufnehmen mit Erweiterung: "V20 gilt auch für externe Quellen-Aussagen (Stakeholder, Literatur, Domänen-Experten). Subagents zitieren wörtlich oder nah-paraphrasiert mit Quellen-Referenz; eigene Einschätzungen sind als solche zu markieren."

## Befund 3 — V18 Mother-Fork-Topologie als Branch-Light-Mode tragfähig

### Beobachtung

Die V18-Spezifikation sieht separate Repos für Mother und Fork vor. In diesem Pilot wurde stattdessen ein Branch im Mother-Repo gewählt (`sugw-frontend-rework`). Das war pragmatisch: ein Repo, keine zusätzliche Wartung, leichte Reflux-Pfade durch Branch-Merge.

**Trade-off:** auf einem Branch kann der Methodenmotor (Mother-METHOD-Updates) und die Project-Arbeit nicht sauber getrennt werden — wenn jemand auf `main` weiterarbeitet, muss der Fork-Branch rebasen oder mergen. Bei der single-curator-session war das kein Problem.

Bei mehreren parallelen Forks: Branches im Mother-Repo skalieren ohne Probleme bis ~5 parallele Forks. Darüber hinaus separate Repos sinnvoll.

### Methodischer Ertrag

V18 sollte zwei Modi unterstützen:

- **V18a "Light-Mode" (Branch im Mother-Repo):** für 1-5 Forks, einfache Wartung, schnelle Reflux. Geeignet für Pilot-Anwendungen oder Forks mit überschaubarer Lebensdauer.
- **V18b "Full-Mode" (separate Repos mit `method-version`-Frontmatter):** für viele Forks, lange Lebensdauer, externe Stakeholder. Geeignet für reife Anwendungen.

### Mother-METHOD-Konsequenz

V18 in METHOD mit zwei Modi formalisieren. Light-Mode als Default für erste Forks; Migration zu Full-Mode bei Skalierungs-Druck.

## Befund 4 — Subagent-Briefing-Aufwand ist substantiell, aber nicht Bug

### Beobachtung

Vor dem Subagent-Start wurden ~1000 Zeilen Vorbereitungs-Material erstellt:
- 2 vollständige System-Prompts (Phase 1-5-Coverage, Re-Entry-Logik)
- 1 Pfad-Cheat-Sheet
- 2 Templates (Vorschlag, Verifikation)
- 1 Daten-Architektur-Knowledge-Doc
- 1 Traceability-Matrix-Skeleton
- Roadmap-Erweiterung

Substanz-Verhältnis: 1000 Zeilen Vorbereitung erzeugten 700 Zeilen Subagent-Output (bei guter Qualität). Das wirkt zunächst wie Overhead.

**Aber:** das Vorbereitungs-Material ist nicht nur Subagent-Briefing — es ist gleichzeitig Project-Setup (Roadmap), Knowledge-Asset (Daten-Architektur), Template-Asset (wiederverwendbar in Folge-Forks), Traceability-Infrastruktur. Subagents profitieren als erste Konsumenten; spätere Konsumenten (Phase 4-Implementations-Agents, Phase 5-Verifikations-Master, User-Verifikation) profitieren ebenfalls.

### Methodischer Ertrag

Subagent-Briefing-Größe ist Feature, nicht Bug — sie erzwingt Vault-Arbeit als Setup-Schritt. Ohne den Briefing-Aufwand würden die Subagents weniger konsistent arbeiten und der Vault wäre nicht selbst-erklärend.

### Mother-METHOD-Konsequenz

V15 in METHOD aufnehmen mit Hinweis: "Subagent-Briefing-Material ist gleichzeitig Project-Setup. Erwarteter Vorbereitungs-Aufwand pro Subagent: ~300-500 Zeilen System-Prompt plus Vault-Setup. Akzeptabel als Setup-Cost, weil Material wiederverwendbar in Folge-Phasen."

## Befund 5 — Vollständigkeitsprinzip hält Stakeholder-Material aus Drift

### Beobachtung

Project-Fork-MISSION enthielt explizit Vollständigkeitsprinzip ("Kein Stakeholder-Feedback-Punkt darf still abgewählt werden"). Phase 2 Traceability-Matrix-Befüllung zeigte: alle 37 S-IDs konnten via 11 V-IDs adressiert werden. 4 S-IDs (S30, S33, S36) sind methodisch-dokumentarisch ohne eigene V-ID, aber mit expliziter Markierung — keine S-ID still verloren.

Ohne Vollständigkeitsprinzip wäre die Versuchung gegeben, "kleinere" Stakeholder-Punkte (S2 Wiener Urkundenbuch, S4 Auswertungslücke, S14 Spaltenbreite) im Methodenrauschen zu verlieren.

### Methodischer Ertrag

Vollständigkeitsprinzip ist eine eigenständige Methode-Konvention, die V20 ergänzt: V20 schützt vor Stellungnahmen-Drift, Vollständigkeitsprinzip schützt vor Stakeholder-Drift.

### Mother-METHOD-Konsequenz

Neue V-Konvention proposen — V23 (oder analog) "Vollständigkeitsprinzip für externe Stakeholder-Aussagen": Bei Project-Forks mit externen Stakeholdern muss jeder Stakeholder-Aussagepunkt entweder via V-ID adressiert oder explizit als methodisch-dokumentarisch markiert werden. Kein stilles Abwählen.

## Quality Flags zum Phase-E-Pilot

Gegen MISSION-Erfolgskriterien des Project-Forks:

- **EK-1 Terminologisch konsistent:** ⚠ Risiko (V6+V7 Phase-3-fertig, Phase-4-pendent).
- **EK-2 Datenseitig korrekt:** ✗ Verletzt (IST), Phase 4 muss V1+V2 implementieren.
- **EK-3 Suchbar:** ✗ Verletzt (IST), V3 mit konkretem Test-Anker.
- **EK-4 Navigierbar:** ✗ Verletzt (IST), V4+V5 Phase-3-fertig.
- **EK-5 Interpretierbar:** ⚠ Risiko (V6+V8).
- **Methodische Lessons (für Mother):** ✓ Validiert (5 strukturelle Befunde wie oben).

## Reflux-Aktion

Diese Lessons werden in Mother-Branch `main` als Pull-Request eingebracht, sobald sugw-frontend-rework mindestens Phase 4 abgeschlossen hat (Implementation gibt zusätzliche Validierung).

## Anschluss

- [[MISSION]] — Project-Fork-MISSION.
- [[METHOD]] — Mother-METHOD (V15, V18, V20 betroffen).
- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan.
- [[Project/sugw-Traceability-Matrix]] — Vollständigkeits-Audit.
- [[Sessions/2026-04-26 - sugw Synthesis 1]] — Phase-2-Lage-Notiz.
- [[BACKLOG]] auf Mother — V15, V18, V20 mit Phase-E-Stellungnahmen ergänzen.
