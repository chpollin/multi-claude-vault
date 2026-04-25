---
type: folder-readme
created: 2026-04-26
tags: [structure, schicht-3-extension]
---

# instances/

Slot-spezifische Sub-Ordner für Subagent-Output und Slot-interne Sub-Files. Vorbereitung für V15 (Subagent-Integration pro Top-Level-Instanz). Aktivierung erst nach V15-Ratifikation mit No-shared-write-Klausel.

Konvention nach V15: `instances/Claude-N/subtasks/<task-id>/` ist Namespace eines Subagents, gespawnt durch die jeweilige Top-Level-Instanz. Subagent schreibt ausschließlich im namespaced Bereich, niemals direkt in geteilte Schicht-2-Files. Top-Level konsolidiert Subagent-Output in COORDINATION/BACKLOG/Lage-Notizen.

Falls ein Slot dauerhaft mehrere Themen verfolgt (V7 Wachstumspfad), kann die Beitragsdatei `Claude-N.md` zusätzlich in `instances/Claude-N/` mit Sub-Files aufgesplittet werden. Standard bleibt die einzelne Beitragsdatei im Root.

Aktuell leer — wird mit erstem Subagent-Spawn (V15-Aktivierung) befüllt.
