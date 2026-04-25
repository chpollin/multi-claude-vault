---
type: mission
created: 2026-04-26
tags: [meta, mission, project-fork, sugw]
status: active
fork-of: "main (Mother-Vault MISSION = Methodenentwicklung)"
method-version: "main@e355bac"
---

# MISSION — Project-Fork sugw-frontend-rework

Project-Fork des [[multi-claude-vault]] (Mother). Erste Phase-E-Anwendung der Methode an einem realen Projekt.

## Projektkontext

**Projekt:** Stadt und Gemeinschaft Wien (sugw) — Datenbank zu mittelalterlichen Wiener Rechtsgeschäften, freigegebener Zeitraum 1177–1412 (QGW II/1 und II/2 bis 1414).

**Repos:**
- Pipeline: `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/` (TEI-Quellen, Build, Templates)
- Edition: `c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions_edition/` (Build-Output, GitHub Pages)

**Stakeholder-Feedback:** Meeting 23.4.2026 (Gonaus, Handl, Lutter, Siegl, Steinböck) — Protokoll als Word und PowerPoint in `c:/Users/Chrisi/Downloads/`. Zentrale Befunde: Terminologische Überarbeitung, Suchfunktion-Defizit (2/3–3/4 der Hits fehlen), Personen-Profile fehlen, Filterung auf geprüfte Korpora (QGW + StB) nicht implementiert, Q-Kategorie zu intern, Verb-Browser zu kleinteilig, Korpuskontrolle ausstehend.

## Forschungsfrage des Forks

Wie verbessern wir das sugw-Frontend so, dass es

1. **terminologisch konsistent** ist (Glossar, Kategorienerklärungen, "Tod" → "als verstorben genannt", "Factoids" → angemessener Begriff)
2. **datenseitig korrekt** ist (nur geprüfte Korpora QGW + StB, keine ungeprüften Daten in Indizes/Zählungen)
3. **suchbar** ist (Suchleiste findet Personen zuverlässig, alle Hits, Umlaute)
4. **navigierbar** ist (Personen-Profile parallel zu Regesten, bidirektionale Verlinkung Person ↔ Urkunde)
5. **interpretierbar** ist (% statt absolute Quellenmenge pro Dekade, Erläuterungen pro Tabellen-Spalte)

## Scope

**In-Scope:**
- Frontend-Refactoring der Edition (HTML, JS, JSON-Daten-Pipeline)
- Korpuskontrolle (Klassifikation der vorhandenen Korpora nach Approval-Status)
- Filter-Mechanik in Pipeline und Frontend
- Glossar + Kategorien-Erklärungen
- Personen-Profile parallel zu Regesten
- Verb-Browser-Aggregation

**Out-of-Scope (Phase-E-Constraint):**
- Inhaltliche Korrektur einzelner TEI-Quellen (das ist Forschungsarbeit der Projektpartner, nicht Frontend)
- Korbinian-Daten außerhalb QGW/StB (gesperrt bis Überprüfung)
- GitHub-Pages-Deployment-Setup (vorhanden, nur Inhalt fließt)

## Erfolgskriterien

- Alle Stakeholder-Feedback-Punkte aus dem Protokoll 23.4.2026 sind in Findings dokumentiert mit konkreter Lösungsrichtung.
- Korpuskontrolle abgeschlossen — Approval-Status pro Korpus klar markiert.
- Mindestens drei zentrale Issues (Suchfunktion, Personen-Profile, Filterung auf geprüfte Korpora) sind implementierungsbereit spezifiziert.
- Glossar-Entwurf vorliegt mit den im Feedback genannten Begriffen.
- Methodische Reflux-Items für die Mother (Lessons aus Phase E) sind dokumentiert.

## Anschluss zur Mother (multi-claude-vault main)

- METHOD shared aus Mother (siehe `method-version: main@e355bac` im Frontmatter).
- MISSION per-Instance — diese Datei.
- Schicht-3-Beitragsdateien (`Roles/Claude-N.md`) frisch pro Fork: bei Sessionstart aktualisieren mit `fork: sugw-frontend-rework` im Frontmatter.
- Findings-Reflux: kritische methodische Befunde aus diesem Fork wandern als markierte Findings (`reflux-target: main@multi-claude-vault`) zurück in die Mother. Nicht-methodische Frontend-Issues bleiben hier.
- METHOD-Änderungen kommen ausschließlich aus Mother — Forks dürfen METHOD nicht editieren (V18-Klausel).

## Forschungsleitstelle-Anschluss

Optional spätere Phase: Ergebnisse als Validierungsmaterial für die Forschungsleitstelle-Spezifikation (siehe Mother [[MISSION#Anschluss an die Forschungsleitstelle]]).
