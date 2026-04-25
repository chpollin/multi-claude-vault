---
type: finding
created: 2026-04-26
tags: [sugw, frontend, inspektion]
status: complete
author: Claude A (Subagent — Frontend-Inspektor)
---

# Finding 2026-04-26 — sugw Frontend-Inspektion

## Zusammenfassung

Inspektion des sugw-Frontends auf `http://127.0.0.1:8765/` (Edition-Repo, Datenstand 17. April 2026). 17 Pflicht-Pages plus Stichproben in Detailpages durchgegangen. Zentrale technische Befunde: (1) Korpus-Wahl im Quellenverzeichnis nur als Chip-Buttons, kein default-Restrict auf geprüfte Korpora — der ungeprüfte Korpus QGW II/2 (1415–1417) ist live und in den Indizes mitgezählt. (2) Suchfunktion ist substring-`indexOf` ohne Diakritika-Normalisierung — Eingabe ohne Umlaut findet die mit Umlaut nicht und umgekehrt. (3) Personen-Detailseiten existieren nicht — Verlinkung aus Urkunden geht nur auf Tabellenzeilen-Anker `register/persons.html#pe__...`. (4) Statistiken (Timeline, KPIs) sind absolut, nicht relativ. (5) Glossar enthält 9 Einträge, die zentralen vom Stakeholder-Protokoll geforderten Begriffe (Untersuchungskategorie, Q-Kategorie, Regest, Transaktion, Bestand, Factoid, Approval-Status) fehlen. (6) Begriff "Factoid" im UI weiterhin sichtbar (Toggle in jeder Urkunde, `factoid-toggle`/`factoid-view`).

## Inspizierte Pages

### / (index.html)

- Layout: Hero-Header "Stadt und Gemeinschaft Wien — Datenbank", Top-Nav mit Brand, Badge "Prototyp", Hamburger, dropdown-basierte Hauptnavigation.
- Navigation enthält: Quellen, Register (Dropdown: Personen, Organisationen, Orte), Exploration (Dropdown: Rollen, Beziehungen, Transaktionen, Orte), Analyse, Projekt (Dropdown: Über das Projekt, Statistik, Qualität, Editionsrichtlinien, Glossar, Impressum).
- **Befund:** Im Register-Dropdown sind Organisationen und Orte mit `class="nav-disabled" aria-disabled="true" title="Noch nicht freigegeben"` markiert. Die Pages existieren aber als HTML-Dateien und sind direkt aufrufbar.
- **Befund:** Globale Suchleiste auf der Landing nicht erkennbar (nur seitenspezifische Suche auf Listen-Pages).

### /documents.html — Quellenverzeichnis

- Layout: Suchbox, drei Korpus-Chips (Buttons), Filter (Ort, Faksimile, Qualität), Range-Slider Datum, Histogram, sortierbare Tabelle (Nr., Datum, Ort, Regest), Click-to-preview pro Zeile.
- Korpus-Chips:
  - `QGW/Vienna_1177-1414_ready` — "QGW II/1 (1177–1414) — Regest + Faksimile"
  - `Stadtbuecher/Band_1_1395-1400_ready` — "Stadtbücher Bd. 1 (1395–1400) — Volltext"
  - `QGW/Vienna_1415-1417` — "QGW II/2 (1415–1417) — Regest + Faksimile"
- Filter "Ort" (15+ Werte mit Counts): Wien (1537), Pressburg (9), Mödling (9), Prag (9), Wiener Neustadt (9), Graz (6), Ofen (6), Wiener-Neustadt (6) ... — duplizierter Eintrag "Wiener Neustadt" vs. "Wiener-Neustadt" sichtbar.
- Filter "Faksimile": Mit (2011) / Ohne (624).
- Filter "Qualität": Fehlerfrei (697) / Hinweise (1793) / Warnungen (145).
- Verteilung in `data/search.json`: 2.635 Quellen total, davon 2.023 QGW II/1, 578 Stadtbücher Bd. 1, **34 QGW II/2** (= außerhalb Stakeholder-Scope, der nur bis 1414 freigegeben ist).
- **Befund:** Ohne aktive Filter werden alle drei Korpora gemischt angezeigt. Ein default-Restrict auf "geprüfte Korpora" existiert nicht. Kein Approval-Marker im Datenmodell sichtbar — Korpus = Pfad-String, kein Status-Feld.
- **Befund:** Filter "Qualität" zeigt absolute Zahlen, nicht Prozente.

### /register/persons.html — Personenregister

- Layout: Suchbox, drei Filter (Geschlecht, Quellenverknüpfungen, Datenqualität), Sortierung, Tabelle.
- Geschlecht-Filter: Alle / Weiblich (f) / Männlich (m).
- Quellenverknüpfungen-Filter: Alle / Mit Quellen (1).
- Datenqualität-Filter: Alle / Fehlerfrei (0) / Hinweise (1).
- Datenbasis `data/persons_search.json`: 16.084 Einträge mit Feldern `id, n, fn, sn, sex, d, dc, qw`. **Kein `c`/`corpus`-Feld** — Personen sind nicht nach Korpus filterbar.
- **Befund:** Person → Urkunden-Verlinkung nicht direkt sichtbar in der Tabelle. Detailseiten pro Person existieren nicht (`ls register/` zeigt nur `persons.html` + `persons.json`, keine Sub-Pages).
- **Befund:** Personen aus dem nicht freigegebenen QGW II/2 (1415–1417) sind in `persons_search.json` enthalten (sample IDs mit `_FRA_II_52_1401_...`, `_QGW_II_III_...` u.a.) — keine Korpus-Filterung möglich.

### /register/organisations.html und /register/places.html

- Pages existieren als HTML, im Top-Nav als `nav-disabled` markiert ("Noch nicht freigegeben").
- Direkt aufrufbar via URL trotz aria-disabled.
- **Befund:** Inkonsistenz zwischen Navigations-Sperre und tatsächlicher Verfügbarkeit. User, der Direkt-Link kennt oder Browser-Verlauf hat, gelangt zu nicht freigegebener Page.

### /exploration/index.html — Exploration-Hub

- Vier Hub-Cards: Rollen, Beziehungen, Transaktionen, Orte.
- **Befund:** Im Top-Nav-Dropdown "Exploration" fehlt der Link zum Hub selbst (`exploration/index.html`) — Dropdown listet nur die vier Sub-Pages.

### /exploration/transactions.html

- Vier Sub-Sektionen: Transaktionstypen im Zeitverlauf, Verb-Browser, Institutionelle Empfänger, Institutionstyp × Transaktionstyp.
- **Befund:** Verb-Browser vorhanden — Granularität nicht detailliert geprüft, aber das gesamte Konzept "Transaktionen" entspricht laut Stakeholder-Protokoll dem irreführenden Begriff (S. Stakeholder-Feedback, Claude B).

### /exploration/places.html

- Zwei Sektionen: Siedlungskarte, Ortsregister.
- Stakeholder-Protokoll (laut Subagent-Prompts): "weglassen, unsystematisch". Frontend bestätigt: Sektion vorhanden.

### /exploration/roles.html

- Drei Sektionen: Funktionsrollen nach Geschlecht, Institutionelle Zugehörigkeit, Detail.

### /exploration/networks.html — Beziehungen

- Fünf Sektionen: Zugehörigkeitsformen nach Geschlecht, Bezeichnungen, Vertretungsrichtung, Freundschaftsbeziehungen, Detail.

### /analysis/index.html

- Page existiert mit `<h1>Analyse</h1>`, Inhalt nicht weiter durchsucht in dieser Inspektionsrunde.

### /project/about.html

- Strukturierte Projektbeschreibung: Projektbeschreibung, Forschungskontext, Forschungsfragen, Quellenbestand, Annotationsmodell, Technische Umsetzung, Qualitätssicherung, Zitierweise, Kontakt.

### /project/glossary.html — Glossar

Inhaltlicher Stand (alphabetisch, 9 Einträge): Event, Gesamtnennung, Individuelle Person, Menschen-Event, Quelle, Quellenkorpus, Rechtsgeschäft, Rolle, Rollenkombination.

- **Befund:** Folgende vom Stakeholder-Protokoll laut Subagent-Prompt explizit genannte Begriffe **fehlen**: Quelle (vorhanden), Untersuchungskategorie (fehlt), Factoid (fehlt — obwohl im UI verwendet), Regest (fehlt), Q-Kategorie (fehlt), Transaktion (fehlt — als Standalone-Eintrag, "Rechtsgeschäft" ist da), Bestand (fehlt). Korpus, QGW, StB, Approval-Status fehlen ebenfalls.
- Eintrag "Quellenkorpus" referenziert die alte Bezeichnung "Sammlung" als überholt — solche Etymologie-Notizen sind methodisch sauber dokumentiert.
- Eintrag "Menschen-Event" ist ein eigenes editionsmodell-spezifisches Konstrukt, nicht selbsterklärend.

### /project/edition-guidelines.html

- Zehn-Punkte-Struktur: Projektkontext, Annotationsmodell (Vier Ebenen), Tagging-Workflow (Sieben Schritte), ID-Konstruktionsregeln, Normalisierungsregeln, Kontrolliertes Vokabular, Editor-Liste, Zitierhinweis, Lizenz, Versionsgeschichte.

### /project/quality.html — Datenqualität

- Drei Sektionen: Findings nach Kategorie, Qualität nach Quellenkorpus, Datenexport.
- KPI-Lede: "2.071 Findings in 2.635 Dateien."
- Begrifflichkeit: "Findings", "Hinweise", "Warnungen", "Kategorie", "Datenqualität". Der vom Stakeholder-Protokoll kritisierte Begriff "Q-Kategorie" erscheint im sichtbaren Text **nicht direkt** — vermutlich interner Backend-Begriff oder Ableitung aus dem Quality-Filter (0/1/2).
- **Befund:** Quality-Page ist in der Top-Nav unter "Projekt" sichtbar — Stakeholder-Protokoll laut Subagent-Prompt: "zu intern". Page exponiert validierungs-interne Befunde an Endnutzerinnen.

### /project/statistics.html

- KPI-Header: "2.635 Quellen aus mehreren Quellenkorpora dokumentieren Wiener Rechtsgeschäfte (ca. 1177–1417). 16.084 individuelle Personen sind im Register erfasst. 2.011 Quellen (76.3%) sind mit Faksimiles verknüpft."
- KPIs als Click-Buttons mit `prov-popover`-Tooltips (Provenance-Popovers verlinken zum Glossar).
- Sektionen: Zeitliche Verteilung, Quellenkorpora, Funktionsrollen, Annotationstiefe, Registerabdeckung, Meistgenannte Einträge, Aktivste Akteure.
- Timeline-Daten in `data/timeline.json`: Dekaden-basiert mit `{total, QGW, Stadtbuecher}` pro Decade. **Werte sind absolute Zählungen.** Beispiel 1170: total=1, QGW=1; 1280: total=6, QGW=6; 1290: ...
- Personen-Sub-KPI: "♀ 4.224 · ♂ 11.860" als absolute Zahlen.
- **Befund:** Stakeholder-Forderung "% statt absolute Quellenmenge pro Dekade" trifft die Timeline direkt. Die Timeline visualisiert absolute Zahlen, was bei stark variierender Korpus-Dichte über Jahrhunderte irreführend ist.
- **Befund:** Geschlechter-Aufteilung 26%/74% wird nicht prominent als Verhältnis kommuniziert, sondern absolut.

## Inspizierte Detailpages

### Urkunde 1 (`/documents/QGW/Vienna_1177-1414_ready/1.html`)

- `<h1>Nr. 1</h1>`, Title "1 ([1198-1230])".
- Personen-Verlinkung im Detail: drei Links auf `../../../register/persons.html#pe__hadmar_von_schoenberg_QGW_II_I_1`, `#pe__rapoto_von_schoenberg_QGW_II_I_1`, `#pe__jutta_QGW_II_I_1`. Anker-Sprünge auf Tabellenzeilen, **kein Personen-Profil**.
- Rollen-Markup: `data-role="issuer"`, `data-role="recipient"` — kontrolliertes Rollenvokabular im DOM.
- Factoid-View: `factoid-toggle` Button und `factoid-view` Container vorhanden. JavaScript-Modul `static/js/document.js` hat Funktion `buildFactoidTable` und Kommentar "Factoid View — extract atomic assertions from annotation spans".
- **Befund:** Begriff "Factoid" ist sowohl im Code (DOM-IDs, JS-Funktionsnamen) als auch im UI-Toggle direkt sichtbar.

### Urkunden-IDs der freigegebenen Korpora

- QGW II/1: 0a, 0b, 1, 10, 100, ... (alphanumerisch, ID-Schema fortlaufend)
- 1415-1417: separater Pfad, Stichprobe nicht im Detail durchgegangen.

### Personen-Detail

- **Befund kritisch:** `register/persons.html` ist die einzige Personen-Page; einzelne Personen haben keine eigenen URLs. Filesystem bestätigt: `register/` enthält nur `persons.html`, `persons.json`, `organisations.html`, `organisations.json`, `places.html`, `places.json`. Keine `register/persons/<id>.html`.
- Verlinkungen aus Urkunden enden auf Anker `#pe__...`, der im Tabellen-Row als `id`-Attribut gerendert wird. Der User landet auf der Riesentabelle bei der richtigen Zeile, ohne Person-zentrierte Übersicht (welche Urkunden? welche Rollen? welcher Zeitraum?).

## Funktionstest-Befunde

### Suchfunktion in /documents.html

- Implementierung in `static/js/index.js`: Multi-Word-AND, `doc._s.indexOf(word)` — pure substring-Suche auf vorgebautem Such-String pro Doc. Keine sichtbare Diakritika-Normalisierung im Filter-Code.
- ID-Suche: implizit möglich, weil `_s` vermutlich `id` enthält (nicht im Detail bestätigt — Test mit User durchführen).

### Suchfunktion in /register/persons.html

- Implementierung in `static/js/register.js`: gleicher Pattern (substring-Filter).
- **Tests gegen `data/persons_search.json` (16.084 Einträge), substring-case-insensitiv:**

| Eingabe | Hits | Bewertung |
|---|---|---|
| "Pilgrim" | 44 | OK |
| "Ulrich" | 659 | OK |
| "Schönberg" | 9 | OK (mit Umlaut) |
| "Schoenberg" | 0 | **DEFEKT** — gleiche Person mit ASCII-Schreibweise nicht findbar |
| "Schoneberg" | 0 | DEFEKT (alternative Transkription) |
| "Müller" | 1 | OK |
| "Mueller" | 0 | **DEFEKT** — Umlaut-ASCII-Variante nicht findbar |
| "Möringer" | 0 | (kein Treffer; Name ggf. nicht im Korpus) |
| "Moringer" | 0 | (siehe oben) |

- **Befund:** Suchindex enthält den `n`-Feld-Wortlaut (mit Umlauten wie geschrieben), aber kein Such-Index mit normalisierten Diakritika. Eingaben ohne Umlaut treffen Einträge mit Umlaut nicht und umgekehrt. Das deckt sich mit der Stakeholder-Aussage laut Subagent-Prompt ("Suchfunktion findet 2/3-3/4 der Hits nicht").
- **Befund:** Der Suchindex `_s` wird im Code dynamisch zusammengesetzt — Anpassung dort möglich (Doppel-Index: original + normalisiert).
- ID-Suche im Personen-Index: `id`-Feld ist `pe__<name>_<korpus>_<docnr>` strukturiert. Test "hadmar_von_schoenberg" findet 2 IDs in `persons_search.json` direkt. Ob die UI-Suche das `id`-Feld in `_s` aufnimmt, ist nicht aus dem Filter-Snippet ersichtlich — User-Verifikation nötig.

### Filter

| Page | Filter vorhanden | Filter fehlend (laut Stakeholder-Anliegen) |
|---|---|---|
| documents.html | Ort, Faksimile, Qualität, Datum-Range | **Korpus als Filter** (nur Chip-Buttons, kein Default) |
| persons.html | Geschlecht, Quellenverknüpfungen, Qualität | **Korpus** (kein `c`-Feld in JSON) |
| organisations.html | (nicht inspiziert — disabled in Nav) | — |
| places.html | (nicht inspiziert) | — |

### Verlinkung

| Richtung | Status |
|---|---|
| Urkunde → Person | vorhanden, Anker auf Tabellenzeile (kein Profil) |
| Person → Urkunden | **fehlt** (keine Personen-Detailseite, Tabellenzeile zeigt nur n/fn/sn/sex/d/dc/qw) |
| Urkunde → Organisation | nicht in Stichprobe geprüft |
| Urkunde → Ort | nicht in Stichprobe geprüft |

## Kritische Befunde im Bezug zum Stakeholder-Protokoll

(Mapping erfolgt in Phase 2 durch den Koordinator. Hier nur die technische Befund-Seite, sortiert nach den Hauptpunkten aus den Subagent-Prompts.)

1. **Suchfunktion findet 2/3–3/4 der Hits nicht** — bestätigt im Code: substring ohne Umlaut-/Diakritika-Normalisierung. Mögliche Doppel-Index-Lösung in `_s`-Aufbau. Auch ID-Suche möglicherweise nicht im `_s` enthalten.
2. **Personen-Profile parallel zu Regesten** — fehlen vollständig. Verlinkung aus Urkunde geht auf Tabellen-Anker. Person-zentrierte Sicht (welche Urkunden? welche Rollen? Lebensspanne aus Datenmenge?) nicht generiert.
3. **Bidirektionale Verlinkung Person ↔ Urkunde** — Hin-Richtung vorhanden (Urkunde → Person-Anker), Rück-Richtung fehlt strukturell, weil keine Detailseite.
4. **Korpus-Filterung auf nur QGW + StB** — datenseitig nicht umgesetzt: QGW II/2 (1415–1417) ist in `search.json` (34 Quellen) und über Korpus-Chip aufrufbar. `persons_search.json` hat kein Korpus-Feld, daher Filterung dort nicht möglich. Approval-Status nicht im Datenmodell.
5. **Glossar — fehlende Begriffe** (Quelle, Untersuchungskategorie, Factoid, Regest, Q-Kategorie, Transaktion, Bestand): "Quelle" ist da, alle anderen fehlen.
6. **Q-Kategorie sichtbar mit Erklärung** — auf `quality.html` heißt es "Datenqualität / Findings nach Kategorie / Hinweise / Warnungen". Der Begriff "Q-Kategorie" als solcher steht im sichtbaren Text nicht; im Quellen-Index taucht der Filter "Qualität" mit `0/1/2` auf. Stakeholder-Punkt geht eher gegen das Vorhandensein/die Sichtbarkeit der gesamten Quality-Page in der Hauptnav als gegen einen einzelnen Begriff.
7. **Statistiken: % statt absolut** — Timeline und KPIs sind absolut. `timeline.json` hat keine Prozentwerte, nur Counts pro Dekade pro Korpus.
8. **Verb-Browser-Granularität** — Section vorhanden auf transactions.html. Detail-Granularität nicht im Detail durchgegangen, aber Existenz bestätigt; Aggregations-Logik in Phase 3 inhaltlich zu klären.
9. **"Tod"-Kategorie** — in Urkunde 1 nicht direkt sichtbar (issuer/recipient), Stichprobe zu klein. Rollenvokabular ist laut Editions-Richtlinien-Page kontrolliert; eigene Sektion 6 dort. Volltext-Check des Vokabulars steht aus.
10. **"Factoids"** — als Toggle und JS-Funktion in jeder Urkunden-Detailseite verwendet. Begriff als Wort im UI sichtbar, im Glossar nicht erläutert.

## Befunde, die im Protokoll NICHT stehen (aus Inspektion)

- **Inkonsistenz Nav-disabled vs. Pages erreichbar** — `register/organisations.html` und `register/places.html` sind als Pages erreichbar, im Top-Nav aber disabled. Direktlinks führen User zu nicht-freigegebenen Inhalten.
- **Doppelter Eintrag im Ort-Filter** — "Wiener Neustadt" (9) und "Wiener-Neustadt" (6) als getrennte Werte. Normalisierungsbug in der Aggregation.
- **Exploration-Hub fehlt im Dropdown** — `exploration/index.html` ist nur über Klick auf "Exploration" als Trigger oder Direktlink erreichbar; Dropdown listet nur Sub-Pages.
- **Keine globale Suchleiste** — Landing hat keine page-übergreifende Suche; Suche ist pro-Page (Quellen / Personen / ...).
- **Korpus-Mismatch zwischen Indizes** — Quellen-Index zählt QGW II/2 mit (34 Stück), Personen-Index zählt potentiell auch dortige Personen mit, ohne Filtermöglichkeit. Konsistenz zwischen Indizes nicht gegeben.
- **Datenstand-Fußzeile** — "17. April 2026" — Stand vor Stakeholder-Meeting (23.04.); Inspektion läuft auf Pre-Meeting-Stand.
- **Provenance-Popovers** — Statistik-KPIs öffnen Popovers mit Erklärung und Datenquelle (`<code>sources/*/done/*.xml</code>`). Methodisch sauberes Pattern, das in Phase 3 für Glossar-Tooltips wiederverwendet werden könnte.

## Offene Fragen

- Enthält der Suchindex `_s` (in `index.js` und `register.js`) das `id`-Feld? Falls nein, muss V3 das mit-aufnehmen, damit Stakeholder eine Urkunde per ID finden können.
- Stakeholder-Punkt "Q-Kategorie zu intern": Bezieht sich das auf die gesamte `quality.html`-Page in der Top-Nav, auf den Filter "Qualität" im Quellen-Index, oder auf einen anderen Ort? Klärung mit Claude B / Koordinator nötig.
- "Tod"-Rolle: ist im kontrollierten Rollenvokabular vorhanden? Stichprobe zu klein. Volltext-Audit des Rollen-Sets aus `edition-guidelines.html` Sektion 6 oder aus TEI-Quellen erforderlich.
- Verb-Browser-Granularität: Konkrete Aggregations-Kandidaten (welche Verben werden gleich behandelt?) müssen vom Inhalt-Strang kommen.
- Approval-Status im Datenmodell: Wo soll der Marker leben — im TEI-Header, in einer separaten `approved.json`, oder im Pfad-Schema? Designentscheidung für V1.
- Personen-Profile (V4): Generierungspfad — Templates pro Person aus `persons_search.json` plus Cross-Reference aus `search.json`-Doc-Felder, oder eigene Aggregation in der Pipeline?
- Browser-Tests mit JS-aktiver Suche (Edge headless) bisher nicht gefahren — alle Suchtests laufen direkt gegen die JSON-Datenquelle; reale UI-Latenz, JS-Filterung mit `_s`-Aufbau und URL-Parameter-Übernahme nicht in Inspektion abgedeckt.

## Anschluss

- Sister-Finding (Stakeholder-Sicht): `Findings/2026-04-26 - sugw Stakeholder-Feedback.md` (Claude B, ausstehend).
- Daten-Architektur (Tech-Referenz): `Knowledge/sugw Daten-Architektur.md` (Koordinator, ausstehend).
- Synthese: `Sessions/2026-04-26 - sugw Synthesis 1.md` (Koordinator, Phase 2).
- Traceability-Matrix: `Project/sugw-Traceability-Matrix.md` (Koordinator, Phase 2).
- Phase 3-Folge: V1 (Korpuskontrolle/Approval-Marker), V2 (Filterung Indizes), V3 (Suche + Umlaut), V4 (Personen-Profile), V5 (Bidirektionale Verlinkung), V8 (Statistik %), V9 (Verb-Browser), V10 (Exploration-Aufräumen) — Detailspezifikation Phase 3.

## Bearbeitungs-LOG

- 2026-04-26 — Claude A — Sessionstart: CLAUDE/MISSION/METHOD/Roadmap/Subagent-Prompts gelesen, Branch `sugw-frontend-rework` bestätigt. Re-Entry-Files (Findings/Sessions/Traceability) noch nicht vorhanden → Phase 1 frisch.
- 2026-04-26 — Claude A — Server `:8765` HTTP 200, Site-Struktur über Filesystem und curl erfasst.
- 2026-04-26 — Claude A — 17 Pflicht-Pages durchgegangen, Headings/Filter/Datenstrukturen extrahiert. Eine Urkunden-Detail-Stichprobe (Nr. 1) inspiziert. Personen-Detail-Stichprobe negativ (existiert nicht).
- 2026-04-26 — Claude A — Suchsemantik gegen `persons_search.json` direkt getestet (substring, case-insensitiv) — Umlaut-Fehlertoleranz negativ bestätigt.
- 2026-04-26 — Claude A — Findings-Datei `status: complete`. Phase 1 abgeschlossen, warte auf Koordinator-Synthese (Phase 2).
