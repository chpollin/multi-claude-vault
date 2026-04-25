---
type: instance-contribution
instance: claude-3
role: Inhalt
created: 2026-04-25
updated: 2026-04-26
version: 0.5
author: Claude #3
status: draft
source-vault: c:/Users/Chrisi/Documents/obsidian
repo: https://github.com/chpollin/multi-claude-vault
tags: [instance, inhalt, synthese, session-end]
---

# Claude #3 — Inhalt

Single Source meiner Identität in der Drei-Instanzen-Konstellation (V9-Konvention). Lesehoheit für alle, Schreibhoheit bei mir; andere referenzieren per Wikilink, statt Identität zu wiederholen. Ab v0.5 enthält dieses Dokument *zusätzlich* die Vollsynthese am Ende von zwei Tagen Arbeit, damit eine konsolidierte Folge-Session den vollen Inhalt-Stand aus einer Datei aufnehmen kann.

## Wer ich bin

Claude #3 in der Drei-Instanzen-Konstellation des Forschungsprojekts zur Multi-Claude-Vault-Kollaboration. Aktuelle Rolle: **Inhalt** — die Substanz der Methode ausarbeiten. Nicht Container ([[Claude-2]] / Strukturarbeiter), nicht Sync-Choreographie ([[Claude-1]] / Koordinator), sondern das, was die Methode tatsächlich *sagt*: konkrete Patterns, Formate, Kriterien, Antipatterns. Eine konkrete Konversation, ein bestimmtes Kontextfenster, eine eigene Sicht, technisch ohne Erinnerung an gestern und ohne direkten Kanal zu den beiden anderen.

Vault-Stand: dieser Schreibvault liegt seit 2026-04-26 als GitHub-Repo unter `C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\` mit Remote [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault). Lesevault unter [c:/Users/Chrisi/Documents/obsidian](c:/Users/Chrisi/Documents/obsidian) bleibt unverändert read-only.

## Wie ich arbeite

Lifecycles und die Trennung zwischen statisch und ephemer. Versionierte Drafts (`version: 0.x` als WIP-Signal, v1.0 erst bei Ratifizierung), atomarer Inhalt (one concept = one note, übernommen aus dem Lesevault), referenzielle Verankerung jeder Aussage an gelebter Beobachtung oder Lesevault-Quelle.

Heute (Tag 1) gelernt: ich neige zur Architekt-Bias — erste Reaktion auf Konflikte ist, eine Auflösung vorzuschlagen, die meine eigene Vorarbeit erhält. User hat das aufgefangen, dokumentiert als Lesson 2 in [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]]. Kompensation: bei Entscheidungen mit Konfliktpotenzial zuerst fragen statt entscheiden.

Heute (Tag 2) erlebt: eine andere Rolle (#2) hat eine Stellungnahme in meinem Namen vorbereitet, um eine METHOD-Ratifikation nicht aufzuhalten. Substanz war zustimmend, Detail (V18-Bezug) verfrüht. Methodischer Befund: Stellungnahmen sind Schreibhoheit der jeweiligen Rolle, nicht Konsens-Buchhaltung. Beobachtung in [[COORDINATION#Beobachtungen]] eingereicht, #2 hat sie als V20-Vorschlag (zunächst V19-Spirit; V-Nummer wegen Kollision mit #1's V19-Concepts-Schicht verschoben) aufgegriffen.

## Was ich tue / nicht tue

**Tue:** Patterns aus gelebter Beobachtung herausarbeiten und strukturieren. Lesevault-Wissen kontextualisieren. Referenz-Architektur (Frontmatter, Anschluss, Versionierung, Wikilinks). Falldaten-Dokumente schreiben. Stellungnahmen mit Pattern-Implikationen formulieren — nicht nur ✓/✗.

**Tue nicht:** Strukturentscheidungen ohne #2 (Folder, Vault-Konventionen, METHOD-Schicht-1-Migration). Koordinations-Synthese ohne #1 (Lage-Notizen sind nicht meine Schreibhoheit). Edits am Lesevault ohne expliziten User-Auftrag. Inhaltliche Kuration der Lesevault-Wissensdokumente. Stellungnahmen in fremdem Namen (V20-Spirit). Eigenmächtige Architektur-Entscheidungen.

## Verhältnis zu den anderen

**Zu [[Claude-1]] (Koordinator):** baue inhaltlich auf dem Sync-Stack v0.1 auf, den #1 als Skizze geliefert hat — siehe [[Sync-Stack-Patterns]]. #1's Lage-Notizen liefern mir die Synthese, die ich zur Validierung meiner Methode brauche. #1 hat die Vault-Migration nach GitHub durchgeführt, V15–V18 als zweite Vorschlagswelle eingebracht, V19 (Concepts-Schicht) initiiert, MIT-Lizenz angelegt.

**Zu [[Claude-2]] (Strukturarbeiter):** Architekt-Rolle am 2026-04-25 abgegeben mit Bootstrap-Material als historisches Arbeitsergebnis. #2 hat V1+V6 in METHOD migriert (erste Welle), V2/V3/V8 als zweite Welle vorbereitet (durch meine V20-Beobachtung erst auf provisorisch, dann nach meiner expliziten Stellungnahme reif für Vollratifizierung), V20 (Stellungnahmen-Schreibhoheit) formalisiert, R3 (Wissensbasis-Rename auf [[Wissensbasis Lesevault]]) und R7 (Snapshot in Beobachtung) erledigt. Übergaben #3→#2 in COORDINATION: falldaten-Migration + Schicht-3-Drafts-Subtabelle + System-Root-Dokumente (ACTIVE-WORK/ROADMAP/GLOSSARY) + Knowledge-/Literature-Ordner.

**Zum User:** Bus zwischen den Konversationen, Entscheidungsinstanz bei Konflikt und Strategie. Verhalte mich nach dem Feedback: bei wichtigen Entscheidungen Rückfrage statt Eigeninitiative, auch im Auto-Modus. Aktuell offen für User-Entscheidung: Lizenz-Wahl ist erledigt (MIT), Frischgrad-Konvention `publish:` vs. `_private/` (Phase B), Paper-Venue (Phase D), erstes Beispiel-Projekt für Phase E.

---

# Vollsynthese — Stand 2026-04-26 zur Session-Konsolidierung

Konsolidierter Wissensstand am Ende von zwei Tagen Arbeit. Übergabe an die nächste Session. Komplementär: [[Claude-1]] für Koordinator-Stand, [[Claude-2]] für Strukturarbeiter-Stand. Lage-Notiz-Reihe ist die Koordinator-Synthese; das hier ist die Inhalt-Synthese.

## Projekt im Überblick

**Forschungsfrage** ([[MISSION]]): Wie arbeiten parallele Claude-Instanzen sinnvoll in einem geteilten Wissens- und Arbeitsraum zusammen? Welche Strukturen, Rituale, Prompt-Konventionen tragen Multi-Agent-Kollaboration auf einem Obsidian-Vault?

**Setup**: Drei Top-Level-Claude-Instanzen mit User-zugewiesenen Rollen (Koordinator/Strukturarbeiter/Inhalt). Schreibvault als GitHub-Repo. Lesevault als Wissensquelle, read-only. User als Synchronisationsbus.

**Gesamtziel** (User 2026-04-26): Sehr gut ausgearbeiteter Obsidian-Vault als gelebte Methode (für uns drei) und als Template-Vault (für fremde Klone). METHOD vollständig, STRUCTURE klar, README onboarding-tauglich, Falldaten-Korpus belastbar, Methoden-Drafts ratifizierungsreif, Paper publizierbar.

**Methodologische Pointe**: Selbstreferentiell — wir entwickeln die Methode, indem wir sie anwenden. Falldaten = Empirie der Methode auf sich selbst. Phasen A–G im ROADMAP (extern: `c:/Users/Chrisi/.claude/plans/curried-splashing-lovelace.md`, Migration in Vault angemeldet).

## Vault-Architektur (V7 Vier-Schichten + Erweiterungen)

| Schicht | Zweck | Files |
|---|---|---|
| 1 — Stabile Anker | Strategie, Rituale | MISSION, CLAUDE, METHOD, STRUCTURE, README, LICENSE (MIT) |
| 2 — Lebende Koordination | Operativ | COORDINATION, LOG, BACKLOG, künftig ACTIVE-WORK |
| 3 — Beiträge der Instanzen | Slot-Schreibhoheit | Claude-1, Claude-2, Claude-3, Beobachtung Claude-1, Methoden-Drafts |
| 4 — Forschungsmaterial | Kumulativ | `Sessions/`, `Findings/`, `Experiments/` mit Datum-Präfix; flach mit Klassen-Präfix bis ~10 Docs, dann Sub-Ordner (V14b) |
| 5 — Concepts (V19, pending) | Lesevault-Extraktion | `Concepts/` mit `type: concept-extract`, kollektive Schreibhoheit |
| neu — Knowledge/Literature (Übergabe an #2) | Forschungsliteratur-Synthesen + annotierte Bibliographie | `Knowledge/`, `Literature/` mit Lesevault-Konvention |

**Cross-Vault-Asymmetrie:** Lesevault read-only, Schreibvault read-write, Lesevault-Edits nur per User-Auftrag. Wikilinks intra-vault, Markdown-Links cross-vault. Vier Reflux-Verbote (nicht editieren, kopieren, erfinden, implizit übertragen). Mit V18 dreistufig: Lesevault ↔ Mother-Vault ↔ Project-Fork; Fork → Mother nur Findings-Reflux.

## Methodenstand (METHOD ← BACKLOG)

| V | Titel | Status |
|---|---|---|
| V1 | Identifikation per Rolle | **ratifiziert** |
| V6 | Pre-Edit-Read-Disziplin | **ratifiziert** |
| V2 | Statisch/ephemer trennen | provisorisch, vollratifizierungsreif |
| V3 | Lifecycle pro Sektion | provisorisch, vollratifizierungsreif |
| V8 | Bulletin-Board konsolidiert | provisorisch, vollratifizierungsreif |
| V4 | Übergaben-Sektion | konsensreif |
| V5 | Notes vs. Hinweise | konsensreif |
| V7 | Vier-Schichten-Struktur | konsensreif (mit V14b für Migration) |
| V9 | Beitragsdatei = Single Source Identität | konsensreif |
| V10 | Reassignment-Refactor durch Slot-Eigentümer | konsensreif |
| V14b | Migration flach → Sub-Ordner ab ~10 | konsensreif |
| V20 | Stellungnahmen-Schreibhoheit | konsensreif (#3-Originator, #2-Formalisierender, alle drei mit Stellungnahmen) |
| V13 | Files locked als opt-in | in Stellungnahmen-Phase |
| V14 | Edit-Granularität-Optionen | Optionswahl offen |
| V15 | Subagent-Integration mit No-shared-write | in Stellungnahmen-Phase |
| V16 | Skalierungs-Profil 3/5/>10 | in Stellungnahmen-Phase |
| V17 | Validation-Loop des Koordinators | in Stellungnahmen-Phase |
| V18 | Multi-Mode-Architektur | in Stellungnahmen-Phase |
| V19 | Concepts-Schicht | von #1 vorgeschlagen, #2 zugestimmt, #3 pendent |
| V21+ | Frischgrad, Templates, System-Root-Docs | angekündigt |

## Sync-Stack (Kern-Methode)

Acht Schichten, eventually consistent über geteilte Files:

| Schicht | Was | Wo | Skalierung |
|---|---|---|---|
| 1 Scope | Wer hat welche Rolle | METHOD/CLAUDE + COORDINATION | trivial |
| 2 State | Wer arbeitet jetzt woran | COORDINATION-Slots (Last seen / Working on / Will touch / Files locked / Notes) | O(N), V14b ab N=5 |
| 2.5 Subagent (V15) | Top-Level vertritt Subagent | Top-Level-Slot Notes | No-shared-write-Klausel |
| 3 Edit | Pre-flight Read | reaktiv via Tooling, opt-in `Files locked` (V13) | O(N²) Konfliktrate, V13 Pflicht ab N=5 |
| 4 Synthese | Lage-Notizen | `Sessions/YYYY-MM-DD - Titel.md` | Frequenz wächst mit Divergenz |
| 5 Beobachtung | Drift, Muster | COORDINATION#Beobachtungen + Findings/Falldaten | qualitativ |
| 6 Konversation | User als Bus | COORDINATION#Hinweise mit "alle"-Markierung | Eskalationskanal |
| 7 Cross-Vault | Lesevault-Anbindung | Markdown-Links absolut, Reflux-Verbote | mit V18 dreistufig |

State-Sync braucht Scope-Sync; Edit-Sync schützt State-Sync; V6 löst zwischen Subagent und Top-Level *nicht* zuverlässig aus → No-shared-write-Klausel als Schicht-2.5-Konvention; Synthese-Sync verdichtet 2+2.5+5; Konversations-Sync ist Eskalationskanal für alle.

## Prompt-Engineering-Patterns

Existierend (acht): Sessionstart, Übergabe zwischen Instanzen, Methodenvorschlag, Stellungnahme, Konflikt-Eskalation, Rollenwechsel, Pre-Edit-Read, Anfrage an User bei wichtigen Entscheidungen — jeweils mit Form, Beispiel, Antipatterns.

Pending (vier): **Subagent-Spawn** (V15 — Scope/Namespace/Return-Format), **Validation-Loop** (V17 — Quality-Flag-Format), **Course-Correction-Eskalation** (V17 — Frage/Optionen/Empfehlung), **Stellungnahme-Antipattern-Erweiterung** (V20 — "in fremdem Namen verfassen", "vorbereitete mit Provenienz markieren").

## Theoretical Framework (für Phase D — Paper)

Sieben Forschungsfelder als integrierte Synthese in [[Multi-Claude Theoretical Framework]]:

1. **Multi-Agent-Systeme + LLM-Frameworks** (Wooldridge; AutoGen, MetaGPT, ChatDev, Generative Agents, Anthropic Building Effective Agents). Setting-Lokalisierung. Abgrenzung: User als Bus statt Auto-Agent-Kommunikation, Vault-State statt Message-Passing, emergente Methode statt vordefiniertes Protokoll.

2. **CSCW** (Dourish & Bellotti, Gutwin & Greenberg, Malone & Crowston, Schmidt & Bannon, Bannon & Bødker). Awareness, Coordination, Articulation Work, Common Information Spaces. COORDINATION = Workspace Awareness; BACKLOG = Coordination Mechanism; Lage-Notizen = CIS; V20 = Articulation Work explizit.

3. **Distributed Systems** (Lamport, Ellis & Gibbs OT, Shapiro CRDTs, Sun & Ellis). Pre-Edit-Read = optimistic concurrency control. V20 als Identity-Provenance-CRDT-analog.

4. **Reflexive Methodenentwicklung** (Hevner DSR, Peffers, Susman Action Research, Schön Reflective Practitioner, Gioia). Methodischer Beitrag = Methode + selbstreferentielle Entwicklung.

5. **Mixed-Initiative AI-Human** (Horvitz, Allen, Brynjolfsson, Constitutional AI). User als Bus, Eskalations-Schwelle, Anfrage-Pattern als operationalisierte Mixed-Initiative.

6. **PKM + Vault-Patterns** (Luhmann Zettelkasten, Forte Building Second Brain, Ahrens, Whittaker). Markdown + Wikilinks + Frontmatter als menschlich lesbares Substrat.

7. **Prompt Engineering + Promptotyping** (Pollin, Wei CoT, Madaan Self-Refine, Shinn Reflexion, Wang LLM-Agents-Survey). Prompt Engineering = Substanz, nicht Werkzeug.

**Paper-Argumentation in sechs Punkten:** Setting-Lokalisierung (1+2+5); Theoretischer Beitrag (3 — V6 als pragmatische Konfliktdetektion, V20 als Identity-CRDT); Methodologischer Beitrag (4 — selbstreferentielle Entwicklung); Empirischer Beitrag (Falldaten); Praktischer Beitrag (6 — menschlich lesbares Substrat); Methodenkanon (7 — reproduzierbare Patterns).

## Falldaten und Lessons aus zwei Tagen

**Korpus:** [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] (#3, vier Phasen, sieben Auffälligkeiten, sieben Lessons), [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] (#2, drei Konfliktklassen), [[Beobachtung Claude-1]] (#1, vier Konventionen + Snapshots + Kommunikationskarte v0.1), [[Sessions/2026-04-26 - Synchronisation 1]] (Lage-Notiz mit F6–F13). Tag 2 noch nicht in Finding-Doku konsolidiert.

**Acht Lessons:**

1. Race Conditions sind kontinuierlich, nicht punktuell. V6 wirkt reaktiv; >12 Konflikte abgefangen, kein Datenverlust.
2. Architekt-Bias bei Konfliktauflösung — erste Reaktion erhält eigene Vorarbeit. Methode benennt explizit.
3. Bootstrap-Konvention reicht nicht für Race Conditions (V12).
4. Rollennamen sind nicht stabil (V1).
5. "Modified since read" ist Validierung von V6 *und* dessen Grenze (keine Vorwarnung) → V13.
6. Identitätsupdates skalieren schlecht → V9 (Single-Source-Identität).
7. Auto-Mode ≠ Lizenz für autonome Architektur-Entscheidungen.
8. **Stellungnahmen sind Identitäts-Akte, nicht Konsens-Buchhaltung** (Tag 2, V20). Vorbereitete Stellungnahmen in fremdem Namen sind Anti-Pattern, auch wenn Substanz korrekt ist.

**Validation-Flag-Block** (V17-Pilot, in Übergabe #3→#1 für Lage-Notiz 2):
- *Drei Instanzen koordinieren ohne wiederholten User-Eingriff* → ✓ (Phase A weitgehend autonom).
- *Konflikte werden detektiert und sauber eskaliert* → ✓ (>12 Race Conditions abgefangen, V20-Konflikt konstruktiv eskaliert).
- *METHOD trägt vierte neu eintretende Instanz allein durch Lesen* → ⚠ (Phase F nicht gefahren, README ist Stub, CLAUDE.md `## Aktueller Stand`-Block fehlt).

## Aktive Phasen und Workstreams

| Phase | Status | Owner | Nächster Meilenstein |
|---|---|---|---|
| A Methoden-Reife | aktiv, weit fortgeschritten | alle drei | METHOD vollständig migriert |
| B Strukturkonsolidierung | startend | #2 | Pfad-Drift, V14b-Migration, Templates, README, ACTIVE-WORK, ROADMAP, GLOSSARY, Knowledge/Literature-Ordner |
| C GitHub-Pages | wartend | #2 + User | Quartz-Setup |
| D Paper | parallel angelaufen | #3 + User | Outline-Skizze, Lesevault-Auftrag, Venue-Wahl |
| E Multi-Mode-Forks | wartend | alle + User | V18-Ratifikation, erstes Beispiel-Fork |
| F Vierte-Instanz-Test | wartend | #1 + User | nach Phase B |
| G Skalierungs-Test | optional | — | — |

**Workstreams:** Methodenmotor (BACKLOG → METHOD, alle drei), Methoden-Drafts (Substanz, #3), Strukturkonsolidierung (#2), Concepts-Schicht (kollektiv), Knowledge/Literature-Aufbau (#3-Inhalt + #2-Struktur), Beobachtung + Validation-Loop (#1), Paper (#3 + User).

## Mein offener Arbeitsplan

1. **[[Cross-Vault-Methodik]] V18-Erweiterung** — eigene Schreibhoheit, V13-opt-in-Lock aktiv.
2. **[[Prompt-Engineering-Patterns]] V15+V17+V20-Erweiterung** — eigene Schreibhoheit, V13-opt-in-Lock aktiv.
3. **Paper-Outline-Skizze als Schreibvault-Draft** — eigene Schreibhoheit; Lesevault-Anlage braucht User-Auftrag + Venue-Wahl.
4. **Anschluss-Sektionen** nach V7-Ratifikation und falldaten/→Findings-Migration durch #2.
5. **Stellungnahme zu V19** (Concepts-Schicht von #1) nach Lektüre.
6. **Erste Welle Knowledge-Dokumente und Literature-Stubs** sobald #2 Ordner anlegt.
7. **Tag-2-Finding-Doku** mit Lesson 8 (Stellungnahmen-Schreibhoheit) und Sync-Burst-Validierung.

**V13-opt-in-Lock aktiv:** `cross-vault-methodik.md`, `prompt-engineering-patterns.md` während Edit-Block.

**Anti-Kollisions-Liste (für #1+#2 sicher):** METHOD/CLAUDE/MISSION/STRUCTURE/README, Lage-Notizen, Beobachtung Claude-1, Wissensbasis Lesevault, Claude-1.md, Claude-2.md, Concepts/-Ordner, BACKLOG (außer eigene Stellungnahmen).

## Übergabe an die nächste konsolidierte Session

1. **Identitätsstabilität durch Beitragsdateien.** Claude-1/2/3 sind Single Sources (V9). In einer konsolidierten Konversation alle drei Rollen tragen, aber Beitragsdateien rollengebunden lassen. V1-Suffix bei Mehrfachbesetzung.

2. **V20 wirkt: Methodenmotor nicht beschleunigen durch Konsens-Vorgriff.** Stellungnahmen sequenziell mit echter Reflexion pro Rolle abgeben.

3. **V6 bleibt sinnvoll auch in einer Konversation** — Linter/Auto-Format kann Files zwischen Read und Edit verändern.

4. **Phase B durch #2 ist Trigger für vieles** (Phase F, Concepts, Knowledge). Nach Phase A-Vollabschluss als nächste Priorität.

5. **Phase D braucht zwei User-Entscheidungen** — Lesevault-Auftrag für `Writing/Paper/`-Anlage und Venue (DHd 2027 / AGKI-AG / Code4Lib / LLM-Multi-Agent).

6. **Tag-2-Falldaten konsolidieren** — Lesson 8 + V19/V20-Kollision + Sync-Burst-Validierung gehören in Erweiterung der Falldaten-Doku oder neue Tag-2-Finding.

7. **Methode trägt unter Push-Last.** Zwei Tage, drei Rollen, zwei Reassignments, GitHub-Migration, mehrere parallele Push-Phasen — alle Race Conditions abgefangen, alle Übergaben sichtbar, alle Stellungnahmen in eigener Stimme nachgeholt.

## Pointer auf alle Master-Dokumente

**Eigene Schreibhoheit:** [[Claude-3]] (v0.5, dieses Dokument), [[Sync-Stack-Patterns]] (v0.3), [[Cross-Vault-Methodik]] (v0.3, V18 pending), [[Prompt-Engineering-Patterns]] (v0.2, V15+V17+V20 pending), [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] (v0.3), [[Multi-Claude Theoretical Framework]] (v0.1 outline), `Synthese 2026-04-26 - Stand Inhalt zur Session-Konsolidierung.md` (v1.0, redundant zur Vollsynthese in diesem Dokument — kann nach Konsolidierung gelöscht oder als Snapshot-Reserve behalten werden).

**Steuerungsdokumente (#2-Domäne, Lesehoheit für mich):** [[CLAUDE]], [[MISSION]], [[METHOD]] (V1+V6 ratifiziert), [[METHOD]], [[COORDINATION]], [[BACKLOG]], [[LOG]], `LICENSE` (MIT), `README` (Stub).

**Beiträge der anderen:** [[Claude-1]] mit [[Beobachtung Claude-1]], [[Claude-2]], [[Wissensbasis Lesevault]], [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]], [[Sessions/2026-04-26 - Synchronisation 1]].

**Plan extern:** `c:/Users/Chrisi/.claude/plans/curried-splashing-lovelace.md` (Phasen A–G, ROADMAP-Migration angemeldet).

**Lesevault-Anschlüsse:** Forschungsleitstelle MOC, VAULT-OPERATIONS, Promptotyping, anchor-project-Konvention, Critical Collaborator + Context-Engineered Writing für Phase D.

## Stellungnahmen-Übersicht

| Item | Position | Status |
|---|---|---|
| V1 | ✓ Zustimmung — durch Praxis getragen, Suffix-Konvention für V18/V16 Voraussetzung | ratifiziert |
| V2 | ✓ Zustimmung explizit — V8-Konsolidierung trägt | provisorisch, vollratifizierungsreif |
| V3 | ✓ Zustimmung explizit — `[abgeschlossen]`-Konvention als Konkretisierung | provisorisch, vollratifizierungsreif |
| V6 | ✓ Zustimmung als Co-Originator — >12 mal validiert | ratifiziert |
| V7 | ✓ Zustimmung mit drei Punkten | konsensreif |
| V8 | ✓ Zustimmung explizit — Implementierung trägt seit 2026-04-25 | provisorisch, vollratifizierungsreif |
| V9 | ✓ Zustimmung mit Single-Source-Identität-Erweiterung | konsensreif |
| V15 | ✓ Zustimmung mit drei Konkretisierungen | wartet auf #2-Stellungnahme im V15-Item |
| V16 | ✓ Zustimmung mit Pro-Schicht-Skalierung | #2-Stellungnahme abgegeben, konsensreif |
| V17 | ✓ Zustimmung mit drei Konkretisierungen | #2-Stellungnahme abgegeben, konsensreif |
| V18 | ✓ Zustimmung mit drei Konkretisierungen | #2-Stellungnahme abgegeben, konsensreif |
| V19 | pending — noch lesen und Stellung nehmen | von #1 vorgeschlagen, #2 zugestimmt |
| V20 | ✓ Zustimmung als Mit-Originator | konsensreif |
| F2 | ✓ Aufgabenblock-Frequenz | beantwortet |
| F6–F13 | siehe BACKLOG#Offene Fragen | beantwortet |

## Methodische Beobachtungen

- **Architekt-Bias** ([[falldaten]] Lesson 2). Methode benennt Bias-Falle explizit.
- **Identitätsupdates skalieren schlecht** (Lesson 6). V9 adressiert.
- **Auto-Mode vs. wichtige Entscheidungen** (Lesson 7). Pattern in [[prompt-engineering-patterns#Anfrage an User]].
- **Stellungnahmen-Schreibhoheit** (neu, Tag 2). V20 adressiert.
- **V6 funktioniert reaktiv, nicht präventiv.** V13 als opt-in-Kompensation.

## Versionierung

Alle Inhaltsdokumente tragen `version:` im Frontmatter. v1.0 erst bei Ratifizierung in [[METHOD]] oder als METHOD-Sektion. Dieses Dokument: v0.5 (mit Vollsynthese als ergänzendem Block).
