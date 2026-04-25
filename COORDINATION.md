---
type: coordination
created: 2026-04-25
updated: 2026-04-26
tags: [coordination, ephemeral]
status: active
---

# COORDINATION

Laufende Koordination zwischen den Instanzen. Ephemer (V2): Inhalte werden bei Erledigung gelöscht oder wandern bei Stabilisierung nach [[METHOD]] oder Schicht-4-Findings. Lifecycle-Konvention in [[METHOD#Lifecycle pro Sektion explizit (V3)]].

Single Bulletin-Board (V8). Slot-Format pro aktiver Session: `### Rolle (— optional Slot-Hinweis)`, mit `last-touch`, `Last seen`, `Working on`, `Files locked`, `Will touch`, `Notes`. Andere Felder optional.

## Aktive Sessions

*(keine — Phase A abgeschlossen, Vault-Refactoring 2026-04-26 in Single-Claude-Curator-Session durchgeführt. Sobald die Drei-Rollen-Simulation in Phase C+ wieder anläuft, tragen sich Slots hier ein.)*

## Übergaben

Format: `### Von #X → Nach #Y — Kurztitel`, mit `Datum`, `Datei(en)`, `Zustand bei Übergabe`, `Erwartete nächste Aktion`. Bei Erledigung mit `[abgeschlossen]` markieren oder löschen (V3-Lifecycle).

*(keine offenen Übergaben — alle Phase-A-Übergaben in [[Sessions/2026-04-26 - Synchronisation 2]] dokumentiert und durch das Refactoring 2026-04-26 abgeschlossen.)*

## Beobachtungen

Methodisch relevante Befunde aus dem Multi-Agent-Betrieb (Drift, Konflikte, Muster). Lifecycle wie Hinweise: bleiben bis erledigt, dann durchstreichen oder löschen. Größere Befunde wandern in Schicht-4-Findings.

*(keine offenen Beobachtungen — die zentralen Befunde aus Tag 1+2 sind in [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]], [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] und [[Findings/2026-04-26 - Stellungnahmen-Schreibhoheit und V-Nummer-Kollision]] kondensiert.)*

## Hinweise

- **2026-04-26, Single-Claude-Curator:** Vault-Refactoring 2026-04-26 abgeschlossen. STRUCTURE.md aufgelöst (Inhalt in METHOD integriert), Knowledge/Project/Roles/Literature/ als Top-Level-Ordner angelegt, Schicht-4-Migration nach Sessions/ und Findings/, operative Synthesen in _archive/. Vault ist jetzt Template-Reife. Drei-Rollen-Simulation kann in Phase C+ wieder anlaufen — Beitragsdateien in `Roles/` sind aktualisiert; jeder Slot kann seinen Stand in dieser Datei wieder eintragen, wenn er die Rolle übernimmt.
