---
type: knowledge
created: 2026-04-26
tags: [sugw, verifikation, index]
status: phase-5-skeleton
---

# sugw-Verifikation — Index

User-zentrierte Verifikations-Dokumente, gespeist nach Implementation pro V-ID. Werden in **Phase 5** (nach Phase-4-Implementation) befüllt — Schritt-für-Schritt-Anleitung für Stakeholder zum Abgleich Port 8765 (alt) vs. Port 8766 (neu).

Konsolidiert in [[../sugw-Verifikations-Master]].

## V-Verifikations-Docs (Phase 5)

| V-ID | Datei | Status |
|---|---|---|
| V1 | V1-Verifikation.md | wartet auf Implementation |
| V2 | V2-Verifikation.md | wartet auf Implementation |
| V3 | V3-Verifikation.md | wartet auf Implementation |
| V4 | V4-Verifikation.md | wartet auf Implementation |
| V5 | V5-Verifikation.md | wartet auf Implementation |
| V6 | V6-Verifikation.md | wartet auf Implementation |
| V7 | V7-Verifikation.md | wartet auf Implementation |
| V8 | V8-Verifikation.md | wartet auf Implementation |
| V9 | V9-Verifikation.md | wartet auf Implementation |
| V10 | V10-Verifikation.md | wartet auf Implementation |
| V11 | V11-Verifikation.md | wartet auf Implementation |

## Stakeholder-zentrierte Verifikationen

Falls eine S-ID besonders sensibles Stakeholder-Echo erfordert (z.B. S20 Pötel/Pötlin/Regest 3819), eigene Datei `S<id>-Verifikation.md` mit explizitem Stakeholder-Bezug. Aktuell geplant:

- S20-Verifikation.md — Test-Anker Pötel/Pötlin (wird in V3+V4+V5 referenziert)
- S37-Verifikation.md — Audit "Interface = DB" über alle Statistiken

## Konventionen pro V-Verifikations-Doc

```yaml
type: knowledge
verifikation-id: V<n>
v-doc: "[[V<n> - <kurztitel>]]"
github-issue: <n>
status: draft | bestätigt-vom-user | offen-mit-notiz
verifiziert-am: YYYY-MM-DD
```

Inhalt:
1. **Setup** — Server-Befehle Port 8765 + 8766
2. **Schritt-für-Schritt** — pro Akzeptanzkriterium ein Klick-Pfad
3. **Stakeholder-Stichprobe** — Test-Anker (z.B. Pötel/Pötlin)
4. **Erwartetes Ergebnis** — visuelle/inhaltliche Differenz alt-vs-neu
5. **Bei Fehlschlag** — Eskalation mit Notiz

## Anschluss

- [[../sugw-Verifikations-Master]] — Konsolidierte User-Anleitung.
- [[../sugw-Vorschläge/README]] — V-Doc-Index.
- [[../sugw-Traceability-Matrix]] — S→V-Matrix.
