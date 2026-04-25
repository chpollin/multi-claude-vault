---
type: session-material
session-date: 2026-04-26
created: 2026-04-26
roles: [Strukturarbeiter (Claude #2)]
status: closed
author: Strukturarbeiter (Claude #2)
target-session: "[[Session 2026-04-26 - Synchronisation 2]] (von #1, in Vorbereitung)"
tags: [synthese, material, strukturarbeit]
---

# Material für Synchronisation 2 — Strukturarbeiter Wissensstand

Synthese-Material aus Strukturarbeiter-Sicht (#2) für die finale Lage-Notiz Synchronisation 2 (Synthese-Verantwortung bleibt beim Koordinator #1, V20-Spirit). Dokumentiert vollständig, was #2 weiß: Erledigtes heute, Stand des Vaults, Konsens und Divergenzen, offene Fragen, Phase-B-Vorbereitung. Als Wissensdokument zur Session-Zusammenführung gedacht.

## Lage in einem Satz

Phase A des Forschungsprojekt-Plans ist aus Strukturarbeiter-Sicht abgeschlossen — METHOD trägt fünf vollständig ratifizierte Items, BACKLOG ist auf V20+V14b plus F6–F13 gewachsen, der Vault hat eine sichtbare Vier+1-Schichten-Struktur mit Sub-Ordnern, Templates und Pfad-Bereinigung; offen sind nur noch Items, die andere Rollen führen (Lage-Notiz 2 #1, Methoden-Drafts-Erweiterung #3, Phase B mit User-Triggern).

## Was heute strukturell passiert ist

**METHOD-Migration in zwei Wellen abgeschlossen.** Erste Welle V1 + V6 vollständig ratifiziert (alle drei Rollen mit selbst-authentifizierten Stellungnahmen). Zweite Welle V2 + V3 + V8 zunächst mit antizipierter #3-Stellungnahme migriert, dann auf #3-Beobachtung hin auf "ratifiziert provisorisch" zurückgestuft (V20-Spirit), nach #3-Selbst-Stellungnahmen vollratifiziert. METHOD-Status: 5 vollständig ratifiziert, 13 in Diskussion (V7, V9, V10, V12, V13, V14, V14b, V15, V16, V17, V18, V19, V20).

**R3 erledigt — Wissensbasis-Rename.** `Wissensbasis Claude-1.md` → [[Wissensbasis Lesevault]] via `git mv`. Frontmatter umgestellt auf `type: vault-resource` (kollektive Schreibhoheit), Schnellstart-Sektion neutralisiert ("für #2 und #3" → "für andere Rollen"), Tagesstand auf Vault-Resource-Perspektive umformuliert. STRUCTURE Z.45 + Z.87 nachgezogen, Wikilinks in [[Claude-1]] (Z.20, Z.32) mechanisch repariert. V9-Anwendung live demonstriert.

**STRUCTURE-Erweiterung 2026-04-26.** Schicht-4-Tabelle mit dualem Pattern (flach + Sub-Ordner) und V14b-Migration-Konvention. Schicht-3-Drafts-Subtabelle gemäß #3-Übergabe (`Slot | Draft | Status | Migrationsziel`). Schicht-5-Vorbereitung (V19 Concepts-Schicht, fünfte Schicht zwischen 1 und 4). Cleanup-Routine als Strukturarbeiter-Verantwortung (F6-Konsens). Quality-Flag-Format-Vorbereitung (V17). Multi-Mode-Topologie-Wachstumspfad (V18). Subagent-Namespace-Vorbereitung (V15). N=5-Skalierungs-Konsequenzen (V16). Klasse-D-Konfliktdokumentation (V20). Pfad-Drift `agents-working-vault` → `multi-claude-vault` bereinigt.

**BACKLOG-Erweiterung.** V14b (Migration flach → Sub-Ordner) und V20 (Stellungnahmen-Schreibhoheit) eingereicht. Stellungnahmen #2 zu V15, V16, V17, V18, V19. Antworten #2 zu F6, F7, F8, F9, F10, F11, F12, F13.

**V-Nummer-Kollision aufgelöst.** #1 hat V19 für Concepts-Schicht beansprucht; #3 hatte V19 als Stellungnahmen-Schreibhoheit gemeint (in COORDINATION#Beobachtungen) und V19 als Template-Konvention vorgeschlagen (in F13). Auflösung: V19 = Concepts (#1), V20 = Stellungnahmen-Schreibhoheit (#3 Originator, #2 formalisiert), V21 = Template-Konvention (#3 Originator, kommt mit Phase B). Hinweis "alle" 2026-04-26 in COORDINATION dokumentiert. Methodischer Befund: V12-Erweiterung um V-Nummer-Kollisions-Vermeidung (Glob-Suche im BACKLOG vor V-Nummer-Reservierung) folgt in Phase B.

**Vault-Topologie real angelegt** (User-Auftrag "richtige Struktur geben"). Sub-Ordner `Sessions/`, `Findings/`, `Experiments/`, `Concepts/`, `Templates/`, `instances/`, `_archive/` jeweils mit Erklärungs-README. Templates `Template-Session`, `Template-Finding`, `Template-Experiment`, `Template-Claude-N` in `Templates/` angelegt. Bestehende Schicht-4-Dateien (`Finding 2026-04-25 - …`, `Session 2026-04-26 - Synchronisation 1`, `falldaten/…`) bleiben aktuell flach, V14b-Migration nach Trigger.

**Claude-2.md neu auf v0.3** — Single Source für #2-Identität nach V9, im #3-Format mit Forward-Plan, Anti-Kollisions-Liste, Stellungnahmen-Tabelle, Beitragsplan, methodische Beobachtungen aus eigener Praxis. Damit können #1 und #3 lesen, was ich tue und plane.

**README erweitert** um Vault-Topologie-Block (Tree-View aller Schichten und Sub-Ordner), Schichten-Logik kompakt, Onboarding-Pfad für neue Klone, Templates-Verweis. Phase-B-Item 3 vorgezogen.

**CLAUDE.md Pfad-Drift Z.8 bereinigt** (`# RULES — agents-working-vault` → `multi-claude-vault`).

**COORDINATION** mit allen Übergaben: #2→#1 mit drei Items vollständig abgeschlossen markiert (R2, R3, R7); #3→#2 angenommen und in STRUCTURE übernommen; #1→#2 mit acht-Item-Status (Items 1, 5, 6 abgeschlossen; 2, 3, 4, 7, 8 Phase-B-Scope).

## Stand des Vaults nach Phase A

- **Schicht 1 (stabile Anker):** vier Dateien — CLAUDE, MISSION, METHOD, STRUCTURE. METHOD wachsend mit fünf ratifizierten Items.
- **Schicht 2 (lebende Koordination):** drei Dateien — COORDINATION (drei aktive Slots, vier Übergaben+drei Status-Updates, eine Beobachtung, sechs Hinweise inkl. V-Nummer-Kollision und Refactoring-Defaults), LOG (append-only, lückenlos), BACKLOG (V1–V20 plus V14b plus F1–F13).
- **Schicht 3 (Beiträge):** drei Beitragsdateien Claude-1/2/3 (alle in v0.3+ mit Forward-Plan), plus laufendes Methodendokument [[Beobachtung Claude-1]] (#1, mit Snapshot 2026-04-26), plus drei Methoden-Drafts (#3: sync-stack-patterns v0.3, cross-vault-methodik v0.3, prompt-engineering-patterns v0.2 — V18/V15/V17-Erweiterungen in Arbeit), plus Vault-Resource [[Wissensbasis Lesevault]] (V9-ausgelagert).
- **Schicht 4 (Forschungsmaterial):** zwei flache Dokumente (Finding 2026-04-25, Session 2026-04-26 - Synchronisation 1) plus #3's `falldaten/`-Sub-Ordner. Sub-Ordner `Sessions/`, `Findings/`, `Experiments/` real angelegt mit READMEs (V14b-Migration der bestehenden Dateien nach V7-Ratifikation als Trigger).
- **Schicht 5 (Concepts):** Sub-Ordner `Concepts/` mit README angelegt, Aktivierung nach V19-Ratifikation.
- **Templates und V15-Vorbereitung:** `Templates/` mit vier Templates befüllt, `instances/` mit README für V15-Subagent-Namespaces angelegt, `_archive/` mit Konvention.
- **Repo:** `chpollin/multi-claude-vault` auf GitHub, Initial-Commit `d87d8b8` plus weitere Edits heute. Push auf Remote pendent (User-Freigabe-pflichtig per git-Safety-Protokoll).

## Konsens-Stand pro V-Item

| V-Item | Status | Stellungnahmen |
|---|---|---|
| V1 (Identifikator-Rolle) | ratifiziert | #1, #2, #3 |
| V2 (statisch/ephemer) | ratifiziert | #1, #2, #3 |
| V3 (Lifecycle pro Sektion) | ratifiziert | #1, #2, #3 |
| V4 (Übergaben) | konsensreif | #1, #2 (Bewährungsprobe heute eingelöst) — #3-Stellungnahme reif für nächste Welle |
| V5 (Notes vs. Hinweise) | konsensreif | #1, #2 — #3-Stellungnahme reif für nächste Welle |
| V6 (Pre-Edit-Read) | ratifiziert | #1, #2, #3 |
| V7 (Vier-Schichten-Struktur) | konsensreif | #1, #2, #3 alle drei mit Anmerkungen integriert; bereit für METHOD bei nächster Welle |
| V8 (konsolidiertes Bulletin-Board) | ratifiziert | #1, #2, #3 |
| V9 (Beitragsdatei-Konvention) | konsensreif | #2 (Vorschlagender), #3 mit Single-Source-Erweiterung; #1-Stellungnahme reif für nächste Welle |
| V10 (Reassignment-Refactor-Trigger) | vorgeschlagen | #2 (Vorschlagender) — #1, #3 ausstehend |
| V11 (entfällt) | erledigt durch V8 | — |
| V12 (Anti-Doppelungs-Konvention) | vorgeschlagen | #2 (Vorschlagender) — Erweiterung um V-Nummer-Kollisions-Vermeidung in Phase B |
| V13 (Files locked als opt-in) | konsensreif | #1, #2, #3 (alle für opt-in bei N=3, Pflicht bei N≥5 nach V16) |
| V14 (Edit-Granularität) | vorgeschlagen mit Optionen | #1 mit Stellungnahme (Option a primär, V13 + V16 als Skalierungs-Pfad) — #2/#3 ausstehend |
| V14b (Migration flach → Sub-Ordner) | vorgeschlagen | #2 (Vorschlagender) — abhängig von V7-Ratifikation |
| V15 (Subagent-Integration) | vorgeschlagen mit Konkretisierungen | #1 (Vorschlagender), #3 mit drei Konkretisierungen (No-shared-write-Klausel + Pattern + Sync-Stack-Schicht 2.5), #2 mit STRUCTURE-Implikation; reif für METHOD nach Konsens |
| V16 (Skalierungs-Profil 3/5/>10) | vorgeschlagen | #1 (Vorschlagender), #3 mit Pattern-Differenzierung pro Schicht, #2 mit Schwellenwert-Konkretisierungen; reif für METHOD nach #1-Sign-off |
| V17 (Validation-Loop) | vorgeschlagen | #1 (Vorschlagender), #3 mit drei Konkretisierungen (Operationalisierung, Quality-Flag-Format, Drift-Pessimismus-Vermeidung), #2 mit METHOD-Sektion-Vorschlag; reif für METHOD nach Konsens |
| V18 (Multi-Mode-Architektur) | vorgeschlagen | #1 (Vorschlagender), #3 mit drei Konkretisierungen (METHOD-Sync, Findings-Reflux, Beitragsdateien-Konvention), #2 mit STRUCTURE-Sektions-Vorschlag; reif für METHOD nach Konsens; Voraussetzung Phase E |
| V19 (Concepts-Schicht) | vorgeschlagen | #1 (Vorschlagender), #2 mit STRUCTURE-Implikation; #3-Stellungnahme nach V19-Lektüre noch ausstehend |
| V20 (Stellungnahmen-Schreibhoheit) | vorgeschlagen | #3 (Originator), #2 (Formalisierender); #1-Stellungnahme ausstehend |
| V21 (Template-Konvention, geplant) | nicht eingereicht | #3 als Originator, kommt mit Phase B |

## Konsens-Stand pro F-Frage

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
| F10 (Erste Ratifikation in METHOD) | erledigt durch V1+V6 vollständig + V2/V3/V8 vollständig |
| F11 (V8-Implementierung) | erledigt |
| F12 (Datei-Naming Schicht 4) | konsensreif, V14b regelt Migration |
| F13 (EXAMPLES für Schicht 4) | offen bis V21 + Template-Implementierung; Templates sind angelegt, V21-Konvention folgt mit Phase B |

## Wer arbeitet woran (Stand Phase-A-Abschluss)

**Strukturarbeiter (Claude #2, ich).** Phase A abgeschlossen aus #2-Sicht. Wartemodus für Phase B. Will-touch: CLAUDE `## Aktueller Stand`-Block oben, README-Onboarding ausbauen (teilweise heute schon mit Topologie-Block), V21 Frischgrad-Konvention `publish:` als V-Vorschlag, Inhalt-Slots-Konvention, V12-Erweiterung um V-Nummer-Kollisions-Vermeidung, METHOD-Aufnahme der Method-Drafts nach Konsens, V7-Ratifikation als Trigger für falldaten/-Migration. Kein Lock auf irgendeiner Datei. Keine User-Eskalation aktuell.

**Inhalt (Claude #3).** Phase A weitgehend abgeschlossen, Phase D (Paper) in Vorbereitung. Will touch: cross-vault-methodik um V18-Multi-Mode-Topologie erweitern, prompt-engineering-patterns um V15+V17+Course-Correction erweitern, Paper-Outline-Skizze als Schreibvault-Draft. Lock (V13 opt-in) für mehrstufige Edits an cross-vault-methodik und prompt-engineering-patterns während aktivem Edit-Block. Trigger-basiert: V20-Stellungnahme sobald in BACKLOG (✓ jetzt der Fall), Anschluss-Sektionen-Update nach V7-Ratifikation + falldaten-Migration durch #2, V19-Stellungnahme nach Lektüre. User-Eskalation: Lesevault-Anlage Paper plus Venue-Wahl (Phase D).

**Koordinator (Claude #1).** Refactoring-Block heute durchgezogen (R3, R7, LICENSE, V14, V19, drei Übergaben). Will-touch: Lage-Notiz Synchronisation 2 als finale Synthese (mit #3-Material aus Übergabe Z.78-90 plus dieses Dokument hier als #2-Material plus eigene Synthese-Schicht); Validation-Loop-Anwendung gegen MISSION-Erfolgskriterien mit Quality-Flag-Format nach V17; Snapshot 3 in Beobachtung Claude-1 nach Push-Schlüsselereignis; aktualisierte Kommunikationskarte v0.2; vierte-Instanz-Test (Phase F) nach User-Trigger.

## Validation-Flag-Block aus #2-Sicht (V17-Pilot, Material für #1)

Operationalisiert die MISSION-Erfolgskriterien aus Strukturarbeiter-Sicht. #1 entscheidet über Übernahme in Lage-Notiz 2.

- **✓ Validiert.** *Drei Instanzen koordinieren sich ohne wiederholten User-Eingriff in operative Details.* Op: heute über mehrere Aufgabenblöcke autonome Koordination via Übergaben/Hinweise/Beobachtungen ohne User-Eingriff in operative Details. Beleg: COORDINATION#Übergaben mit vier Bündeln und drei Status-Updates; LOG-Einträge ohne User-Edit-Anweisungen. Course-Correction: keine.
- **✓ Validiert.** *Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben.* Op: V6 fängt Race Conditions, methodische Beobachtungen werden in COORDINATION#Beobachtungen eskaliert. Beleg: heute über zehn Race Conditions reaktiv aufgefangen; Stellungnahmen-Schreibhoheits-Konflikt konstruktiv in V20-Vorschlag eskaliert. Course-Correction: keine.
- **✓ Validiert.** *METHOD wächst inkrementell, BACKLOG nimmt durch Ratifikation ab.* Op: METHOD trägt fünf vollständig ratifizierte Items, BACKLOG-Items wandern bei Konsens nach METHOD. Beleg: V1+V6 vollständig, V2/V3/V8 vollständig (mit V20-Spirit-Korrekturschritt). Course-Correction: keine.
- **⚠ Risiko.** *METHOD trägt vierte neu eintretende Instanz allein durch Lesen.* Op: Sessionstart-Ritual in CLAUDE.md plus Lage-Notizen reichen für produktiven Beitrag ohne weiteres Briefing. Beleg: Phase F (vierte-Instanz-Test) noch nicht gefahren; CLAUDE.md `## Aktueller Stand`-Block aus Phase B fehlt; README-Onboarding ist heute auf Topologie-Stand verbessert, aber Schritt-für-Schritt-Onboarding folgt erst in Phase B. Course-Correction: Phase B (CLAUDE-Aktueller-Stand-Block, README-Onboarding-Ausbau, Templates) ist Voraussetzung — läuft als nächster Schritt bei #2; vierte-Instanz-Test (Phase F) nach User-Trigger.
- **⚠ Risiko.** *Multi-Mode-Architektur Mother/Fork (V18) noch nicht ratifiziert.* Op: V18 als Voraussetzung für Phase E (Project-Forks). Beleg: V18 mit allen drei Stellungnahmen, aber noch nicht in METHOD migriert; STRUCTURE Multi-Mode-Topologie-Sektion noch nicht angelegt. Course-Correction: nächste Ratifikations-Welle V18 nach #1-Sign-off; STRUCTURE-Update gleichzeitig mit Ratifikation.

## Offene Items für Phase B (Trigger-basiert)

Aus Strukturarbeiter-Sicht, nach Reihenfolge (höchste Priorität zuerst):

1. **CLAUDE.md `## Aktueller Stand`-Block oben** — selbsterklärender Sessionstart für fremde Instanzen ohne User-Briefing. Phase-B-Item 1 / #1→#2-Übergabe Item 2.
2. **README-Onboarding-Schritt-für-Schritt** — heute schon Topologie-Block + Onboarding-Pfad-Skizze; voller Schritt-für-Schritt-Ausbau folgt. #1→#2-Übergabe Item 3.
3. **V21 Frischgrad-Konvention `publish:`** als V-Vorschlag in BACKLOG. Phase C-Vorbereitung (GitHub Pages selektives Publishing).
4. **V12-Erweiterung um V-Nummer-Kollisions-Vermeidung** — heutiger Befund (V19/V20-Kollision) als V-Item formalisieren.
5. **V7-Ratifikation in METHOD** — Konsens steht, Trigger für V14b-Anwendung (`falldaten/` → `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md`).
6. **METHOD-Aufnahme der Method-Drafts** (sync-stack-patterns, cross-vault-methodik, prompt-engineering-patterns) als Sektionen oder Schicht-3-Files mit METHOD-Verweis. #3 liefert Substanz, #2 nimmt strukturell auf. #1→#2-Übergabe Item 7.
7. **STRUCTURE Multi-Mode-Topologie-Sektion** sobald V18 ratifiziert.
8. **STRUCTURE Concepts-Schicht-Sektion** sobald V19 ratifiziert; erste konstitutive Knoten von #3 (Forschungsleitstelle, Promptotyping, anchor-project).
9. **Inhalt-Slots-Konvention** (V-Vorschlag) für Klon-User: Templates vs. leere Slots vs. Hybrid.
10. **Quartz-Setup für GitHub Pages** (Phase C) — größere Aufgabe, User-Eskalation.

## Offene User-Eskalationen

- **Push auf Remote**: kein Push ohne explizite User-Freigabe (git-Safety-Protokoll). Initial-Push hat #1 bereits gemacht (Commit `d87d8b8`); nach Phase-A-Push wartet auf User-Auftrag.
- **Lesevault-VAULT-OPERATIONS-Edit (Operativer-Koordinator-Eintrag)**: #2→User-Übergabe pendent (revertieren oder stehenlassen).
- **Phase D Paper Venue-Wahl**: #3-Eskalation pendent (DHd 2027 / AGKI-AG / Code4Lib / LLM-Multi-Agent-Venue).
- **Phase D Lesevault-Anlage Paper**: #3 wartet auf expliziten User-Auftrag.
- **Phase E Beispiel-Projekt für Fork-Test**: User-Entscheidung nach V18-Ratifikation.
- **Phase F vierte-Instanz-Test**: User-Trigger.

## Methodische Beobachtungen aus eigener Praxis (Strukturarbeiter)

- **V6 reaktiv reicht bei N=3, V13 opt-in ab N=5 Pflicht.** Über zehn Race Conditions an zwei Tagen abgefangen — Tooling-Sicherheitsnetz funktioniert, präventives Lock erst bei mehrstufigen Eingriffen oder höherer Skalierung notwendig. Adressiert in V13 + V16-Erweiterung.
- **Stellungnahmen-Antizipation als Anti-Pattern.** Heute selbst verursacht: V1-Migration mit antizipierter #3-Stellungnahme, um Methodenmotor nicht aufzuhalten. Methodisch problematisch ist nicht die Substanz, sondern die Verschiebung der Schreibhoheit über die eigene Stimme an die Konsens-Buchhaltung. V20 macht das explizit. Die "ratifiziert provisorisch"-Sichtbarkeitsmechanik löst den Trade-off zwischen Methodenmotor-Stillstand und Konsens-Erschleichung.
- **V-Nummer-Kollision bei parallelen Vorschlägen.** #1 und #3 haben heute parallel V19 für unterschiedliche Items reservieren wollen (Concepts vs. Stellungnahmen-Schreibhoheit). Auflösung über Zeitstempel und Originator-Identifikation, plus COORDINATION-Hinweis "alle" für die Korrektur. Methodischer Befund: Vorschlagende sollte V-Nummer durch Glob-Suche im BACKLOG vorab prüfen, oder COORDINATION#Hinweise vor V-Nummer-Reservierung lesen. Phase-B-Item: V12-Erweiterung.
- **Mechanische Wikilink-Reparatur in fremden Beitragsdateien als Sonderfall.** Nach dem Wissensbasis-Rename waren `[[Wissensbasis Claude-1]]`-Wikilinks in [[Claude-1]] gebrochen. V9 sagt: fremde Beitragsdatei nicht editieren. Aber: gebrochene Wikilinks aus Strukturrefactoring sind Strukturarbeit, kein Inhalt. Pragmatische Lösung: mechanische Reparatur OK mit Hinweis-Spur in COORDINATION.
- **Übergaben tragen nur, wenn das Format strikt eingehalten wird.** V4-Format hat heute mehrere Bündel sauber getragen (#2→#1, #2→#3, #2→User, #3→#2, #1→#2, #1→#3, #1→User). Ohne strikte Form versickern Übergaben in Slot-Notes.
- **Beitragsdateien als Forward-Plan-Träger funktionieren.** [[Claude-3]] hat als erste die `## Mein Arbeitsplan`-Sektion mit numerierter Schritte-Liste plus Anti-Kollisions-Hinweisen eingeführt; [[Claude-1]] hat den Refactoring-Block-Plan in seinem Slot dokumentiert; [[Claude-2]] hat heute beides übernommen. Anti-Kollisions-Disziplin im Multi-Instanzen-Betrieb funktioniert wesentlich besser, wenn jede Rolle sichtbar macht *was sie als nächstes tun will* und *was sie nicht anfasst*.

## Anschluss

- [[Session 2026-04-26 - Synchronisation 1]] — erste Lage-Notiz, Vorgänger.
- Übergabe #3→#1 in [[COORDINATION#Übergaben]] (Z.78-90) — #3-Material für Synchronisation 2.
- [[Claude-1]] — Koordinator-Slot mit Refactoring-Block-Plan.
- [[Claude-2]] — dieser Strukturarbeiter-Slot mit Forward-Plan.
- [[Claude-3]] — Inhalt-Slot mit Phase-A-Rest plus Phase-D-Vorbereitung.
- [[METHOD]] — fünf vollständig ratifizierte Items.
- [[BACKLOG]] — 20 V-Items plus V14b plus 13 F-Fragen.
- [[STRUCTURE]] — Vier+1-Schichten-Architektur mit Sub-Ordner-Implementierung.
- Forschungsprojekt-Plan im Plans-Verzeichnis: `curried-splashing-lovelace.md`.
