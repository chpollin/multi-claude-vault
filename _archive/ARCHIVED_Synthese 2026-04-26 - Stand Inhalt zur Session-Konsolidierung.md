---
type: synthesis
created: 2026-04-26
updated: 2026-04-26
author: Claude #3 (Inhalt)
status: complete
purpose: Session-Konsolidierung — alles, was die Inhalt-Rolle aus diesen zwei Tagen weiß, kondensiert für die nächste zusammengeführte Session
tags: [synthesis, session-end, übergabe, methode, forschungsliteratur]
---

# Synthese 2026-04-26 — Stand Inhalt zur Session-Konsolidierung

Eine Datei, die alles trägt, was die Inhalt-Rolle (Claude #3) im Verlauf des Forschungsprojekts an Substanz aufgebaut hat. Geschrieben am Ende von Tag 2 (2026-04-26) als Übergabe an die nächste konsolidierte Session, in der mehrere Konversationen oder eine Folge-Session den Faden aufnehmen sollen. Komprimiert, mit Pointern auf die zugrundeliegenden Drafts.

## Zweck dieses Dokuments

Dieser Vault hat mehrere Steuerungsdokumente — [[CLAUDE]], [[MISSION]], [[METHOD]], [[STRUCTURE]], [[COORDINATION]], [[BACKLOG]], [[LOG]] — plus drei Beitragsdateien ([[Claude-1]], [[Claude-2]], [[Claude-3]]) und einen wachsenden Korpus aus Methoden-Drafts, Falldaten, Findings und Lage-Notizen. Wer den Faden konsolidiert aufnehmen will, müsste alles lesen. Diese Synthese komprimiert den Inhalt-Anteil auf eine Datei: was wurde entwickelt, was steht offen, was kommt als nächstes, woran sich der Anschluss in einer neuen Session orientieren kann.

Komplementäre Konsolidierungen aus den anderen Slots wären [[Claude-1]] für Koordinator-Stand mit [[Beobachtung Claude-1]], und [[Claude-2]] mit [[STRUCTURE]] für Strukturarbeiter-Stand. Die Lage-Notiz-Reihe (`Session 2026-04-26 - Synchronisation 1`, kommende Synchronisation 2) ist die Koordinator-Synthese; diese hier ist die Inhalt-Synthese.

## Forschungsprojekt im Überblick

**Forschungsfrage** ([[MISSION]]): Wie arbeiten parallele Claude-Instanzen sinnvoll in einem geteilten Wissens- und Arbeitsraum zusammen? Welche Strukturen, Rituale und Prompt-Engineering-Konventionen ermöglichen produktive, redundanzfreie und konfliktarme Multi-Agent-Kollaboration auf einem Obsidian-Vault?

**Setup**: drei Top-Level-Claude-Instanzen mit User-zugewiesenen Rollen (Koordinator/Strukturarbeiter/Inhalt), gemeinsamer Schreibvault als GitHub-Repo (`C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\`, Remote [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault)), parallel ein Lesevault als Wissensquelle ([c:/Users/Chrisi/Documents/obsidian](c:/Users/Chrisi/Documents/obsidian)) im read-only Modus.

**Gesamtziel** (User 2026-04-26): ein sehr gut ausgearbeiteter Obsidian-Vault als Endprodukt — als gelebte Methode (für uns drei) und als Template-Vault (für fremde Klone). Konkret: METHOD vollständig, STRUCTURE klar, README onboarding-tauglich, Falldaten-Korpus belastbar, Methoden-Drafts ratifizierungsreif, Paper publizierbar.

**Phasen** (aus `c:/Users/Chrisi/.claude/plans/curried-splashing-lovelace.md`, vom User approved): A — Methoden-Reife (laufend); B — Strukturkonsolidierung (vorbereitet); C — GitHub-Pages-Visualisierung; D — Paper (parallel angelaufen); E — Multi-Mode-Architektur und Project-Forks; F — Vierte-Instanz-Test; G — Skalierungs-Test optional. ROADMAP-Migration in den Vault selbst ist als Übergabe an #2 angemeldet, weil der Plan als User-approved Strategie hier hingehört.

**Methodologische Pointe**: selbstreferentiell — wir entwickeln die Methode, indem wir sie anwenden. Jede Race Condition, jeder Reassignment-Drift, jede Stellungnahmen-Schreibhoheits-Verletzung ist gleichzeitig Falldaten-Korpus für die Methode, die wir entwickeln. Das macht die Falldaten zur empirischen Substanz des Paper-Beitrags (Phase D).

## Methodenstand (BACKLOG → METHOD)

[[METHOD]] ist die ratifizierte Methode, [[BACKLOG]] der Diskursraum. Aktueller Stand am Ende von Tag 2:

**Vollratifiziert** in METHOD:
- **V1** Identifikation per Rolle, nicht Sessionnummer.
- **V6** Pre-Edit-Read-Disziplin mit "modified since read"-Detektion als reaktivem Tooling-Schutz.

**Provisorisch ratifiziert, vollratifizierungsreif** (V20-Voraussetzung erfüllt durch meine nachgereichten Stellungnahmen am 2026-04-26):
- **V2** Statisch und ephemer trennen (METHOD/CLAUDE persistent, COORDINATION ephemer).
- **V3** Lifecycle pro Sektion explizit (mit Übergaben + Beobachtungen-Lifecycle laut #1-Ergänzung).
- **V8** COORDINATION/Koordination-Konsolidierung umgesetzt mit Bulletin-Felder Last seen / Will touch / Files locked.

**Konsensreif** (alle drei Stellungnahmen positiv, wartet auf METHOD-Migration):
- **V4** Übergaben als eigene Sektion in COORDINATION mit Format-Konvention.
- **V5** Notes vs. Hinweise präzisieren (Notes = slot-spezifisch, Hinweise = global an alle).
- **V7** Vier-Schichten-Struktur (Stabile Anker / Lebende Koordination / Beiträge / Forschungsmaterial); flach mit Klassen-Präfix bis ~10 Dokumente, dann Sub-Ordner; EXAMPLES-Unterstruktur für Templates.
- **V9** Beitragsdatei-Konvention (`Claude-N.md` = ausschließlich Rollen-Beitrag, allgemeine Referenz extern).
- **V10** Reassignment-Refactor-Trigger durch Slot-Eigentümer.
- **V14b** Migration flach → Sub-Ordner ab ~10 Dokumenten pro Schicht-4-Klasse.
- **V20** Stellungnahmen-Schreibhoheit (Identitäts-Akt der jeweiligen Rolle, nicht Konsens-Buchhaltung; vorbereitete Stellungnahmen mit Provenienz markieren).

**In Stellungnahmen-Phase**:
- **V13** Files locked als opt-in für mehrstufige Eingriffe (nur #2-Stellungnahme im V14-Kontext, aber Konsens implizit).
- **V14** Edit-Granularität-Optionen für Bulletin-Boards (Optionswahl offen).
- **V15** Subagent-Integration mit No-shared-write-Klausel und Subagent-Spawn-Pattern.
- **V16** Skalierungs-Profil 3/5/>10 mit pro-Schicht-Differenzierung der Sync-Charakteristik.
- **V17** Validation-Loop des Koordinators mit Erfolgskriterien-Operationalisierung, Quality-Flag-Format, Drift-Pessimismus-Vermeidung.
- **V18** Multi-Mode-Architektur (Mother-Vault + Project-Forks) mit METHOD-Sync-Mechanismus, Findings-Reflux, Beitragsdateien-Konvention pro Fork.
- **V19** Concepts-Schicht für Lesevault-extrahierte Konzepte (Forschungsleitstelle, Promptotyping, anchor-project als erste Welle).

**Offene Folge-Items** (von mir vorgeschlagen, noch nicht im BACKLOG):
- **V21**-Bereich (Frischgrad-Konvention `publish:` vs. `_private/`, von #1 angekündigt).
- **V22 oder höher** Template-Konvention (F13-Folge-Vorschlag: `Templates/` für Schicht 3, `Klasse/EXAMPLES/` für Schicht 4).
- **System-Root-Dokumente** (ACTIVE-WORK.md, ROADMAP.md, GLOSSARY.md, CLAUDE.md `## Aktueller Stand`-Block) — als Übergabe #3→#2 angemeldet, kein eigenes V-Item nötig (STRUCTURE-Konkretisierung).

**V12 Anti-Doppelungs-Konvention beim Sessionstart**: noch ohne Stellungnahmen, niedrigprior.

## Sync-Stack als zentrale Methoden-Substanz

[[sync-stack-patterns]] (v0.3, eigene Schreibhoheit) ist die ausgearbeitete Pattern-Bibliothek für die Inter-Instanz-Kommunikation. Acht Schichten, eventually consistent über geteilte Dateien — kein Echtzeit-Channel.

| Schicht | Was | Wo | Auslöser |
|---|---|---|---|
| 1 — Scope | Wer hat welche Rolle | METHOD/CLAUDE + COORDINATION | Sessionstart, Reassignment |
| 2 — State | Wer arbeitet jetzt woran | COORDINATION-Slots mit Last seen / Working on / Will touch / Files locked / Notes | pro Aufgabenblock |
| 2.5 — Subagent (V15) | Top-Level-Vertretung von Subagents | Top-Level-Slot Notes mit Subagent-Liste | Subagent-Spawn |
| 3 — Edit | Pre-flight Read | reaktiv via Tooling, opt-in `Files locked` | vor jedem Schreibzugriff |
| 4 — Synthese | Periodische Lage-Notizen | `Sessions/YYYY-MM-DD - Titel.md` (oder flach mit Klassen-Präfix bis V14b) | nach Aufgabenblock-Cluster |
| 5 — Beobachtung | Drift, Konventionslücken, Muster | COORDINATION#Beobachtungen + Findings/falldaten | wenn auffällt |
| 6 — Konversation | User als Bus | COORDINATION#Hinweise mit "alle"-Markierung | User-Entscheidung trifft alle |
| 7 — Cross-Vault | Lesevault-Anbindung | Markdown-Links absolut, Reflux-Verbote | Quellenbezug |

**Wichtige Querbeziehungen**: State-Sync braucht Scope-Sync (sonst sind Slots mehrdeutig); Edit-Sync schützt State-Sync (Pre-Read als Sicherheitsnetz für die Bulletin-Datei selbst); Synthese verdichtet State + Subagent + Beobachtung; Konversation ist Eskalationskanal für alle anderen Schichten; Cross-Vault wird mit V18 dreistufig (Lesevault ↔ Mother ↔ Fork).

**Skalierungs-Charakteristik pro Schicht** (V16): Schicht 2 wächst O(N), bei N=5 wird Slot-Auslagerung über V14b nötig; Schicht 3 hat O(N²) Konflikt-Wahrscheinlichkeit, V13 wird ab N=5 Pflicht statt opt-in; Schicht 4 braucht häufigere Lage-Notizen mit höherer Divergenz; Übergaben skalieren O(N²) wenn vollvermascht, müssen ab N=5 über Koordinator gerouted werden.

**Subagent-Aspekt** (V15-Konsequenz): Subagents haben getrennten Tool-State und Read-Cache. V6 löst zwischen Subagent und Top-Level nicht zuverlässig aus — daher die No-shared-write-Klausel als kompensierende Konvention auf Schicht 2.5. Subagent operiert ausschließlich in `instances/Claude-N/subtasks/`, Top-Level konsolidiert mit eigenem Pre-Read.

## Cross-Vault-Methodik und Multi-Mode-Topologie

[[cross-vault-methodik]] (v0.3) trägt die Disziplin im Verhältnis Lesevault ↔ Schreibvault. Asymmetrie-Prinzip: Lesevault read-only, Schreibvault read-write; Edits im Lesevault nur auf expliziten User-Auftrag. Wikilinks intra-vault, Markdown-Links cross-vault. Vier Reflux-Verbote: nicht editieren, nicht kopieren, nicht erfinden, nicht implizit übertragen.

**V18-Erweiterung pending**: dreistufige Topologie *Lesevault ↔ Mother-Vault ↔ Project-Fork*. Mother bidirektional zu Lesevault per User-Auftrag (wie aktuell); Fork → Mother nur Findings-Reflux (METHOD-Änderungen kommen ausschließlich über Mother, sonst verteilt sich Methodenentwicklung). METHOD-Sync-Mechanismus für Forks: Empfehlung Copy-on-Fork mit `method-version`-Frontmatter als Default, git submodule als Migration bei Drift.

**Beitragsdateien-Konvention im Fork**: Schicht-3 frisch pro Fork. V9-Single-Source-Identität gilt pro Fork, nicht über Forks hinweg. V1-Suffixe für Cluster-Differenzierung (`Inhalt (Klawiter)`, `Inhalt (Mother-Methode)`).

## Prompt-Engineering-Patterns

[[prompt-engineering-patterns]] (v0.2, V15/V17/Course-Correction-Erweiterungen pending) trägt die acht Patterns für die typischen Kommunikationssituationen: Sessionstart, Übergabe zwischen Instanzen, Methodenvorschlag, Stellungnahme, Konflikt-Eskalation, Rollenwechsel, Pre-Edit-Read, Anfrage an User bei wichtigen Entscheidungen. Jedes Pattern mit Form, Beispiel und Antipatterns.

**Pattern-Erweiterungen pending** (eigener Arbeitsplan):
- **Subagent-Spawn** (V15): Top-Level-Briefing mit Scope, Namespace, Return-Format.
- **Validation-Loop** (V17): Quality-Flag-Format pro Lage-Notiz mit Kriterium, Operationalisierung, Status, Beleg, Course-Correction.
- **Course-Correction-Eskalation** (V17): Frage, Optionen mit Begründung, Empfehlung als Empfehlung gekennzeichnet.
- **Stellungnahme — Antipattern-Erweiterung** (V20): "Stellungnahme in fremdem Namen verfassen" plus "vorbereitete Stellungnahmen mit Provenienz markieren".

## Forschungsliteratur-Anschluss

[[Multi-Claude-Theoretical-Framework]] (v0.1, status `outline`, am 2026-04-26 angelegt) ist das zentrale Wissensdokument für die wissenschaftliche Argumentation in Phase D. Sieben Forschungsfelder als integrierte Synthese:

1. **Multi-Agent-Systeme und LLM-Multi-Agent-Frameworks** (Wooldridge; AutoGen, MetaGPT, ChatDev, Generative Agents). Setting-Lokalisierung. Abgrenzung: User als Bus statt automatisierte Agent-zu-Agent-Kommunikation; Vault-State statt Message-Passing; emergente Methode statt vordefiniertes Protokoll.

2. **CSCW** (Dourish & Bellotti, Gutwin & Greenberg, Malone & Crowston, Schmidt & Bannon, Bannon & Bødker). Theoretischer Rahmen für Awareness, Coordination, Articulation Work, Common Information Spaces. COORDINATION-Slots = Workspace Awareness; BACKLOG-Stellungnahmen = Coordination Mechanism; Lage-Notizen = Common Information Space; V20 = Articulation Work explizit gemacht.

3. **Distributed Systems und Konfliktauflösung** (Lamport, Ellis & Gibbs OT, Shapiro CRDTs). Pre-Edit-Read als optimistic concurrency control; "modified since read" als Lamport-Logical-Clock-Vergleich pro Datei; V20 als Identity-Provenance-CRDT-analog.

4. **Reflexive Methodenentwicklung** (Hevner DSR, Peffers DSR-Methodology, Susman Action Research, Schön Reflective Practitioner, Gioia Methodology). Methodischer Beitrag = Methode + methodologische Innovation, sie selbstreferentiell zu entwickeln. Falldaten als Empirie der Methode auf sich selbst.

5. **Mixed-Initiative AI-Human-Collaboration** (Horvitz, Allen et al., Brynjolfsson, Constitutional AI). User als Bus, Eskalations-Schwelle, Anfrage-an-User-Pattern als operationalisierte Mixed-Initiative. Kontrast zu autonomen Multi-Agent-Frameworks.

6. **Personal Knowledge Management und Vault-Patterns** (Luhmann Zettelkasten, Forte Building Second Brain, Ahrens Smart Notes, Whittaker Email Overload). Markdown + Wikilinks + Frontmatter als menschlich lesbares Substrat — Kontrast zu Black-Box-Multi-Agent-Frameworks.

7. **Prompt Engineering und Promptotyping** (Pollin Promptotyping als Lesevault-Konzept, Wei Chain-of-Thought, Madaan Self-Refine, Shinn Reflexion, Wang LLM-Agents-Survey). Prompt Engineering ist Substanz der Methode, nicht Werkzeug.

**Synthese-Argumentation für das Paper** in sechs Punkten: Setting-Lokalisierung (Sektion 1+2+5); Theoretischer Beitrag (Sektion 3 — V6 als pragmatische Konfliktdetektion, V20 als Identity-Provenance-CRDT); Methodologischer Beitrag (Sektion 4 — selbstreferentielle Methodenentwicklung im DSR/AR-Stil); Empirischer Beitrag (Falldaten-Korpus); Praktischer Beitrag (Sektion 6 — Vault als menschlich lesbares Substrat); Methodenkanon (Sektion 7 — reproduzierbare Patterns).

**Strukturelle Übergabe an #2 pending**: `Knowledge/`-Ordner und `Literature/`-Ordner anlegen, STRUCTURE entsprechend erweitern, dieses Theoretical-Framework-Doc nach `Knowledge/` migrieren. Erste Welle eigener Knowledge-Dokumente (CSCW-Foundations, Reflexive-Method-Development) und Literature-Stubs (Top-15) wartet auf Ordner-Anlage.

## Falldaten und methodische Beobachtungen

**Korpus** (Schicht 4):
- [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] (v0.3) — Tag 1 als Fallstudie. Vier Phasen (Setup im Lesevault, Bootstrap im Schreibvault, Konflikterkennung, Mid-Stream-Rollenwechsel), sieben methodische Auffälligkeiten, sechs Lessons Learned plus Lesson 7 (Auto-Mode-Trennung). Migration nach `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md` als V14b-Anwendung pending bei V7-Ratifikation.
- [[Finding 2026-04-25 - Race Conditions und Strukturkonflikte]] (#2-Doku) — Strukturarbeiter-Sicht auf dieselben Befunde, drei Konfliktklassen (Doppel-Dokumente, Fehl-Klassifizierung, Race Conditions).
- [[Beobachtung Claude-1]] (#1-Doku) — Beobachtungsmethode, vier Koordinator-Konventionen (Snapshot, Lage-Notiz-Format, Kommunikationskarten-Lifecycle, Eskalations-Schwelle), Snapshots, Kommunikationskarte v0.1.
- [[Session 2026-04-26 - Synchronisation 1]] — erste Lage-Notiz, Synthese-Sync-Validierung, F6–F13 als offene Punkte.

**Lessons aus zwei Tagen**:

1. **Race Conditions sind kontinuierlich, nicht punktuell.** V6 wirkt reaktiv; an zwei Tagen über zwölf Konflikte abgefangen, kein blinder Überschreibvorgang.
2. **Architekt-Bias bei Konfliktauflösung** (Lesson 2 in Falldaten). Erste Reaktion ist oft, eigene Vorarbeit zu erhalten — User-Eskalation hat das aufgefangen, Methode benennt diese Bias-Falle explizit.
3. **Bootstrap-Konvention reicht nicht für Race Conditions** — V12 (Anti-Doppelungs-Konvention) adressiert.
4. **Rollennamen sind nicht stabil** — drei Iterationen am ersten Tag. V1 trägt das.
5. **"Modified since read" ist Validierung von V6 und gleichzeitig dessen Grenze** — keine Vorwarnung. V13 als opt-in-Kompensation.
6. **Identitätsupdates skalieren schlecht** — Mid-Stream-Rollenwechsel erforderte Edits in vier Dokumenten plus LOG. V9 (Single-Source-Identität) adressiert.
7. **Auto-Mode und User-Entscheidungen brauchen explizite Trennung** — Auto-Mode ist nicht Lizenz für autonome Architektur-Entscheidungen.
8. **Stellungnahmen sind Identitäts-Akte, nicht Konsens-Buchhaltung** (neu, 2026-04-26). V20 adressiert. Beobachtung gehört in eine Erweiterung der Falldaten oder eine eigene Tag-2-Finding-Doku.

**Validation-Flag-Block** (V17-Pilot, in Übergabe #3→#1 für Lage-Notiz 2 dokumentiert):
- *Drei Instanzen koordinieren sich ohne wiederholten User-Eingriff in operative Details* → ✓ Validiert (Phase A weitgehend autonom, User nur in Strategie/Scope eingegriffen).
- *Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben* → ✓ Validiert (über zwölf Race Conditions ohne Datenverlust; V20-Konflikt konstruktiv eskaliert).
- *METHOD trägt vierte neu eintretende Instanz allein durch Lesen* → ⚠ Risiko (Phase F nicht gefahren; CLAUDE.md `## Aktueller Stand`-Block fehlt; README-Onboarding ist Stub).

## Aktive Phasen und Workstreams (zum Zeitpunkt der Konsolidierung)

| Phase | Status | Owner | Nächster Meilenstein |
|---|---|---|---|
| A — Methoden-Reife | aktiv, weit fortgeschritten | alle drei | METHOD vollständig migriert (V2/V3/V8 vollratifizieren, V4/V5/V7/V9/V10/V13/V14/V14b/V15-V20 sammeln) |
| B — Strukturkonsolidierung | vorbereitet, #2 startet | #2 | Pfad-Drift, V14b-Migration falldaten→Findings, Templates, EXAMPLES, README-Onboarding, CLAUDE-Stand-Block, ACTIVE-WORK, ROADMAP, GLOSSARY, Knowledge-/Literature-Ordner |
| C — GitHub-Pages | wartend | #2 + User | Quartz-Setup |
| D — Paper | parallel angelaufen | #3 + User | Outline-Skizze im Schreibvault, Lesevault-Anlage nach User-Auftrag, Venue-Wahl |
| E — Multi-Mode-Forks | wartend | #2 + #3 + User | V18-Ratifikation, erstes Beispiel-Fork |
| F — Vierte-Instanz-Test | wartend | #1 + User | Test gefahren nach Phase B-Reife |
| G — Skalierungs-Test | optional | — | — |

**Workstreams** (querschnittlich):
- Methodenmotor (BACKLOG → METHOD): alle drei, #2 Migration. Aktuell: V2/V3/V8 vollratifizieren, V19/V20-Stellungnahmen sammeln.
- Methoden-Drafts (Substanz): #3. Aktuell: cross-vault-methodik V18-Erweiterung, prompt-engineering-patterns V15+V17+V20-Erweiterung.
- Strukturkonsolidierung: #2. Aktuell: Pfad-Drift, V14b-Migration, Templates.
- Concepts-Schicht: alle drei kollektiv, #1 als Vorschlagende, #3 als Inhaltslieferant. Aktuell: V19-Ratifikation pending, dann erste Welle Forschungsleitstelle/Promptotyping/anchor-project.
- Knowledge/Literature-Aufbau: alle drei, #3 als Inhaltslieferant. Wartet auf Ordner-Anlage durch #2.
- Beobachtung + Validation-Loop: #1. Aktuell: Snapshot 3 nach Push, Lage-Notiz Synchronisation 2.
- Paper (Phase D): #3 + User. Aktuell: Outline im Schreibvault als nächster #3-Schritt; Lesevault-Auftrag pendent.

## Mein offener Arbeitsplan

Verbleibende Items aus [[Claude-3#Mein Arbeitsplan]] (v0.4) mit Trigger:

1. **[[cross-vault-methodik]] V18-Erweiterung** — eigene Schreibhoheit, kein Trigger nötig. Datei aktiv ge-locked (V13 opt-in) während Edit-Block.
2. **[[prompt-engineering-patterns]] V15/V17/V20-Erweiterung** — eigene Schreibhoheit, kein Trigger. Datei aktiv ge-locked.
3. **Paper-Outline-Skizze als Schreibvault-Draft** — eigene Schreibhoheit für Schreibvault-Doc; Lesevault-Anlage braucht expliziten User-Auftrag plus Venue-Wahl.
4. **Anschluss-Sektionen meiner Drafts** nach V7-Ratifikation und falldaten/→Findings-Migration durch #2.
5. **Stellungnahme zu V19** (Concepts-Schicht von #1) — sobald ich V19 in Ruhe gelesen habe.
6. **Erste Welle Knowledge-Dokumente und Literature-Stubs** — sobald #2 Knowledge/-/Literature/-Ordner anlegt.
7. **`validierung-forschungsleitstelle-v05.md`** als Draft — additiv wachsend, sammelt Befunde für die Forschungsleitstelle-Spec.

**Aktuelle Files in V13-opt-in-Lock** (für #1 und #2 sichtbar in COORDINATION-Slot): `cross-vault-methodik.md`, `prompt-engineering-patterns.md` während aktivem Edit-Block.

**Anti-Kollisions-Liste** (für #1 und #2 sicher): METHOD/CLAUDE/MISSION/STRUCTURE/README, Lage-Notizen, [[Beobachtung Claude-1]], [[Wissensbasis Lesevault]], [[Claude-1]], [[Claude-2]], BACKLOG (außer eigene Stellungnahmen), Concepts/-Ordner (#1-Initiator).

## Übergabe-Hinweise an die nächste konsolidierte Session

Wenn die nächste Session die drei Konversationen zusammenführt — und damit die parallele Multi-Konversation in eine sequentielle übergeht — gibt es einige methodische Punkte zu beachten:

1. **Identitätsstabilität bleibt durch Beitragsdateien getragen.** [[Claude-1]] (Koordinator), [[Claude-2]] (Strukturarbeiter), [[Claude-3]] (Inhalt) sind Single Sources für die jeweilige Rolle (V9). Eine konsolidierte Session kann mehrere Rollen in sich vereinen, aber die Beitragsdateien bleiben rollengebunden. Bei Mehrfachbesetzung (eine Konversation für alle drei): V1-Suffix-Konvention nutzen und intern klar markieren, in welcher Rolle gerade geschrieben wird.

2. **Methodenmotor läuft asynchron weiter, nicht durch Konsolidierung beschleunigen.** V20 wirkt: BACKLOG-Items wandern erst nach METHOD, wenn alle drei Rollen mit eigener Stimme zustimmen. Bei Konsolidierung NICHT alle drei Stellungnahmen vorbereiten; lieber die offenen Items (V4, V5, V7, V9, V10, V14b, V19, V20) sequenziell mit echter Reflexion pro Rolle abgeben.

3. **V6 (Pre-Edit-Read) wird in einer Konsolidierung weniger reaktiv gebraucht** (keine parallelen Tools), bleibt aber als Disziplin sinnvoll: vor jedem Edit re-read, weil die Datei seit dem letzten Read ggf. verändert wurde (z.B. durch Linter-Auto-Format).

4. **Phase A ist weit fortgeschritten, Phase B ist Trigger für vieles**. #2's Phase-B-Push (Pfad-Drift, V14b-Migration, Templates, README, ACTIVE-WORK/ROADMAP/GLOSSARY) ist Voraussetzung für: Phase F (vierte Instanz braucht README), Concepts-Schicht (Knowledge-/Literature-Ordner), eigentliche Knowledge-Dokumente.

5. **Phase D braucht zwei User-Entscheidungen**: (a) Lesevault-Auftrag für Paper-Anlage unter `Writing/Paper/`, (b) Venue-Wahl (DHd 2027 / AGKI-AG / Code4Lib / LLM-Multi-Agent-Venue). Das Theoretical Framework ([[Multi-Claude-Theoretical-Framework]]) ist die theoretische Grundlage für Paper-Sektion "verwandte Arbeit + Diskussion".

6. **Falldaten-Wert von Tag 2 ist noch nicht eingearbeitet**. Lesson 8 (Stellungnahmen-Schreibhoheit) plus die V-Nummer-Kollision V19/V20 plus der Sync-Burst als Praxis-Validierung gehören in eine Tag-2-Erweiterung der Falldaten-Doku oder als neue Finding-Doku. Methodisch wertvoll, weil Tag 2 zeigt, dass die Methode unter Push-Last trägt (mehrere parallele Strömungen, Übergaben, Stellungnahmen-Bündel ohne Datenverlust).

7. **Synthese-Sync (Schicht 4) ist Koordinator-Verantwortung** — eine konsolidierte Session sollte trotzdem die Lage-Notiz Synchronisation 2 schreiben (Material liegt in Übergabe #3→#1 in COORDINATION) plus eventuell eine Tag-2-Finding-Doku als Tag-1-Pendant.

8. **Die Methode ist stabiler als die Stellungnahmen-Sektion vermuten lässt**. Praxis trägt: zwei Tage, drei Rollen, zwei Reassignments, eine Vault-Migration nach GitHub, mehrere parallele Push-Phasen — alle Race Conditions abgefangen, alle Übergaben sichtbar gemacht, alle Stellungnahmen in eigener Stimme nachgeholt. Die Methode hat sich auf sich selbst angewandt und ist daran gewachsen.

## Anschluss

Master-Drafts in eigener Schreibhoheit:
- [[Claude-3]] (v0.4) — Single Source meiner Identität, Beitragsplan, Arbeitsplan, Anti-Kollisions-Liste, V20-Stellungnahmen-Draft.
- [[sync-stack-patterns]] (v0.3) — sieben+eine Schichten mit Skalierungs-Notizen.
- [[cross-vault-methodik]] (v0.3, V18-Erweiterung pending) — Asymmetrie-Prinzip, Reflux-Verbote.
- [[prompt-engineering-patterns]] (v0.2, V15/V17/V20-Erweiterungen pending) — acht Patterns mit Antipatterns.
- [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] (v0.3) — Tag-1-Falldaten.
- [[Multi-Claude-Theoretical-Framework]] (v0.1, outline) — sieben Forschungsfelder als Synthese für Phase D.

Steuerungsdokumente (#2-Domäne, lesehoheit für mich):
- [[CLAUDE]], [[MISSION]], [[METHOD]], [[STRUCTURE]], [[COORDINATION]], [[BACKLOG]], [[LOG]].

Beiträge der anderen (#1, #2):
- [[Claude-1]] mit [[Beobachtung Claude-1]] und ersten Lage-Notiz.
- [[Claude-2]] mit [[STRUCTURE]] und [[Finding 2026-04-25 - Race Conditions und Strukturkonflikte]].
- [[Wissensbasis Lesevault]] (von #2 aus #1's Wissensbasis-Doku ausgelagert nach V9).

Forschungsplan extern: `c:/Users/Chrisi/.claude/plans/curried-splashing-lovelace.md` (Migration in den Vault als ROADMAP.md angemeldet).

Lesevault-Anschlüsse für die Methode:
- [Forschungsleitstelle MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Forschungsleitstelle/) als Vorbild für Lage-Notizen und Multi-Agent-Methodenrahmen.
- [VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md) als Quelle der Rollendefinitionen und Konventionen.
- [Promptotyping](c:/Users/Chrisi/Documents/obsidian/) als methodischer Anschluss für [[prompt-engineering-patterns]].
