# multi-claude-vault

Coordination method and Obsidian-vault template for parallel Claude Code agents working in three roles.

`multi-claude-vault` ist Methode und Template für mehrere parallel laufende Claude-Code-Instanzen, die über einen gemeinsam genutzten Obsidian-Vault koordinieren. Das Setup verteilt drei Rollen — Koordination, Struktur, Inhalt — auf drei (oder mehr) Top-Level-Agenten, die sich asynchron über geteilte Dateien synchronisieren: ein Bulletin-Board für aktive Sessions, ein append-only Log als Audit-Spur, ein Backlog für Methodenvorschläge, periodische Lage-Notizen für Synthese und Quality-Flags. Die Methode entwickelt sich selbstreferentiell — die drei Agenten produzieren METHOD.md, indem sie METHOD.md anwenden, und die Falldaten ihrer eigenen Konflikte sind der Untersuchungsgegenstand. Das Repo ist als Template gedacht: kloneable für projektspezifische oder projektübergreifende Multi-Agent-Arbeit.

## Status

Initial commit — Bootstrap und erste Iteration. Die Methode ist im Wachstum, METHOD.md noch leer (wartet auf erste Ratifikationen aus BACKLOG). Diese README ist ein Stub, der bei der nächsten Strukturarbeit ausgebaut wird (Onboarding-Flow, Beispiele, Tooling-Hinweise).

## Einstieg

Drei Anker-Dokumente für die Orientierung:

- [MISSION.md](MISSION.md) — Forschungsfrage, Scope, Erfolgskriterien.
- [CLAUDE.md](CLAUDE.md) — Identität, Rollen, Sessionstart-Ritual, Pre-Edit-Read, Konfliktlogik.
- [STRUCTURE.md](STRUCTURE.md) — Vier-Schichten-Vorschlag für die Vault-Organisation.

Aktuelle operative Lage:

- [COORDINATION.md](COORDINATION.md) — Bulletin-Board mit aktiven Sessions, Übergaben, Hinweisen.
- [LOG.md](LOG.md) — Append-only Audit-Spur.
- [BACKLOG.md](BACKLOG.md) — Methodenvorschläge V1–V8 mit Stellungnahmen, offene Fragen F1–F5.

Synthese:

- [Session 2026-04-26 - Synchronisation 1.md](Session%202026-04-26%20-%20Synchronisation%201.md) — erste Lage-Notiz nach Eintreten aller drei Rollen.

## Lizenz und Kontribution

Noch offen — siehe BACKLOG.
