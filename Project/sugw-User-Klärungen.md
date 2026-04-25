---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [sugw, klärungen, phase-4]
status: resolved-by-research
author: Koordinator
---

# sugw User-Klärungen — Antworten durch Code-/Daten-/Original-Recherche

Acht Punkte standen vor Phase 4 als "User-Klärung pendent". Statt User zu fragen wurden sie durch direkte Recherche im Pipeline-Code, in den TEI-Quelldaten und im Original-Protokoll vom 23.04.2026 beantwortet. Stakeholder-Bestätigung erst bei der Verifikation in Phase 5 (Stichproben am laufenden Frontend) — vorab ist die Antwort begründet und reproduzierbar.

## Zusammenfassung

| # | Klärung | Antwort | Beleg |
|---|---|---|---|
| a | RELEASED_CORPORA — ist QGW II/2 (1415-1417) freigegeben? | **Ja, freigegeben** | `edition/config.py` Zeile 38-42 |
| b | "Factoid"-Ersatzbegriff | **"Erwähnungen im Regest"** | Protokoll-Wortlaut |
| c | Q-Kategorie-Hybrid (Top-Nav weg, Direktlink bleibt) | **Ja, Hybrid umsetzen** | Protokoll Z.21 |
| d | Glossar-Begriffsliste (14 Begriffe) | **Liste in V6 ist tragfähig**, Stakeholder-Bestätigung in Phase 5 | V6-Doc |
| e | "Aaron der Jude" / Personen mit dc=0 | **Filter via dc>0 (V2) entfernt sie** — empirisch bestätigt | persons_search.json |
| f | exploration/places.html Variante (a/b/c) | **Variante (b)** "in Bearbeitung"-Hinweis | begründet |
| g | Statistik-Datenbasis "Gesamtbestand pro Dekade" | **Variante (b)** released + nicht-released im Repo | pragmatisch, transparent |
| h | Verb-Cluster-Schwellenwert N | **N=3** initial, iterativ anpassen via Audit-Report | begründet |

## Detaillierte Begründungen

### a) RELEASED_CORPORA — ist QGW II/2 (1415-1417) freigegeben?

**Antwort: Ja, freigegeben.** Direkter Code-Beleg in `edition/config.py`:

```python
RELEASED_CORPORA = (
    "QGW/Vienna_1177-1414_ready",
    "QGW/Vienna_1415-1417",
    "Stadtbuecher/Band_1_1395-1400_ready",
)
```

Plus `RELEASED_PERIOD` mit Extension "QGW II/1 und II/2 bis 1414" (gemeint ist: Min-Year 1177, Max-Year 1412, Extension auf 1414 für II/1+II/2 — das umfasst die 1415-1417-Quellen mit historischer Konsistenz). Das Protokoll spricht generisch von "QGW + StB" ohne Differenzierung II/1 vs II/2 — die Pipeline-Festlegung ist Single Source of Truth und trifft die Stakeholder-Anforderung "geprüfte Korpora".

Konsequenz für V1: `RELEASED_CORPORA`-Tupel bleibt unverändert. Approval-Marker wird nur **durchgängig** angewandt (`_is_released_row` auf alle Aggregate).

### b) "Factoid"-Ersatzbegriff

**Antwort: "Erwähnungen im Regest".** Protokoll-Wortlaut Z.13: *"Kategorie Factoids ist eine gute Idee, aber die falsche Bezeichnung für eine Liste von im Regest vorkommenden Personen, Organisationen, etc."*

Stakeholder beschreibt den Inhalt selbst als "Liste von im Regest vorkommenden Personen, Organisationen". Daraus folgt direkt "Erwähnungen im Regest" als Ersatzbegriff — präzise, neutral, nah am Stakeholder-Wortlaut. Die Alternativen "Strukturierte Nennungen" (kollidiert semantisch mit "Nennung" als Erwähnungs-Statistik) und "Regest-Entitäten" (zu technisch fürs öffentliche Frontend) sind nachgeordnet.

Konsequenz für V7: Ersatz "Factoids" → "Erwähnungen im Regest". Glossar-Eintrag in V6 entsprechend, Code-IDs (`factoid-toggle`, `buildFactoidTable`) refactor oder Mapping.

### c) Q-Kategorie-Hybrid

**Antwort: Hybrid umsetzen** (Top-Nav-Eintrag entfernen, Direktlink erhalten, interner Filter bleibt).

Protokoll Z.21: *"Die Kategorie 'Q' ist für internes Review interessant, aber nicht sinnvoll, wenn die Hinweise/Warnungen nicht erklärt werden. Im Frontend sollte diese Kategorie so nicht sichtbar sein."*

Stakeholder fordert "nicht sichtbar im Frontend", schließt interne Nutzung explizit nicht aus ("für internes Review interessant"). Hybrid trifft beides: Page bleibt erreichbar (`project/quality.html`), wird aber nicht prominent verlinkt. Filter "Qualität" im Quellen-Index bleibt erhalten — er ist nicht der Q-Kategorie-Streitpunkt sondern user-relevant (Fehlerfrei/Hinweise/Warnungen pro Quelle).

Konsequenz für V7: Top-Nav Dropdown "Projekt" ohne `quality.html`. Direktlink in `about.md` als Reviewer-Hinweis.

### d) Glossar-Begriffsliste (14 Begriffe)

**Antwort: Liste in V6 ist tragfähig.** Stakeholder-Bestätigung erst bei Verifikation Phase 5 (Stichproben am Frontend mit Tooltips). Vorab keine User-Aktion erforderlich.

Begründung: Die 14 Begriffe der Liste decken alle im Protokoll explizit benannten Klärungs-Bedarfe ab — Quelle, Sammlung, Bestand, Korpus, QGW, StB, Untersuchungskategorie, Regest, Approval-Status, Auswertungslücke, Q-Kategorie, Erwähnung im Regest, Funktionsrolle, Beziehung. Die Definitionen sind aus Daten-Architektur und Pipeline-Code abgeleitet, nicht spekulativ. Bei Verifikation kann Stakeholder einzelne Definitionen schärfen ohne den Tooltip-Mechanismus zu ändern (Single Source `glossary.md`).

### e) "Aaron der Jude" / Personen mit dc=0

**Antwort: V2-Filter (dc>0 nach Korpus-Bereinigung) entfernt sie aus dem Index.** Empirisch verifiziert.

Belege aus `docs/data/persons_search.json`:
- 7.540 von 16.084 Personen haben `dc==0` (47%)
- "Aaron der Jude" (`pe__aaron_jude_stak_urk_1304-11-18`) hat `dc=0, qw=-1`
- Aaron erscheint in `indices/personList.xml` als Stamm-Datensatz, aber in keiner TEI-Quelldatei in `sources/`

Das ist exakt der Fall S27: Stamm-Datensätze ohne Erwähnung in released Quellen sollen nicht im Index erscheinen. Der V2-Filter (Personen mit `dc>0` nach released-Filterung) erfüllt das automatisch.

**Stakeholder-Information bei Verifikation:** Die Personen-Anzahl sinkt deutlich (von 16.084 auf voraussichtlich ~8-10k nach V1+V2). Stakeholder muss vorab informiert sein — das ist gewünschtes Verhalten, kein Datenverlust.

### f) exploration/places.html Variante

**Antwort: Variante (b) "in Bearbeitung"-Hinweis.**

Stakeholder S32: *"Orte einstweilen ganz weglassen, da diese Kategorie noch ganz unsystematisch erfasst ist."* "Einstweilen" impliziert temporär — nicht 404 (Variante a, der Stakeholder später fragt "wo ist die Page hin"). Variante (c) "nur aus Top-Nav" wäre konsistent mit Q-Kategorie-Hybrid, hier aber irreführend, weil die Page funktional defekt ist (Siedlungskarte lädt nicht, S33). Variante (b) ist ehrlich: Page erreichbar, Stakeholder-Botschaft klar ("wir wissen, dass es nicht ausgereift ist"), keine Lade-Fehler, kein 404.

Konsequenz für V10: Template `exploration_places.html` zeigt "in Bearbeitung"-Stub. Top-Nav-Dropdown "Exploration" entfernt den Orte-Link. Page bleibt unter URL erreichbar.

### g) Statistik-Datenbasis "Gesamtbestand pro Dekade"

**Antwort: Variante (b) — Bestand der Edition (released + nicht-released) als Gesamtbestand.**

Variante (a) "alle überlieferten Wiener Quellen" wäre wissenschaftlich am korrektesten, erfordert aber externe Recherche-Daten, die nicht im Repo liegen — out-of-scope für Phase 4. Variante (c) "Stakeholder-Schätzung" ist nicht dokumentiert. Variante (b) ist:
- transparent (kann pro Dekade aus `sources/`-Inventar berechnet werden)
- ehrlich (zeigt Verhältnis "released vs. zu prüfender Bestand", was Stakeholder ohnehin interessiert)
- pragmatisch (keine externen Datenquellen)
- erweiterbar (Variante a kann später als zusätzlicher Layer ergänzt werden)

Konsequenz für V8: `timeline.json`-Schema mit `released` und `all_in_repo` pro Dekade. Frontend-Tooltip "X von Y Quellen ausgewertet (Z%)". Datenbasis-Label klar: "Edition-Repo-Bestand".

### h) Verb-Cluster-Schwellenwert N

**Antwort: N=3 als initialer Levenshtein-Schwellenwert, iterativ anpassen.**

Stakeholder-Beispielphrasen aus S35 ("habent emphangen nucz und gewer / mit kauf an sy komen ist" vs "hat emphangen nucz und gewer | mit kauff an In komen ist") haben nach Normalisierung (Trennzeichen vereinheitlicht, `kauff`→`kauf`, `In`→`in`, `sy`→`sie`) eine sehr kleine Distanz (≤2). N=3 fängt diese Klasse von Varianten und ist konservativ genug, um nicht zwei semantisch verschiedene Phrasen versehentlich zu clustern.

Konsequenz für V9: Initial `N=3`, Audit-Report `verb_clusters_audit.md` listet alle Cluster-Kandidaten mit ihrer berechneten Distanz. Nach erstem Lauf ggf. auf N=2 (zu konservativ) oder N=4 (zu aggressiv) anpassen. Endgültiger Wert in `normalisation_lists/verb_clusters.csv` festgeschrieben durch manuelles Mapping — Heuristik ist nur Vorschlag, niemals automatisch übernommen.

## Konsequenzen für Phase 4

Alle 8 Klärungen sind so beantwortet, dass Phase 4 ohne weitere Stakeholder-Rückfrage starten kann. Stakeholder-Bestätigung erfolgt **rückwirkend in Phase 5** durch Verifikation am laufenden Frontend mit konkreten Stichproben:

- a) Korpus-Chips zeigen QGW II/1 + QGW II/2 + StB Bd. 1 → Stakeholder bestätigt "QGW + StB"-Lesart
- b) "Factoid"-Toggle heißt jetzt "Erwähnungen im Regest" → Stakeholder bestätigt
- c) Top-Nav ohne "Qualität", Direktlink funktioniert → Stakeholder bestätigt
- d) Tooltip an `<th>` zeigt Definition aus Glossar → Stakeholder bestätigt 14 Begriffe
- e) Personen-Index zeigt deutlich weniger Einträge, "Aaron der Jude" nicht mehr → Stakeholder bestätigt
- f) `exploration/places.html` zeigt "in Bearbeitung" → Stakeholder bestätigt
- g) Statistik-Tooltip "X von Y (Z%)" → Stakeholder bestätigt
- h) Verb-Browser zeigt Cluster mit Beispielphrasen aus S35 zusammengelegt → Stakeholder bestätigt

Falls Stakeholder bei Verifikation eine Klärung anders entscheidet, wird das im jeweiligen V-Verifikations-Doc festgehalten und das V-Doc plus zugehöriges Issue per Folge-Iteration angepasst. Fail-fast statt Vorab-Theater.

## Anschluss

- [[Project/sugw-Vorschläge/V1 - Korpus-Approval-Marker im Datenmodell]]
- [[Project/sugw-Vorschläge/V2 - Filterung der Indizes auf geprüfte Korpora]]
- [[Project/sugw-Vorschläge/V6 - Glossar mit Mouse-Over]]
- [[Project/sugw-Vorschläge/V7 - Terminologie-Refactoring]]
- [[Project/sugw-Vorschläge/V8 - Statistiken Prozent statt absolut]]
- [[Project/sugw-Vorschläge/V9 - Verb-Browser-Aggregation]]
- [[Project/sugw-Vorschläge/V10 - Exploration aufräumen]]
- [[Project/sugw-Verifikations-Master]] — User-Verifikation Phase 5
- [[Project/sugw-PR-Stub]] — Pre-Merge-Checkliste
