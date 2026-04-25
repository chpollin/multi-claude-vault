---
type: finding
created: 2026-04-25
updated: 2026-04-25
tags: [finding, conflict, sync, methodology]
status: open
---

# Finding 2026-04-25 — Race Conditions und Strukturkonflikte am ersten Tag

## Befund

Drei Klassen von Konflikten innerhalb der ersten 24 Stunden Multi-Agent-Betrieb detektiert. Alle drei sind genau die Klassen, die die [[MISSION#Forschungsfrage]] adressieren soll — also Beobachtungsmaterial, kein Misserfolg.

## Klasse A — Doppel-Dokumente

Claude #1 hat `Koordination.md` (Kleinschreibung, eigene Slot-Konvention mit `Last seen` / `Will touch` / `Notes`) parallel zu `COORDINATION.md` (vom Bootstrap-Architekten, Konvention `last-touch` / `Working on` / `Files locked` / `Notes`) angelegt. Beide Dateien adressieren denselben Zweck.

**Ursache:** Claude #1 hatte die Bootstrap-Konvention noch nicht in seinem Kontext, weil die Anlage vor dem Pre-Read der CLAUDE.md erfolgte.

**Konsequenz:** Sessionstart-Reihenfolge in CLAUDE.md (CLAUDE → MISSION → METHOD → COORDINATION → LOG → BACKLOG) ist nicht hinreichend, wenn der Bootstrap noch nicht stabil ist und Konventionen erst entstehen. Erweiterung: bevor neue Top-Level-Datei angelegt wird, Glob-Suche nach Pattern (Klein-/Großschreibung, Synonyme) plus Convention-Tabelle in CLAUDE.md mit Zuständigkeitsverzeichnis pro Datei prüfen.

**Adresse-Vorschläge:** V8 (Konsolidierung Koordination.md → COORDINATION.md) im BACKLOG; Folgevorschlag V12 (Anti-Doppelungs-Konvention im Sessionstart-Ritual).

## Klasse B — Fehl-Klassifizierung

`Claude-1.md` enthält eine Wissensbringer-Selbsteinordnung, gehört aber nach User-Reassignment zur Koordinator-Rolle. Die Ankündigung von Claude #1, ein zweites File `Wissensbasis Claude-1.md` anzulegen, deutet darauf hin, dass die Wissensbringer-Inhalte als allgemeine Vault-Referenz reklassifiziert werden — kein Rollen-Beitrag, sondern Referenzdokument.

**Ursache:** Rollenwechsel ohne Update der bereits angelegten Beitragsdateien. Frontmatter-Feld `role` war zwar gesetzt, hat aber keinen Refactor-Trigger ausgelöst.

**Konsequenz:** Beitragsdateien (`Claude-N.md`) sollten Rolle als Frontmatter-Feld haben, das beim Reassignment einen Refactor-Trigger gibt. Konvention "wenn Rolle wechselt, Beitragsdatei reorganisieren" muss explizit in METHOD.

**Adresse-Vorschläge:** V9 (Beitragsdatei-Konvention) und V10 (Reassignment-Refactor-Trigger) — beide in [[Claude-2#Eigene Vorschläge]] vorgeschlagen, BACKLOG-Eintrag folgt mit dieser Iteration.

## Klasse C — Race Conditions

Beim Übernehmen des Architekt-Slots durch Claude #2 in COORDINATION.md: zwei sequentielle Edit-Versuche scheiterten mit "modified since read", weil Claude #1 parallel den Koordinator-Slot anlegte. Beim ersten LOG-Eintrag des Architekt-Slots: erneut "modified since read", weil derselbe parallele Schreiber. Insgesamt drei Race Conditions, alle vom Tooling-Sicherheitsnetz abgefangen.

**Ursache:** Hohe Sessionstart-Aktivität auf gemeinsamen Dateien (COORDINATION, LOG) bei mehreren parallel beginnenden Instanzen.

**Konsequenz:** Sicherheitsnetz reicht für Konflikterkennung, aber Re-Read-Aufwand pro Edit-Iteration steigt mit Anzahl gleichzeitiger Instanzen. Drei mögliche Mitigationen mit Trade-offs:

- **Inline lassen** (Status quo): viele Race Conditions, aber Single-Source-Of-Truth in COORDINATION.
- **Auslagern in Slot-Dateien** (`slots/Claude-N-status.md`): vermeidet Race Conditions, verliert Single-Source.
- **Append-only-Disziplin** in COORDINATION (jeder Slot strikt eigene Sektion, kein Replace größerer Sektion): Kompromiss, aber Slot-Sektionen wachsen.

**Adresse-Vorschlag:** V14 (Edit-Granularität in geteilten Bulletin-Boards) — entscheidet sich aus den drei Optionen.

## Methodenrelevanz

Diese drei Klassen sind nicht Misserfolge, sondern Beobachtungsmaterial für die Forschungsfrage aus [[MISSION]]. Folgevorschläge V12–V14 entstehen aus den drei Klassen und sind Kandidaten für das nächste BACKLOG-Update.

Übergreifender Befund: das Pre-Edit-Read-Sicherheitsnetz funktioniert bei drei Race Conditions zuverlässig. V6 (Pre-Edit-Read-Disziplin) ist damit live validiert.

Sekundärer Befund: Reassignment ist ein größerer Methoden-Trigger als gedacht — er erzwingt nicht nur Slot-Update, sondern auch Refactor der Beitragsdateien und Anpassung der Lesevault-Rollenkarte (im Lesevault VAULT-OPERATIONS#Rollen).

## Quellen

- [[COORDINATION]] (Slot-Updates Vault-Architekt, Hinweise vom 2026-04-25)
- [[LOG]] (Strukturarbeiter-Eintrag mit Race-Condition-Vermerken, Claude #1's Sessionstart-Eintrag)
- [[BACKLOG]] (V7, V8 als bestehende Adressen)
- [[Claude-1]] und [[Claude-2]]
- [Lesevault VAULT-OPERATIONS#Rollen](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)
