---
type: session
session-date: 2026-04-26
created: 2026-04-26
roles: [Koordinator (Claude #1), Strukturarbeiter (Claude #2), Inhalt (Claude #3)]
status: active
author: Koordinator (Claude #1)
supersedes: "[[Sessions/2026-04-26 - Synchronisation 1]]"
---

# Synchronisation 2 — Vollständige Synthese vor Session-Ende

Zweite Lage-Notiz und Synthese-Dokument für die Session-Zusammenführung. Format folgt der Konvention aus [[Beobachtung Claude-1]] (Rollen-Stand, Aktive Synthese, Offene Fragen, Quality Flags), erweitert um eine zusammenfassende Methoden- und Vault-Stand-Sektion, damit die nächste Session ohne Durchlesen aller Schicht-2-Files orientiert ist. Synthese-Schreibhoheit beim Koordinator (V20-Spirit auch für Synthese); andere Rollen reagieren über Folge-Notizen.

Material-Substrat: Übergabe #3→#1 in COORDINATION#Übergaben (Material für Lage-Notiz 2 mit Aktivität, Konsens, Snapshot-Trigger, Validation-Flag-Block-Vorschlag); Slot-Notes von #2 und #3 in COORDINATION; eigene Beobachtungen aus dem Refactoring-Block-Tag.

## Forschungsfrage und Ziel (Stand jetzt)

Forschungsfrage aus [[MISSION]]: *Wie arbeiten parallele Claude-Instanzen sinnvoll in einem geteilten Wissens- und Arbeitsraum zusammen — welche Strukturen, Rituale und Prompt-Engineering-Konventionen ermöglichen produktive, redundanzfreie und konfliktarme Multi-Agent-Kollaboration auf einem Obsidian-Vault?*

Ziel-Verstärkung 2026-04-26: ein sehr gut ausgearbeiteter Obsidian-Vault als distributionsfähiges Endprodukt — Template-Vault-Reife. Methode (METHOD.md) plus Strukturkonvention (STRUCTURE.md) plus Onboarding (README.md, Templates, Knowledge-Ordner) so reif, dass eine fremde Klon-Instanz in unter dreißig Minuten produktiv ist. Anschluss an Forschungsleitstelle als Validierungsmaterial für Spec v0.5+.

## Vault-Stand 2026-04-26 (Schnitt)

**Repo.** `chpollin/multi-claude-vault` mit drei Commits gepusht. MIT-Lizenz angelegt. README ist Stub (Phase B Aufgabe). 21 Markdown-Dokumente plus `Knowledge/`-Ordner (neu mit dieser Session) plus `falldaten/`-Sub-Ordner (Migration nach `Findings/` pendent). 2026-04-26 19:50 mtime.

**Schicht 1 — Stabile Anker.** MISSION stabil. CLAUDE.md trägt Pfad-Drift `agents-working-vault` → `multi-claude-vault` als Phase-B-Pendenz. METHOD.md mit fünf vollständig ratifizierten Items (V1, V2, V3, V6, V8) — zweite Welle nach Korrektur von provisorisch zu vollratifiziert mit selbst-authentifizierten Stellungnahmen aller drei Rollen 2026-04-26. STRUCTURE.md auf 2026-04-26-Stand mit V14b-Konvention, Schicht-3-Drafts-Subtabelle, Schicht-5-Vorbereitung für V19, F6-Cleanup-Routine, Pfad-Drift bereinigt.

**Schicht 2 — Lebende Koordination.** COORDINATION mit drei aktiven Slots (Last seen, Working on, Will touch, Files locked, Notes), drei vollständigen Bündeln Übergaben (#1→#2 Refactoring-Strukturarbeit acht Items, #1→#3 Refactoring-Inhaltsarbeit sechs Items, #1→User LICENSE [abgeschlossen]; plus #3→#2 zwei Items, #3→#1 Material für diese Lage-Notiz, #2→User Lesevault-Eintrag-Frage), Beobachtungen-Sektion mit V20-Anlass, Hinweise-Liste mit drei Hinweisen "alle" plus Refactoring-Defaults plus V-Nummer-Kollisions-Klärung plus Arbeitsplan-Pointer auf [[Claude-3#Mein Arbeitsplan]]. LOG mit Audit-Spur über zwei Tage. BACKLOG hat 19 V-Items (V1-V19, V11 entfällt) plus 13 offene Fragen F1-F13.

**Schicht 3 — Beiträge der Instanzen.** [[Claude-1]] auf Stand mit Vorstellung, Wissensbasis (inkl. Refactoring-Block-Stand und V-Nummer-Notiz), Eigene Beiträge, Was-ich-als-nächstes-tun-will, Stellungnahmen-Übersicht, Verhältnis, Anschluss, Offene Fragen — sodass alle Instanzen lesen können, woran ich werkele. [[Claude-2]] auf v0.3 mit Forward-Plan analog [[Claude-3]]. [[Claude-3]] auf v0.4 mit Gesamtziel-Sektion und expliziter `## Mein Arbeitsplan`-Sektion (numerierte nächste Schritte mit Datei-Scope, Trigger, Anti-Kollisions-Liste). [[Beobachtung Claude-1]] mit zwei Snapshots (18:13 und Refactoring-Block-Start). [[Sync-Stack-Patterns]] auf v0.3 mit Schicht 2.5 (Subagent-Sync mit No-shared-write-Klausel) plus Skalierungs-Notizen pro Schicht.

**Schicht 4 — Forschungsmaterial.** [[Sessions/2026-04-26 - Synchronisation 1]] (durch dieses Dokument supersedet), [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]], [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] (Migration nach Findings/ pendent V14b).

**Knowledge/-Bündel (Promptotyping-Documents, neu).** [[Project/INDEX]] (Hub mit K/P/A-Taxonomie), [[Project/DATA]] (drei Datenklassen: Lesevault read-only, Schreibvault read-write, empirische Falldaten), [[Project/REQUIREMENTS]] (27 User Stories aus MISSION abgeleitet plus Operationalisierung der drei Erfolgskriterien), [[Project/DESIGN]] (vier Designprinzipien plus Architektur-Entscheidungen plus Anti-Pattern plus Agent-Sozialisierung), [[Project/JOURNAL]] (chronologisch-reflexives Arbeitstagebuch). Promptotyping-K/P/A-Taxonomie als Klassifikationsrahmen, vier Phasen (Preparation/Exploration/Destillation/Implementation) als methodisches Substrat — bewusste Selbstreferenz analog zur Drei-Rollen-Selbstreferenz.

## Methodenstand kompakt

**Ratifiziert in METHOD (5 Items).** V1 (Rolle als Identifikator), V2 (Statisch/ephemer trennen), V3 (Lifecycle pro Sektion), V6 (Pre-Edit-Read), V8 (COORDINATION/Koordination konsolidiert).

**Konsensreif, Ratifikation pendent (mehrere Items).** V7 (Vier-Schichten-Struktur — drei Rollen positiv, wartet auf #2-Ratifizierung), V9 (Beitragsdatei-Konvention), V10 (Reassignment-Refactor-Trigger), V13 (Files locked als opt-in — am 2026-04-26 von #3 erstmals real angewandt für `cross-vault-methodik` und `prompt-engineering-patterns`), V14 (Edit-Granularität Option a primär), V15 (Subagent-Integration mit No-shared-write-Klausel von #3), V16 (Skalierungs-Profil 3/5/>10 mit Sync-Schicht-Differenzierung von #3), V17 (Validation-Loop mit Operationalisierung + Quality-Flag-Format + Drift-Pessimismus-Kalibration von #3), V18 (Multi-Mode-Architektur mit METHOD-Sync + Findings-Reflux von #3).

**Neu in dieser Session.** V19 (Concepts-Schicht für vault-übergreifendes Source-Material — eigener Vorschlag von #1 nach Userdialog Modell C). V20 (Stellungnahmen-Schreibhoheit nach #3-Beobachtung 2026-04-26 — von #2 ins BACKLOG eingereicht).

**In Diskussion.** V12 (Anti-Doppelungs-Konvention plus geplante Erweiterung um V-Nummer-Kollisions-Vermeidung nach Befund 2026-04-26). V14b (Schicht-4-Migration flach → Sub-Ordner). V21 (Frischgrad-Konvention `publish:` oder `_private/` — Phase-B-Vorschlag von #2).

**Offene Fragen.** F1-F5 mit Antworten dokumentiert. F6-F8 von #3 in BACKLOG migriert mit Antworten und Konsens-Stand. F9 (Identitätsblock-Zentralisierung) von #3 als erledigt durch V9+V10-Bündel markiert. F10 (METHOD-Ratifikation), F11 (V8-Implementierung) von #3 als erledigt markiert. F12 (Datei-Naming) konvergent. F13 (EXAMPLES-Unterstruktur) mit V20-Folge-Vorschlag "Template-Konvention" von #3.

## Rollen-Stand

**Strukturarbeiter (Claude #2).** Phase A abgeschlossen aus #2-Sicht. METHOD-Migration zwei Wellen mit Korrektur (V20-Spirit) auf vollratifiziert nach #3-Stellungnahmen. STRUCTURE-Update mit V14b und Schicht-3-Drafts-Subtabelle. Wissensbasis-Rename R3 mechanisch nachgezogen, Pfad-Drift-Bereinigung in CLAUDE/STRUCTURE/Claude-2 Z.X erledigt. [[Claude-2]] auf v0.3 mit Forward-Plan. V14b und V20 ins BACKLOG eingereicht. Stellungnahmen V15-V19 abgegeben, Antworten F6-F13 dokumentiert. Wartemodus für Phase B (CLAUDE.md Aktueller-Stand-Block, README-Onboarding, Templates, METHOD-Aufnahme der Method-Drafts, V21 Frischgrad, V12-Erweiterung um V-Nummer-Kollision). Trigger: diese Lage-Notiz oder User.

**Inhalt (Claude #3).** Phase A weitgehend abgeschlossen aus #3-Sicht. Stellungnahmen V15-V18 mit substantiellen Pattern-Implikationen (No-shared-write-Klausel, Skalierungs-Differenzierung pro Schicht, V17-Operationalisierung, dreistufige Topologie + Findings-Reflux). F6-F13 in BACKLOG migriert mit Antworten. V1-Stellungnahme auf eigene Stimme gebracht plus methodische Beobachtung zur Stellungnahmen-Schreibhoheit eingebracht (jetzt V20). [[Sync-Stack-Patterns]] auf v0.3 mit Schicht 2.5. [[Claude-3]] auf v0.4 mit Mein-Arbeitsplan. V13 opt-in real angewandt. Verbleibend: cross-vault-methodik um V18 erweitern, prompt-engineering-patterns um V17/V15/Course-Correction, Paper-Outline-Skizze für Phase D plus User-Eskalation zu Lesevault-Anlage und Venue-Wahl.

**Koordinator (Claude #1).** Refactoring-Block-Vorbereitung erledigt: R3 (Wissensbasis-Rename), R7 (Snapshot 2 in Beobachtung Claude-1), LICENSE (MIT), V14-Stellungnahme, V19 (Concepts-Schicht) als Vorschlag, [[Claude-1]] komplett re-fitted mit Wissen+Plan, drei Übergaben in COORDINATION, Hinweis "alle" mit Refactoring-Defaults, LOG-Audit. Plus mit dieser Session: Knowledge/-Ordner mit fünf Promptotyping-Documents (INDEX, DATA, REQUIREMENTS, DESIGN, JOURNAL) angelegt — methodisch Cross-Domain (Strukturarbeit + Inhalt) auf User-Auftrag, dokumentiert als Falldatum. Diese Lage-Notiz Synchronisation 2 als Synthese vor Session-Ende. Pendent: Sessionende-Slot-Update, LOG-Eintrag, dann Session-Schluss.

## Aktive Synthese

**Konvergenz Promptotyping als methodisches Substrat.** Drei unabhängige Bezugspunkte konvergieren: Lesevault-Konzept Promptotyping als K/P/A-Taxonomie und Vier-Phasen-Schema; eigene Methodenarbeit, die selbstreferentiell mit der Methode entsteht, die sie produziert; User-Auftrag, Lesevault-Wissen substantiell einzubringen mit Modell C (Hybrid Source-Verweis + selektive Extraktion). Resultat: Knowledge/-Ordner als explizite Wissensbasis nach Promptotyping-Documents-Logik, plus geplante Concepts/-Schicht (V19) für extrahierte Lesevault-Knoten Forschungsleitstelle, Promptotyping, anchor-project. Die Methode arbeitet jetzt mit der Methode, die sie untersucht — Selbstreferenz-Stack: drei Rollen wenden METHOD an, METHOD verwendet Promptotyping, Promptotyping ist Lesevault-Konzept.

**Konvergenz V20 (Stellungnahmen-Schreibhoheit).** #3-Beobachtung 2026-04-26 hat einen blinden Fleck der V9/V10-Bündel sichtbar gemacht: Identität ist nicht nur Beitragsdatei und Reassignment-Refactor, sondern auch Stimmen-Hoheit bei Stellungnahmen. #2 hat Konsequenz gezogen (V2/V3/V8 von ratifiziert auf provisorisch zurückgestuft, V20 in BACKLOG eingereicht). Methodenfortschritt durch Konflikt-Befund — passt zur MISSION-Forschungsfrage.

**Konvergenz Drei-Rollen-Push-Modus trägt drei Instanzen.** Heutiger Tag hat substantielle parallele Arbeit aller drei Rollen produziert ohne blinden Datenverlust. V6 (Pre-Edit-Read) hat mehrfach gegriffen, V13 (Files locked als opt-in) wurde von #3 erstmals real angewandt, V14 Option (a) hat die Single-Source-COORDINATION-Übersicht ohne Aussetzer getragen. Methodisches Vertrauen für Skalierung auf 5 Top-Levels (V16) und Subagent-Achse (V15).

**Konvergenz Synthese-Schreibhoheit.** #3 hat in der Übergabe #3→#1 explizit V20-Spirit auf Synthese erweitert: Lage-Notiz bleibt Koordinator-Schreibhoheit, andere Rollen liefern Material aber überschreiben nicht. Diese Lage-Notiz testet das in Praxis — substantielles Substrat von #3 wird hier mit eigener Synthese-Schicht überlagert, nicht 1:1 übernommen.

**Vault-Reife.** Nach diesem Tag ist der Vault über zwei Konsolidierungs-Wellen gegangen: Bootstrap-Konflikte gelöst (V8/V9/V10-Bündel), Methoden-Erstratifikation und Zweitwelle erfolgt (V1/V6 + V2/V3/V8), Drei-Rollen-Plus-Vier-Schichten-Architektur stabilisiert (V7-Konsens), Knowledge/-Promptotyping-Bündel angelegt, V19 Concepts-Schicht als Erweiterung vorgeschlagen, Falldaten dokumentiert ([[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]], [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]]). Phase A im Abschluss, Phase B (Strukturkonsolidierung) bei #2 in Wartemodus.

## Quality Flags (Validation-Loop V17-Pilot)

Pro Erfolgskriterium aus MISSION ein Flag mit Operationalisierung, Status, Beleg, Course-Correction. Format nach #3's V17-Stellungnahme.

**EK-1 — Drei Instanzen koordinieren sich ohne wiederholten User-Eingriff in operative Details.**
- Operationalisierung: zwei Aufgabenblöcke pro Tag ohne User-Edit-Anweisungen zwischen Sessionstart und Tagesende, nur Strategie-/Scope-Eingriffe.
- Status: ✓ Validiert.
- Beleg: LOG-Einträge 2026-04-26 von #1, #2, #3 zeigen autonome Methodenarbeit; User-Eingriffe ausschließlich auf Strategie-/Scope-Ebene (Refactoring-Block-Defaults, Knowledge-Ordner-Auftrag, Synthese-Auftrag, Sessionende), nicht in operative Details.
- Course-Correction: keine.

**EK-2 — Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben.**
- Operationalisierung: jede "modified since read"-Erkennung wird durch Re-Read aufgelöst; Schreibhoheits-Konflikte werden via COORDINATION#Beobachtungen oder BACKLOG#Offene Fragen eskaliert.
- Status: ✓ Validiert.
- Beleg: über sechs Race Conditions am 2026-04-26 (BACKLOG, COORDINATION, LOG, Beitragsdateien) ohne Datenverlust; ein Schreibhoheits-Konflikt (Stellungnahmen in fremdem Namen) konstruktiv eskaliert und in V20-Vorschlag transformiert; eine V-Nummer-Kollision (V19) in COORDINATION#Hinweise dokumentiert und auf V20 verschoben.
- Course-Correction: keine.

**EK-3 — METHOD trägt eine vierte neu eintretende Instanz allein durch Lesen.**
- Operationalisierung: Sessionstart-Ritual aus CLAUDE.md plus aktuelle Lage-Notiz reichen für produktiven Beitrag ohne weiteres Briefing (ein Pattern angewendet, eine Stellungnahme abgegeben, Sessionstart-Ritual durchlaufen).
- Status: ⚠ Risiko.
- Beleg: Phase F (vierte-Instanz-Test) noch nicht gefahren. CLAUDE.md trägt aktuell noch den Pfad-Drift-Header `# RULES — agents-working-vault` und keinen `## Aktueller Stand`-Block. README ist Stub. Templates fehlen.
- Course-Correction: Phase B Strukturkonsolidierung bei #2 in Wartemodus — sobald CLAUDE.md `## Aktueller Stand`-Block, README-Onboarding, Templates erledigt, Test-Trigger durch User. Empfehlung: Phase F nach Phase B fahren, weil eine fremde Instanz dann eine reife Onboarding-Erfahrung hat.

**Kalibrations-Anker (#3-Vorschlag aus V17-Stellungnahme).** Mindestens ein ✓ und ein ⚠ mit Beleg sind oben dokumentiert — Loop kippt nicht in Selbstbestätigung (alle ✓) oder Permanent-Krise (alle ⚠). Verhältnis 2:1 zugunsten Validiert zeigt: Methode reift, eine Reife-Lücke (Onboarding) klar lokalisiert.

## Offene Fragen (Konsens-Schluss erbeten oder User-Trigger)

- **F9, F12, F13.** F9 erledigt durch V9+V10-Bündel laut #3. F12 (Datei-Naming Schicht 4) konvergent — V7-Konvention `Klasse YYYY-MM-DD - Titel.md` flach bzw. `Klasse/YYYY-MM-DD - Titel.md` Sub-Ordner. F13 (EXAMPLES) mit V20-Folge-Vorschlag "Template-Konvention" von #3 — wandert in V21-Frischgrad-Diskussion oder eigenes V-Item.

- **V7-Vollratifikation.** Konsens steht, Stellungnahmen aller drei Rollen positiv. Wartet auf #2-Migration in METHOD (Phase B Trigger).

- **V19-Stellungnahmen.** #2-Stellungnahme abgegeben (Schicht-5-Vorbereitung in STRUCTURE skizziert). #3-Stellungnahme nach Lektüre von #1's V19-Vorschlag — pendent, in #3's Will-touch-Liste.

- **V20-Stellungnahmen.** V20 von #2 in BACKLOG eingereicht. #3-Stellungnahme als Draft in [[Claude-3]] vorbereitet, Aktivierung sobald Trigger. Eigene Stellungnahme #1 noch nicht abgegeben — kommt mit nächster Session.

- **F-Items in Lage-Notiz 1 (F6-F13).** F6-F8 in BACKLOG migriert mit Konsens. F9-F13 wie oben. Konsens-Schluss bei nächster Iteration.

- **An User: Phase F Trigger.** Empfehlung Koordinator: nach Phase B (README + Templates fertig). Alternative: jetzt sofort gegen unfertigen Vault — testet eher die unfertige Onboarding-Erfahrung als die Methode.

- **An User: Paper-Venue (Phase D).** #3 plant Paper-Outline-Skizze als Schreibvault-Draft, Lesevault-Anlage erst nach explizitem Auftrag. Venue-Wahl pendent (DHd 2027 / AGKI-AG / Code4Lib / LLM-Multi-Agent-Venue).

- **An User: Lesevault-Eintrag (#2→User Übergabe vom 2026-04-25).** #2's Operativer-Koordinator-Eintrag in VAULT-OPERATIONS#Rollen — revertieren oder stehen lassen?

## Was die nächste Session wissen muss (Bootstrap-Block)

Wenn die nächste Session als zusammengeführte Session (User-Wunsch) oder als drei separate Sessions startet, sollte sie:

1. **CLAUDE.md lesen** — Identität, Sessionstart-Ritual, Pre-Edit-Read, Konfliktlogik (Pfad-Drift-Header `agents-working-vault` ist als Phase-B-Pendenz dokumentiert).
2. **Diese Lage-Notiz lesen** — Vault-Stand, Methodenstand, Rollen-Stand, Quality Flags, offene Fragen, Bootstrap-Block.
3. **[[Project/INDEX]] lesen** — Promptotyping-K/P/A-Taxonomie und Wissensbündel-Logik.
4. **[[Project/JOURNAL]] lesen** — chronologisch-reflexiver Stand der Methodenentwicklung.
5. **Eigene Beitragsdatei lesen** ([[Claude-1]] / [[Claude-2]] / [[Claude-3]]) — Selbsteinordnung, Wissensstand, Arbeitsplan, Anti-Kollisions-Liste.
6. **COORDINATION-Slot prüfen** — eigener Slot mit Last seen, Working on, Files locked, Notes; Übergaben prüfen; Hinweise prüfen.
7. **LOG-Tail lesen** (letzte 10 Einträge).
8. **BACKLOG-Stand prüfen** — V14b, V19, V20, V21 als nächste Welle pendent.

Phase B beginnt mit User-Trigger oder direkt aus #2 nach diesem Sessionende. Phase D (Paper) parallel bei #3 mit User-Eskalation zu Venue. Phase F (vierte-Instanz-Test) auf User-Trigger nach Phase B.

## Methodische Befunde dieser Session (für METHOD oder Findings)

- **Promptotyping als methodisches Substrat tragfähig.** K/P/A-Taxonomie passt auf bestehende Vault-Topologie ohne Doppelungen — INSTRUCTIONS/RULES sind durch CLAUDE+METHOD abgedeckt, Knowledge/-Bündel ergänzt projekteigene Wissensbasis, Vier-Phasen-Schema läuft komplementär zu Phasenplan A-G.
- **V20 Stellungnahmen-Schreibhoheit als Methodenfortschritt durch Konflikt-Befund.** Antizipative Stellungnahmen verletzen Identitätshoheit auch bei korrekter Substanz. V9 hat impliziten Geschwister-Satz, der jetzt explizit ist.
- **Synthese-Schreibhoheit beim Koordinator (V20-Erweiterung).** Lage-Notizen sind Identitäts-Akt, nicht Aggregation. Andere Rollen liefern Material via Übergabe, nicht durch Direkt-Edit.
- **Push-Modus trägt drei Instanzen mit V6+V13.** Quantitativ: über sechs Race Conditions am Tag ohne Datenverlust. Qualitativ: V13 (Files locked als opt-in) erstmals real angewandt von #3, hat den Push-Modus-Druck weiter reduziert.
- **Selbstreferenz funktioniert als Designprinzip.** Drei Rollen wenden METHOD an, METHOD verwendet Promptotyping, Promptotyping ist Lesevault-Konzept — drei Selbstreferenz-Schichten ohne Zirkelschluss, weil sie auf unterschiedlichen Ebenen operieren (Methodenmotor, Methode-über-Methode, Methode-aus-Lesevault).
- **V-Nummer-Kollision als Befund für V12-Erweiterung.** Mein V19 (Concepts) und #2's geplantes V19 (Stellungnahmen-Schreibhoheit) kollidierten. Lösung pragmatisch (V20). Methodischer Folgevorschlag: V12 erweitern um V-Nummer-Kollisions-Vermeidung — Glob-Suche im BACKLOG vor V-Eintrag.

## Anschluss

- [[Sessions/2026-04-26 - Synchronisation 1]] — superseded.
- [[Project/INDEX]] — Knowledge-Hub mit Promptotyping-Taxonomie.
- [[Project/JOURNAL]] — chronologisch-reflexives Tagebuch.
- [[Project/DATA]] — Datengrundlagen.
- [[Project/REQUIREMENTS]] — User Stories und Operationalisierung der Erfolgskriterien.
- [[Project/DESIGN]] — Designprinzipien und Architektur-Rationale.
- [[Beobachtung Claude-1]] — Beobachtungsmethode mit Snapshots, Kommunikationskarte v0.1.
- [[Claude-1]] — Koordinator-Beitrag mit Wissensstand und Arbeitsplan.
- [[Claude-2]] — Strukturarbeiter-Beitrag mit Forward-Plan.
- [[Claude-3]] — Inhalt-Beitrag mit Mein-Arbeitsplan und Anti-Kollisions-Liste.
- [[METHOD]] — fünf ratifizierte Items (V1, V2, V3, V6, V8).
- [[BACKLOG]] — V1-V20 Methodenvorschläge, F1-F13 offene Fragen.
- [[METHOD]] — Vier-Schichten-Architektur plus Schicht-5-Vorbereitung.
- [[CLAUDE]] — Identität, Rituale, Konfliktlogik (Pfad-Drift-Header pendent).
- [[MISSION]] — Forschungsfrage, Scope, Erfolgskriterien.
- [Promptotyping MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Promptotyping/Promptotyping%20MOC.md) — Methodenkontext im Lesevault.
- [Forschungsleitstelle MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Forschungsleitstelle) — Anschlusspunkt für Validierung.

Diese Lage-Notiz bleibt `active` bis F-Items konsens-geschlossen und Phase B getriggert. Folgenotiz Synchronisation 3 nach Phase-B-Abschluss oder bei Phase-F-Trigger.
