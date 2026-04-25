---
type: knowledge
promptotyping-type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [promptotyping, knowledge, hub]
status: active
---

# Knowledge — Methodenwissensbasis nach Promptotyping

Dieser Ordner trägt die strukturierte Wissensbasis über das Forschungsprojekt selbst, organisiert nach der [Promptotyping](https://github.com/DigitalHumanitiesCraft/Promptotyping)-Dokument-Taxonomie. Promptotyping ist eine iterative Context-Engineering-Arbeitstechnik aus der Digital Humanities; wir nutzen sie als methodisches Substrat unserer Multi-Claude-Vault-Methodenentwicklung — bewusste Selbstreferenz analog zur Drei-Rollen-Selbstreferenz, die METHOD.md produziert, indem sie METHOD.md anwendet.

Komplementär zu den Schicht-1-Ankern (MISSION/CLAUDE/METHOD/STRUCTURE) und den Schicht-2-Operativen (COORDINATION/LOG/BACKLOG): während dort die Methode lebt und gepflegt wird, hält Knowledge/ den expliziten Kontext, gegen den die Methode läuft. Source of Truth über das Projekt.

## Promptotyping-K/P/A-Taxonomie

Drei analytisch unterscheidbare Dokumenttypen, in denen jedes Knowledge/-File eine klare Rolle hat. Hybride sind erlaubt (DESIGN ist typischerweise K/A).

| Typ | Rolle | Beispiele in Knowledge/ | Diagnostik bei Problemen |
|---|---|---|---|
| **Knowledge** (deklarativ) | Erweitern den epistemischen Horizont. Beschreiben Daten, Domäne, Kontext, Forschungsfragen. | DATA, REQUIREMENTS, DESIGN (Knowledge-Anteil), README (Top-Level) | Output inhaltlich falsch → Knowledge prüfen |
| **Process** (chronologisch/analytisch) | Dokumentieren den Arbeitsprozess. Werden kontinuierlich aktualisiert. | JOURNAL | Entscheidungslogik unklar → Process prüfen |
| **Action** (imperativ) | Beschreiben, was Agenten tun können. Steuern Modellverhalten. | CLAUDE, METHOD (Top-Level), DESIGN (Action-Anteil) | Output formal falsch → Action prüfen |

## Inhalt von Knowledge/

| Dokument | Funktion | Typ |
|---|---|---|
| [[Project/INDEX|INDEX]] (dieses Dokument) | Hub, Promptotyping-Taxonomie-Erklärung | Knowledge |
| [[Project/DATA|DATA]] | Datengrundlagen — Lesevault als Wissensquelle, Forschungsleitstelle als Anschlusspunkt, eigene Falldaten als empirische Basis | Knowledge |
| [[Project/REQUIREMENTS|REQUIREMENTS]] | User Stories und Anforderungen — aus MISSION abgeleitet, operationalisiert für Drei-Rollen-Setup und Template-Vault-Distribution | Knowledge |
| [[Project/DESIGN|DESIGN]] | Designentscheidungen für Vault-Architektur, Sync-Mechanismen, Rollenmodell — Rationale, nicht Spezifikation (die ist in STRUCTURE) | Knowledge / Action |
| [[Project/JOURNAL|JOURNAL]] | Arbeitstagebuch — Entscheidungen, Wendepunkte, Dead Ends, Lernerfahrungen | Process |

INSTRUCTIONS.md (typisch in Promptotyping-Repos) ist bei uns durch [[CLAUDE]] (Sessionstart-Ritual, Pre-Edit-Read, Konfliktlogik) und [[METHOD]] (ratifizierte Konventionen) abgedeckt — kein eigenes Knowledge/INSTRUCTIONS.md, stattdessen Verweis auf bestehende Schicht-1-Anker.

RULES.md (typisch globale Entwicklungsprinzipien) ist bei uns durch CLAUDE.md plus die ratifizierten METHOD-Items abgedeckt — kein eigenes Knowledge/RULES.md.

## Zusammenspiel mit den V7-Schichten

V7 (Vier-Schichten-Architektur) bleibt die Vault-Topologie: Schicht 1 (Anker), Schicht 2 (Operativ), Schicht 3 (Beiträge), Schicht 4 (Forschungsmaterial). Knowledge/ ist eine ergänzende Klasse, die quer dazu liegt — nicht hierarchisch unter einer Schicht, sondern als *Promptotyping-Documents-Bündel*, das den Kontext explizit macht, gegen den alle Schichten arbeiten.

Verhältnis zu V19 (Concepts-Schicht, in BACKLOG vorgeschlagen): Concepts/ wird die fünfte Schicht für aus dem Lesevault extrahierte atomare Wissensdokumente (Forschungsleitstelle, Promptotyping, anchor-project als erste Welle). Knowledge/ ist *projekteigene* Wissensbasis, Concepts/ ist *vault-übergreifende* Wissensbasis — zwei klar getrennte Klassen mit unterschiedlicher Schreibhoheit (Knowledge/ kollektiv, Concepts/ ebenfalls kollektiv aber mit Reflux-Verboten gegen den Lesevault).

## Promptotyping als Substrat — was das für die Methodenarbeit bedeutet

Vier-Phasen-Schema aus Promptotyping als Komplement zum bestehenden Phasenplan A-G:

- **Preparation.** Bei uns: Bootstrap-Phase 2026-04-25 — Forschungsfrage, Rollenmodell, Lesevault-Zugang, Cross-Vault-Asymmetrie geklärt. Abgeschlossen.
- **Exploration.** Bei uns: Phase A 2026-04-25 bis 2026-04-26 — Methodenvorschläge V1-V19, Konflikte erprobt, Sync-Stack ausgearbeitet, Race-Conditions getestet, erste Lage-Notiz. Im Abschluss.
- **Destillation.** Bei uns: Phase B+ — METHOD-Ratifikation, README-Onboarding, Templates, Concepts/ aus Lesevault. Aktuell.
- **Implementation.** Bei uns: Phase D Paper, Phase E Project-Forks, Phase F vierte-Instanz-Test, Phase G Skalierung. Folgt.

Die Phasen-Schemata sind kompatibel, nicht konkurrierend. A-G ist der projektspezifische Plan, Promptotyping-Phasen sind das methodische Substrat.

## Anschluss

- [[MISSION]] — Forschungsfrage, Scope, Erfolgskriterien.
- [[CLAUDE]] — Identität, Rituale, Konfliktlogik (Action-Doc Top-Level).
- [[METHOD]] — Ratifizierte Konventionen (Action-Doc Top-Level).
- [[METHOD]] — Vier-Schichten-Architektur (vorgeschlagen, V19 erweitert um Concepts-Schicht).
- [Promptotyping MOC](c:/Users/Chrisi/Documents/obsidian/Projects/Promptotyping/Promptotyping%20MOC.md) — Methodenkontext im Lesevault.
- [Promptotyping Wissensdokument](c:/Users/Chrisi/Documents/obsidian/Applied%20Generative%20AI/Promptotyping.md) — Methodenkern im Lesevault.
