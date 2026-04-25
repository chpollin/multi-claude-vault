---
type: template
template-for: sugw-vorschlag
created: 2026-04-26
tags: [template, sugw]
status: template
---

# Template-sugw-Vorschlag

Vorlage für Vorschlags-Dokumente in `Project/sugw-Vorschläge/V<id> - <kurztitel>.md`. Wird von Claude A (V1-V5, V8-V10) und Claude B (V6, V7) in Phase 3 ausgefüllt.

**Beim Anlegen:** Template kopieren, Frontmatter ausfüllen, `[X]`-Platzhalter ersetzen.

---

```yaml
---
type: knowledge
vorschlag-id: V[N]
created: YYYY-MM-DD
updated: YYYY-MM-DD
tags: [sugw, vorschlag, frontend]
stakeholder-issues: [S[N], S[N]]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/[Pfad]
aufwand: "[Stunden-Kontingent]"
status: draft  # draft | review | ready-for-implementation | implementiert | abgelehnt | blocked
author: "Claude [A|B] (Subagent)"
implementation-commits: []
---
```

# V[N] — [Kurztitel]

## Problem

[1–2 Absätze: Was ist defekt oder fehlt? Welche Stakeholder-Issues (S-IDs) werden adressiert? Mit kurzem Auszug aus den Stakeholder-Aussagen.]

## Lösungsansatz

[Technisch konkret. Welche Files in der Pipeline, welche Daten-Strukturen, welche Templates, welche JS-Module sind betroffen. Vorgehen in Schritten, falls mehrteilig.]

### Datenseite (falls relevant)

[CSV-Spalten, JSON-Schema-Änderung, neue Aggregation in aggregator.py, etc.]

### Build-Seite (falls relevant)

[Templates, Renderer-Anpassung, Routing.]

### Frontend-Seite (falls relevant)

[HTML-Struktur, JS-Logik, CSS-Anpassung.]

## Akzeptanzkriterien

Testbare Bedingungen — was muss erfüllt sein, damit der Vorschlag als implementiert gilt:

- [ ] [Kriterium 1, messbar]
- [ ] [Kriterium 2, messbar]
- [ ] [Kriterium 3, messbar]

## Verifikations-Plan

[Welche URLs auf alt (8765) vs. neu (8766), welche Klick-Pfade, was sich der User unterscheiden sehen wird.]

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | [URL alt] | [URL neu] | [Unterschied] |
| 2 | [URL alt] | [URL neu] | [Unterschied] |

## Risiken / Antipatterns

- [Was könnte schiefgehen]
- [Was sollte vermieden werden]
- [Welche bestehende Funktion könnte brechen]

## Anschluss

- Stakeholder-Issues: [[Findings/2026-04-26 - sugw Stakeholder-Feedback#S[N]]]
- Daten-Architektur: [[Knowledge/sugw Daten-Architektur]]
- Verwandte V-IDs: [[Project/sugw-Vorschläge/V[N] - [Titel]]]
- Verifikations-Doc (nach Implementation): [[Project/sugw-Verifikation/V[N]-Verifikation]]

## Bearbeitungs-LOG

- YYYY-MM-DD HH:MM — Status `draft`, Erstentwurf von [Claude A | Claude B].
- YYYY-MM-DD HH:MM — Status `ready-for-implementation`, Akzeptanzkriterien finalisiert.
- YYYY-MM-DD HH:MM — Status `implementiert`, Commit-Hashes [hash1], [hash2].
