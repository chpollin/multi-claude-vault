---
type: session
session-date: 2026-04-26
created: 2026-04-26
roles: [Koordinator (Single-Curator), Claude A (Subagent), Claude B (Subagent)]
status: closed
author: Koordinator (Single-Curator)
---

# Synthesis 1 — sugw-frontend-rework Phase-1-Abschluss und Phase-2-Synthese

Phase 1 abgeschlossen, Phase 2 (Synthese, Traceability, Vorschlags-Skizze) durchgeführt. Lage-Notiz für den Übergang in Phase 3 (Vorschlags-Ausarbeitung) und Phase 4 (Implementation in sugw-Pipeline-Repo).

## Rollen-Stand

**Claude A — Frontend-Inspektor (Tech-Strang).** Phase 1 abgeschlossen. Output: [[Findings/2026-04-26 - sugw Frontend-Inspektion]]. 16 Pflicht-Pages plus Detail-Stichproben durchgegangen. Funktionstests gegen `persons_search.json` direkt (16.084 Einträge): substring-Suche ohne Diakritika-Normalisierung verifiziert (Schoenberg→0 Hits trotz Schönberg→9). Personen-Detailseiten existieren nicht. Korpus QGW II/2 (1415-1417) ist live in Indizes obwohl Stakeholder nur QGW + StB freigegeben hat. Statistiken absolut, nicht relativ. Glossar enthält 9 Einträge, zentrale Stakeholder-Begriffe fehlen. Plus 7 zusätzliche Befunde, die im Protokoll nicht stehen aber durch Inspektion sichtbar wurden.

**Claude B — Stakeholder-Feedback-Analyst (Inhalt-Strang).** Phase 1 abgeschlossen. Output: [[Findings/2026-04-26 - sugw Stakeholder-Feedback]]. 37 Stakeholder-Issues (S1–S37) extrahiert aus Protokoll und 12 Slides, in zehn Themengruppen organisiert. V20-Disziplin durchgehalten — Stakeholder-Aussagen wörtlich erhalten, eigene Einschätzungen als solche markiert. Fallbeispiel "Simon Pötel"/"Anna Pötlin"/Regest 3819 als Smoking-Gun für Suchfunktions-Defekt isoliert.

**Koordinator (Single-Curator).** Phase 1 Strang C abgeschlossen ([[Knowledge/sugw Daten-Architektur]] mit Pipeline-Datenfluss TEI → CSV → JSON → HTML, Approval-Mechanismus `RELEASED_CORPORA` in `edition/config.py` identifiziert). Phase 2 durchgeführt: Traceability-Matrix mit allen 37 S-IDs befüllt, 11 Vorschläge V1–V11 zugeordnet, Vollständigkeits-Audit positiv (keine S-ID abgewählt). Diese Lage-Notiz schließt Phase 2.

## Aktive Synthese

### Konvergenter Befund: Approval-Mechanismus existiert, ist aber nicht durchgängig

**Schlüssel-Erkenntnis aus drei Strängen:** Der Approval-Mechanismus `RELEASED_CORPORA` ist in `edition/config.py` definiert (Strang C) und wird in `aggregator.py` über `_is_released_row` partiell angewandt. **Aber:** der ungeprüfte Korpus QGW II/2 (1415-1417) ist als Korpus-Chip in `documents.html` aufrufbar (Strang A), `persons_search.json` enthält Personen aus diesem Korpus ohne Filterung, und `persons_search.json` hat **kein `c`/`corpus`-Feld** — Personen sind datenseitig nicht nach Korpus filterbar (Strang A). Stakeholder fordert genau das (S25, S26, S29 in Strang B).

Die Lücke ist also nicht "Mechanismus fehlt", sondern "Mechanismus ist halb angewandt" — ein wesentlich kleineres Implementations-Volumen als ein Greenfield-Approval-System. **V1 wird damit zu Daten-Modell-Erweiterung (Korpus-Marker pro Entität in Aggregaten) plus Audit der Filter-Anwendung.**

### Konvergenter Befund: Suchfunktions-Defekt ist mehrschichtig

Drei sich verstärkende Defekte addieren sich zu den Stakeholder-Beobachtung "2/3-3/4 fehlen":

1. **Diakritika-Normalisierung fehlt** (Strang A funktional verifiziert: Schoenberg→0, Mueller→0). Adressiert mit V3 via Doppel-Index (original + normalisiert) im Such-String `_s`.
2. **Korpus-Filterung fehlt im Personen-Index** — Personen aus QGW II/2 etc. erscheinen mit, ohne Markierung. Zusammenspiel von V2 (Indizes filtern) und V3 (Suche).
3. **Person → Urkunden-Erschließung fehlt strukturell** (keine Detail-Page, S21/S22/S24). Stakeholder kann nicht von Person-Hit zu vollständiger Erwähnungsliste navigieren — selbst wenn die Suche fände, was sie sollte. V4+V5 schließen das.

Erst V3 + V2 + V4/V5 zusammen erfüllen die Stakeholder-Forderung S19 ("im Schnitt 2/3-3/4 aller Hits fehlen"). Test-Anker S20 (Pötel/Pötlin/Regest 3819) wird Akzeptanzkriterium für V3.

### Divergente Befunde (zu klären)

- **Q-Kategorie — Ausblenden vs. Erklären** (S9). Stakeholder tendiert zu Ausblenden ("Im Frontend sollte diese Kategorie so nicht sichtbar sein"), nennt aber Erklärungen als Alternative. Strang A bestätigt: `quality.html` ist im öffentlichen Top-Nav unter "Projekt". V7 sollte Stakeholder-Präferenz einholen, bevor implementiert wird — möglicherweise Hybrid: Page bleibt aber aus Hauptnavigation entfernt, weiter erreichbar für interne Reviewer via Direkt-Link.
- **"Tod"-Pfad in Pipeline** (S8). Strang A hat die Stichprobe nicht im Detail erfasst, Strang C identifiziert `roleName type="dead"` als Annotation-Level-4-Attribut. Implementations-Pfad: Label-Renaming in `register.py` oder Templates — V7 Detail in Phase 3.
- **"Aaron der Jude" / Personen ohne Dokument-Bezug** (S27). Strang A bestätigt 16.084 Personen in `persons_search.json`. Strang B macht das zur Datenbasis-Klärung. V2 löst es als Index-Filter (mention_count > 0 nach Korpus-Filter), aber die Frage "wo kommen die Einträge ohne Erwähnung her" bleibt offen — vermutlich Register-Stamm-Datensätze ohne aktive Verwendung.

## Quality Flags (V17-Pilot, gegen MISSION-Erfolgskriterien)

### EK-1 — Terminologisch konsistent (Glossar, Kategorienerklärungen)

- **Operationalisierung:** Frontend zeigt für jeden im Protokoll genannten Begriff (Quelle, Sammlung, Bestand, Korpus, Untersuchungskategorie, Factoid alternativ, Regest, Q-Kategorie, Approval-Status, Auswertungslücke, "als verstorben genannt") eine Definition entweder als Glossar-Eintrag oder als Mouse-Over an entsprechender Stelle.
- **Status:** ⚠ Risiko (Phase-3-pendent). Glossar hat aktuell 9 Einträge, mindestens 12 fehlen. V6 + V7 adressieren, aber Stakeholder-Review für "Factoids"-Ersatzbegriff steht aus.
- **Beleg:** Strang A — Glossar-Inhaltsbestand auf `/project/glossary.html`. Strang B — S1, S5, S11, S15.
- **Course-Correction:** V6 mit Stakeholder-Begriffsliste-Review vor Implementation; V7 Stakeholder-Konsultation für "Factoids"-Ersatz.

### EK-2 — Datenseitig korrekt (nur QGW + StB)

- **Operationalisierung:** Alle Personen-, Organisations- und Orts-Indizes plus alle Statistiken zeigen ausschließlich Einträge/Zähler aus den in `RELEASED_CORPORA` definierten Korpora. Ungeprüfte Korpora sind weder direkt aufrufbar noch in Aggregaten gezählt.
- **Status:** ✗ Verletzt (IST-Stand). Korpus QGW II/2 (1415-1417) ist im Quellen-Index als Chip aufrufbar, in `search.json` mit 34 Quellen geführt, in `persons_search.json` ohne Filtermöglichkeit enthalten.
- **Beleg:** Strang A `documents.html`-Inspektion und JSON-Stichproben. Strang C Daten-Architektur. Strang B S25, S26, S37.
- **Course-Correction:** V1 (Approval-Marker durchgängig anwenden) + V2 (Indizes-Filter) + Verifikations-Schritt nach Implementation, der pro Statistik-Wert die Zähl-Quelle prüft.

### EK-3 — Suchbar (alle Hits, Umlaute)

- **Operationalisierung:** Test-Anker Pötel/Pötlin/Regest 3819: in der Dokumentensuche findet "Simon Pötel" das Regest 3819. Umlaut-/ASCII-Normalisierung beidseitig (Schoenberg = Schönberg = Schoneberg findet identische Treffer-Menge ± Variante).
- **Status:** ✗ Verletzt (IST-Stand). Funktional bestätigt: substring-`indexOf` ohne Normalisierung. Schoenberg → 0 Treffer trotz Schönberg → 9.
- **Beleg:** Strang A Code-Inspektion `static/js/index.js`, `register.js` und Funktionstests gegen `persons_search.json`.
- **Course-Correction:** V3 mit Doppel-Index `_s` (original + Diakritika-normalisiert) + Test-Stichproben aus Stakeholder-Korpus für quantitative Akzeptanz.

### EK-4 — Navigierbar (Personen-Profile parallel zu Regesten, bidirektionale Verlinkung)

- **Operationalisierung:** Pro Person eine eigene Detail-Page mit allen Regest-Erwähnungen, Beziehungen, Schreibvarianten. Person↔Urkunden-Verlinkung in beide Richtungen klickbar.
- **Status:** ✗ Verletzt (IST-Stand). Personen-Detail-Pages existieren nicht; Verlinkung aus Urkunden geht nur auf Tabellen-Anker.
- **Beleg:** Strang A — `register/persons/`-Verzeichnis fehlt; Filesystem-Audit. Strang B S21, S22, S24.
- **Course-Correction:** V4 (Personen-Profile) + V5 (Bidirektionale Verlinkung + Beziehungen). Pipeline-Aggregation Person→Urkunden invertieren.

### EK-5 — Interpretierbar (% statt absolut, Erläuterungen)

- **Operationalisierung:** Statistik-Page zeigt pro Dekade % der ausgewerteten Bestände relativ zum Gesamtbestand. Tabellen-Spalten-Header tragen Mouse-Over-Erklärungen.
- **Status:** ✗ Verletzt (IST-Stand). Timeline ist absolute Counts pro Dekade pro Korpus, keine Prozentwerte. Tabellen-Header haben keine Tooltips.
- **Beleg:** Strang A — `data/timeline.json`-Struktur, KPI-Inspektion. Strang B S12, S13.
- **Course-Correction:** V6 (Tooltips an Tabellen) + V8 (Pipeline-Aggregation um Verhältnis-Berechnung).

### Methode-Stand (V17-Pilot-Reflexion)

Quality-Flag-Format hat sich für diese Lage-Notiz gut bewährt: jeweils klare Operationalisierung, IST-Beleg aus Strang A oder Daten-Stichprobe, konkrete Course-Correction. Vier Flags sind ✗ Verletzt — der Vault zeigt die Reibung, ohne sie zu beschönigen. Pflichtgemäßer Drift-Pessimismus-Check: ein Flag ist ⚠, vier sind ✗ — die Verteilung spiegelt den realen Frühphasen-Stand des Refactoring-Projekts wider, kein Selbstbestätigungs-Antipattern.

## Offene Fragen für Phase 3

### F-sugw-1 — "Factoids"-Ersatzbegriff

Stakeholder lehnt "Factoids" ab, schlägt keinen Ersatz vor. Kandidaten in V7 zu diskutieren:

- "Erwähnungen im Regest"
- "Strukturierte Nennungen"
- "Regest-Entitäten"
- "Beteiligte" (für Personen-Subset)

**Empfehlung:** V7 trägt drei Kandidaten plus Pro/Contra; User holt vor V7-Implementation Stakeholder-Präferenz ein.

### F-sugw-2 — Q-Kategorie Ausblenden vs. Erklären

Hybrid-Vorschlag: `quality.html` aus Top-Nav entfernen (öffentlich nicht prominent), Page bleibt erreichbar für interne Reviewer via Direkt-Link. Stakeholder-Bestätigung erbeten.

### F-sugw-3 — Approval-Marker Ort im Datenmodell

Drei Optionen:

- (a) TEI-Header pro Quelle (`<sourceDesc>` Erweiterung) — am dichtesten an der Wahrheit, aber 6.452 TEI-Files zu touchen.
- (b) Korpus-Manifest-Datei `sources/<Korpus>/approval.json` — kompakt, leicht maintainbar, aber nicht atomar pro File.
- (c) Build-Konfiguration `RELEASED_CORPORA` (aktueller Stand) — minimal-invasiv, aber granular nur auf Pfad-Ebene.

**Empfehlung:** (c) für Phase-4-Pilot beibehalten und in V1 dokumentieren plus Audit der Anwendung; (b) als Folge-Iteration wenn pro-File-Granularität nötig wird; (a) als langfristige Lösung wenn TEI-Editierung ohnehin laufen muss.

### F-sugw-4 — Personen-Profil Pflichtfelder

V4-Detail-Diskussion: Lebensdaten, Rollen, alle Erwähnungen mit Kontext, Bezugnahmen, Schreibvarianten — vollständige Liste in V4 zu konsolidieren mit Stakeholder-Review.

### F-sugw-5 — Verb-Browser Aggregations-Heuristik

Stakeholder-Beispiel: "habent emphangen nucz und gewer / mit kauf an sy komen ist" und "hat emphangen nucz und gewer | mit kauff an In komen ist" sollen zusammen. Lemma-basierte Lemmatisierung von Mittelhochdeutsch ist nicht trivial — Cluster-basierte Heuristik (Levenshtein + Common-Substring) als pragmatischer Vorschlag in V9.

## Phase-3-Fahrplan

Phase 3 schreibt V-Docs in `Project/sugw-Vorschläge/V<id> - <kurztitel>.md` nach Vorlage [[Templates/Template-sugw-Vorschlag]]. In dieser Lage-Notiz werden V-Docs als kompakte Skizzen vorab dokumentiert; die finalen V-Docs werden in dieser Single-Curator-Session in einem Schwung geschrieben (siehe Phase-3-Block weiter unten in der Session).

## Anschluss

- [[MISSION]] — Project-Fork-Erfolgskriterien.
- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan.
- [[Project/sugw-Traceability-Matrix]] — vollständige S-ID → V-ID-Zuordnung.
- [[Findings/2026-04-26 - sugw Frontend-Inspektion]] — IST-Befunde Strang A.
- [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] — Stakeholder-Anforderungen Strang B.
- [[Knowledge/sugw Daten-Architektur]] — SOLL-Architektur Strang C.
- `Project/sugw-Vorschläge/V*.md` — V-Docs mit Akzeptanzkriterien (Phase 3 in Bearbeitung).
- [[Project/sugw-Verifikations-Master]] — User-Anleitung nach Phase 5 (geplant).
