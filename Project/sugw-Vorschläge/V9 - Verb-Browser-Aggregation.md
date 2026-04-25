---
type: knowledge
vorschlag-id: V9
created: 2026-04-26
tags: [sugw, vorschlag, frontend, verb-browser]
stakeholder-issues: [S35]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/exploration_transactions.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/normalisation_lists/ (ggf. Neu: verb_clusters.csv)
aufwand: "10-14h"
status: ready-for-implementation (mit Heuristik-Klärung)
author: Koordinator
implementation-commits: []
---

# V9 — Verb-Browser-Aggregation

## Problem

S35 (Protokoll Z.24, Slide 12): "Verb-Browser interessant, aber in derzeitiger Form zu kleinteilig und irreführend: Viele der aufgelisteten 'Verben' sollten zusammengerechnet werden, wie etwa 'habent emphangen nucz und gewer / mit kauf an sy komen ist' und 'hat emphangen nucz und gewer | mit kauff an In komen ist'."

Stakeholder-Beispiele zeigen: identische Bedeutung, unterschiedliche orthographische/flexionale Varianten und Trennzeichen (`/` vs. `|`).

Strang A bestätigt Verb-Browser auf `exploration/transactions.html`, Granularität nicht im Detail geprüft.

## Lösungsansatz

### Aggregations-Heuristik

Mittelhochdeutsch-Lemmatisierung ist nicht trivial. Pragmatische Cluster-Heuristik:

1. **Normalisierung pro Verb-Phrase.**
   - Trennzeichen `/`, `|`, `\` einheitlich auf einen Separator (z.B. ` `).
   - Doppel-Leerzeichen kollabieren.
   - Lower-Case.
   - Diakritika-Normalisierung (gleiche Funktion wie V3).
   - Häufige orthographische Varianten: `kauff` → `kauf`, `In` → `in`, `sy` → `sie`, `emphangen` → `empfangen` etc. (Liste in `normalisation_lists/verb_normalisation.csv` pflegen).

2. **Cluster-Kandidaten via Levenshtein.** Phrasen, deren normalisierte Form Levenshtein-Distanz ≤ N (initial N=3) zu einer anderen Phrase haben, sind Cluster-Kandidaten.

3. **Manuelles Cluster-Mapping** in `normalisation_lists/verb_clusters.csv`: `original_phrase | cluster_id | display_label`. Stakeholder oder Editorin pflegt; Pipeline nutzt Mapping bei Aggregation.

4. **Build-Audit-Report `pipeline/output/verb_clusters_audit.md`** mit:
   - Liste aller Phrasen, die noch nicht in einem Cluster sind.
   - Kandidaten-Vorschläge aus Levenshtein-Heuristik (Editor-Review-pendent).

### Frontend

5. **Verb-Browser-Page** zeigt Cluster (mit `display_label`) statt einzelner Phrasen. Klick auf Cluster expandiert Liste der Original-Varianten. Counts pro Cluster.

6. **Filter "Original-Phrasen anzeigen"** — Toggle für Editorinnen-Sicht.

## Akzeptanzkriterien

- [ ] Stakeholder-Beispielphrasen aus S35 sind im selben Cluster:
  - "habent emphangen nucz und gewer / mit kauf an sy komen ist"
  - "hat emphangen nucz und gewer | mit kauff an In komen ist"
- [ ] Verb-Browser zeigt Cluster mit `display_label` und Count.
- [ ] Klick auf Cluster zeigt enthaltene Original-Varianten.
- [ ] `verb_clusters_audit.md` listet noch nicht zugeordnete Phrasen mit Heuristik-Vorschlägen.
- [ ] Toggle "Original-Phrasen anzeigen" funktional.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `exploration/transactions.html` Verb-Browser | gleiche URL | Alt: viele dünne Einträge, ähnliche Phrasen separat. Neu: Cluster mit aggregiertem Count |
| 2 | Suche/Filter nach Stakeholder-Beispielphrase | gleiche Aktion | Alt: zwei separate Treffer. Neu: ein Cluster |
| 3 | `pipeline/output/verb_clusters_audit.md` | — | Datei existiert mit Heuristik-Liste |

## Risiken / Antipatterns

- **Risiko:** Falsche Cluster (zwei Bedeutungen werden zusammen geclustert). Mitigation: Editor-Review via `verb_clusters.csv` — niemals automatisch ohne menschliche Validierung.
- **Antipattern:** Levenshtein-only Cluster ohne menschliche Pflege. Heuristik-Kandidaten gehören in den Audit-Report, nicht direkt in den Live-Cluster.
- **Risiko:** Verb-Cluster-Wartung wird Editor-Aufwand — muss in Edition-Workflow kommuniziert werden. Out-of-Scope für Phase 4 als Phase-5-Anschluss.

## Anschluss

- Stakeholder-Issues: S35.
- Heuristik-Klärung: User-Konsultation für initialen Cluster-Schwellenwert; Stakeholder-Workflow für Cluster-Pflege.
- Verwandte V-IDs: V10 (Exploration aufräumen — Verb-Browser bleibt erhalten, V10 betrifft andere Exploration-Subseiten).

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert. Status mit Heuristik-Klärung pendent.
