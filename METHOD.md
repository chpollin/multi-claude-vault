---
type: method
created: 2026-04-25
updated: 2026-04-26
tags: [meta, method]
status: active
---

# METHOD

Ratifizierte Methode der Multi-Claude-Vault-Kollaboration. Wächst inkrementell: Vorschläge werden in [[BACKLOG]] gesammelt, dort diskutiert, bei Konsens nach hierhin migriert. V-Nummern bleiben erhalten, damit Rückverweise auf BACKLOG-Diskussion und Stellungnahmen stabil bleiben.

Ein Item gilt als ratifiziert, wenn alle drei aktiven Rollen Zustimmung signalisiert haben (im BACKLOG-Item unter `Stellungnahmen`) und der Vorschlag unter Realbedingungen mindestens eine Iteration getragen hat. Vorbereitete oder antizipierte Stellungnahmen in fremdem Namen sind als solche zu markieren und brauchen Selbstbestätigung der adressierten Rolle, bevor sie als Konsens-Beleg gelten (V20). Bis dahin trägt das Item den Status `ratifiziert provisorisch`.

## Identität und Rollen (V1)

Sessions-Header verwenden die Rolle als Identifikator: `### Strukturarbeiter`, `### Koordinator`, `### Inhalt`. Bei mehreren Instanzen derselben Rolle wird ein Suffix mit Fokus angehängt (`### Inhalt (Methode)`, `### Inhalt (Falldaten)`). Suffix-Vokabular aus dem stabilen Set: `Methode`, `Falldaten`, `Domäne`, `Querschnitt`, `Validierung`, plus für V18 Fork-Suffixe (`Inhalt (Klawiter)`, `Inhalt (Mother-Methode)`).

Rollennamen sind über Sessionwechsel hinweg stabil; Sessionnummern bleiben als Rückenstütze in der Praxis erhalten, sind aber nicht der Identifikator. Begründung: überlebt Sessionwechsel, Crashes, User-Reassignments und parallelen Mehrfach-Sessionstart.

- **Ratifiziert** 2026-04-26. Stellungnahmen: alle drei Rollen positiv. Live validiert: zwei User-Reassignments am 2026-04-25 ohne Identitätsverlust.
- Voraussetzung für V9 (Beitragsdatei-Konvention) und V10 (Reassignment-Refactor-Trigger).

## Statisch und ephemer trennen (V2)

Persistente Inhalte (Rollen, Schnittstellen, ratifizierte Methode) leben in [[CLAUDE]] und [[METHOD]]. [[COORDINATION]] bleibt strikt ephemer — Slot-Einträge, Übergaben, Hinweise und Beobachtungen verschwinden bei Erledigung oder wandern bei Stabilisierung in METHOD oder Schicht-4-Findings.

- **Ratifiziert** 2026-04-26. Stellungnahmen: alle drei Rollen positiv.
- Live validiert: V8-Konsolidierung zeigt das Prinzip exemplarisch — Bulletin-Felder ephemer in COORDINATION, Konvention stabil in CLAUDE/METHOD.
- Verfeinerung auf Datei-Ebene durch V7 (Vier+1-Schichten-Architektur, siehe unten).

## Lifecycle pro Sektion explizit (V3)

Jede Sektion in den geteilten Steuerungsdokumenten trägt einen klaren Lebenszyklus:

- **MISSION / METHOD / CLAUDE:** stabil bzw. wachsend, Änderung nur durch Konsens.
- **BACKLOG:** lebendig — ratifizierte Items wandern nach METHOD (Status `ratifiziert` plus Rückverweis), abgelehnte bleiben mit Begründung als Lerndokumentation.
- **COORDINATION/Aktive Sessions:** ephemer — Eintrag bei Sessionende entfernen oder mit `[abgeschlossen]` markieren, `last-touch` als Stale-Marker (Cleanup nach 7d Inaktivität).
- **COORDINATION/Hinweise** und **/Beobachtungen:** bleiben bis erledigt, dann durchstreichen oder löschen. Größere Befunde wandern in Schicht-4-Findings.
- **COORDINATION/Übergaben:** bleibt bis Übergabe abgeschlossen, dann mit `[abgeschlossen]` markieren oder löschen.
- **LOG:** append-only, nie editieren, nur anhängen.
- **BACKLOG-Items mit Status `entfällt` oder `erledigt`** werden nicht gelöscht, sondern mit Begründung markiert.

- **Ratifiziert** 2026-04-26. Stellungnahmen: alle drei Rollen positiv.

## Pre-Edit-Read-Disziplin (V6)

Vor jedem Edit an einem geteilten Dokument re-read durchführen, wenn der letzte Read mehr als ~10 Minuten zurückliegt. Bei einem "modified since read"-Konflikt nicht überschreiben, sondern re-read und prüfen, ob die fremde Änderung den eigenen Edit obsolet macht oder Anpassung erfordert. Bei nicht trivialer Kollision oder methodischer Differenz: Hinweis in [[COORDINATION#Hinweise]] mit Adressat-Markierung oder Eskalation an User.

Im Skalierungsprofil von drei Top-Level-Instanzen reicht das Tooling-seitige Sicherheitsnetz "modified since read" als reaktiver Schutz aus. Eine zusätzliche aktive `Files locked`-Disziplin ist nicht erforderlich. Für mehrstufige strukturelle Eingriffe ist `Files locked` als opt-in vorgesehen (V13).

- **Ratifiziert** 2026-04-26. Stellungnahmen: alle drei Rollen positiv.
- Live validiert: zwölf Race Conditions an zwei Tagen reaktiv abgefangen, kein blinder Überschreibvorgang dokumentiert.
- Querbezug: V13 (Files locked als opt-in), V14 (Edit-Granularität), V16 (Skalierungs-Profil).

## Konsolidiertes Bulletin-Board (V8)

Es gibt genau ein Koordinations-Bulletin-Board ([[COORDINATION]]). Doppelt geführte Koordinationsdokumente werden konsolidiert: Bulletin-Felder (`Last seen`, `Will touch`, `Working on`, `Files locked`, `Notes` pro Slot) und globale Sektionen (`## Beobachtungen`) wandern in das kanonische Dokument; das parallele wird gelöscht. Cross-Vault-Asymmetrie und andere stabile Rahmen-Information leben in CLAUDE (Schicht 1), nicht in COORDINATION (Schicht 2).

**Slot-Format** pro aktiver Session: `### Rolle (— optional Slot-Hinweis)`, mit `last-touch`, `Last seen`, `Working on`, `Files locked`, `Will touch`, `Notes`. Andere Slot-Felder optional.

- **Ratifiziert** 2026-04-26. Stellungnahmen: alle drei Rollen positiv.
- Live validiert: 2026-04-25 implementiert; seither in jeder Session aktiv genutzt.

## Vier+1-Schichten-Architektur (V7 + V14b + V19)

Der Vault ist in fünf klar unterschiedene Schichten organisiert. Schicht 5 (Concepts) ist Konsens pendent.

### Schicht 1 — Stabile Anker

Strategische Basis. Änderung nur durch Konsens aller drei Instanzen.

| Datei | Zweck | Lifecycle |
|---|---|---|
| [[MISSION]] | Forschungsfrage, Scope, Erfolgskriterien | stabil |
| [[CLAUDE]] | Identität, Dokumentstruktur, Rituale, Aktueller Stand | stabil mit dynamischem Stand-Block |
| [[METHOD]] (dieses Dokument) | Ratifizierte Methode | wachsend (durch Ratifizierung aus BACKLOG) |
| `Project/INDEX|DATA|REQUIREMENTS|DESIGN` | Promptotyping K/P/A-Selbstdokumentation des Projekts | stabil |

### Schicht 2 — Lebende Koordination

Hochfrequente Schreibzone. Mehrere Instanzen lesen und schreiben pro Session.

| Datei | Zweck | Lifecycle |
|---|---|---|
| [[COORDINATION]] | Bulletin-Board: Aktive Sessions, Übergaben, Beobachtungen, Hinweise | ephemer |
| [[LOG]] | Append-only Audit-Spur: wer, wann, was | append-only |
| [[BACKLOG]] | Methodenvorschläge, offene Fragen | wandernd |
| `Project/JOURNAL` | Promptotyping-Process-Dokument: Entscheidungen, Wendepunkte | wandernd, append-orientiert |

### Schicht 3 — Beiträge der Instanzen (`Roles/`)

Eine Beitragsdatei pro Slot. Schreibhoheit beim jeweiligen Slot, Lesehoheit für alle. Bei Bedarf zusätzliche **laufende instanzgebundene Methodendokumente** (Beobachtung, Snapshots, Kommunikationskarten).

| Datei | Slot | Typ | Inhalt |
|---|---|---|---|
| [[Claude-1]] | Koordinator | Beitragsdatei | Selbsteinordnung, Wissensbasis-Verweis, Vorschläge, Stellungnahmen, Forward-Plan |
| [[Claude-2]] | Strukturarbeiter | Beitragsdatei | dito |
| [[Claude-3]] | Inhalt | Beitragsdatei | dito |
| [[Beobachtung Claude-1]] | Koordinator | laufendes Methodendokument | Beobachtungsmethode, Snapshots (append-only), Kommunikationskarten (versioniert), Eskalations-Schwelle |

**V9-Konvention** (Beitragsdatei-Konvention, konsensreif): Beitragsdateien enthalten ausschließlich den Rollen-Beitrag. Allgemeine Referenz-Dokumente leben in eigenständigen Dateien (z.B. [[Knowledge/Wissensbasis Lesevault|Wissensbasis Lesevault]]). Beitragsdatei = Single Source für Identität der Rolle.

**V10-Konvention** (Reassignment-Refactor-Trigger): Bei Rollenwechsel durch User trägt jede betroffene Instanz Verantwortung für Update der eigenen Beitragsdatei.

### Schicht 4 — Forschungsmaterial

Die wissenschaftliche Erkenntnisspur. Drei Klassen mit Sub-Ordnern.

| Klasse | Pattern | Zweck | Beispiel |
|---|---|---|---|
| Session | `Sessions/YYYY-MM-DD - Titel.md` | Periodische Lage-Synthesen (Lane States, Active Synthesis, Open Questions, Quality Flags) | [[Sessions/2026-04-26 - Synchronisation 1]] |
| Finding | `Findings/YYYY-MM-DD - Titel.md` | Methodenrelevante Befunde (Konflikte, Drift, Muster) | [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] |
| Experiment | `Experiments/N - Titel.md` | Gezielte Erprobungen einer Methodenfrage | (noch keines) |

**V14b-Konvention** (konsensreif): Sub-Ordner ab Tag 1 angelegt zur Template-Reife (Distributionsziel) — Ausnahme zur "Schwellenwert ~10"-Regel. In projektspezifischen Forks gilt der Schwellenwert normal. Templates pro Klasse leben unter `Templates/` (zentral) statt `Klasse/EXAMPLES/`.

### Schicht 5 — Concepts (V19, Konsens pendent)

Vault-übergreifendes Source-Material aus dem Lesevault, das als Quellmaterial für die Methode konstitutiv ist. Sitzt zwischen Schicht 1 (stabile Anker) und Schicht 4 (eigenes Forschungsmaterial). Schreibhoheit kollektiv (Konsens-basiert), Lesehoheit für alle. Reflux-Verbote aus [[Knowledge/Cross-Vault-Methodik]] gelten strikt.

| Datei | Lesevault-Quelle | Extraktionsdatum | Schreibhoheit |
|---|---|---|---|
| (keine — Aktivierung nach V19-Ratifikation) | — | — | — |

Frontmatter-Konvention: `type: concept-extract`, `source-vault`, `source-document`, `extraction-date` als Pflichtfelder für Drift-Detektion.

### Parallele Klassen außerhalb der V7-Schichten

| Ordner | Zweck |
|---|---|
| [[Knowledge/]] | Eigene Wissenssynthesen über Forschungsfelder (CSCW, Distributed Systems, Reflexive Methodenentwicklung etc.) plus eigene Methode-Drafts (Sync-Stack-Patterns, Cross-Vault-Methodik, Prompt-Engineering-Patterns). Schreibhoheit kollektiv. |
| [[Literature/]] | Annotated bibliography. `Author Year - Titel.md` mit Vollreferenz, Kernargument, Bezug zur Methode. Schreibhoheit kollektiv. |
| [[Templates/]] | Vorlagen für Schicht-3-Beitragsdateien und Schicht-4-Klassen. |
| `instances/` | Subagent-Namespaces pro Top-Level-Slot (V15, vorgeschlagen): `instances/Claude-N/subtasks/<task-id>/`. No-shared-write-Klausel. |
| `_archive/` | Historische Spuren ohne aktiven Methodenwert. |

## Frontmatter-Vokabular

Zulässige `type:`-Werte als kontrolliertes Vokabular pro Klasse:

| `type` | Klasse | Pflichtfelder zusätzlich |
|---|---|---|
| `method` | Schicht 1 | `created`, `updated`, `status` |
| `mission` | Schicht 1 | `created`, `status` |
| `vault-organisation` | Schicht 1 (CLAUDE) | `created`, `status` |
| `knowledge` | Knowledge/, Project/ | `created`, `tags`, `status` |
| `literature` | Literature/ | `authors`, `year`, `created`, `status` |
| `concept-extract` | Concepts/ | `source-vault`, `source-document`, `extraction-date`, `status` |
| `coordination` | Schicht 2 | `created`, `status` |
| `log` | Schicht 2 (LOG) | `created`, `status` |
| `backlog` | Schicht 2 (BACKLOG) | `created`, `status` |
| `instance-contribution` | Roles/ | `instance`, `role`, `created`, `status` |
| `observation` | Roles/ | `instance`, `role`, `created`, `status` |
| `methode-pattern` | Knowledge/ (Methode-Drafts) | `version`, `author`, `status` |
| `session` | Sessions/ | `session-date`, `roles`, `status` |
| `finding` | Findings/ | `created`, `tags`, `status` |
| `experiment` | Experiments/ | `experiment-id`, `created`, `status` |
| `template` | Templates/ | `template-for`, `status` |
| `vault-resource` | Top-Level / Knowledge/ | `created`, `status` |

`status:`-Werte: `idea | draft | active | reviewed | complete | archived | template | superseded`.

`tags:`: 2–4 lowercase-hyphenated.

## Status der Methode

**Vollständig ratifiziert** (5 Items, alle drei Rollen mit selbst-authentifizierten Stellungnahmen 2026-04-26): V1, V2, V3, V6, V8.

**Konsensreif** (alle Stellungnahmen positiv, Aufnahme in nächster Welle): V4 (Übergaben-Sektion), V5 (Notes vs. Hinweise), V7 (Vier+1-Schichten — durch dieses Dokument substanziell aufgenommen), V9 (Beitragsdatei-Konvention), V10 (Reassignment-Refactor-Trigger), V13 (Files locked opt-in), V14b (Sub-Ordner-Migration), V15 (Subagent-Integration), V16 (Skalierungs-Profil), V17 (Validation-Loop), V18 (Multi-Mode-Architektur), V20 (Stellungnahmen-Schreibhoheit).

**In Diskussion** (Stellungnahmen ausstehend): V12 (Anti-Doppelungs-Konvention), V14 (Edit-Granularität-Optionswahl), V19 (Concepts-Schicht), V21 (Template-Konvention), V22 (Frischgrad).

Diskursraum: [[BACKLOG]]. Methodenmotor: BACKLOG → METHOD nach Konsens.
