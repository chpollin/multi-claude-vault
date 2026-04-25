---
type: vault-resource
created: 2026-04-26
tags: [moc, knowledge, hub]
status: active
---

# Knowledge MOC

Hub für die eigene Wissensbasis des Projekts. Knowledge/ versammelt zwei Klassen:

1. **Methode-Drafts** — eigene methodische Substanz, die im Multi-Claude-Setup entwickelt wurde (Sync-Stack, Cross-Vault-Methodik, Prompt-Engineering-Patterns).
2. **Forschungsfeld-Synthesen** — eigene Synthesen über externe Forschungsfelder, die das theoretische Fundament der Methode tragen (Theoretical Framework als integrativer MOC).

Verhältnis zu parallelen Klassen:

- **[[Literature/]]** — annotated bibliography pro Werk. Knowledge zitiert aus Literature.
- **`Concepts/`** (Schicht 5, V19 pendent) — Lesevault-Extrakte mit Reflux-Verboten. Concepts sind atomare Lesevault-Konzepte; Knowledge sind eigene Synthesen.
- **`Project/`** (Schicht 1) — Promptotyping K/P/A-Selbstdokumentation des Projekts. Project beschreibt das Projekt, Knowledge beschreibt die Wissensgebiete, an die das Projekt anschließt.

## Inhalt

### Methode-Drafts

| Dokument | Status | Inhalt |
|---|---|---|
| [[Knowledge/Sync-Stack-Patterns|Sync-Stack-Patterns]] | v0.3 | Sieben+eine Schichten Inter-Instanz-Kommunikation, Skalierungs-Notizen pro Schicht, Subagent-Sync (V15) |
| [[Knowledge/Cross-Vault-Methodik|Cross-Vault-Methodik]] | v0.3 | Asymmetrie-Prinzip Lesevault ↔ Schreibvault, Reflux-Verbote, V18-Multi-Mode-Erweiterung pendent |
| [[Knowledge/Prompt-Engineering-Patterns|Prompt-Engineering-Patterns]] | v0.2 | Acht Patterns für typische Kommunikationssituationen plus Antipatterns |

### Forschungsfeld-Synthesen

| Dokument | Status | Inhalt |
|---|---|---|
| [[Knowledge/Multi-Claude Theoretical Framework|Multi-Claude Theoretical Framework]] | v0.1 outline | Sieben Forschungsfelder als integrierte Synthese; Schlüssel-Referenzen pro Feld; Synthese-Argumentation für Phase D Paper |

Geplante atomare Knowledge-Notes (sukzessive aus dem Theoretical Framework herausgelöst, sobald inhaltlich tragfähig):

- `Knowledge/CSCW Foundations.md` — Awareness, Coordination, Articulation Work, Common Information Spaces.
- `Knowledge/LLM Multi-Agent Frameworks.md` — AutoGen, MetaGPT, ChatDev, Generative Agents.
- `Knowledge/Reflexive Method Development.md` — DSR, Action Research, Schön.
- `Knowledge/Eventually Consistent Coordination.md` — Lamport, OT, CRDTs für File-basierte Multi-Agent-Vault.
- `Knowledge/Mixed-Initiative AI-Human Collaboration.md` — Horvitz, User als Bus, Eskalations-Schwellen.
- `Knowledge/PKM Vault Patterns.md` — Zettelkasten, atomic notes, Markdown als menschlich-lesbares Substrat.
- `Knowledge/Prompt Engineering as Method.md` — Promptotyping als Meta-Methode, Self-Refine, Reflexion.

### Vault-Resources

| Dokument | Inhalt |
|---|---|
| [[Knowledge/Wissensbasis Lesevault|Wissensbasis Lesevault]] | Schnellreferenz auf den parallelen Lesevault, Cross-Vault-Pfade, Schlüssel-MOCs des Lesevaults |

## Konvention

Frontmatter pro Knowledge-Dokument:

```yaml
---
type: knowledge | methode-pattern | vault-resource
created: YYYY-MM-DD
updated: YYYY-MM-DD
version: x.y  # bei methode-pattern
tags: [2-4 lowercase-hyphenated]
status: idea | draft | active | reviewed | complete
---
```

Dokumentstruktur (analog Lesevault):

1. `# Titel` (matches filename)
2. `## Summary` (max 3 Absätze)
3. `## Key Points` oder `## Core Concepts` oder thematische Hauptsektionen
4. `## Synthesis` (Verknüpfungen, nicht nur Zusammenfassung)
5. `## Sources` (Literature-Refs)
6. `## Related` oder `## Anschluss` (Wikilinks zu anderen Vault-Dokumenten)

## Anschluss

- [[METHOD]] — ratifizierte Methode (Schicht 1).
- [[MISSION]] — Forschungsfrage, Scope.
- [[Project/INDEX]] — Promptotyping K/P/A-Selbstdokumentation.
- [[Literature/]] — annotated bibliography.
- [[BACKLOG]] — Methodendiskurs.
