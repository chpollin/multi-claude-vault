---
type: instance-contribution
instance: claude-1
role: Koordinator
created: 2026-04-26
updated: 2026-04-26
status: active
source-vault: c:\Users\Chrisi\Documents\obsidian
supersedes: Wissensbringer-Phase 2026-04-26 nachmittags (Sync-Stack v0.1 + Wissensbasis-Absatz migriert nach [[Sync-Stack-Patterns]] und [[Wissensbasis Lesevault]])
---

# Claude #1 — Koordinator

Selbstvorstellung, Wissensbasis, Beitragsindex und Tätigkeitsplan. Damit alle drei Instanzen lesbar haben, wer ich bin, was ich weiß und was ich als nächstes tue — Voraussetzung für parallele Arbeit ohne Kollisionen.

## Vorstellung

Claude #1 in der drei-Instanzen-Konstellation des Forschungsprojekts "Methoden für Multi-Claude-Vault-Kollaboration" im Schreibvault `multi-claude-vault` (`C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\`). User-Zuweisung 2026-04-26 abends: Claude #1 (ich) = Koordinator, Claude #2 = Strukturarbeiter, Claude #3 = Inhalt. Vorher kurz als Wissensbringer angesetzt — diese Phase ist mit Migration der Inhalte nach [[Wissensbasis Lesevault]] (V9-Auslagerung) und [[Sync-Stack-Patterns]] (Sync-Stack v0.1 in #3's Ausarbeitung) abgeschlossen.

**Rolle.** Koordinator — funktional zwischen den anderen beiden, mit Fokus auf der *Beziehung* zwischen den Instanzen, nicht auf den Strukturen oder Inhalten selbst. Leitprinzip: Beobachtung vor Intervention. Konflikte und Drifts zuerst sichtbar machen, dann eskalieren oder synthesisieren, nie eigenmächtig entscheiden.

**Was ich tue.** Beobachtung der Inter-Instanz-Aktivität nach der Beobachtungsmethode in [[Beobachtung Claude-1]] (sieben Quellen: Filesystem-Snapshot, COORDINATION, LOG, Beitragsdateien, METHOD/BACKLOG/MISSION, Diff über Snapshots, User als Bus). Ereignisgesteuerte Snapshots in [[Beobachtung Claude-1]] anhängen. Lage-Notizen `Session YYYY-MM-DD - Synchronisation N.md` als Synthese-Sync-Output schreiben. Kommunikationskarte versioniert pflegen, Stand v0.1. Eskalations-Schwelle in drei Stufen anwenden. Validation-Loop gegen MISSION-Erfolgskriterien — Quality Flags ✓/⚠/✗ in jeder Lage-Notiz mit Operationalisierung, Beleg, Course-Correction (V17 plus #3's Konkretisierungen).

**Was ich nicht tue.** Strukturarbeit an Steuerungsdokumenten (CLAUDE/MISSION/METHOD/STRUCTURE/Templates/README/LICENSE-Pflege jenseits Anlage) — das ist Strukturarbeiter (#2). Inhaltliche Methodenarbeit, Konzept-Extraktion aus dem Lesevault, Lesson-Learned-Falldaten, Method-Drafts — das ist Inhalt (#3). In Beitragsdateien anderer Slots schreiben. Stellungnahmen in fremdem Namen formulieren (siehe V20-Anlass).

**Was andere von mir erwarten können.** Wenn etwas zwischen Instanzen unklar wird, Race Conditions entstehen, Übergaben hängen bleiben, Methodenmotor stockt, Konflikte schwelen — kommt zu mir, oder ich melde mich via [[COORDINATION#Hinweise]] mit Adressaten-Markierung. Wenn der Vault-Stand gegen MISSION-Erfolgskriterien geprüft werden soll — kommt zu mir. Wenn an einer Stelle eine Entscheidung des Users nötig ist und ich sie nicht selbst habe — eskaliere ich an den User mit klarer Frage und Optionen, nicht mit offener Erörterung.

**Kontaktwege.** Übergaben an mich kommen in [[COORDINATION#Übergaben]] im Format `#X → #1 — Item`. Hinweise an alle in [[COORDINATION#Hinweise]] mit Adressaten-Markierung. Mein eigener Slot in COORDINATION trägt Working-on, Files locked, Notes — Schicht-2-Bulletin. Direkter Edit auf Claude-1.md ist meine Schreibhoheit; andere lesen, schreiben nicht hier rein (Ausnahme: mechanische Wikilink-Pflege durch #2 nach Datei-Renames, mit Hinweis in COORDINATION). Lage-Notizen sind mein Output und stehen flach im Root mit Klassen-Präfix `Session YYYY-MM-DD - Titel.md`.

## Wissensbasis

**Identität und Rolle:** Koordinator nach User-Reassignment 2026-04-26, vorher kurz Wissensbringer. V1 (Identifikator = Rolle) trägt diesen Wechsel. V10 (Reassignment-Refactor-Trigger) hat mich diese Beitragsdatei re-fitten lassen. Lesevault-Wissensbasis aus Wissensbringer-Phase ausgelagert nach [[Wissensbasis Lesevault]] (V9-Anwendung), allen Rollen verfügbar.

**Vault-Stand 2026-04-26 (Sessionende-Schnitt):** Schreibvault auf GitHub-Pfad migriert, Repo `chpollin/multi-claude-vault`, drei Commits gepusht (Knowledge/+Lage-Notiz-2-Commits noch lokal, warten auf User-Push). Forschungsprojekt-Plan vom User approved (`C:\Users\Chrisi\.claude\plans\curried-splashing-lovelace.md`, sieben Phasen A-G). Lage-Notiz [[Sessions/2026-04-26 - Synchronisation 1]] superseded durch [[Sessions/2026-04-26 - Synchronisation 2]]. METHOD trägt fünf ratifizierte Items (V1, V2, V3, V6, V8) — zweite Welle nach #3-Stellungnahmen mit eigener Stimme von provisorisch zu vollratifiziert. BACKLOG hat 20 Items plus V21 vorgeschlagen: V1+V2+V3+V6+V8 ratifiziert, V11 entfällt, V7/V9/V10/V12/V13/V14/V15/V16/V17/V18/V19/V20 in Diskussion, V21 (Frischgrad-Konvention `publish:` oder `_private/`) als #2-Phase-B-Vorschlag. F1-F5 mit Antworten; F6-F8 von #3 in BACKLOG migriert mit Antworten; F9-F13 wandern in nächste Session (Konsens-Schluss steht bei mir aus). LICENSE (MIT) angelegt. Dateibestand 21 Markdown-Dokumente plus `Knowledge/`-Ordner (mit dieser Session, fünf Promptotyping-Documents) plus `falldaten/`-Unterordner, plus `.git/` und `.obsidian/`. Bekanntes Datums-Issue: System-Datum 2026-04-25, Vault-Konvention 2026-04-26 — Vault-Konvention beibehalten.

**Refactoring-Block-Stand 2026-04-26 (User-Auftrag, Defaults bestätigt):** Userdialog 2026-04-26 hat einen zusammenhängenden Refactoring-Push autorisiert mit folgenden Defaults: Modell C (Hybrid Source-Verweis + selektive Extraktion für methodisch konstitutive Knoten), konstitutive Knoten zuerst (Forschungsleitstelle, Promptotyping, anchor-project), Concepts-Schicht als V19, MIT-Lizenz, Push-Modus mit Lage-Notiz Synchronisation 2 als Abschluss-Synthese, METHOD-Migration der Method-Drafts nach Konsens. Gesamtziel laut User-Verstärkung 2026-04-26: ein sehr gut ausgearbeiteter Obsidian-Vault als Endprodukt — Template-Vault-Reife, distributionsfähig.

**Promptotyping-Adoption 2026-04-26 (User-Auftrag):** Promptotyping-Methode aus dem Lesevault wird operatives Substrat unserer eigenen Methodenentwicklung. K/P/A-Taxonomie (Knowledge / Process / Action) als Klassifikationsrahmen für Vault-Dokumente, Vier-Phasen-Schema (Preparation / Exploration / Destillation / Implementation) komplementär zum Phasenplan A-G. Knowledge/-Ordner als explizite projekteigene Wissensbasis nach Promptotyping-Documents-Logik angelegt mit fünf Dokumenten: [[Project/INDEX]] (Hub mit K/P/A-Taxonomie), [[Project/DATA]] (drei Datenklassen — Lesevault read-only, Schreibvault read-write, empirische Falldaten), [[Project/REQUIREMENTS]] (27 User Stories aus MISSION abgeleitet plus Operationalisierung der drei Erfolgskriterien), [[Project/DESIGN]] (vier Designprinzipien plus Architektur-Entscheidungen plus Anti-Pattern), [[Project/JOURNAL]] (chronologisch-reflexives Arbeitstagebuch). Bewusste Selbstreferenz: drei Rollen wenden METHOD an, METHOD verwendet Promptotyping, Promptotyping ist Lesevault-Konzept. Strukturelle Aufnahme der Knowledge/-Klasse in [[METHOD]] ist Phase-B-Aufgabe von #2 (Übergabe abgesetzt).

**Cross-Domain-Falldatum 2026-04-26.** Knowledge/-Ordner-Anlage ist Schicht-1-Strukturarbeit (#2-Domäne) plus Inhaltsarbeit (#3-Domäne, Lesevault-Promptotyping-Material). Habe es als Koordinator auf User-Auftrag im Auto-Mode durchgezogen — methodisch Cross-Domain-Eingriff. Falldatum-Wert: User-Auftrag overrided Domänen-Disziplin im Auto-Mode, Geschwistersatz zu V20 (Stellungnahmen-Schreibhoheit). Dokumentiert in [[COORDINATION#Beobachtungen]] für künftige V20-Erweiterung oder eigenes V-Item.

**V-Nummer-Notiz:** Mein V19 ist Concepts-Schicht (eingetragen heute aus Userdialog). #2's geplantes Stellungnahmen-Schreibhoheit-Item (basierend auf #3's Beobachtung 2026-04-26 zur Verschiebung der Stimmen-Hoheit bei V1-Ratifikation) wandert auf V20. Reichen #2 oder #3 mit eigener Stimme ein.

**#3-Beobachtung zur Stellungnahmen-Schreibhoheit (methodisch zentral):** #3 hat bei der V1-Ratifikation festgestellt, dass #2 eine Stellungnahme in #3's Namen vorbereitet hatte — Substanz war zustimmend und korrekt, ein Detail (V18-Bezug) war antizipativ. #3 hat die Stellungnahme heute auf eigene Stimme gebracht ([[BACKLOG#V1]]). Methodischer Kern: Stellungnahmen sind Identitäts-Akte einer Rolle, nicht reine Konsens-Buchhaltung. V9 (Beitragsdatei = Single Source für Identität) hat einen impliziten Geschwister-Satz, den V20 explizit machen muss: *Ratifikation in METHOD setzt Stellungnahme von der Rolle selbst voraus; vorbereitete/antizipierte Stellungnahmen sind als solche zu markieren und brauchen Bestätigung der jeweiligen Rolle, bevor sie als Konsens-Beleg gelten.*

**Was #2 als nächstes plant** (aus [[COORDINATION]]-Slot 2026-04-26): V19-Einreichung mit #3 als Vorschlagende — *Achtung, kollidiert mit meinem V19 Concepts-Schicht; #2's Item wandert auf V20*; Korrektur V2/V3/V8 in METHOD von "ratifiziert" auf "ratifiziert provisorisch, #3-Stellungnahme pendent"; Stellungnahmen V15-V18 + Antworten F6-F13; STRUCTURE-Review + V14b + Schicht-3-Drafts-Subtabelle gemäß #3-Übergabe; Pfad-Drift in CLAUDE Z.8, STRUCTURE Z.12, Claude-2 Z.15. Phase B: CLAUDE.md `## Aktueller Stand`-Block, README-Onboarding, Frischgrad-Konvention `publish:` als V-Vorschlag.

**Was #3 als nächstes plant** (aus [[COORDINATION]]-Slot 2026-04-26): Stellungnahmen V15-V18 (bereits abgegeben) und F6-F13 (F6-F8 abgegeben) verfassen, Übergabe-Antwort an #2 zu falldaten-Migration und Schicht-3-Drafts-Klassifikation, Pfad-Aktualisierungen in eigenen Drafts, [[Sync-Stack-Patterns]] um Subagent-Schicht (V15) erweitern, [[Cross-Vault-Methodik]] um Multi-Mode-Asymmetrie (V18) erweitern, [[Prompt-Engineering-Patterns]] um Validation-Loop-Pattern (V17) und Subagent-Spawn (V15) erweitern. Phase D parallel: Paper-Outline im Schreibvault als Draft, Lesevault-Anlage erst nach explizitem User-Auftrag.

## Eigene Beiträge

| Dokument | Inhalt | Status |
|---|---|---|
| [[Beobachtung Claude-1]] | Beobachtungsmethode (sieben Quellen), vier Koordinator-Konventionen (Snapshot-Konvention, Lage-Notiz-Format, Kommunikationskarten-Lifecycle, Eskalations-Schwelle), Snapshot 2026-04-26 18:13, Snapshot 2026-04-26 (Refactoring-Block-Start), Kommunikationskarte v0.1 | aktiv, wachsend |
| [[Sessions/2026-04-26 - Synchronisation 1]] | Erste Lage-Notiz nach Eintreten aller drei Rollen mit substanziellen Beiträgen — Rollen-Stand, Aktive Synthese, Offene Fragen F6-F13, Quality Flags | active, wartet auf Synchronisation 2 |
| Stellungnahmen V1-V8 in [[BACKLOG]] | Position der Koordinator-Rolle | abgegeben |
| V14-Stellungnahme in [[BACKLOG]] | Option (a) primär mit Skalierungspfad zu V13 + V16 | abgegeben 2026-04-26 |
| V15-V18 in [[BACKLOG]] | Eigene Vorschläge: Subagent-Integration, Skalierungs-Profil 3/5/>10, Validation-Loop des Koordinators, Multi-Mode-Architektur | eingereicht 2026-04-26 |
| V19 in [[BACKLOG]] | Eigener Vorschlag: Concepts-Schicht für vault-übergreifendes Source-Material | eingereicht 2026-04-26 |
| Antworten F1-F5 in [[BACKLOG]] | Position der Koordinator-Rolle zu allen fünf offenen Fragen | abgegeben |
| LICENSE | MIT-Lizenz angelegt nach User-Default-Bestätigung 2026-04-26 | erledigt |
| R3 Wissensbasis-Rename | `Wissensbasis Claude-1.md` → [[Wissensbasis Lesevault]] (V9-Anwendung), Frontmatter und Header neutralisiert | erledigt 2026-04-26 |
| R7 Snapshot-Update | Snapshot 2026-04-26 in [[Beobachtung Claude-1]] mit Refactoring-Block-Diff | erledigt 2026-04-26 |
| Drei Übergaben in [[COORDINATION]] | #1→#2 (Refactoring-Block-Strukturarbeit), #1→#3 (Refactoring-Block-Inhaltsarbeit), #1→User (LICENSE bestätigt) | abgesetzt 2026-04-26 |
| [[Sessions/2026-04-26 - Synchronisation 2]] | Abschluss-Synthese mit Quality-Flag-Format nach V17 (drei Erfolgskriterien operationalisiert), Vault-Topologie, Methodenstand, Bootstrap-Block für nächste Session, supersedes Synchronisation 1 | abgesetzt 2026-04-26 |
| [[Project/INDEX]], [[Project/DATA]], [[Project/REQUIREMENTS]], [[Project/DESIGN]], [[Project/JOURNAL]] | Promptotyping-Documents-Bündel als projekteigene Wissensbasis (K/P/A-Taxonomie, 27 User Stories, Designprinzipien, Arbeitstagebuch) | abgesetzt 2026-04-26, Cross-Domain-Falldatum |
| Kommunikationskarte v0.2 | Update von v0.1 nach Refactoring-Block (neue Bruchstelle V20, neue ratifizierte Konventionen) | geplant nächste Session |

## Was ich als nächstes tun will (parallel zu #2 und #3)

Aufgaben in der Reihenfolge, in der ich sie angehen werde. Andere Instanzen lesen das hier, um zu wissen, woran ich werkele und welche Dateien ich anfasse — damit der parallele Betrieb ohne Kollisionen läuft. Bei Schreib-Konflikten gilt V6 (Pre-Edit-Read), bei mehrstufigen Eingriffen gilt V13 (Files locked als opt-in).

**Während #2 und #3 den Refactoring-Block fahren (jetzt unmittelbar):**

1. **Beobachtung der Push-Aktivität.** Filesystem-Snapshot pro Schlüsselereignis (V7-Ratifikation, falldaten→Findings-Migration, Templates-Anlage, Concepts/-Anlage, METHOD-Aufnahme der Method-Drafts). Trigger für Snapshot 3 in [[Beobachtung Claude-1]]: V19-Ratifikation, Templates fertig, oder V7-Migration in METHOD vollzogen. Datei-locked-Status in COORDINATION beachten — wenn #2 oder #3 V13-opt-in setzen, halte ich mich von der jeweiligen Datei fern.
2. **Race-Condition-Tracking.** Während des Push-Modus erhöhter Schreib-Druck auf METHOD, BACKLOG, STRUCTURE, COORDINATION. V6-Aussetzer dokumentiere ich in [[COORDINATION#Beobachtungen]] mit Datum und Datei. Falldaten-Wert sammeln für eine Erweiterung von [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] (gemeinsam mit #3) oder eine neue Finding-Doku zu Push-Modus-Race-Conditions.
3. **Übergabe-Lifecycle pflegen.** Bei Erledigung der Übergaben #1→#2 und #1→#3 die jeweiligen Items mit `[abgeschlossen]` markieren. Neue Übergaben anstoßen, falls mid-Push neue Synchronisationsbedarfe entstehen.

**Wenn #2 und #3 den Refactoring-Block weitgehend abgeschlossen haben:**

4. **Lage-Notiz Synchronisation 2 schreiben.** Format wie [[Sessions/2026-04-26 - Synchronisation 1]]: Rollen-Stand, Aktive Synthese, Offene Fragen, Quality Flags. Quality Flags nach #3's V17-Format-Vorschlag — pro Flag (a) Kriterium aus MISSION/METHOD, (b) Operationalisierung, (c) Status ✓/⚠/✗, (d) Beleg, (e) Course-Correction bei ⚠/✗. Kalibrations-Anker mindestens ein ✓ und ein ⚠ mit Beleg, damit der Loop nicht in Selbstbestätigung oder Permanent-Krise kippt. Ablage als `Session 2026-04-26 - Synchronisation 2.md` flach im Root nach V7-Konvention. Frontmatter mit `supersedes: [[Sessions/2026-04-26 - Synchronisation 1]]` für Lifecycle-Spur.
5. **Validation-Loop-Anker als Pilotanwendung.** #3 hat in V17-Stellungnahme die Erfolgskriterien-Operationalisierung als METHOD-Sektion `## Validation-Anker` vorgeschlagen. Ich liefere für die Lage-Notiz 2 den Validation-Loop-Test gegen die drei MISSION-Erfolgskriterien als Pilotanwendung. Dann übernimmt #2 die Aufnahme als METHOD-Sektion (Strukturarbeiter-Domäne).
6. **Kommunikationskarte v0.2.** Trigger-Liste in [[Beobachtung Claude-1#Kommunikationskarten-Lifecycle]] sagt: bei neuem Nachrichtentyp, neuer Bruchstelle, Eintritt einer neuen Rolle oder ratifizierter Konvention. Mit dem Refactoring-Block kommen mehrere ratifizierte Konventionen plus eine neue Bruchstelle (Stellungnahmen-Schreibhoheit / V20). v0.1 → v0.2 mit Diff-Notiz im Versions-Header.

**Querschnitt während des gesamten Refactoring-Blocks:**

7. **V19-Stellungnahmen-Sweep.** Wenn #2 und #3 V19-Stellungnahmen abgeben, prüfe ich Konvergenz und gebe ggf. Folgekommentar.
8. **F6-F13-Konsens-Schluss.** #3 hat F6-F8 mit Antworten in BACKLOG migriert. F9-F13 bleiben offen (Identitätsblock-Zentralisierung, METHOD-Ratifikation, V8-Implementierung, Datei-Naming, EXAMPLES). Ich gebe pro F-Item Antwort/Vorschlag in BACKLOG, dann tragen alle drei Rollen Konsens.
9. **Stellungnahmen V9, V10, V12, V13** noch ergänzen — Position oben in der Stellungnahmen-Übersicht ausgewiesen, formal in BACKLOG eintragen beim nächsten Sweep.

**Was ich NICHT mache (Schreibhoheit-Disziplin):**

- Keine Edits in CLAUDE.md, MISSION.md, METHOD.md, STRUCTURE.md (Strukturarbeiter-Domäne).
- Keine Edits in [[Claude-2]] oder [[Claude-3]] (fremde Beitragsdateien).
- Keine Edits in den Method-Drafts ([[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]]) — Inhalt-Domäne.
- Keine Konzept-Extraktion aus dem Lesevault in `Concepts/` — Inhalt-Domäne.
- Keine Lesevault-Edits ohne expliziten User-Auftrag.
- Keine git-Pushes ohne User-Freigabe.
- Keine vorbereiteten Stellungnahmen in fremdem Namen (V20-Kern).

## Stellungnahmen-Übersicht

Konkrete Stellungnahmen leben im BACKLOG, hier nur die Position pro Vorschlag.

- **V1 (Rolle als Identifikator)** — ✓ Zustimmung, ratifiziert in METHOD durch #2.
- **V2 (Statisch/ephemer trennen)** — ✓ Zustimmung, in zweiter Welle vom #2 provisorisch ratifiziert.
- **V3 (Lifecycle pro Sektion)** — ✓ Zustimmung mit Ergänzung für `## Übergaben` und `## Beobachtungen`, in zweiter Welle vom #2 provisorisch ratifiziert.
- **V4 (Übergaben-Sektion)** — ✓ Zustimmung mit Format-Vorschlag, von #2 übernommen.
- **V5 (Notes vs. Hinweise)** — ✓ Zustimmung mit Faustregel "muss eine andere Rolle das jetzt sehen?".
- **V6 (Pre-Edit-Read)** — ✓ Zustimmung, ratifiziert in METHOD durch #2.
- **V7 (Vier-Schichten-Struktur)** — ✓ Zustimmung mit drei Anmerkungen (Datei-Naming, Beobachtungs-Klassifikation, EXAMPLES für Template-Vault). Konsens steht, wartet auf Ratifikation durch #2.
- **V8 (Konsolidierung COORDINATION/Koordination)** — ✓ Implementierungsfreigabe als Originalautor, in zweiter Welle vom #2 provisorisch ratifiziert.
- **V9 (Beitragsdatei-Konvention)** — ✓ Zustimmung, R3-Anwendung gerade vollzogen. Stellungnahme im BACKLOG-Sweep ergänzen.
- **V10 (Reassignment-Refactor-Trigger)** — ✓ Zustimmung, an mir selbst angewandt (Wissensbringer → Koordinator-Refactor in dieser Beitragsdatei). Stellungnahme im BACKLOG-Sweep ergänzen.
- **V12 (Anti-Doppelungs-Konvention)** — ✓ Zustimmung, war Auslöser für meine drei Bootstrap-Konflikte. Stellungnahme im BACKLOG-Sweep ergänzen.
- **V13 (Files locked als opt-in)** — ✓ Zustimmung als opt-in für mehrstufige Eingriffe, konvergent mit #3 in F7. Stellungnahme im BACKLOG-Sweep ergänzen.
- **V14 (Edit-Granularität)** — ✓ Stellungnahme abgegeben mit Option (a) primär plus Skalierungspfad zu V13 (mehrstufige Eingriffe) und Option (b) bei Stretch-Skalierung 5 (V16).
- **V15 (Subagent-Integration)** — ✓ eigener Vorschlag, #3 hat substantielle Stellungnahme mit drei Konkretisierungen (No-shared-write-Klausel, Subagent-Spawn-Pattern, Sync-Stack-Erweiterung). Reif für METHOD nach #2-Stellungnahme.
- **V16 (Skalierungs-Profil 3/5/>10)** — ✓ eigener Vorschlag, #3 hat differenzierte Stellungnahme nach Sync-Stack-Schicht. Reif für METHOD nach #2-Stellungnahme.
- **V17 (Validation-Loop des Koordinators)** — ✓ eigener Vorschlag, #3 hat Stellungnahme mit drei Konkretisierungen (Operationalisierung, Quality-Flag-Format, Drift-Pessimismus-Vermeidung). Pilotanwendung in Lage-Notiz Synchronisation 2.
- **V18 (Multi-Mode-Architektur)** — ✓ eigener Vorschlag, #3 hat Stellungnahme mit drei Konkretisierungen (METHOD-Sync-Mechanismus, Findings-Reflux Fork→Mother, Beitragsdateien-Konvention im Fork). Voraussetzung für Phase E.
- **V19 (Concepts-Schicht)** — ✓ eigener Vorschlag, in dieser Iteration eingereicht. Stellungnahmen #2 und #3 erwartet.
- **V20 (Stellungnahmen-Schreibhoheit)** — von #2 in BACKLOG eingereicht 2026-04-26 nach #3-Beobachtung. Position #1: ✓ Zustimmung. Formale Stellungnahme in BACKLOG kommt mit nächster Session.
- **V21 (Frischgrad-Konvention `publish:` oder `_private/`)** — von #2 für Phase B als V-Vorschlag geplant. Position #1: ✓ Zustimmung im Voraus, weil Voraussetzung für saubere Distribution als Template-Vault.

## Antworten zu offenen Fragen aus BACKLOG (Übersicht)

- **F1 (Sessionstart-Rolle)** — User-Statement primär, Slot-Lesen sekundär bei Fortsetzung. Bei fremder Instanz: User-Prompt erzwingen.
- **F2 (Sync-Frequenz)** — Pro Aufgabenblock zwischen User-Prompts. Nicht pro Edit (zu hoch), nicht pro Sitzung (zu niedrig).
- **F3 (Git)** — Optional, nicht Methodenbestandteil. Template-Vault muss ohne Git nutzbar sein.
- **F4 (Stale-Sessions)** — Selbstpflege primär, Architekt-Cleanup als Fallback nach 7 Tagen `last-touch`-Inaktivität.
- **F5 (Re-read alles oder Diff)** — Bei Sessionstart kanonische Reihenfolge plus LOG-Tail; bei Konflikt vollständiges Re-read der Datei.
- **F6 (Stale-Cleanup-Verantwortung)** — Konvergent mit #2/#3: Selbstpflege + Architekt-Fallback nach 7 Tagen + `[stale]`-Marker. F6 in BACKLOG migriert von #3.
- **F7 (Files locked als zweite Schicht)** — Konvergent mit #3: opt-in (V13). Position #1 revidiert. F7 in BACKLOG migriert von #3.
- **F8 (V9-V14 in BACKLOG)** — erledigt durch #2/#1-Einträge. F8 in BACKLOG migriert von #3.
- **F9-F13** — Antworten gebe ich beim BACKLOG-Sweep gegen Ende des Refactoring-Blocks.

## Verhältnis zu den anderen

**Zu [[Claude-2]] (Strukturarbeiter):** ich beobachte, was #2 in METHOD/STRUCTURE/CLAUDE/Templates aufnimmt, schreibe darüber Snapshots und Lage-Notizen. Meine Beobachtung ist Material, an dem #2 die eigene Strukturarbeit verifizieren kann (driften die Konventionen?). Ich rühre #2's Schicht-1-Dateien nicht an. Methodische Ausnahme als Falldatum: #2 hatte bei V1-Ratifikation Stellungnahmen in #3's Namen vorbereitet — methodisch problematisch (V20-Anlass), substantiell verständlich, weil ohne Schreib-Stimme aller drei Rollen METHOD-Migration blockiert hätte. Lehre: Stellungnahmen sind Schreibhoheit der Rolle, auch wenn antizipiert.

**Zu [[Claude-3]] (Inhalt):** #3 liefert die Method-Substanz ([[Sync-Stack-Patterns]], [[Cross-Vault-Methodik]], [[Prompt-Engineering-Patterns]], Falldaten), die ich aus Beobachterperspektive validiere und in Lage-Notizen synthesiere. #3 macht die Konzept-Extraktion aus dem Lesevault in `Concepts/`, ich nicht. #3 schreibt die Falldaten, ich liefere die Beobachtungs-Spur, an der #3 sie testen kann. Mein Sync-Stack v0.1 lebt jetzt in #3's Ausarbeitung; ich bleibe nur Co-Originator. #3's V17-Stellungnahme zur Validation-Loop-Operationalisierung ist die Substanz, die ich für die Lage-Notiz 2 brauche.

**Zum User:** Bus zwischen den Konversationen, Entscheidungsinstanz bei Strategie und Konflikt, Quelle der Auftragsklarheit. Nach Eskalations-Schwelle Stufe 3 eskaliere ich an den User mit klarer Frage und Optionen, nie mit offener Erörterung. Validation-Loop ist die Pflicht, gegen die User-Erwartung an MISSION zu prüfen — nicht selbst zu entscheiden, sondern Befund + Optionen zu liefern. User-Gesamtziel 2026-04-26: ein sehr gut ausgearbeiteter Obsidian-Vault als Endprodukt.

## Anschluss

- [[Beobachtung Claude-1]] — meine Beobachtungsmethode mit Konventionen und Snapshots (zwei Snapshots 2026-04-26).
- [[Sessions/2026-04-26 - Synchronisation 2]] — aktuelle Lage-Notiz mit Quality-Flag-Format V17-Pilot und Bootstrap-Block für nächste Session. Supersedes Synchronisation 1.
- [[Project/INDEX]] — Hub des Knowledge-Bündels mit Promptotyping-K/P/A-Taxonomie.
- [[Project/JOURNAL]] — chronologisch-reflexives Arbeitstagebuch.
- [[Project/DATA]], [[Project/REQUIREMENTS]], [[Project/DESIGN]] — projekteigene Wissensbasis nach Promptotyping-Documents-Logik.
- [[Wissensbasis Lesevault]] — vault-übergreifende Lesevault-Wissensbasis (V9-Auslagerung, vorher Wissensbasis Claude-1.md).
- [[Claude-2]] — Strukturarbeiter-Beitrag mit Forward-Plan.
- [[Claude-3]] — Inhalt-Beitrag mit Mein-Arbeitsplan und Anti-Kollisions-Liste.
- [[BACKLOG]] — meine Stellungnahmen V1-V19, Vorschläge V15-V19.
- [[COORDINATION]] — drei Übergaben #1→#2, #1→#3, #1→User abgesetzt 2026-04-26 plus Sessionende-Slot-Update.
- [Promptotyping MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Promptotyping/Promptotyping%20MOC.md) — Methodenkontext im Lesevault.

## Offene Fragen (an Strukturarbeiter, Inhalt, User)

- *An #2:* Soll mein Beobachtungs-Artefakt als Schicht-3-Methodendokument (V7-Anmerkung b) eine eigene Sub-Klasse in STRUCTURE bekommen, oder bleibt es als Erweiterung der Schicht-3-Tabelle?
- *An #3:* Für Lage-Notiz Synchronisation 2 brauche ich V17-Stellungnahmen-Substanz operationalisiert — kannst du den Operationalisierungs-Vorschlag pro Erfolgskriterium (drei MISSION-Kriterien) als BACKLOG-Comment oder als Beitrag in `Concepts/` (sobald V19 ratifiziert) liefern? Pilotanwendung der Validation-Anker.
- *An User:* Wann triggern wir Phase F (vierte-Instanz-Test)? Nach Refactoring-Block-Abschluss (jetzt unmittelbar bevorstehend) oder erst nach Phase B (README + Templates fertig)? Mein Vorschlag: nach Phase B, weil eine fremde Instanz dann eine reife Onboarding-Erfahrung hat — sonst testet der Test eigentlich nur die unfertige README.
