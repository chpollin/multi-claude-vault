# multi-claude-vault

Coordination method and Obsidian-vault template for parallel Claude Code agents working in three roles.

`multi-claude-vault` ist Methode und Template für mehrere parallel laufende Claude-Code-Instanzen, die über einen gemeinsam genutzten Obsidian-Vault koordinieren. Das Setup verteilt drei Rollen — Koordination, Struktur, Inhalt — auf drei (oder mehr) Top-Level-Agenten, die sich asynchron über geteilte Dateien synchronisieren: ein Bulletin-Board für aktive Sessions, ein append-only Log als Audit-Spur, ein Backlog für Methodenvorschläge, periodische Lage-Notizen für Synthese und Quality-Flags. Die Methode entwickelt sich selbstreferentiell — die drei Agenten produzieren METHOD.md, indem sie METHOD.md anwenden, und die Falldaten ihrer eigenen Konflikte sind der Untersuchungsgegenstand. Das Repo ist als Template gedacht: kloneable für projektspezifische oder projektübergreifende Multi-Agent-Arbeit.

## Status (2026-04-26, post-refactoring)

Phase A (Methoden-Reife) und Phase B (Strukturkonsolidierung) abgeschlossen. METHOD trägt 5 ratifizierte Items (V1, V2, V3, V6, V8) plus die Vier+1-Schichten-Architektur als integrierte Sektion. 12 weitere V-Items konsensreif für die nächste Welle. Vault ist auf Template-Reife refaktoriert.

## Vault-Topologie

```
multi-claude-vault/
│
├── README.md                    GitHub-Onboarding (du bist hier)
├── HOME.md                      Obsidian-Einstieg / MOC
├── LICENSE                      MIT
│
├── CLAUDE.md                    Schicht 1: Identität, Rituale, Aktueller Stand
├── MISSION.md                   Schicht 1: Forschungsfrage, Scope, Erfolgskriterien
├── METHOD.md                    Schicht 1: ratifizierte Methode + Vier+1-Schichten-Architektur
│
├── COORDINATION.md              Schicht 2: Bulletin-Board (ephemer)
├── LOG.md                       Schicht 2: append-only Audit-Spur
├── BACKLOG.md                   Schicht 2: Methodenvorschläge V1–V22, offene Fragen F1–F13
│
├── Project/                     Schicht 1+2: Promptotyping K/P/A-Selbstdokumentation
│   ├── INDEX.md                 Hub, K/P/A-Taxonomie
│   ├── DATA.md                  Datengrundlagen (Knowledge-Doc)
│   ├── REQUIREMENTS.md          User Stories (Knowledge-Doc)
│   ├── DESIGN.md                Designentscheidungen (Knowledge-/Action-Doc)
│   └── JOURNAL.md               Arbeitstagebuch (Process-Doc, Schicht 2)
│
├── Roles/                       Schicht 3: Beiträge der Instanzen
│   ├── Claude-1.md              Koordinator
│   ├── Claude-2.md              Strukturarbeiter
│   ├── Claude-3.md              Inhalt
│   └── Beobachtung Claude-1.md  Koordinator-Methodendokument (Snapshots, Komm-Karte)
│
├── Knowledge/                   Eigene Wissenssynthesen + Methode-Drafts
│   ├── Knowledge MOC.md
│   ├── Sync-Stack-Patterns.md
│   ├── Cross-Vault-Methodik.md
│   ├── Prompt-Engineering-Patterns.md
│   ├── Multi-Claude Theoretical Framework.md
│   └── Wissensbasis Lesevault.md
│
├── Literature/                  Annotated bibliography (Author Year - Title.md)
│   └── README.md                Konvention + Top-15-Welle
│
├── Concepts/                    Schicht 5 (V19, pendent): Lesevault-Extrakte
│
├── Sessions/                    Schicht 4: periodische Lage-Synthesen
├── Findings/                    Schicht 4: methodenrelevante Befunde
├── Experiments/                 Schicht 4: gezielte Methodenerprobungen
│
├── Templates/                   Vorlagen für Schicht-3- und Schicht-4-Dokumente
├── instances/                   V15: Subagent-Namespaces pro Top-Level-Slot
└── _archive/                    historische Spuren
```

## Schichten-Logik (Kurzfassung)

- **Schicht 1 — Stabile Anker:** MISSION, CLAUDE, METHOD plus Project/INDEX/DATA/REQUIREMENTS/DESIGN. Änderung nur durch Konsens.
- **Schicht 2 — Lebende Koordination:** COORDINATION (ephemer), LOG (append-only), BACKLOG (wandernd), Project/JOURNAL (wandernd append).
- **Schicht 3 — Beiträge der Instanzen:** `Roles/Claude-N.md` pro Slot mit Schreibhoheit beim Slot, plus laufende instanzgebundene Methodendokumente.
- **Schicht 4 — Forschungsmaterial:** `Sessions/`, `Findings/`, `Experiments/` mit Datums-Naming (V14b).
- **Schicht 5 — Concepts (V19, Konsens pendent):** `Concepts/` für vault-übergreifendes Source-Material aus dem Lesevault.

Volle Beschreibung in [METHOD.md](METHOD.md).

## Onboarding für neue Klone

### Drei Anker-Dokumente für die Orientierung

- [MISSION.md](MISSION.md) — Forschungsfrage, Scope, Erfolgskriterien.
- [CLAUDE.md](CLAUDE.md) — Identität, Rollen, Sessionstart-Ritual, Pre-Edit-Read, Konfliktlogik, Aktueller Stand.
- [METHOD.md](METHOD.md) — ratifizierte Methode mit Vier+1-Schichten-Architektur und Frontmatter-Vokabular.

### Operative Lage

- [COORDINATION.md](COORDINATION.md) — Bulletin-Board mit aktiven Sessions, Übergaben, Beobachtungen, Hinweisen.
- [LOG.md](LOG.md) — Append-only Audit-Spur.
- [BACKLOG.md](BACKLOG.md) — Methodenvorschläge V1–V22 mit Stellungnahmen, Status-Tabelle, offene Fragen F1–F13.

### Sessionstart-Anleitung für eine fremde Klon-Instanz

1. **Sessionstart-Ritual** nach [CLAUDE#Rituale](CLAUDE.md): CLAUDE → MISSION → METHOD → COORDINATION → LOG → BACKLOG plus die Beitragsdatei der eigenen Rolle in `Roles/`.
2. **Rollen-Zuweisung erfragen** (User-Statement primär) oder den eigenen Slot in COORDINATION fortsetzen. Drei Rollen: Koordinator, Strukturarbeiter, Inhalt.
3. **Eigenen Slot setzen** in COORDINATION#Aktive Sessions mit `last-touch`, `Working on`, `Files locked`, `Will touch`, `Notes`.
4. **LOG-Eintrag** "Session gestartet, Rolle X, Fokus Y".
5. **Pre-Edit-Read-Disziplin (V6)** anwenden — vor jedem Edit re-read, bei "modified since read"-Konflikt nicht überschreiben.
6. **Stellungnahmen-Schreibhoheit (V20)** beachten — Stellungnahmen zu BACKLOG-Items sind Schreibhoheit der jeweiligen Rolle, nicht antizipierbar.

### Templates

Vorlagen in [Templates/](Templates/): `Template-Session.md`, `Template-Finding.md`, `Template-Experiment.md`, `Template-Claude-N.md`. Beim Anlegen einer neuen Datei der jeweiligen Klasse: Template kopieren und Frontmatter auf reale Werte umstellen.

## Lizenz und Kontribution

MIT-Lizenz, siehe [LICENSE](LICENSE). Pull Requests willkommen, sofern sie die Methode oder das Template strukturell verbessern. Keine Pushes auf Remote ohne explizite User-Freigabe — git-Safety-Protokoll gilt für alle Instanzen.
