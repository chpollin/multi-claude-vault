---
type: vault-organisation
created: 2026-04-25
tags: [meta, coordination]
status: active
---

# RULES — agents-working-vault

Dieser Vault ist Werkstatt eines Forschungsprojekts: drei parallele Claude-Instanzen entwickeln eine Methode für die kollaborative Vault-Arbeit. Der parallele Lesevault `c:\Users\Chrisi\Documents\obsidian` ist Wissensquelle und bleibt unangetastet — hier wird gearbeitet, dort wird gelesen.

## Identität

Identifikator ist die Rolle, nicht eine Sessionnummer. Drei Rollen, abgestimmt mit der Rollenkarte im Lesevault ([VAULT-OPERATIONS.md#Rollen](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)):

- **Vault-Architekt** — *am* Vault: Form, Struktur, Steuerungsdokumente, Konventionen, Koordinationsdokumente.
- **Operativer Koordinator** — *quer durch* den Vault: Cross-Project-Sicht, ACTIVE-WORK-Status, Synergien, Paper-Writing-Index, Slide Library.
- **Rolle 3** — noch offen (im Lesevault als "[Rolle 3 — bitte selbst eintragen]" markiert, vermutlich inhaltliche/textliche Kuration).

Rollen werden vom User beim Sessionstart zugewiesen. Die kanonische Rollendefinition lebt im Lesevault; im Schreibvault halten wir nur die für die Simulation relevanten Anpassungen in [[METHOD]] (sobald ratifiziert).

## Dokumentstruktur

| Dokument | Zweck | Lifecycle |
|---|---|---|
| [[MISSION]] | Forschungsfrage, Scope, Nicht-Ziele | stabil |
| [[METHOD]] | Ratifizierte Arbeitsmethode | wächst inkrementell |
| [[COORDINATION]] | Sessions, Übergaben, Hinweise | ephemer |
| [[LOG]] | Append-only Audit-Spur (wer, wann, was) | append-only |
| [[BACKLOG]] | Methodenvorschläge, offene Fragen, Experimente | wandernd |

Ordner `EXPERIMENTS/` bei Bedarf für konkrete Erprobungen.

## Rituale

**Sessionstart**

1. Reihenfolge lesen: CLAUDE.md → MISSION.md → METHOD.md → COORDINATION.md (oben + eigene Rollensektion) → LOG.md (letzte 10 Einträge) → BACKLOG.md.
2. Eigenen Eintrag in COORDINATION.md unter `## Aktive Sessions` setzen oder aktualisieren (`last-touch` auf heute).
3. LOG-Eintrag: "Session gestartet, Rolle X, Fokus Y".

**Pre-Edit-Read** (vor jedem Edit an einem geteilten Dokument)

- Wenn letzter Read mehr als ~10 min her: re-read.
- COORDINATION.md auf `Files locked` prüfen; eigene Edits dort kurz markieren.

**Sessionende**

1. Eigenen Eintrag in COORDINATION.md entfernen oder mit `[abgeschlossen]` markieren.
2. LOG-Eintrag mit Kernarbeit der Session.

**Konflikt** — bei kollidierender Edit-Absicht oder inhaltlicher Differenz: nicht überschreiben, nicht überreden. Hinweis in COORDINATION.md unter `## Hinweise`, Eskalation an User.

## Quellenbezug zum Lesevault

Inhalte aus dem Lesevault werden zitiert über Markdown-Links mit absolutem oder relativem Pfad (z.B. `[VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)`). Wikilinks `[[...]]` wirken nur innerhalb dieses Vaults; cross-vault muss als Markdown-Link.

Niemals in den Lesevault zurückschreiben.
