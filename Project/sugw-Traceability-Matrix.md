---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [project, sugw, traceability, matrix]
status: phase-2-complete
author: Koordinator (Single-Curator)
---

# sugw Traceability-Matrix

Vollständige Zuordnung Stakeholder-Issue → Vorschlag → Implementations-Status → Verifikations-Doc. Phase-2-Befüllung 2026-04-26 nach Rückkehr von Claude A (Frontend-Inspektion mit 16 inspizierten Pages und Funktionstests gegen `persons_search.json`) und Claude B (37 S-IDs aus Protokoll + 12 Slides).

## Zusammenfassung

- **37 Stakeholder-Issues** (S1–S37) aus Protokoll und PPT.
- **11 Vorschläge** (V1–V11): 8 technisch (Claude A in Phase 3), 2 inhaltlich (Claude B), 1 Frontend-Polish (gemischt).
- **Keine S-ID abgewählt.** Jede S-ID hat mindestens eine V-ID. S30 und S36 sind methodische/dokumentarische Ankerpunkte ohne eigene Implementation, aber traceabel.
- **5 Blocker-Issues** adressiert in V1, V2, V3, V4, V5 — diese müssen für Stakeholder-Akzeptanz vollständig implementiert sein.

## Status-Legende

- **Schweregrad:** Blocker / Major / Minor / Methodisch
- **Schicht:** TEI / Pipeline / Aggregator / Frontend-HTML / Frontend-JS / Daten-Modell / Mehrere
- **Impl.-Status:** offen / in Arbeit / implementiert / abgelehnt-mit-Begründung / blocked
- **V-Owner:** A (Tech) / B (Inhalt) / A+B (gemischt)

## Matrix

| S-ID | Stakeholder-Aussage (Auszug) | Quelle | Page/Komponente | Schicht | Schweregrad | V-ID(s) | V-Owner | Impl.-Status |
|---|---|---|---|---|---|---|---|---|
| S1 | Allgemeine terminologische Überarbeitung | Prot Z.2, Slide 1 | Frontend-übergreifend | Templates | Major | V7 | B | offen |
| S2 | "Wiener Urkundenbuch" vermeiden | Slide 1 | Projektinfo | Templates | Minor | V7 | B | offen |
| S3 | Begriffe Quellen/Sammlungen/Bestände präzisieren | Prot Z.6, Slide 1 | Glossar + Tabellen | Templates+Glossar | Major | V6, V7 | B | offen |
| S4 | "Überlieferungslücke" → "Auswertungslücke" | Slide 1 | Projektinfo/Statistik | Templates | Minor | V7 | B | offen |
| S5 | Glossar mit Mouse-Over | Prot Z.4, Slides 1+2 | Frontend-übergreifend | HTML/JS+Glossar | Major | V6 | A+B | offen |
| S6 | Mouse-Over Tabellen-Spalten-Header | Slide 2 | Alle Tabellen | HTML/JS | Major | V6 | A+B | offen |
| S7 | Erklärung pro Tabellen-Kategorie | Prot Z.10 | Alle Tabellen | HTML/JS+Glossar | Major | V6 | A+B | offen |
| S8 | "Tod" → "als verstorben genannt" | Prot Z.11, Slide 2 | Personen-Tabellen/Detail | Aggregator+Templates | Major | V7 | B | offen |
| S9 | Q-Kategorie ausblenden oder erklären | Prot Z.21, Slide 2 | quality.html, Filter | Frontend+Build | Major | V7 | B | offen |
| S10 | "Factoids" falsche Bezeichnung | Prot Z.13, Slide 6 | Regest-Detail | Templates+JS | Major | V7 | B | offen |
| S11 | Begriffe wie Quelle/Untersuchungskategorie erklären | Prot Z.6 | Glossar | Glossar | Major | V6 | B | offen |
| S12 | Ausgewertete Bestände in Relation zum Gesamtbestand | Slide 2 | Statistik | Pipeline+Frontend | Major | V8 | A | offen |
| S13 | % statt absolute Quellenmenge pro Dekade | Prot Z.9 | Statistik | Pipeline+Frontend | Major | V8 | A | offen |
| S14 | Regestentext-Spalte füllt nicht volle Breite | Slide 2 | documents.html | CSS | Minor | V11 | A | offen |
| S15 | Projektinfo/Statistik/Editionsrichtlinien überarbeiten | Slide 3 | project/* | Templates+Inhalt | Major | V6 | B | offen |
| S16 | Personen-Auffindbarkeit zentrales Problem | Prot Z.12, Slide 4 | Suche | JS+Daten | **Blocker** | V3 | A | offen |
| S17 | Wonach sucht die Suchleiste? | Prot Z.12, Slides 4-5 | Suche | JS+Glossar | Major | V3, V6 | A+B | offen |
| S18 | Umlaut-Behandlung | Prot Z.12 | Suche | JS+Daten | Major | V3 | A | offen |
| S19 | 2/3-3/4 aller Hits fehlen | Prot Z.13 | Suche/Personen-Detail | JS+Aggregator | **Blocker** | V3, V4 | A | offen |
| S20 | Fallbeispiel Pötel/Pötlin Regest 3819 | Slides 4-5 | Suche | JS+Aggregator | **Blocker** | V3 | A | offen |
| S21 | Person-View parallel zu Regesten | Prot Z.15, Slide 7 | Personen-Detail (NEU) | Build+Templates | **Blocker** | V4 | A | offen |
| S22 | Profil pro Entität: Beziehungen, Schreibvarianten | Slides 7-8 | Personen-Detail | Aggregator+Templates | **Blocker** | V4, V5 | A | offen |
| S23 | Verwandtschaftsbeziehungen ausgewiesen aber unsichtbar | Slides 7-8 | Personen-Detail | Aggregator+Templates | Major | V5 | A | offen |
| S24 | Bidirektionale Verlinkung Person ↔ Urkunde | Prot Z.16 | Personen-Detail | Aggregator+Templates | **Blocker** | V5 | A | offen |
| S25 | Personen-Liste nur aus geprüften Korpora | Prot Z.17, Slide 9 | Alle Indizes | Pipeline+Aggregator | **Blocker** | V1, V2 | A | offen |
| S26 | Ungeprüfte Korpora nicht in Auswertungen | Prot Z.18, Slides 9-10 | Statistik+Counter | Aggregator | **Blocker** | V1, V2, V8 | A | offen |
| S27 | Personen mit 0 Dokumenten nicht anzeigen | Slide 9 | Personen-Index | Aggregator | Major | V2 | A | offen |
| S28 | Korbinian-Daten gesperrt | Prot Z.30 | Frontend-übergreifend | Pipeline | **Blocker** | V1 | A | offen |
| S29 | Indizes auf geprüfte Korpora filtern | Prot Z.31 | Alle Indizes | Aggregator | Major | V1, V2 | A | offen |
| S30 | Verbindung Interface ↔ Git-Repository | Prot Z.29 | Methodisch | Doku | Major | (Strang C) | Koord | dokumentiert in [[Knowledge/sugw Daten-Architektur]] |
| S31 | Korpus-Approval-Markierung im System | Prot Z.27 | Daten-Modell | TEI/Pipeline | Major | V1 | A | offen |
| S32 | Exploration/Orte weglassen | Prot Z.22, Slide 11 | exploration/places.html | Templates+Routing | Major | V10 | A | offen |
| S33 | Siedlungskarte lädt nicht | Slide 11 | Siedlungskarte | Frontend-JS | Major | V10 | A | offen (entfällt mit V10 wenn Page entfernt) |
| S34 | Exploration/Transaktionen irreführend | Prot Z.23, Slide 12 | exploration/transactions.html | Templates+Aggregator | Major | V10 | A | offen |
| S35 | Verb-Browser zu kleinteilig | Prot Z.24, Slide 12 | Verb-Browser | Pipeline+Frontend | Major | V9 | A | offen |
| S36 | DB-Qualität hat Vorrang | Prot Z.33 | Methodisch (Workflow) | — | Methodisch | (in MISSION verankert) | Koord | dokumentiert in [[MISSION#Out-of-Scope]] |
| S37 | Interface-Zahlen müssen mit DB übereinstimmen | Prot Z.32 | Statistik+Counter | Aggregator+Verifikation | **Blocker** | V1, V2, V8, Verifikations-Master | A+Koord | offen |

## Vorschlags-Übersicht

| V-ID | Kurztitel | Adressiert S-IDs | V-Owner | Schicht-Schwerpunkt |
|---|---|---|---|---|
| V1 | Korpus-Approval-Marker im Datenmodell | S25, S26, S28, S29, S31, S37 | A | Pipeline-Konfiguration / TEI-Header |
| V2 | Filterung der Indizes auf geprüfte Korpora | S25, S26, S27, S29, S37 | A | Aggregator (durchgängige Anwendung) |
| V3 | Suche: Volltext + ID + Diakritika-Normalisierung | S16, S17, S18, S19, S20 | A | Frontend-JS + Aggregator-Index |
| V4 | Personen-Profile parallel zu Regesten | S21, S22, S27 | A | Build + Templates + Aggregator |
| V5 | Bidirektionale Verlinkung + Beziehungen anzeigen | S22, S23, S24 | A | Aggregator + Templates |
| V6 | Glossar mit Mouse-Over an Tabellen-Spalten | S3, S5, S6, S7, S11, S15, S17 | A+B | Glossar-Inhalt + Tooltip-Komponente |
| V7 | Terminologie-Refactoring | S1, S2, S3, S4, S8, S9, S10 | B | Templates + Daten-Labels |
| V8 | Statistiken: % statt absolut, Relation Gesamtbestand | S12, S13, S26, S37 | A | Pipeline-Aggregation + Frontend-Charts |
| V9 | Verb-Browser-Aggregation | S35 | A | Pipeline (Verb-Cluster) + Frontend |
| V10 | Exploration aufräumen | S32, S33, S34 | A | Templates + Routing |
| V11 | Frontend-Polish | S14 + Claude-A-Befunde (Nav-Disabled-Inkonsistenz, Wiener-Neustadt-Dublette, Exploration-Hub-Dropdown, Datenstand-Fußzeile) | A | CSS + Templates + Aggregator-Normalisierung |

## Vollständigkeits-Audit Phase 2

- [x] Jede S-ID aus [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] erscheint in einer Zeile (S1–S37 vollständig).
- [x] Jede Zeile hat mindestens eine V-ID oder explizite Methodisch-Markierung (S30, S36 als Methodisch — keine Implementations-V-ID, aber traceabel über Strang C bzw. MISSION).
- [x] Jede V-ID adressiert mindestens eine S-ID.
- [x] V-Owner (A/B) eindeutig zugewiesen (gemischte: V5/V6 als A+B).
- [x] Schweregrade verteilt: 8× Blocker, 21× Major, 4× Minor, 4× Methodisch — angemessene Streuung.
- [x] Schicht-Zuordnung konsistent mit [[Knowledge/sugw Daten-Architektur]].
- [x] Befunde aus Claude A's "im Protokoll NICHT stehen"-Sektion in V11 mitgeführt.

## Anschluss

- [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] — kanonische S-ID-Liste.
- [[Findings/2026-04-26 - sugw Frontend-Inspektion]] — IST-Befunde.
- [[Knowledge/sugw Daten-Architektur]] — SOLL-Architektur und Pipeline-Stellen.
- [[Sessions/2026-04-26 - sugw Synthesis 1]] — Lage-Notiz mit Quality Flags.
- `Project/sugw-Vorschläge/V*.md` — V-Docs mit Akzeptanzkriterien.
- [[Project/sugw-Verifikations-Master]] — User-Anleitung nach Phase 5 (Phase-5-Audit).
