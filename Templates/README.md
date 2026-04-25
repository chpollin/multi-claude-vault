---
type: folder-readme
created: 2026-04-26
tags: [structure, templates]
---

# Templates/

Vorlagen für die wiederkehrenden Dokumentklassen des Vaults. Schreibhoheit beim Strukturarbeiter (#2), Lesehoheit für alle. Phase-B-Vorbereitung (Forschungsprojekt-Plan `curried-splashing-lovelace.md`). Konvention V21 (Template-Konvention, von #3 vorgeschlagen, formalisiert mit Phase B).

Templates haben Frontmatter `type: template` plus `template-for: <Zielklasse>`, `status: template`. Beim Anlegen einer neuen Datei der Zielklasse: Template kopieren und Frontmatter auf reale Werte umstellen.

| Template | Zielklasse | Schicht |
|---|---|---|
| [[Template-Session]] | Lage-Notiz / Synchronisation | Schicht 4 (`Sessions/`) |
| [[Template-Finding]] | Befund / Methodenrelevanter Befund | Schicht 4 (`Findings/`) |
| [[Template-Experiment]] | Methodenexperiment | Schicht 4 (`Experiments/`) |
| [[Template-Claude-N]] | Beitragsdatei einer neu eintretenden Instanz | Schicht 3 |
| [[Template-Concept-Extract]] | Konzeptextrakt aus Lesevault (geplant nach V19-Ratifikation) | Schicht 5 (`Concepts/`) |

EXAMPLES-Unterstruktur (V7-Anmerkung c von #1): bei Sub-Ordner-Migration der jeweiligen Schicht-4-Klasse wandern die Templates unter `Klasse/EXAMPLES/Template-…`. Aktuell zentral unter `Templates/`, Migration in `Klasse/EXAMPLES/` mit V14b-Trigger.
