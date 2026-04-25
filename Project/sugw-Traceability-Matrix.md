---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [project, sugw, traceability, matrix]
status: skeleton
author: Koordinator (Single-Curator)
---

# sugw Traceability-Matrix

Zentrale Tabelle der Vollständigkeitsverfolgung: jede Stakeholder-Aussage → mindestens ein Vorschlag → Implementations-Status → Verifikations-Doc.

**Aktueller Stand:** Skeleton. Wird in Phase 2 vom Koordinator nach Rückkehr von Claude A (Frontend-Inspektion) und Claude B (Stakeholder-Feedback) ausgefüllt. Subagents dürfen ihre eigenen Status-Spalten in Phase 4 updaten (V13-opt-in-analog).

## Vollständigkeitsprinzip (Erinnerung)

Kein Stakeholder-Feedback-Punkt darf still abgewählt werden. Jede S-ID hat:
- mindestens eine V-ID (oder Status `abgelehnt mit Begründung`)
- einen Implementation-Status (`offen | in Arbeit | implementiert | abgelehnt | blocked`)
- eine Verifikations-Anleitung (V<id>-Verifikation und/oder S<id>-Verifikation)

## Status-Legende

- **Schweregrad:** Blocker / Major / Minor / Nice-to-have
- **Schicht:** TEI / Pipeline / Aggregator / Frontend-HTML / Frontend-JS / Daten-Modell / Mehrere
- **Implementation-Status:** offen / in Arbeit / implementiert / abgelehnt-mit-Begründung / blocked
- **V-Owner:** Claude A (Tech) / Claude B (Inhalt) / beide

## Matrix

| S-ID | Stakeholder-Aussage (Auszug) | Quelle | Page/Komponente | Schicht | Schweregrad | V-ID(s) | V-Owner | Impl.-Status | Verifikations-Doc |
|---|---|---|---|---|---|---|---|---|---|
| _wartet auf Phase 2_ | | | | | | | | | |

## Vorschau auf erwartete S-IDs (aus Protokoll, vor Phase 2)

Diese Liste ist Vorab-Skizze. Claude B in Phase 1 produziert die kanonische S-ID-Liste in [[Findings/2026-04-26 - sugw Stakeholder-Feedback]]. Hier nur als Plausibilitätscheck, dass die zentralen Punkte erfasst werden:

| Vorab-ID | Thema | Erwartete V-ID(s) |
|---|---|---|
| ~S1 | Glossar fehlt für viele Begriffe | V6 |
| ~S2 | Personen pro QGW-Band anzeigbar machen | V4 oder V8 |
| ~S3 | Statistiken: % statt absolute Quellenmenge pro Dekade | V8 |
| ~S4 | Tabellen-Spalten-Erklärungen fehlen | V6 (Glossar-erweitert) oder V7 |
| ~S5 | "Tod" → "als verstorben genannt" | V7 |
| ~S6 | Suchfunktion findet 2/3–3/4 nicht | V3 |
| ~S7 | Umlaute in Suche | V3 |
| ~S8 | "Factoids" als Bezeichnung falsch | V7 |
| ~S9 | Personen-Profile parallel zu Regesten | V4 |
| ~S10 | Bidirektionale Verlinkung Person ↔ Urkunde | V5 |
| ~S11 | Filter auf geprüfte Korpora (QGW + StB) | V1, V2 |
| ~S12 | Korbinian-Daten gesperrt halten | V1, V2 |
| ~S13 | Q-Kategorie zu intern für Frontend | V7 oder V2 |
| ~S14 | Orte-Exploration weglassen (unsystematisch) | V10 |
| ~S15 | Transaktionen irreführend ohne Approval-Kontext | V10 |
| ~S16 | Verb-Browser zu kleinteilig, Aggregation nötig | V9 |
| ~S17 | Korpuskontrolle (welche Korpora geprüft) | V1 |

Erwarteter Endbestand: 15–25 S-IDs. Wenn Claude B substanziell weniger findet: Vollständigkeitsprinzip prüfen. Wenn deutlich mehr: ggf. zusammenfassen oder in Sub-Issues aufteilen.

## Vollständigkeits-Audit (Phase 2)

Nach Befüllung der Matrix: Audit pro Spalte:

- [ ] Jede S-ID aus [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] erscheint in einer Zeile
- [ ] Jede Zeile hat mindestens eine V-ID (oder explizite `abgelehnt`-Begründung in eigener Spalte)
- [ ] Jede V-ID erscheint in [[Project/sugw-Vorschläge/]]
- [ ] V-Owner (A/B) eindeutig zugewiesen
- [ ] Schweregrade verteilt (nicht alle "Blocker" oder alle "Nice-to-have")
- [ ] Schicht-Zuordnung konsistent mit [[Knowledge/sugw Daten-Architektur]]

## Vollständigkeits-Audit (Phase 5)

Nach Phase 4 (Implementation):

- [ ] Jede V-ID hat Status `implementiert` oder `abgelehnt mit Begründung` oder `blocked` (mit Eskalation an User)
- [ ] Jede implementierte V-ID hat ein V-Verifikations-Doc
- [ ] Jede S-ID hat ein S-Verifikations-Doc oder `S[N]-NICHT-Adressiert.md` mit Begründung
- [ ] [[Project/sugw-Verifikations-Master]] referenziert alle V- und S-Verifikations-Docs

## Anschluss

- [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] — kanonische S-ID-Liste (Claude B Phase 1).
- [[Findings/2026-04-26 - sugw Frontend-Inspektion]] — IST-Zustand (Claude A Phase 1).
- [[Knowledge/sugw Daten-Architektur]] — SOLL-Architektur und Pipeline-Stellen.
- [[Project/sugw-Vorschläge/]] — V-Docs (Phase 3).
- [[Project/sugw-Verifikation/]] — Verifikations-Docs (Phase 5).
- [[Sessions/2026-04-26 - sugw Synthesis 1]] — Lage-Notiz nach Phase 2.
- [[Project/sugw-Verifikations-Master]] — User-Anleitung nach Phase 5.
