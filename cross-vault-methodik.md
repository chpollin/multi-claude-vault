---
type: methode-konvention
created: 2026-04-25
updated: 2026-04-25
version: 0.2
author: Claude #3 (Inhalt)
status: draft
tags: [cross-vault, methode]
---

# Cross-Vault-Methodik

Konkrete Disziplin im Verhältnis Lesevault [c:/Users/Chrisi/Documents/obsidian](c:/Users/Chrisi/Documents/obsidian) und Schreibvault `agents-working-vault`. Die Asymmetrie ist konstitutiv: Lesevault ist Quelle und bleibt read-only, Schreibvault ist Werkstatt und ist read-write.

Klassenzuordnung nach [[STRUCTURE]]: Methoden-Draft ohne eigene V7-Klasse. Lebt provisorisch im Root, bei Ratifizierung Migration nach [[METHOD]] (siehe V7-Stellungnahme im [[BACKLOG]]).

## Asymmetrie-Prinzip

Der Lesevault wird im Forschungsprojekt als Untersuchungsobjekt und Wissensquelle behandelt. Edits dort verändern das, was wir untersuchen — methodisch unsauber, weil Beobachtung und Eingriff vermischt würden. Daher: Lesevault read-only.

Ausnahme: wenn der User explizit den Auftrag gibt, im Lesevault zu editieren (z.B. Methodenelemente aus dem Schreibvault zurück nach VAULT-OPERATIONS migrieren). Dann ist es eine bewusste, dokumentierte Anwendung — nicht Beifang der Forschung. Ein solcher Auftrag wandert über Schicht 6 (Konversations-Sync, siehe [[sync-stack-patterns]]) als Hinweis "alle" in [[COORDINATION]].

## Zitierregeln

**Within-Vault (intra Schreibvault):** Wikilinks `[[Dokument]]` oder `[[Dokument#Sektion]]`. Obsidian-Standard.

**Cross-Vault (Schreibvault → Lesevault):** Markdown-Link mit absolutem oder relativem Pfad. Beispiel:

```markdown
[VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)
```

Wikilinks funktionieren cross-vault nicht — der Verweis bleibt unaufgelöst. Bei Sektions-Referenz: Anchor-Suffix `#Sektion` möglich, aber nicht in jedem Renderer zuverlässig.

**Cross-Vault (Lesevault → Schreibvault):** nicht vorgesehen. Lesevault soll nichts vom Schreibvault wissen müssen, sonst koppelt sich das Untersuchungsobjekt an die Untersuchung.

## Reflux-Verbote

- **Nicht editieren:** jeder Inhalt im Lesevault ohne expliziten User-Auftrag.
- **Nicht kopieren:** Lesevault-Inhalt im Schreibvault verdoppeln. Stattdessen referenzieren.
- **Nicht erfinden:** Inhalte im Schreibvault produzieren und so tun, als kämen sie aus dem Lesevault.
- **Nicht implizit übertragen:** stillschweigend Lesevault-Konventionen im Schreibvault anwenden, ohne sie hier zu nennen. [[CLAUDE]] des Schreibvaults ist eigenständig — die Lesevault-CLAUDE.md gilt nicht automatisch hier.

## Drift-Vermeidung

Der Lesevault entwickelt sich auch ohne uns weiter. Während dieser Forschung wurde z.B. VAULT-OPERATIONS.md mehrfach refactored. Konsequenz für die Methode:

- Bei jeder substantiellen Lesevault-Referenz: Datum des letzten Reads vermerken, wenn die Aussage von einer konkreten Inhaltsversion abhängt.
- Bei längerer Pause: vor erneuter Verwendung re-read.
- Bei strukturellem Refactoring im Lesevault: Hinweis in [[COORDINATION]] unter `## Hinweise`, sodass andere Instanzen ihre Annahmen aktualisieren.

## Migrationspfad (Methode → Lesevault)

Wenn ein Methodenelement im Schreibvault ratifiziert ist und in den Lesevault wandern soll (z.B. die Multi-Claude-Arbeitsmethode in VAULT-OPERATIONS):

1. User-Auftrag explizit einholen.
2. Architekt-Rolle ([[Claude-2]]) übernimmt Migration.
3. Schreibvault-Quelle als Footnote oder Provenance-Verweis im Lesevault-Eintrag belassen, damit nachvollziehbar bleibt, woher das Element stammt.
4. Schreibvault-Eintrag mit `migrated-to: [Lesevault-Pfad]` markieren, nicht löschen — das Original ist weiter Audit-Spur.

## Falldaten und Beobachtungen

Beobachtungen aus dem Lesevault, die Falldaten für unsere Methode liefern (z.B. wie ein Refactoring im Lesevault aussieht, wie eine andere Instanz dort agiert), werden im Schreibvault unter `falldaten/` (oder per V7 `Findings/`) dokumentiert mit Lesevault-Referenz, *nicht* durch Lesevault-Annotation. Beispiel: [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]].

## Anschluss

- [[sync-stack-patterns]] Schicht 7 (Cross-Vault-Sync) — formal verankert.
- [[CLAUDE]] Sektion "Quellenbezug zum Lesevault" — provisorisch verankert, wird bei Ratifizierung dieses Dokuments verschlankt und auf hier verwiesen.
- [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] — Lesevault-Refactoring während des Bootstraps als Falldaten-Beispiel.

## Offene Fragen

- Brauchen wir eine spezielle Konvention für temporäre Lesevault-Edits durch externe Claude-Instanzen, die nicht zur Forschung gehören (z.B. die parallel im Lesevault laufenden Repo-Instanzen)?
- Wie behandeln wir die Forschungsleitstelle-Sessions im Lesevault — Vorbild und Benchmark für unsere Lage-Notizen, oder eigenständiges Format?
- Wie kommunizieren wir Lesevault-Refactorings, die *nicht* von uns ausgelöst sind, aber unsere Referenzen invalidieren?
