---
type: knowledge
created: 2026-04-26
tags: [sugw, vorschläge, index]
status: complete
---

# sugw-Vorschläge — Index

Konkrete Implementations-Vorschläge V1–V11, abgeleitet aus Stakeholder-Meeting 23.04.2026 und Frontend-Inspektion. Pro Vorschlag: Frontmatter mit `vorschlag-id`, `stakeholder-issues`, `betroffene-files`, `aufwand`, `status`, `github-issue` plus Problem, Lösungsansatz, Akzeptanzkriterien, Verifikations-Plan, Risiken/Antipatterns, Anschluss, Bearbeitungs-LOG.

Gespiegelt als GitHub-Issues im Edition-Repo. Code-Implementation passiert im **Pipeline-Repo** auf Branch `frontend-rework-2026-04`.

## V-IDs

| V-ID | Issue | Datei | Adressiert | Aufwand |
|---|---|---|---|---|
| V1 | [#1](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/1) | [V1 - Korpus-Approval-Marker im Datenmodell](V1%20-%20Korpus-Approval-Marker%20im%20Datenmodell.md) | S25, S26, S28, S29, S31, S37 | 8-12h |
| V2 | [#2](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/2) | [V2 - Filterung der Indizes](V2%20-%20Filterung%20der%20Indizes%20auf%20gepr%C3%BCfte%20Korpora.md) | S25, S26, S27, S29, S37 | 4-6h |
| V3 | [#3](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/3) | [V3 - Suche Volltext + ID + Diakritika](V3%20-%20Suche%20Volltext%20%2B%20ID%20%2B%20Diakritika.md) | S16, S17, S18, S19, S20 | 8-12h |
| V4 | [#4](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/4) | [V4 - Personen-Profile](V4%20-%20Personen-Profile%20parallel%20zu%20Regesten.md) | S21, S22, S27 | 12-16h |
| V5 | [#5](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/5) | [V5 - Bidirektionale Verlinkung](V5%20-%20Bidirektionale%20Verlinkung%20und%20Beziehungen.md) | S22, S23, S24 | 6-8h |
| V6 | [#6](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/6) | [V6 - Glossar mit Mouse-Over](V6%20-%20Glossar%20mit%20Mouse-Over.md) | S3, S5, S6, S7, S11, S15, S17 | 10-14h |
| V7 | [#7](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/7) | [V7 - Terminologie-Refactoring](V7%20-%20Terminologie-Refactoring.md) | S1, S2, S3, S4, S8, S9, S10 | 6-10h |
| V8 | [#8](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/8) | [V8 - Statistiken Prozent statt absolut](V8%20-%20Statistiken%20Prozent%20statt%20absolut.md) | S12, S13, S26, S37 | 8-10h |
| V9 | [#9](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/9) | [V9 - Verb-Browser-Aggregation](V9%20-%20Verb-Browser-Aggregation.md) | S35 | 10-14h |
| V10 | [#10](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/10) | [V10 - Exploration aufräumen](V10%20-%20Exploration%20aufr%C3%A4umen.md) | S32, S33, S34 | 3-5h |
| V11 | [#11](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/11) | [V11 - Frontend-Polish](V11%20-%20Frontend-Polish.md) | S14 + Inspektions-Befunde | 4-6h |

Tracking-Issue: [#12 Frontend-Rework Übersicht](https://github.com/chpollin/db_for_medieval_legal_transactions_edition/issues/12). Milestone: `frontend-rework-2026-04`.

## Implementations-Reihenfolge

1. **#1 → #2** (Korpus-Filter durchgängig — Voraussetzung für Folge)
2. **#3** (Suche, S20-Smoking-Gun)
3. **#4 + #5** gemeinsam (Personen-Profile + Beziehungen)
4. **#6 + #7** synchron (Glossar liefert Begriffe, Terminologie setzt sie ein)
5. **#8** (Statistik baut auf #1+#2+#6)
6. **#9, #10** parallel (Exploration und Verb-Browser)
7. **#11** zum Abschluss (Polish)

## Konventionen

- Status-Lifecycle pro V-Doc: `draft` → `review` → `ready-for-implementation` → `implementiert` → (optional `verifiziert`).
- Nach Implementation: V-Doc-Status auf `implementiert`, Issue auf `closed`, `implementation-commits` im Frontmatter befüllt.
- Verifikations-Doc pro V-ID in `Project/sugw-Verifikation/V<id>-Verifikation.md`.
- V-Doc bleibt Source of Truth für inhaltliche Beschreibung; GitHub-Issue ist Tracking-Spiegel.

## Anschluss

- [[Project/sugw-Traceability-Matrix]] — Vollständige S-ID-Matrix.
- [[Project/sugw-Verifikations-Master]] — User-Anleitung Phase 5.
- [[Project/sugw-User-Klärungen]] — 8 Klärungen durch Recherche beantwortet.
- [[Project/sugw-PR-Stub]] — Pre-Merge-Checkliste.
