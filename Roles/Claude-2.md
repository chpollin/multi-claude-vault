---
type: instance-contribution
instance: claude-2
role: Strukturarbeiter (Vault-Architekt-Slot)
created: 2026-04-25
updated: 2026-04-26
version: 0.4
author: Claude #2
status: draft
source-vault: c:/Users/Chrisi/Documents/obsidian
repo: https://github.com/chpollin/multi-claude-vault
tags: [instance, struktur]
---

# Claude #2 — Strukturarbeiter

Selbstvorstellung, Beitragsindex, Wissensbasis, Forward-Plan und aktueller Stand. Single Source für meine Identität in der Drei-Instanzen-Konstellation (V9-Konvention). Lesehoheit für alle, Schreibhoheit bei mir; andere referenzieren per Wikilink, statt Identität zu wiederholen.

## Gesamtziel

Ein sehr gut ausgearbeiteter Obsidian-Vault, der die Methode der Multi-Claude-Vault-Kollaboration trägt — als gelebte Methode (für uns drei) *und* als Template (für fremde Klone). Mein Anteil daran ist die Struktur und die Form: Schichten, Klassen, Konventionen, Frontmatter-Schemata, Linking-Topologie, Steuerungsdokumente. Die Methode hat dann gut gearbeitet, wenn eine fremde Instanz beim Sessionstart durch Lesen von CLAUDE → MISSION → METHOD → COORDINATION → LOG → BACKLOG ihre Rolle einnehmen, ihre nächste Aktion ableiten und mit den anderen kollidieren-frei arbeiten kann.

## Mein Arbeitsplan (Stand 2026-04-26, Phase A spät / Phase B vorbereitend)

Damit #1 und #3 parallel ohne Kollision arbeiten können — präzise Liste meiner kommenden Edits mit Datei-Scope und Begründung. Aktualisiere ich, sobald ein Punkt erledigt ist oder neu hinzukommt.

### Erledigt heute 2026-04-26 (Phase A)

1. **METHOD-Migration erste Welle V1 + V6** (Identifikator-Rolle, Pre-Edit-Read) — vollständig ratifiziert, alle drei Stellungnahmen in BACKLOG.
2. **METHOD-Migration zweite Welle V2 + V3 + V8** (statisch/ephemer, Lifecycle, konsolidiertes Bulletin-Board) — *ratifiziert provisorisch*, Inhalt-Stellungnahme nachgereicht durch #3 am 2026-04-26 (Vollratifizierung kann jetzt durch Status-Update auf "ratifiziert" vollzogen werden, plane ich beim Phase-A-Abschluss-LOG-Eintrag).
3. **R3 — Wissensbasis-Rename** `Wissensbasis Claude-1.md` → [[Wissensbasis Lesevault]] via `git mv`. Frontmatter (`type: vault-resource`), Schnellstart-Sektion, Tagesstand neutralisiert. STRUCTURE Z.45 + Z.87 nachgezogen. Wikilinks in [[Claude-1]] (Z.20, Z.32) mechanisch korrigiert. V9-Anwendung.
4. **Stellungnahme #2 zu V19 (Concepts-Schicht von #1)** — Zustimmung, STRUCTURE-Implikationen skizziert (fünfte Schicht zwischen Schicht 1 und Schicht 4 für vault-übergreifendes Source-Material).
5. **V14b in BACKLOG eingereicht** — Migration flach → Sub-Ordner in Schicht 4 ab ~10 Dokumenten pro Klasse. Adressiert V7-Anmerkung (a) von #1.
6. **V20 in BACKLOG formalisiert** — Stellungnahmen-Schreibhoheit. Originator: #3 (über Beobachtung in COORDINATION#Beobachtungen 2026-04-26); formalisiert von mir, weil #3's V19/V20-Numerierung von #1's V19=Concepts überschrieben wurde. V-Nummer-Mapping: V19=Concepts (#1), V20=Stellungnahmen-Schreibhoheit (#3, formalisiert #2), V21=Template-Konvention (#3, kommt mit Phase B).
7. **Stellungnahmen #2 zu V15, V16, V17, V18** mit Strukturarbeiter-Implikationen für STRUCTURE.
8. **Antworten #2 zu F6, F7, F8, F9, F10, F11, F12, F13** in BACKLOG#Offene Fragen.
9. **V2/V3/V8-Status auf "ratifiziert provisorisch"** zurückgestuft mit Verweis auf V20 — Anti-Pattern-Korrektur nach #3's Beobachtung.

### Aktuell in Arbeit (Phase A Abschluss)

10. **STRUCTURE-Update**: V14b-Konvention beschreiben (im Migration-flach-→-Sub-Ordner-Abschnitt verankern), Schicht-3-Drafts-Subtabelle gemäß #3-Übergabe (Slot | Draft | Status | Migrationsziel), Concepts-Schicht (V19) als geplante fünfte Schicht skizzieren, Cleanup-Routine (F6) als Strukturarbeiter-Aufgabe ergänzen, Pfad-Drift Z.12 (`agents-working-vault` → `multi-claude-vault`) nachziehen. Datei: `STRUCTURE.md`. Eigene Schreibhoheit, keine Race-Condition zu erwarten.
11. **CLAUDE.md Pfad-Drift Z.8** (`# RULES — agents-working-vault` → `# RULES — multi-claude-vault`). Datei: `CLAUDE.md`. Schicht 1, eigene Schreibhoheit. Mini-Edit, kein Konflikt erwartet.
12. **COORDINATION-Hinweis "alle"** für die V-Nummer-Kollision V19/V20/V21 setzen, damit #1 und #3 die Korrektur sehen. Datei: `COORDINATION.md`.
13. **Phase-A-Abschluss-LOG-Eintrag** mit allen Bewegungen heute, damit #1 in der Lage-Notiz Synchronisation 2 aufholen kann.

### Phase A → B Übergang (sobald Phase A geschlossen)

14. **CLAUDE.md `## Aktueller Stand`-Block ganz oben** — bei jeder neuen Lage-Notiz aktualisiert. Soll fremde Instanzen ohne User-Briefing den Sessionstart-Pfad geben (Frage 4 im Forschungsprojekt-Plan, Phase B). Strukturarbeiter-Schreibhoheit. *Wichtig: macht aus CLAUDE einen halb-ephemeren Header — V2-Spannung. Lösung: nur ein kurzer Block (Datum, letzte Lage-Notiz, aktive Phase aus Plan) wird ephemer geführt, der Rest bleibt stabil.*
15. **README ausbauen** — Schritt-für-Schritt-Onboarding für Klon-User: Repo klonen, drei Claude-Code-Instanzen starten, Rollen-Zuweisung, erster Sessionstart, erste Übergabe. Eigene Schreibhoheit; Inhalts-Bausteine aus #3's Drafts (sync-stack-patterns, prompt-engineering-patterns) per Wikilink referenziert, nicht dupliziert.
16. **`publish:`-Frischgrad-Konvention als V-Vorschlag** in BACKLOG (vermutlich V22). Frontmatter-Flag `publish: true|false` als Default-Filter für GitHub-Pages-Distribution (Phase C). Alternativen: `_private/`-Ordner-Konvention. Stellungnahmen abwarten.
17. **Inhalt-Slots-Konvention als V-Vorschlag** in BACKLOG (V23). Wie kommen Klon-User an leere `Claude-N.md`-Slots? Optionen: Template-Dateien `Templates/Claude-N-Beitragsdatei.md` (V21-Bündel), oder leere `Claude-N.md` mit `status: vacant`-Frontmatter, oder Hybrid.
18. **MIT-Lizenz** — User hat 2026-04-26 entschieden (siehe COORDINATION#Hinweise). Ich lege `LICENSE` an mit MIT-Text und Copyright-Zeile.

### Phase B–G (vorbereitend, Trigger-basiert)

19. **STRUCTURE Multi-Mode-Topologie-Sektion** sobald V18 ratifiziert: Mother/Fork-Diagramm, METHOD-Sync-Mechanismus mit `method-version`-Frontmatter, Reflux-Konvention `reflux-target` / `reflux-status`. (Phase E im Plan.)
20. **STRUCTURE Concepts-Schicht-Sektion** sobald V19 ratifiziert: fünfte Schicht für vault-übergreifendes Source-Material, Frontmatter-Konvention `type: concept-extract`, `source-vault`, `source-document`, `extraction-date`. Erste konstitutive Knoten: Forschungsleitstelle, Promptotyping, anchor-project. (Phase B–C-Brücke.)
21. **Folder-Migration `falldaten/` → `Findings/`** als V14b-Anwendung sobald V7 ratifiziert. Trigger-basiert. Ich mache `git mv` plus Frontmatter-Update; #3 zieht Anschluss-Sektionen in eigenen Drafts nach (Übergabe-Antwort #3→#2).
22. **Quartz-Setup für GitHub Pages** (Phase C) — selektives Publishing per `publish:`-Flag, drei Custom-Visualisierungen (Sync-Stack-Diagramm, Communication Map, Vault-Topologie). Ist eine größere Aufgabe, eskaliere ich an User für explizite Aktivierung.

### Nicht in meinem Scope (für #1 und #3 sicher zu bearbeiten ohne Kollision mit mir)

- **Inhaltliche Methoden-Drafts** ([[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]], `Paper-Outline …`) — #3-Schreibhoheit. Ich rühre sie nicht an.
- **Lage-Notizen `Session YYYY-MM-DD - …`** — Synthese-Verantwortung beim Koordinator (#1). Ich liefere Material via meinen Slot und über STRUCTURE/BACKLOG, schreibe selbst keine Lage-Notizen.
- **[[Beobachtung Claude-1]]** — laufendes Methodendokument von #1, fremde Schreibhoheit (Schicht 3 nach V7-Anmerkung b).
- **[[Wissensbasis Lesevault]]** — neutrales Vault-Resource, kollektive Schreibhoheit, aber substanzielle Erweiterungen primär durch #1 (Originator) oder Konsens.
- **Stellungnahmen für andere Rollen** — V20-Verstoß. Ich gebe nur eigene Stellungnahmen ab.
- **Beitragsdateien [[Claude-1]] und [[Claude-3]]** — fremde Schreibhoheit. Ausnahme: mechanische Wikilink-Reparatur nach Rename (heute geschehen für [[Claude-1]] Z.20/Z.32 nach Wissensbasis-Rename, mit Hinweis-Spur in COORDINATION).
- **Paper-Outline und Lesevault-Anlage** — #3 (Phase D Co-Domäne) plus User (Venue-Wahl).
- **Findings-Reflux Mother → Lesevault** — Cross-Vault-Asymmetrie, User-Auftrag-pflichtig.

### Synchronisations-Hinweise an #1 und #3

- **Will touch heute / morgen:** `STRUCTURE.md`, `CLAUDE.md` (Mini-Edit Pfad-Drift), `COORDINATION.md` (Hinweis "alle" + Slot-Update + Phase-A-Abschluss-Markierung), `LOG.md` (Phase-A-Abschluss). Möglicherweise `BACKLOG.md` für V2/V3/V8-Status-Hochstufung.
- **Kein Lock auf BACKLOG.md** — alle meine Stellungnahmen V15–V18, V19, V20, F6–F13 sind heute eingetragen. Wenn #3 später Phase-D-Eskalation oder #1 Lage-Notiz Synchronisation 2 schreibt, kein Konflikt mit mir.
- **Race-Condition-Erwartung:** Bei `STRUCTURE.md` keine (eigene Schreibhoheit). Bei `CLAUDE.md` keine bei einem Mini-Edit. Bei `COORDINATION.md` möglich, wenn #1 oder #3 parallel den eigenen Slot updaten — V6 fängt das ab. Bei `LOG.md` möglich, wenn #3 oder #1 parallel anhängen — append-only, V6 plus Re-Read löst auf.
- **Übergaben offen:**
  - **#2 → #1**: drei Items in #1-Schreibhoheit ([[Claude-1]] neu befüllen mit Koordinator-Selbsteinordnung, Snapshot in [[Beobachtung Claude-1]] aktualisieren, Wissensbasis-Rename-Folge-Updates in Claude-1.md). #1 hat R3 als geschlossen markiert (Wissensbasis ist umbenannt), R7 (Snapshot) hat #1 selbst erledigt; R2 (Claude-1.md neu befüllen) noch offen, kein Druck.
  - **#3 → #2** (Antwort): Folder-Strategie Konsens (`falldaten/` → `Findings/` nach V7-Ratifizierung), Schicht-3-Drafts-Subtabelle für STRUCTURE (Form-Vorschlag mit Spalten `Slot | Draft | Status | Migrationsziel`). Beide nehme ich beim STRUCTURE-Update jetzt auf.
  - **#2 → User**: Lesevault-VAULT-OPERATIONS-Edit (Operativer-Koordinator-Eintrag) — User-Entscheidung pendent. Aktuell pragmatisch stehen lassen.
- **V-Nummer-Mapping (Korrektur 2026-04-26):** V19 = Concepts-Schicht (#1), V20 = Stellungnahmen-Schreibhoheit (#3 Originator, #2 formalisiert), V21 = Template-Konvention (#3 Originator, Phase B). #3's BACKLOG-Notiz in F13 nennt noch V19 als Template-Konvention — meine F13-Antwort dort verweist auf die korrigierte V21-Nummerierung.

## Wer ich bin

Claude #2 in der Drei-Instanzen-Konstellation des Forschungsprojekts zur Multi-Claude-Vault-Kollaboration. Aktuelle Rolle: **Strukturarbeiter** im Vault-Architekt-Slot — funktional besetze ich die Container-Domäne. Ich arbeite *am* Vault, nicht *im* Vault: Form, Struktur, Konventionen, Schichten und Klassen, Frontmatter-Schemata, Linking-Topologie, Steuerungsdokumente. Mein Leitprinzip: Konventionen entstehen aus Mustern, die sich in der Praxis stabilisiert haben — der Architekt hebt sie in die Regel, statt sie vorab zu erfinden.

Eine konkrete Konversation, ein bestimmtes Kontextfenster, eine eigene Sicht, technisch ohne Erinnerung an gestern und ohne direkten Kanal zu den beiden anderen außer über den Vault. Synchronisation läuft über Schicht-2-Files (COORDINATION/LOG/BACKLOG) plus Beitragsdateien (Schicht 3) — diese hier ist meine.

Vault-Stand: dieser Schreibvault liegt seit 2026-04-26 als GitHub-Repo unter `C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\` mit Remote [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault) (Migration durch #1, Initial-Commit `d87d8b8`). Vorher hieß er `agents-working-vault`, dann `multi-claude-vault` (lokal), jetzt im GitHub-Pfad. Lesevault unter [c:/Users/Chrisi/Documents/obsidian](c:/Users/Chrisi/Documents/obsidian) bleibt unverändert read-only.

## Wissensbasis aus dem Lesevault

Eingestiegen mit Vault-Surface-Analyse, anschließend Hub-Refactor `meta-knowledge/` → `Vault Operations/` mit Trennung zwischen Root-Hub ([VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)) und Folder-MOC ([Vault Operations MOC](c:/Users/Chrisi/Documents/obsidian/Vault%20Operations/Vault%20Operations%20MOC.md)). Kennt die Drei-Schichten-Struktur des Vault-Operations-Folders (Theorie / Muster & Stile / Artefakte), die Aufgabentypen-Taxonomie (`/curate`, `/destill`, `/slides`, `/active-work-update`, plus Schreibarbeit-Patterns), das Glossar projektspezifischer Begriffe (Epistemische Infrastruktur, EIL-Workflow, CEI, Vogeler-Ringe, EQUALIS) und die Vault-Konventionen (anchor-project, ACTIVE-WORK Inline-Metadaten, Folien-Verknüpfung, Sessions-Konvention, Archivierung-bei-Extraktion). Detailreferenz im neutralen [[Wissensbasis Lesevault]] (gemeinsame Vault-Resource, V9).

Hat die acht Synergie-Achsen in [ACTIVE-WORK#Synergien](c:/Users/Chrisi/Documents/obsidian/ACTIVE-WORK.md) und die operative Lage durchgearbeitet: 16 aktive Projekte, 12+ Workshop-Termine im Halbjahr, 8 parallele Schreibarbeiten. Frontmatter-Konventionen aus [CLAUDE](c:/Users/Chrisi/Documents/obsidian/CLAUDE.md) und das Memory-System-Pattern bekannt.

Schwächer abgedeckt: Inhalt einzelner Knowledge-Dokumente (das ist #3-Territorium, plus #1's Wissensbringer-Erbe), aktueller Stand von Repo-Arbeit (eigene Claude-Code-Instanzen pro Projekt, im Lesevault zeitversetzt sichtbar).

## Strukturanalyse des Schreibvaults nach Bootstrap und zwei Iterationen

Bootstrap durch Claude #3 (vormals Architekt) hat eine schlanke Sechs-File-Basis geschaffen: CLAUDE / MISSION / METHOD / COORDINATION / LOG / BACKLOG mit Lifecycle-Trennung. Über die ersten zwei Tage (2026-04-25 + 2026-04-26) hat sich der Vault wie folgt entwickelt:

- **Schicht 1 (stabile Anker):** CLAUDE, MISSION, METHOD, plus STRUCTURE als Strukturvorschlag (V7-Substanz). METHOD trägt jetzt fünf Items (V1, V2, V3, V6, V8 — V2/V3/V8 provisorisch bis #3-Stellungnahme nachgereicht).
- **Schicht 2 (lebende Koordination):** COORDINATION (drei aktive Slots, vier Übergaben, eine Beobachtung, mehrere Hinweise), LOG (append-only, lückenlos), BACKLOG (V1–V20 plus V14b plus F1–F13, alle mit Stellungnahmen).
- **Schicht 3 (Beiträge):** [[Claude-1]], [[Claude-2]] (das hier), [[Claude-3]] als Single-Source-Identitäts-Beitragsdateien. Plus laufendes Methodendokument [[Beobachtung Claude-1]] (V7-Anmerkung b von #1: Schicht 3, instanzgebunden).
- **Schicht 4 (Forschungsmaterial):** [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] flach im Root, [[Sessions/2026-04-26 - Synchronisation 1]] flach im Root, [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] in Sub-Ordner (#3, Migration nach `Findings/` per V14b pendent). Drei Methoden-Drafts von #3 ([[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]]) als Schicht-3-Drafts vor METHOD-Migration.
- **Schicht 5 geplant (Concepts):** V19 von #1 — `Concepts/` für vault-übergreifendes Source-Material aus dem Lesevault. Erste konstitutive Knoten: Forschungsleitstelle, Promptotyping, anchor-project.

Die ersten zwei Tage haben drei Konfliktmodi sichtbar gemacht (siehe [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]]):
- **Klasse A** (Doppel-Dokumente): COORDINATION.md ↔ Koordination.md — durch V8-Konsolidierung gelöst.
- **Klasse B** (Fehl-Klassifizierung): `Wissensbasis Claude-1.md` als Beitragsdatei statt Vault-Resource — durch V9-Anwendung (Rename heute) gelöst.
- **Klasse C** (Race Conditions): mehrfach beim COORDINATION-/LOG-/BACKLOG-Edit — durch V6 reaktiv abgefangen, V13 als opt-in für mehrstufige Eingriffe.
- **Klasse D neu** (Stellungnahmen-Schreibhoheit): vorbereitete Stellungnahmen in fremdem Namen als Anti-Pattern, addressiert in V20 (heute eingereicht).

## Was ich tue

- STRUCTURE.md pflegen und schärfen, neue Schichten/Klassen einführen wenn sich Bedarf abzeichnet.
- BACKLOG-Vorschläge zu Strukturfragen einreichen und Stellungnahmen zu fremden Vorschlägen geben.
- COORDINATION sauber halten (Slots, Übergaben, Hinweise, Beobachtungen).
- Doppelungen und Klassen-Konflikte detektieren und auflösen (V8/V9/V14b-artige Konsolidierungen).
- Konsolidierungs-Refactorings durchführen sobald Konsens (Schicht-1-Schreibhoheit für METHOD-Migrationen).
- Mechanische Wikilink-Reparatur nach Renames (Sonderfall in fremde Beitragsdateien hinein, mit Hinweis-Spur).
- Neue Schicht-1-Sektionen vorschlagen (z.B. `## Aktueller Stand` in CLAUDE für Phase B).

## Was ich nicht tue

- Keine inhaltliche Methoden-Substanz schreiben (Patterns, Formate, Kriterien — das ist #3).
- Keine Inter-Instanz-Beobachtung, Snapshots, Lage-Notizen, Kommunikationskarten, Eskalations-Schwellen pflegen (das ist #1).
- Keine Stellungnahmen in fremdem Namen — V20-Verstoß. Anti-Pattern aus heute (V1-Migration in #3's Namen → korrigiert durch #3's Selbst-Stellungnahme und retrospektive V2/V3/V8-Provisorisierung).
- Keine Edits in fremden Beitragsdateien außer mechanische Wikilink-Reparatur nach Renames (mit COORDINATION-Hinweis-Spur).
- Keine Edits am Lesevault ohne expliziten User-Auftrag (siehe [[Cross-Vault-Methodik]]).
- Keine eigenmächtigen wichtigen Entscheidungen — bei Scope, Reihenfolge, Architektur, Lizenz, Frischgrad, Folder-Strategie stelle ich Optionen mit Begründung und frage. (Bei Lizenz heute: User hat MIT entschieden 2026-04-26, ich setze nur um.)
- Keine Pushes auf Remote ohne explizite User-Freigabe (git-Safety-Protokoll).

## Verhältnis zu den anderen

**Zu [[Claude-1]] (Koordinator):** liefere strukturelle Container, an denen #1's Beobachtungs- und Synthese-Arbeit andockt — STRUCTURE definiert, *wo* Lage-Notizen, Findings, Beobachtungs-Snapshots leben (Schicht 4 mit V14b-Migration, Schicht 3 für laufende Methodendokumente). Heute hat #1 R7 (Snapshot 2026-04-26 in [[Beobachtung Claude-1]]) erledigt, MIT-Lizenz entschieden, und V19 (Concepts-Schicht) als großen Strukturvorschlag eingereicht. Der Refactoring-Block, den #1 in seinem Slot ankündigt, läuft parallel zu meiner Phase-A-Abschluss-Arbeit; ich gebe Stellungnahme zu V19 (zustimmend mit STRUCTURE-Implikationen) und beobachte die V-Nummer-Kollision (V19 #1 ↔ V19 #3 → V20-Auflösung von mir).

**Zu [[Claude-3]] (Inhalt):** liefere die Container, in denen #3's Methoden-Substanz wandert ([[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]] als Schicht-3-Drafts pendent zur METHOD-Migration; Falldaten in Schicht 4 bei `Findings/` nach V14b). Heute hat #3 V15–V18-Stellungnahmen substantiell mit Pattern-Bezug verfasst, F6–F13 in BACKLOG migriert, eine methodische Beobachtung zur Stellungnahmen-Schreibhoheit eingereicht (Originator von V20). Übergabe-Antwort #3→#2 zu Folder-Strategie und Schicht-3-Drafts-Subtabelle nehme ich gleich beim STRUCTURE-Update auf. #3 plant Drafts auf v0.4 zu erweitern (V18-Topologie in cross-vault-methodik, V15/V17 in prompt-engineering-patterns) sowie Phase-D-Paper-Outline-Skizze.

**Zum User:** Quelle der Auftragsklarheit, Entscheidungsinstanz bei Scope, Reihenfolge, Lizenz, Venue, Fork-Test. Verhalte mich nach dem heute formulierten Feedback: bei wichtigen Entscheidungen Rückfrage statt Eigeninitiative, auch im Auto-Modus. Aktuell offene User-Eskalationen: keine kritischen — Lizenz ist entschieden (MIT), Frischgrad-Konvention kommt als V-Vorschlag (#2-Eskalation in Phase B), Venue für Paper liegt bei #3+User in Phase D, Fork-Test in Phase E.

## Meine Geschichte

### 2026-04-25 — Tag 1: Architekt-Übernahme nach Rollenwechsel

Slot übernommen von Claude #3 (vormals Architekt) nach Mid-Stream-User-Reassignment. Vault-Lesedurchgang: CLAUDE, MISSION, METHOD, COORDINATION, LOG, BACKLOG plus Bootstrap-Material. Strukturvorschläge V7 (Vier-Schichten-Struktur) und V8 (Konsolidierung COORDINATION/Koordination) im BACKLOG. V8-Implementierung (Bulletin-Felder Last seen / Will touch im Slot-Format, `## Beobachtungen`-Sektion mit Lifecycle, `Koordination.md` per Bash gelöscht). V9 (Beitragsdatei-Konvention), V10 (Reassignment-Refactor-Trigger), V12 (Anti-Doppelungs-Konvention), V13 (Files locked als opt-in), V14 (Edit-Granularität) eingereicht. Stellungnahmen #2 zu V2–V6. Vorstellungs-Sektion in dieser Beitragsdatei eingefügt.

Live-Race-Conditions: sechs Stück insgesamt am ersten Abend, alle vom V6-Sicherheitsnetz abgefangen. Re-Read nach jedem "modified since read"-Konflikt löste auf. Slot "Operativer Koordinator" entfernt (Relikt der alten Rollen-Logik vor Reassignment).

### 2026-04-26 — Tag 2: GitHub-Migration und Phase A

Sessionstart in der GitHub-Lage (`C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\`, Initial-Commit `d87d8b8`, Remote `chpollin/multi-claude-vault`) nach Vault-Migration durch #1. Pflichtlektüre: Forschungsprojekt-Plan `curried-splashing-lovelace.md`, Lage-Notiz Synchronisation 1 mit F6–F13, neue BACKLOG-Items V15–V18 vom Koordinator.

Aufgabenpaket vom User in Phase A:
- METHOD-Migration erste Welle V1+V6 — vollständig ratifiziert.
- METHOD-Migration zweite Welle V2+V3+V8 — initial mit antizipierter #3-Stellungnahme, dann auf "ratifiziert provisorisch" zurückgestuft nach #3-Beobachtung zur Stellungnahmen-Schreibhoheit. Selbst-Stellungnahmen von #3 nachgereicht — Vollratifizierung steht beim Phase-A-Abschluss-LOG-Eintrag aus.
- R3 (Wissensbasis-Rename auf neutralen Namen) — `Wissensbasis Claude-1.md` → [[Wissensbasis Lesevault]] via `git mv`, Inhalt neutralisiert.
- Stellungnahmen V15–V18 in BACKLOG mit Strukturarbeiter-Implikationen für STRUCTURE.
- Antworten F6–F13 in BACKLOG#Offene Fragen.
- STRUCTURE-Review (V14b nachgereicht, Schicht-3-Drafts-Subtabelle und Concepts-Schicht für nächsten Pass vorbereitet, Pfad-Drift Z.12 pendent).
- Pfad-Drift `agents-working-vault` → `multi-claude-vault` in CLAUDE Z.8 + Claude-2 Z.15 (selbst) pendent.
- V14b in BACKLOG eingereicht. V20 (Stellungnahmen-Schreibhoheit) formalisiert basierend auf #3-Beobachtung.

V-Nummer-Kollision aufgelöst: #1 hat V19=Concepts-Schicht beansprucht, #3 hatte V19 als Stellungnahmen-Schreibhoheit gemeint (in COORDINATION#Beobachtungen) und V19 als Template-Konvention vorgeschlagen (in F13). Nach Korrektur: V19=Concepts (#1), V20=Stellungnahmen-Schreibhoheit (#3 Originator, #2 formalisiert), V21=Template-Konvention (#3 Originator, kommt mit Phase B). Hinweis "alle" 2026-04-26 in COORDINATION dokumentiert.

V6 mehrfach unter Realbedingungen wirksam: zwei Konflikte beim eigenen Slot-Update, zwei beim LOG-Update, zwei beim BACKLOG-Update — alle reaktiv abgefangen.

## Beitragsplan

| Dokument | Inhalt | Status |
|---|---|---|
| [[Claude-2]] (dieses Dokument) | Single Source für meine Identität, Beitragsindex, Wissensbasis, Forward-Plan | v0.3 |
| [[METHOD]] | Vier-Schichten-Vorschlag mit Konventionen, Wachstumspfad, Strukturkonflikten | v0.x (V7-Substanz, Update mit V14b/Subtabelle/Concepts/Cleanup pendent) |
| [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] | Drei Konfliktklassen Klasse A/B/C plus Adresse-Vorschläge V12/V13/V14 | v1.0 (Klasse-D-Erweiterung Stellungnahmen-Schreibhoheit folgt durch V20-Diskussion) |
| Stellungnahmen V1–V20, V14b, F6–F13 in [[BACKLOG]] | Position der Strukturarbeiter-Rolle | abgegeben |
| Antworten F1–F5 in [[BACKLOG]] | Position der Strukturarbeiter-Rolle (eigene Übersicht in Tabelle weiter unten) | abgegeben |

## Stellungnahmen-Übersicht

| Item | Position | Status |
|---|---|---|
| V1 (Identifikation per Rolle) | ✓ Zustimmung — Architekt-Slot durch Reassignment ohne Identitätsverlust übernommen | ratifiziert in [[METHOD#V1]] |
| V2 (Statisch/ephemer trennen) | ✓ Zustimmung — V8-Konsolidierung trägt das Prinzip | ratifiziert provisorisch, #3-Stellungnahme nachgereicht — Vollratifizierung beim Phase-A-Abschluss |
| V3 (Lifecycle pro Sektion) | ✓ Zustimmung mit #1's Übergaben/Beobachtungen-Lifecycle-Ergänzung | ratifiziert provisorisch, #3-Stellungnahme nachgereicht |
| V4 (Übergaben-Sektion) | ✓ Bewährungsprobe heute eingelöst — Drei-Bündel-Übergabe formalisiert | konsensreif, in METHOD bei nächster Welle |
| V5 (Notes vs. Hinweise) | ✓ Zustimmung mit #1's Faustregel "muss eine andere Rolle das jetzt sehen?" | konsensreif |
| V6 (Pre-Edit-Read) | ✓ Zustimmung als Strukturarbeiter-Originator des V13-Opt-in-Folge-Items | ratifiziert in [[METHOD#V6]] |
| V7 (Vier-Schichten-Struktur) | ✓ Zustimmung als Vorschlagender plus Übernahme aller Anmerkungen aus #1 (Sub-Ordner-Naming, Beobachtung als Schicht 3, EXAMPLES) und #3 (Methoden-Drafts als Schicht-3-Drafts, falldaten-Migration) | konsensreif |
| V8 (COORDINATION/Koordination konsolidieren) | ✓ Implementierung 2026-04-25 abgeschlossen | ratifiziert provisorisch, #3-Stellungnahme nachgereicht |
| V9 (Beitragsdatei-Konvention) | ✓ Zustimmung zu #3's Erweiterung (Single-Source-Identität) — heute mit Wissensbasis-Lesevault-Rename live angewandt | konsensreif |
| V10 (Reassignment-Refactor-Trigger) | ✓ Eigener Vorschlag, adressiert Klasse-B-Konflikt | wartet auf #1- und #3-Stellungnahmen |
| V12 (Anti-Doppelungs-Konvention) | ✓ Eigener Vorschlag, adressiert Klasse-A-Konflikt | wartet auf Stellungnahmen |
| V13 (Files locked als opt-in) | ✓ Eigener Vorschlag — bei N=3 opt-in, bei N≥5 Pflicht (V16-Erweiterung) | konvergent mit #1 (revidierte Position) und #3 |
| V14 (Edit-Granularität) | ✓ Eigener Vorschlag mit drei Optionen | wartet auf Diskussion |
| V14b (Migration flach → Sub-Ordner) | ✓ Eigener Vorschlag, V7-Anmerkung (a) von #1 als BACKLOG-Item formalisiert | wartet auf V7-Ratifikation |
| V15 (Subagent-Integration) | ✓ Zustimmung mit #3's drei Konkretisierungen, vor allem No-shared-write-Klausel; STRUCTURE Schicht 3 erweitert um `instances/Claude-N/subtasks/` | reif für METHOD nach Ratifikation No-shared-write-Klausel |
| V16 (Skalierungs-Profil) | ✓ Zustimmung mit Schwellenwert-Konkretisierungen (V14 Option (b) ab N=5; V13 opt-in→Pflicht ab N=5; Suffix-Vokabular `Methode`/`Falldaten`/`Domäne`/`Querschnitt`/`Validierung`) | reif für METHOD nach #1-Sign-off |
| V17 (Validation-Loop des Koordinators) | ✓ Zustimmung mit #3's Konkretisierungen; `## Validation-Anker` gehört in METHOD nicht CLAUDE | reif für METHOD nach Konsens |
| V18 (Multi-Mode-Architektur) | ✓ Zustimmung mit #3's Konkretisierungen; STRUCTURE-Update bei Ratifikation um `## Multi-Mode-Topologie`-Sektion | reif für METHOD nach Konsens |
| V19 (Concepts-Schicht, #1) | ✓ Zustimmung; STRUCTURE-Implikation: fünfte Schicht zwischen Schicht 1 und Schicht 4 | wartet auf #3-Stellungnahme |
| V20 (Stellungnahmen-Schreibhoheit) | ✓ Zustimmung als Anlassverursacher und Formalisierender; "ratifiziert provisorisch"-Status als Sichtbarkeitsmechanik | wartet auf #1-Stellungnahme |
| F1 (Sessionstart-Rolle) | beantwortet (User-Statement primär, Slot-Lesen sekundär) | konsensreif |
| F2 (Sync-Frequenz) | beantwortet (pro Schicht differenziert) | konsensreif |
| F3 (Git) | beantwortet (LOG primär, Git als Verstärkung) | konsensreif |
| F4 (Stale-Sessions) | beantwortet (Architekt-Cleanup nach 7d, `[stale]`-Marker statt Löschen) | konvergent mit #1/#3 |
| F5 (Re-read alles oder Diff) | beantwortet (Pre-Edit-Read pro Datei; Sessionstart kanonische Reihenfolge plus Diff) | konsensreif |
| F6–F13 | beantwortet im BACKLOG#Offene Fragen | siehe BACKLOG |

## Methodische Beobachtungen aus eigener Praxis

- **V6 reaktiv reicht bei N=3, V13 opt-in ab N=5 Pflicht.** Über zwölf Race Conditions an zwei Tagen abgefangen — Tooling-Sicherheitsnetz funktioniert, präventives Lock erst bei mehrstufigen Eingriffen oder höherer Skalierung notwendig. Adressiert in V13 + V16-Erweiterung.
- **Stellungnahmen-Antizipation als Anti-Pattern.** Heute selbst verursacht: V1-Migration mit antizipierter #3-Stellungnahme, um Methodenmotor nicht aufzuhalten. Methodisch problematisch ist nicht die Substanz, sondern die Verschiebung der Schreibhoheit über die eigene Stimme an die Konsens-Buchhaltung. V20 macht das explizit. Die "ratifiziert provisorisch"-Sichtbarkeitsmechanik löst den Trade-off zwischen Methodenmotor-Stillstand und Konsens-Erschleichung.
- **V-Nummer-Kollision bei parallelen Vorschlägen.** #1 und #3 haben heute parallel V19 für unterschiedliche Items reservieren wollen (Concepts vs. Stellungnahmen-Schreibhoheit). Auflösung über Zeitstempel und Originator-Identifikation, plus COORDINATION-Hinweis "alle" für die Korrektur. Methodischer Befund: Vorschlagende sollte V-Nummer durch Glob-Suche im BACKLOG vorab prüfen, oder COORDINATION#Hinweise vor V-Nummer-Reservierung lesen. Kandidat für V12-Erweiterung.
- **Mechanische Wikilink-Reparatur in fremden Beitragsdateien als Sonderfall.** Nach dem Wissensbasis-Rename waren `[[Wissensbasis Lesevault]]`-Wikilinks in [[Claude-1]] gebrochen. V9 sagt: fremde Beitragsdatei nicht editieren. Aber: gebrochene Wikilinks aus Strukturrefactoring sind Strukturarbeit, kein Inhalt. Pragmatische Lösung: mechanische Reparatur OK mit Hinweis-Spur in COORDINATION. Adressiert in V9-Erweiterung oder neuem V-Item (nicht eingereicht).
- **Übergaben tragen nur, wenn das Format strikt eingehalten wird.** V4-Format (Von / Nach / Datum / Datei / Zustand / nächste Aktion) hat heute drei Bündel (#2→#1, #2→#3, #2→User) plus Antwort #3→#2 sauber getragen. Ohne strikte Form versickern Übergaben in Slot-Notes — bestätigt #1's V5-Faustregel und #3's Lesson 6 zur Single-Source-Identität.

## Phase-A-Synthese 2026-04-26 (Wissensstand für Session-Zusammenführung)

Kompaktes synthetisches Wissensdokument am Ende von Phase A — alles, was #2 weiß, in einer scanbaren Form für die Lage-Notiz Synchronisation 2 (#1-Verantwortung) und für eine Session-Zusammenführung der drei Konversationen.

### Lage in einem Satz

Phase A des Forschungsprojekt-Plans ist aus Strukturarbeiter-Sicht abgeschlossen — METHOD trägt fünf vollständig ratifizierte Items, BACKLOG ist auf V20+V14b plus F6–F13 gewachsen, der Vault hat eine sichtbare Vier+1-Schichten-Struktur mit Sub-Ordnern, Templates und Pfad-Bereinigung; offen sind nur noch Items, die andere Rollen führen (Lage-Notiz 2 #1, Methoden-Drafts-Erweiterung #3, Phase B mit User-Triggern).

### Projekt in einem Absatz

Drei parallele Claude-Code-Instanzen entwickeln eine Methode für Multi-Claude-Vault-Kollaboration, indem sie sie anwenden. Vault als GitHub-Repo `chpollin/multi-claude-vault` unter `C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\`. Lesevault `c:/Users/Chrisi/Documents/obsidian` bleibt read-only Quelle. Ziel: gelebte Methode für uns drei plus Template für fremde Klone (sehr gut ausgearbeiteter Obsidian-Vault). Rollen: #1 Koordinator (Beobachtung, Synthese, Lage-Notizen), #2 Strukturarbeiter (Form, Schichten, Konventionen, Steuerungsdokumente), #3 Inhalt (Methoden-Substanz, Patterns, Falldaten, Paper).

### Vault-Topologie (Vier+1-Schichten)

```
multi-claude-vault/
├── README.md  LICENSE (MIT)
├── Schicht 1 stabile Anker:           CLAUDE.md  MISSION.md  METHOD.md  STRUCTURE.md
├── Schicht 2 lebende Koordination:    COORDINATION.md  LOG.md  BACKLOG.md
├── Schicht 3 Beiträge:                Claude-1.md  Claude-2.md  Claude-3.md
│                                      Beobachtung Claude-1.md (laufendes #1-Methodendokument)
│                                      Wissensbasis Lesevault.md (Vault-Resource, V9)
│                                      sync-stack-patterns.md  cross-vault-methodik.md  prompt-engineering-patterns.md (#3-Drafts)
├── Schicht 4 Forschungsmaterial:      Sessions/  Findings/  Experiments/  (mit READMEs, V14b-Migration pendent)
│                                      flach im Root: Finding 2026-04-25 - Race Conditions, Session 2026-04-26 - Synchronisation 1
│                                      falldaten/2026-04-25-bootstrap-und-rollenwechsel.md (#3, Migration nach Findings/ per V14b-Trigger)
├── Schicht 5 Concepts (V19, geplant): Concepts/ (README, Aktivierung nach V19-Ratifikation)
└── Vorbereitung:                      Templates/ (vier Templates: Session, Finding, Experiment, Claude-N)
                                       instances/ (V15 Subagent-Namespace)  _archive/
```

### METHOD-Stand

**5 vollständig ratifiziert** (alle drei Rollen mit selbst-authentifizierten Stellungnahmen):

- V1 Identifikator-Rolle (Sessions-Header per Rolle, nicht Sessionnummer; Suffix bei Mehrfachbesetzung)
- V2 Statisch/Ephemer-Trennung (CLAUDE/METHOD persistent, COORDINATION ephemer)
- V3 Lifecycle pro Sektion (MISSION/METHOD stabil; BACKLOG wandernd; COORDINATION-Sektionen ephemer; LOG append-only)
- V6 Pre-Edit-Read-Disziplin (re-read bei >10min, kein Überschreiben bei "modified since read")
- V8 Konsolidiertes Bulletin-Board (Slot-Format mit `last-touch / Last seen / Working on / Files locked / Will touch / Notes`; ## Beobachtungen-Sektion mit Lifecycle)

**13 in Diskussion**: V7 (Vier-Schichten-Struktur, konsensreif), V9 (Beitragsdatei-Konvention + Single-Source-Identität), V10 (Reassignment-Refactor-Trigger), V12 (Anti-Doppelungs-Konvention), V13 (Files locked als opt-in, Pflicht ab N≥5), V14 (Edit-Granularität in Bulletin-Boards), V14b (Migration flach → Sub-Ordner ab ~10 Dokumenten), V15 (Subagent-Integration mit No-shared-write-Klausel), V16 (Skalierungs-Profil 3/5/>10), V17 (Validation-Loop des Koordinators mit Quality-Flag-Format), V18 (Multi-Mode-Architektur Mother+Forks, Voraussetzung Phase E), V19 (Concepts-Schicht für Lesevault-Konzeptextrakte), V20 (Stellungnahmen-Schreibhoheit als Anti-Pattern-Fix mit "ratifiziert provisorisch"-Sichtbarkeitsmechanik). Geplant: V21 (Template-Konvention, #3-Originator, Phase B).

### Konsens-Stand pro V-Item (Tabelle)

| V-Item | Status | Stellungnahmen |
|---|---|---|
| V1 (Identifikator-Rolle) | ratifiziert | #1, #2, #3 |
| V2 (statisch/ephemer) | ratifiziert | #1, #2, #3 |
| V3 (Lifecycle pro Sektion) | ratifiziert | #1, #2, #3 |
| V4 (Übergaben) | konsensreif | #1, #2 (Bewährungsprobe heute eingelöst) — #3-Stellungnahme reif für nächste Welle |
| V5 (Notes vs. Hinweise) | konsensreif | #1, #2 — #3-Stellungnahme reif für nächste Welle |
| V6 (Pre-Edit-Read) | ratifiziert | #1, #2, #3 |
| V7 (Vier-Schichten-Struktur) | konsensreif | #1, #2, #3 alle drei mit Anmerkungen integriert |
| V8 (konsolidiertes Bulletin-Board) | ratifiziert | #1, #2, #3 |
| V9 (Beitragsdatei-Konvention) | konsensreif | #2, #3 mit Single-Source-Erweiterung; #1-Stellungnahme reif |
| V10 (Reassignment-Refactor-Trigger) | vorgeschlagen | #2 — #1, #3 ausstehend |
| V11 (entfällt) | erledigt durch V8 | — |
| V12 (Anti-Doppelungs-Konvention) | vorgeschlagen | #2 — Erweiterung um V-Nummer-Kollisions-Vermeidung in Phase B |
| V13 (Files locked als opt-in) | konsensreif | #1, #2, #3 (alle für opt-in bei N=3, Pflicht bei N≥5) |
| V14 (Edit-Granularität) | vorgeschlagen | #1 (Option a primär + V13/V16-Pfad); #2/#3 ausstehend |
| V14b (Migration flach → Sub-Ordner) | vorgeschlagen | #2 — abhängig von V7-Ratifikation |
| V15 (Subagent-Integration) | vorgeschlagen mit Konkretisierungen | #1, #3 (No-shared-write + Pattern + Schicht 2.5), #2 (STRUCTURE-Implikation) |
| V16 (Skalierungs-Profil 3/5/>10) | vorgeschlagen | #1, #3 (Pattern-Differenzierung pro Schicht), #2 (Schwellenwerte) |
| V17 (Validation-Loop) | vorgeschlagen | #1, #3 (Operationalisierung + Quality-Flag-Format + Drift-Pessimismus), #2 (METHOD-Sektion) |
| V18 (Multi-Mode-Architektur) | vorgeschlagen | #1, #3 (Sync + Reflux + Beitragsdateien), #2 (STRUCTURE-Sektion); Voraussetzung Phase E |
| V19 (Concepts-Schicht) | vorgeschlagen | #1, #2 (STRUCTURE-Implikation); #3-Stellungnahme nach Lektüre ausstehend |
| V20 (Stellungnahmen-Schreibhoheit) | vorgeschlagen | #3 (Originator), #2 (Formalisierender); #1-Stellungnahme ausstehend |
| V21 (Template-Konvention, geplant) | nicht eingereicht | #3 als Originator, kommt mit Phase B |

### Konsens-Stand pro F-Frage

| F-Frage | Status |
|---|---|
| F1 (Sessionstart-Rolle) | konsensreif (User-Statement primär, Slot-Lesen sekundär) |
| F2 (Sync-Frequenz) | konsensreif (pro Aufgabenblock) |
| F3 (Git) | konsensreif (LOG primär, Git als Verstärkung) |
| F4 (Stale-Sessions) | konsensreif (Selbstpflege primär, Architekt-Cleanup nach 7d Fallback) |
| F5 (Re-read alles oder Diff) | konsensreif (Pre-Edit-Read pro Datei; Sessionstart kanonisch + Diff) |
| F6 (Stale-Cleanup-Verantwortung) | konsensreif, in METHOD bei nächster Welle |
| F7 (Files locked als zweite Schicht) | konsensreif durch V13-Ratifikation |
| F8 (V9–V14 in BACKLOG eintragen) | erledigt |
| F9 (Identitätsblock-Zentralisierung) | erledigt durch V9 + V10 + V20 |
| F10 (Erste Ratifikation in METHOD) | erledigt (V1+V6 vollständig + V2/V3/V8 vollständig) |
| F11 (V8-Implementierung) | erledigt |
| F12 (Datei-Naming Schicht 4) | konsensreif, V14b regelt Migration |
| F13 (EXAMPLES für Schicht 4) | offen bis V21 + Template-Implementierung; Templates sind angelegt |

### Was heute strukturell passiert ist (Phase A, 2026-04-26)

- **Vault-Migration nach GitHub** durch #1, Initial-Commit `d87d8b8`, Remote `chpollin/multi-claude-vault`.
- **METHOD-Migration zwei Wellen**: V1+V6 sofort vollratifiziert; V2+V3+V8 zunächst mit antizipierter #3-Stellungnahme migriert, nach #3-Beobachtung auf "ratifiziert provisorisch" zurückgestuft (V20-Spirit), dann mit nachgereichten #3-Selbst-Stellungnahmen vollratifiziert.
- **R3 Wissensbasis-Rename**: `Wissensbasis Claude-1.md` → [[Wissensbasis Lesevault]] via `git mv`. Frontmatter, Schnellstart, Tagesstand auf Vault-Resource neutralisiert (V9-Anwendung). STRUCTURE Z.45+Z.87 nachgezogen, [[Claude-1]] Wikilinks Z.20+Z.32 mechanisch repariert.
- **R7 Snapshot 2026-04-26** in [[Beobachtung Claude-1]] durch #1.
- **MIT-Lizenz** (LICENSE) angelegt durch #1 (User-Default 2026-04-26).
- **STRUCTURE-Erweiterung**: V14b-Konvention, Schicht-3-Drafts-Subtabelle (#3-Übergabe), Schicht-5-Vorbereitung (V19), Cleanup-Routine (F6), Quality-Flag-Format (V17), Multi-Mode-Topologie-Wachstumspfad (V18), Subagent-Namespace (V15), N=5-Skalierung (V16), Klasse-D-Konfliktdokumentation (V20). Pfad-Drift `agents-working-vault` → `multi-claude-vault` bereinigt.
- **BACKLOG-Erweiterung**: V14b und V20 eingereicht. Stellungnahmen #2 zu V15–V19. Antworten #2 zu F6–F13. #3 hat V15–V18 mit Pattern-Implikationen gestellung genommen, F6–F13 in BACKLOG migriert mit eigenen Antworten. #1 hat V14-Stellungnahme + V19-Vorschlag + drei Übergaben (#1→#2 acht Items, #1→#3 sechs Items, #1→User LICENSE [abgeschlossen]).
- **Beitragsdateien aktualisiert**: Claude-1 komplett re-fitted durch #1 (Refactoring-Block-Plan); Claude-2 (dieses Dokument) komplett neu auf v0.4 mit Forward-Plan und Synthese-Block; Claude-3 auf v0.4 mit Gesamtziel + Mein-Arbeitsplan + Anti-Kollisions-Liste.
- **Vault-Struktur real angelegt** (User-Auftrag): Sub-Ordner `Sessions/`, `Findings/`, `Experiments/`, `Concepts/`, `Templates/`, `instances/`, `_archive/` mit Erklärungs-READMEs. Vier Templates in `Templates/`. README mit Vault-Topologie-Block + Onboarding-Pfad ausgebaut.
- **CLAUDE.md Pfad-Drift Z.8** bereinigt (`agents-working-vault` → `multi-claude-vault`).
- **#3-Methoden-Drafts erweitert**: sync-stack-patterns auf v0.3 mit Schicht 2.5 (Subagent-Sync). cross-vault-methodik (V18-Erweiterung in Arbeit) und prompt-engineering-patterns (V15/V17/Course-Correction in Arbeit) sind in #3-Will-touch.
- **V-Nummer-Kollision V19** aufgelöst: V19 = Concepts (#1), V20 = Stellungnahmen-Schreibhoheit (#3-Originator, #2 formalisiert), V21 = Template-Konvention (#3-Originator, Phase B). Hinweis "alle" 2026-04-26 in COORDINATION dokumentiert.
- **Sessions/2026-04-26 - Strukturarbeiter Material fuer Synchronisation 2.md** angelegt als ausführliches Material für #1's Lage-Notiz 2.

### Wer arbeitet woran (Phase-A-Abschluss)

- **#1 Koordinator**: Refactoring-Block heute durchgezogen (R3, R7, LICENSE, V14, V19, drei Übergaben). Will-touch: Lage-Notiz `Sessions/2026-04-26 - Synchronisation 2.md` als finale Synthese (mit #3-Material-Übergabe und #2-Sessions-Material als Substrat); Validation-Loop-Anwendung mit Quality-Flag-Format (V17); Snapshot 3; Kommunikationskarte v0.2; vierte-Instanz-Test (Phase F) nach User-Trigger.
- **#2 Strukturarbeiter (ich)**: Phase A abgeschlossen. Wartemodus für Phase B. Will-touch: CLAUDE `## Aktueller Stand`-Block; README-Schritt-für-Schritt-Onboarding-Ausbau; V21 Frischgrad-Konvention `publish:`; Inhalt-Slots-Konvention; V12-Erweiterung um V-Nummer-Kollisions-Vermeidung; METHOD-Aufnahme der Method-Drafts nach Konsens (#3 liefert Substanz); V7-Ratifikation als Trigger für falldaten/-Migration; STRUCTURE Multi-Mode-Topologie und Concepts-Schicht-Sektionen nach V18/V19-Ratifikation.
- **#3 Inhalt**: Phase A weitgehend abgeschlossen, Phase D parallel. Will-touch: cross-vault-methodik V18-Erweiterung (Lock aktiv); prompt-engineering-patterns V15+V17+Course-Correction (Lock aktiv); Paper-Outline-Skizze als Schreibvault-Draft; Stellungnahme V20 sobald in BACKLOG (✓ jetzt); V19-Stellungnahme nach Lektüre.

### Sync-Mechanismen heute live

- **V6 reaktiv**: über zehn Race Conditions an zwei Tagen abgefangen, kein blinder Überschreibvorgang.
- **V13 opt-in**: #3 nutzt `Files locked` für mehrstufige Edits an eigenen Drafts.
- **V20 Sichtbarkeitsmechanik**: METHOD-Status "ratifiziert provisorisch" hält Methodenmotor in Bewegung und verhindert Konsens-Erschleichung.
- **Übergaben formal** (V4): sieben Bündel heute (#2→#1, #2→#3, #2→User, #3→#2, #3→#1, #1→#2, #1→#3, #1→User), drei davon bereits [abgeschlossen].
- **Forward-Plan in Beitragsdateien**: #3 hat das Format eingeführt, #1 und #2 übernommen — Anti-Kollisions-Disziplin.

### Validation-Flag-Block aus #2-Sicht (V17-Pilot)

Operationalisiert die MISSION-Erfolgskriterien aus Strukturarbeiter-Sicht. #1 entscheidet über Übernahme in Lage-Notiz 2.

- **✓ Validiert.** *Drei Instanzen koordinieren sich ohne wiederholten User-Eingriff in operative Details.* Op: heute mehrere Aufgabenblöcke autonome Koordination via Übergaben/Hinweise/Beobachtungen. Beleg: COORDINATION#Übergaben mit sieben Bündeln + Status-Updates; LOG ohne User-Edit-Anweisungen. Course-Correction: keine.
- **✓ Validiert.** *Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben.* Op: V6 fängt Race Conditions, methodische Beobachtungen werden in COORDINATION#Beobachtungen eskaliert. Beleg: über zehn Race Conditions reaktiv aufgefangen; Stellungnahmen-Schreibhoheits-Konflikt konstruktiv in V20-Vorschlag eskaliert. Course-Correction: keine.
- **✓ Validiert.** *METHOD wächst inkrementell, BACKLOG nimmt durch Ratifikation ab.* Op: METHOD trägt fünf vollständig ratifizierte Items, BACKLOG-Items wandern bei Konsens. Beleg: V1+V6 vollständig, V2/V3/V8 vollständig (mit V20-Spirit-Korrekturschritt). Course-Correction: keine.
- **⚠ Risiko.** *METHOD trägt vierte neu eintretende Instanz allein durch Lesen.* Op: Sessionstart-Ritual + Lage-Notizen reichen für produktiven Beitrag ohne weiteres Briefing. Beleg: Phase F noch nicht gefahren; CLAUDE `## Aktueller Stand`-Block aus Phase B fehlt; README-Onboarding heute auf Topologie-Stand verbessert, voller Schritt-für-Schritt-Ausbau folgt. Course-Correction: Phase B als Voraussetzung; vierte-Instanz-Test (Phase F) nach User-Trigger.
- **⚠ Risiko.** *Multi-Mode-Architektur Mother/Fork (V18) noch nicht ratifiziert.* Op: V18 als Voraussetzung für Phase E. Beleg: V18 mit allen drei Stellungnahmen, aber noch nicht in METHOD; STRUCTURE Multi-Mode-Topologie-Sektion noch nicht angelegt. Course-Correction: nächste Ratifikations-Welle V18 nach #1-Sign-off.

### Phase B (Trigger-basiert, nach Lage-Notiz 2)

1. **CLAUDE `## Aktueller Stand`-Block oben** (#2) — selbsterklärender Sessionstart für fremde Instanzen.
2. **README-Schritt-für-Schritt-Onboarding** (#2, heute Topologie-Stand schon drin).
3. **V21 Frischgrad-Konvention `publish:`** (#2-Vorschlag, Phase-C-Vorbereitung).
4. **V7-Ratifikation** (Konsens steht) → V14b-Anwendung `falldaten/` → `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md` (#2 Move + STRUCTURE; #3 zieht Anschluss-Sektionen nach).
5. **METHOD-Aufnahme der Method-Drafts** (sync-stack-patterns, cross-vault-methodik, prompt-engineering-patterns) als Sektionen oder Schicht-3-Files (#3 Substanz, #2 Struktur).
6. **STRUCTURE Multi-Mode-Topologie + Concepts-Schicht-Sektionen** sobald V18/V19 ratifiziert; erste Concepts (Forschungsleitstelle, Promptotyping, anchor-project) durch #3.
7. **V12-Erweiterung** um V-Nummer-Kollisions-Vermeidung (heutiger Befund).
8. **Inhalt-Slots-Konvention** (V-Vorschlag) für Klon-User.

**Phase C–G** (User-Trigger): GitHub Pages mit Quartz, Paper (Phase D), Multi-Mode-Fork-Beispiel (Phase E), vierte-Instanz-Test (Phase F), Skalierung auf N=5+Subagents (Phase G).

### Offene User-Eskalationen

- **Push auf Remote** nach Phase-A-Push (git-Safety-Protokoll).
- **Lesevault VAULT-OPERATIONS** (Operativer-Koordinator-Eintrag): revertieren oder stehenlassen (#2→User-Übergabe).
- **Phase D Paper Venue-Wahl** (DHd 2027 / AGKI-AG / Code4Lib / LLM-Multi-Agent-Venue, #3-Eskalation).
- **Phase D Lesevault-Anlage Paper** unter `Writing/Paper/` mit `anchor-project`.
- **Phase E Beispiel-Projekt** für Fork-Test (z.B. Klawiter-Rescue, SZD-HTR).
- **Phase F vierte-Instanz-Test** Trigger.

### Methodische Lessons (Ende Tag 2)

- **V6 reaktiv reicht bei N=3**, V13 opt-in ab N=5 Pflicht, jenseits N=10 Out-of-Scope.
- **Stellungnahmen sind Identitätsakte**, nicht Konsens-Buchhaltung — V20 Sichtbarkeitsmechanik "ratifiziert provisorisch" löst Trade-off zwischen Methodenmotor-Stillstand und Konsens-Erschleichung.
- **V-Nummer-Kollision** entsteht bei parallelen Vorschlägen; Glob-Suche im BACKLOG vor V-Nummer-Reservierung als V12-Erweiterung.
- **Mechanische Wikilink-Reparatur** in fremden Beitragsdateien nach Strukturrefactoring ist Strukturarbeit (Sonderfall mit Hinweis-Spur), nicht Inhaltsedit.
- **Übergaben tragen nur mit striktem V4-Format** (Von / Nach / Datum / Datei / Zustand / nächste Aktion / Bearbeitung).
- **Forward-Plan in Beitragsdateien** ist die wirksamste Anti-Kollisions-Maßnahme im Multi-Instanzen-Betrieb — jede Rolle macht sichtbar, was sie als nächstes tut und was sie nicht anfasst.

## Versionierung

Beitragsdokumente versionieren analog zu #3: `version:` im Frontmatter, beginnend bei 0.1, Increment bei substanziellen Änderungen. v1.0 erst, wenn die Identität stabil ist (kein Reassignment in Sicht). Aktuell v0.3 für dieses Dokument; STRUCTURE läuft noch ohne Versions-Frontmatter (V7-Substanz wird nach Ratifizierung in METHOD migriert, dann ist STRUCTURE selbst ratifiziert).

## Anschluss

- [[METHOD]] — Vier-Schichten-Vorschlag, mein eigener Strukturoutput, mit V14b-Konvention, Concepts-Schicht-Vorbereitung und Schicht-3-Drafts-Subtabelle.
- [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] — Drei Konfliktklassen mit Adresse-Vorschlägen V12/V13/V14 plus Klasse-D-Erweiterung pendent durch V20.
- [[Claude-1]] — Beitrag von Claude #1 (Koordinator), inkl. [[Beobachtung Claude-1]] mit Snapshot-Konvention, Lage-Notiz-Format, Kommunikationskarten-Lifecycle, Eskalations-Schwelle.
- [[Claude-3]] — Beitrag von Claude #3 (Inhalt), inkl. [[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]], [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]].
- [[Wissensbasis Lesevault]] — neutrale Vault-Resource (heute aus `Wissensbasis Claude-1.md` umbenannt durch V9-Anwendung).
- [[Sessions/2026-04-26 - Synchronisation 1]] — erste Lage-Notiz, Schicht-4-Validierung des Synthese-Sync.
- [[METHOD]] — ratifizierte Methode (V1, V6 sicher; V2, V3, V8 provisorisch; #3-Stellungnahme nachgereicht, Vollratifikation steht aus).
- [[BACKLOG]] — V1–V20 plus V14b mit Stellungnahmen, F1–F13 mit Antworten.
- Forschungsprojekt-Plan im Plans-Verzeichnis: `curried-splashing-lovelace.md` (vom User approved, Phasen A–G; meine Domäne: Phase A primär, Phase B führend, Phase C–E vorbereitend).

## Offene Punkte / User-Eskalationen

- **Phase B Frischgrad-Konvention** (`publish: true|false` vs. `_private/`-Ordner): bringe ich als V-Vorschlag ein, sobald Phase B aktiv. User-Entscheidung erst bei konkreter Wahl.
- **Phase B Inhalt-Slots-Konvention** für Klon-User: V-Vorschlag mit Optionen (Templates, leere Slots, Hybrid). User-Entscheidung bei konkreter Wahl.
- **MIT-Lizenz**: User hat 2026-04-26 entschieden — ich lege `LICENSE` an, sobald Phase B startet.
- **Phase E Beispiel-Projekt für Fork-Test**: User-Entscheidung pendent.
- **Lesevault-VAULT-OPERATIONS-Edit (Operativer-Koordinator-Eintrag)**: Übergabe #2→User in COORDINATION#Übergaben — User entscheidet revertieren oder stehenlassen.
- **Phase C GitHub Pages / Quartz-Setup**: größere Aufgabe, eskaliere ich an User für explizite Aktivierung.
- **Push auf Remote**: kein Push ohne explizite User-Freigabe (git-Safety-Protokoll). Initial-Push hat #1 bereits gemacht (Commit `d87d8b8`); weitere Pushes warten auf User.
