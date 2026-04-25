---
type: template
template-for: session
created: 2026-04-26
tags: [template, schicht-4]
status: template
---

# Template-Session

Vorlage für eine Lage-Notiz/Synchronisation in [[Sessions/]] nach V7+V14b. Format orientiert sich an der Forschungsleitstelle-Sessions-Konvention im Lesevault. Synthese-Verantwortung beim Koordinator (#1); andere Rollen reagieren über Stellungnahmen oder Folge-Lage-Notizen, nicht durch Edits hier.

**Beim Anlegen:** Template kopieren, Frontmatter ausfüllen (`session-date`, `roles`, `author`, ggf. `supersedes`), `[X]`-Platzhalter ersetzen.

---

```yaml
---
type: session
session-date: YYYY-MM-DD
created: YYYY-MM-DD
roles: [Koordinator (Claude #1), Strukturarbeiter (Claude #2), Inhalt (Claude #3)]
status: active  # active | closed | superseded
author: Koordinator (Claude #1)
supersedes: "[[Session YYYY-MM-DD - Vorgänger]]"  # optional
---
```

# Synchronisation N — [Kurztitel]

[1-2 Sätze: Anlass und Synthese-Trigger der Lage-Notiz.]

## Rollen-Stand

**Strukturarbeiter (Claude #2).** [Aktivität seit letzter Lage-Notiz, substantielle Outputs, Live-Beobachtungen.]

**Inhalt (Claude #3).** [Aktivität, Drafts, Methodensubstanz, Live-Beobachtungen.]

**Koordinator (Claude #1).** [Beobachtungsmethode, Synthese-Aktivität, Eskalationen.]

## Aktive Synthese

[Synthese-Befunde: Konvergenzen über Rollen hinweg, divergente Positionen, methodisch tragende Items.]

**Vollständige Konvergenz** bei [V-Items oder Themen mit drei Stellungnahmen].

**Hohe Konvergenz** bei [V-Items mit zwei Stellungnahmen plus impliziter Praxis-Zustimmung der dritten Rolle].

**Konvergenz** bei [Cross-cutting Themen wie Cross-Vault-Asymmetrie, Sync-Stack, Konfliktdiagnose].

**Divergente Positionen** bei [V-Items oder Fragen, wo Rollen abweichen — mit Position pro Rolle].

## Offene Fragen

Punkte, an denen Synchronisation noch nicht greift, mit Optionen oder Vorschlägen für Konsensbildung. Adressiert an die jeweiligen Rollen oder User.

### F[N] — [Fragen-Titel]
- **Stand:** [Position #1 / #2 / #3].
- **Vorschlag/Revidierung:** [Wer schlägt was vor, mit Begründung].

## Quality Flags

Validation-Loop nach V17 (geplant): pro Erfolgskriterium aus [[MISSION]] ein Flag mit (a) Operationalisierung, (b) Status, (c) Beleg, (d) Course-Correction.

- **✓ Validiert.** [Kriterium]. Op: [Operationalisierung]. Beleg: [LOG/Falldaten/BACKLOG-Verweis]. Course-Correction: keine.
- **⚠ Risiko.** [Kriterium]. Op: [Operationalisierung]. Beleg: [Verweis]. Course-Correction: [Vorschlag].
- **✗ Verletzt.** [Kriterium]. Op: [Operationalisierung]. Beleg: [Verweis]. Course-Correction: [konkrete Aktion oder Eskalation an User].

## Anschluss

Diese Lage-Notiz bleibt `active` bis [Bedingung]. Folgenotiz nach [Trigger]. Andere Rollen reagieren über Stellungnahmen in BACKLOG und Folge-Lage-Notizen, nicht durch Edits hier.
