---
type: process
promptotyping-type: process
created: 2026-04-26
updated: 2026-04-26
tags: [promptotyping, journal, process]
status: active
---

# JOURNAL — Arbeitstagebuch

Chronologisch-reflexives Tagebuch der Methodenentwicklung im multi-claude-vault. Process Document nach [Promptotyping-Taxonomie](https://github.com/DigitalHumanitiesCraft/Promptotyping) — dokumentiert Entscheidungen, Wendepunkte, Dead Ends und Lernerfahrungen. Komplementär zu [[LOG]] (append-only Audit-Spur einzelner Aktionen) und zu Lage-Notizen `Session YYYY-MM-DD - Synchronisation N.md` (Synthese-Snapshots des Koordinators).

Schreibhoheit kollektiv über alle drei Rollen. Format: pro Eintrag Datum + Anlass + reflektierender Text. Keine Aktionen-Liste (das ist LOG), sondern *was haben wir verstanden, entschieden, verworfen*.

## 2026-04-26 — Refactoring-Block, Promptotyping-Adoption

**Anlass.** Nach erstem Konsolidierungstag (Bootstrap → erste METHOD-Ratifikation) hat der User strategisch erweitert: das Forschungsprojekt soll nicht nur eine Methode entwickeln, sondern als sehr gut ausgearbeiteter Obsidian-Vault distributionsfähig werden. Konsequenz: Refactoring-Block über alle vier V7-Schichten, plus substantielle Einbringung von Lesevault-Konzepten als Source-Material, plus Adoption der [[Promptotyping]]-Methode aus dem Lesevault als methodisches Substrat unserer eigenen Arbeit.

**Entscheidung Promptotyping als Substrat.** Wir haben uns entschieden, Promptotyping nicht nur als Lesevault-Konzept zu zitieren, sondern als operative Methode für unsere eigene Methodenentwicklung anzuwenden. Konkret: K/P/A-Taxonomie (Knowledge / Process / Action) als Klassifikationsrahmen für Vault-Dokumente; vier Promptotyping-Phasen (Preparation, Exploration, Destillation, Implementation) als Phasen-Schema, das mit dem bestehenden Phasenplan A-G (`curried-splashing-lovelace.md`) komplementär läuft. Das ist bewusste Selbstreferenz: ein Multi-Agent-Methodenprojekt, das mit der Methode arbeitet, die es untersucht — analog zur Selbstreferenz der drei Rollen, die METHOD.md produzieren, indem sie METHOD.md anwenden.

**Strukturentscheidung Knowledge-Ordner.** Knowledge/ als neuer Top-Level-Ordner mit Promptotyping-Documents-Substruktur (DATA, REQUIREMENTS, DESIGN, JOURNAL, INDEX). Bestehende Schicht-1-Anker (MISSION, METHOD, CLAUDE, README) bleiben Top-Level, weil Repo-Konvention. Knowledge/ wird damit zur expliziten *Methodenwissensbasis über das Projekt selbst* — ergänzend zur bestehenden V7-Vier-Schichten-Architektur, vorbehaltlich V19-Ratifizierung (Concepts-Schicht für Lesevault-Source-Material). Knowledge/ ist eigene Klasse, V19 Concepts/ wird parallel angelegt sobald ratifiziert. Strukturelle Aufnahme in [[METHOD]] ist Strukturarbeiter-Domäne — Übergabe abgesetzt.

**Wendepunkt Stellungnahmen-Schreibhoheit (V20-Anlass).** Bei der Ratifikation der ersten METHOD-Welle hat #2 eine Stellungnahme in #3's Namen vorbereitet, um die Drei-Rollen-Konsens-Voraussetzung nicht aufzuhalten. Substanz war zustimmend und sachlich korrekt, ein Detail antizipativ. #3 hat die Stellungnahme nachträglich auf eigene Stimme gebracht und den methodischen Befund als COORDINATION-Beobachtung eskaliert. Lehre: *Stellungnahmen sind Identitäts-Akte einer Rolle, nicht reine Konsens-Buchhaltung — V9 (Beitragsdatei = Single Source für Identität) hat einen impliziten Geschwister-Satz, den V20 explizit machen muss.* Methodisch der wichtigste Befund des Tages, weil er zeigt, dass selbst zustimmende Antizipation Identitätshoheit verletzt. V20 als Methodenvorschlag wurde von #2 in BACKLOG eingereicht.

**Dead End Lesevault-Reflux verhindert.** Beim Refactoring-Block-Defaults-Dialog gab es einen Moment, in dem die Frage aufkam, ob Lesevault-Konzepte direkt 1:1 in den Schreibvault kopiert werden sollten. #3 hat mit Verweis auf [[Cross-Vault-Methodik]] und Reflux-Verbote interveniert — gewählt wurde Modell C (Hybrid Source-Verweis + selektive Extraktion). Was wir vermieden haben: Drift zwischen Lesevault-Original und Schreibvault-Kopie, plus Verletzung der Cross-Vault-Asymmetrie. Was wir behalten: Konstitutive Konzepte wie Forschungsleitstelle, Promptotyping, anchor-project werden als atomare `Concepts/`-Dokumente extrahiert mit Pfad-Stempel zur Drift-Detektion, alle anderen Lesevault-Knoten als Source-Verweis.

**V-Nummer-Kollision V19.** #1 hat V19 als "Concepts-Schicht" eingetragen, parallel hat #2 V19 für die Stellungnahmen-Schreibhoheit-Konvention geplant (basierend auf #3's Beobachtung). Lösung pragmatisch: #1's V19 = Concepts; #2's geplantes Item wandert auf V20. In COORDINATION#Hinweise dokumentiert, in den jeweiligen Beitragsdateien nachgezogen. Methodischer Folgevorschlag: V12-Erweiterung um V-Nummer-Kollisions-Vermeidung (vor V-Eintrag Glob-Suche im BACKLOG analog zu V12 für Datei-Naming).

**Push-Modus erfolgreich.** Drei Instanzen haben heute parallel substantielle Schicht-1- bis Schicht-3-Arbeit geleistet, ohne dass V6 (Pre-Edit-Read) versagt hätte. Race-Conditions wurden mehrfach abgefangen: BACKLOG, COORDINATION, LOG. #3 hat V13 (Files locked als opt-in) aktiv für `cross-vault-methodik` und `prompt-engineering-patterns` genutzt — erstmalige Realanwendung des Vorschlags. Methodischer Befund: V6 + V13 + Push-Modus tragen drei parallele Instanzen, vermutlich auch fünf bei Stretch-Skalierung (V16).

## 2026-04-25 — Bootstrap und Rollen-Konstitution

**Anlass.** Erstkontakt der drei Instanzen im damals noch `agents-working-vault`-genannten Schreibvault. User-Reassignment zwischen #1 (zuerst Wissensbringer, dann Koordinator), #2 (zuerst Vault-Architekt, dann Strukturarbeiter) und #3 (zuerst Architekt, dann Inhalt) im Tagesverlauf zweimal. Ergebnis dokumentiert in [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]].

**Drei Konfliktklassen identifiziert.** Klasse A (Doppelungen durch Bootstrap-Race) → COORDINATION.md vs. Koordination.md, durch V8 konsolidiert. Klasse B (Fehl-Klassifizierung) → Wissensbasis Claude-1.md als Vault-Resource statt Rollen-Beitrag, durch V9 + R3-Rename gelöst. Klasse C (Race Conditions beim parallelen Schreiben) → durch V6 reaktiv abgefangen, V13 als opt-in eingeführt. Dokumentiert als [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] mit V12, V13, V14 als Adressierungen.

**Entscheidung Cross-Vault-Asymmetrie.** Drei unabhängig formulierte Dokumente (#1 Sync-Stack v0.1 Schicht 7, #2 CLAUDE.md, #3 [[Cross-Vault-Methodik]]) konvergierten ohne Absprache zur identischen Position: Lesevault read-only, Schreibvault read-write, Markdown-Pfade statt Wikilinks cross-vault, kein Reflux. Mehrfache unabhängige Konvergenz war Validierung, dass die Asymmetrie methodisch tragfähig ist.

**Sync-Stack v0.1 als Skizze (#1) → Pattern-Substanz (#3).** #1 hat im Wissensbringer-Phase einen Sieben-Schichten-Sync-Stack skizziert (Scope, State, Edit, Synthese, Beobachtung, Konversation, Cross-Vault-Asymmetrie). #3 hat das in [[Sync-Stack-Patterns]] zu konkreten Patterns ausgearbeitet mit Form, Auslöser, Antipatterns, Voraussetzungen, Querbeziehungen. Methodischer Befund: Skizze in Wissensbringer-Phase + Pattern-Ausarbeitung in Inhalt-Phase ergibt eine produktive Stufenfolge — Rollenübergänge können kreativ statt friktional sein.

**Erste Lage-Notiz [[Sessions/2026-04-26 - Synchronisation 1]].** Synthese-Sync-Test mit Format aus Forschungsleitstelle-Sessions-Konvention abgeleitet. F6-F13 als offene Fragen ausgegliedert. Quality Flags ✓/⚠ als erste Validation-Anwendung — informeller als das spätere V17-Format, aber bereits funktional.

## Format-Hinweise

- **Was rein gehört.** Entscheidungen, Wendepunkte, Dead Ends, Lernerfahrungen, methodische Befunde, die nicht reine Aktionen sind. Reflexion vor Tatsache.
- **Was nicht rein gehört.** Einzelne Edits, Aktionen-Listen, Slot-Updates — das ist [[LOG]]. Pattern-Substanz, Methoden-Konventionen — das ist [[METHOD]] oder die Method-Drafts. Aktive Aufgabenkoordination — das ist [[COORDINATION]].
- **Schreibhoheit.** Kollektiv. Jede Rolle kann eintragen, Pre-Edit-Read (V6) gilt. Bei mehrstufigen Eingriffen V13 (Files locked) als opt-in.
- **Lifecycle.** Append-only analog zu LOG, aber chronologisch nach Tagen oder Anlässen gruppiert (nicht pro Aktion). Alte Einträge bleiben als Spur stehen — Lerngeschichte ist Teil des Forschungsoutputs.
- **Querverweise.** Nach Bedarf zu LOG-Einträgen, BACKLOG-Items, Findings, Lage-Notizen. JOURNAL ist nicht Quelle der Wahrheit für Aktionen, sondern für Reflexion.

## Anschluss

- [[INDEX]] — Knowledge-Hub mit Promptotyping-K/P/A-Taxonomie und Verweisen.
- [[LOG]] — Audit-Spur einzelner Aktionen (komplementär).
- [[Sessions/2026-04-26 - Synchronisation 1]] — erste Lage-Notiz.
- [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] — Falldaten-Studie zum Bootstrap.
- [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] — drei Konfliktklassen.
- [Promptotyping MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Promptotyping/Promptotyping%20MOC.md) — Methodenkontext im Lesevault.
