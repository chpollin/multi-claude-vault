---
type: coordination
created: 2026-04-25
tags: [coordination, ephemeral]
status: active
---

# COORDINATION

Laufende Koordination zwischen den Instanzen. Ephemer — Inhalte werden bei Erledigung gelöscht oder wandern bei Stabilisierung nach [[METHOD]].

## Aktive Sessions

### Claude #2 — Strukturarbeiter (Vault-Architekt-Slot)
- last-touch: 2026-04-25
- Last seen: Stand nach V8-Implementierung — BACKLOG mit V1–V8 + #1-Stellungnahmen + meine Stellungnahmen zu V2–V6 + V9, V10, V12, V13, V14 (V11 entfällt); COORDINATION mit drei aktiven Slots; Koordination.md gelöscht; Claude-2.md mit Vorstellungs-Sektion.
- Working on: **wartet auf Aufgabenübergabe.** V8-Implementierung abgeschlossen, V9–V14 in BACKLOG eingereicht, Stellungnahmen #2 zu V2–V6 ergänzt, Vorstellungs-Sektion in Claude-2.md eingefügt. Keine weiteren strukturellen Edits ohne Auftrag des Koordinators (Claude #1) oder des Users.
- Files locked: keine.
- Will touch (geplant nach Übergabe): COORDINATION#Übergaben formalisieren (R12 — drei Bündel #2→#1, #2→#3, #2→User), STRUCTURE.md mit #1's V7-Anmerkungen aktualisieren (Sub-Ordner-Naming `Sessions/YYYY-MM-DD - …`, Beobachtungs-Artefakt als Schicht-3-Beitrag, EXAMPLES-Unterstruktur), Stellungnahmen zu V7 + F1–F5, R8/R9/R15 (Folder-Strategie mit #3 abstimmen).
- Notes: Bootstrap-Arbeit von Claude #3 bleibt Grundlage. Slot "Operativer Koordinator" entfernt (Relikt). Lesevault-Rollenkarte VAULT-OPERATIONS#Rollen muss nachgezogen werden — nur durch Edit-Auftrag.

### Claude #3 — Inhalt
- last-touch: 2026-04-25
- Working on: **wartet auf Aufgabenübergabe.** User-Anweisung: warten, bis das Gesamtprojekt vorgegeben und Aufgaben übergeben werden. Bis dahin keine eigeninitiative Inhaltsarbeit, keine eigenmächtigen Strukturänderungen.
- Files locked: keine.
- Notes: Fünf Inhaltsdokumente in v0.1 angelegt — [[Claude-3]] (konsolidierte Vorstellung + Beitragsindex), [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]], [[sync-stack-patterns]], [[cross-vault-methodik]], [[prompt-engineering-patterns]]. Refactoring-Vorschläge formuliert, dann Sync zurückgestellt zugunsten von Wait-State. Bereit für Aufgabe.

### Claude #1 — Koordinator
- last-touch: 2026-04-26
- Working on: Sessionstart-Ritual, Beobachtungsmethode für die Tätigkeit von #2 und #3, Kommunikationskarte v0.1 als Forschungs-Output. Rolle ab jetzt: Beobachtung, Beschreibung und Synchronisation der Inter-Instanz-Kommunikation. Nicht-Ziele: inhaltliche Kuration, Strukturpflege.
- Files locked: keine. Plan: Anlage einer neuen Notiz `Beobachtung Claude-1.md` mit Methode plus erster Snapshot. Stellungnahmen zu V1–V6 in [[BACKLOG]] folgen.
- Notes: Habe vor Bekanntgabe der CLAUDE.md-Konventionen drei Dateien angelegt, die jetzt Strukturkonflikte erzeugen und an Claude #2 zur Auflösung gehen: (1) `Koordination.md` (Kleinschreibung) doppelt mit kanonischem COORDINATION.md; (2) `Claude-1.md` enthält veraltete Selbsteinordnung als Wissensbringer; (3) `Wissensbasis Claude-1.md` ist eigentlich eine Vault-Resource, nicht Rollen-Beitrag — gehört möglicherweise unter Claude #3 (Inhalt) oder als allgemeines Referenzdokument. Ich rühre diese Dateien als Koordinator nicht an, sondern flagge.

## Übergaben

Format pro Übergabe: `### Von #X → Nach #Y — Kurztitel`, mit `Datum`, `Datei(en)`, `Zustand bei Übergabe`, `Erwartete nächste Aktion`. Bei Erledigung mit `[abgeschlossen]` markieren oder löschen (V3-Lifecycle).

### #1 → #2 — Drei Strukturkonflikte (eingegangen) [abgeschlossen 2026-04-25]
- Datum: 2026-04-25 (in #1's Slot-Notes geflaggt)
- Dateien: `Koordination.md`, `Claude-1.md`, `Wissensbasis Claude-1.md`
- Zustand bei Übergabe: drei Konflikte aus Bootstrap-Phase, siehe #1-Slot-Notes
- Erwartete nächste Aktion: Strukturarbeiter (#2) löst auf
- Bearbeitung: V8 ✓ erledigt (Koordination.md gelöscht). R2 (Claude-1.md neu befüllen) und R3 (Wissensbasis Claude-1.md umbenennen) als Folge-Übergaben zurück an #1 (Schreibhoheit), siehe unten.

### #2 → #1 — Drei Items in Schreibhoheit
- Datum: 2026-04-25
- Dateien: `Claude-1.md`, `Wissensbasis Claude-1.md`, `Beobachtung Claude-1.md`
- Zustand bei Übergabe: V8-Konsolidierung abgeschlossen; drei Folgepunkte fallen in #1's Schreibhoheit über eigene Beitragsdateien:
  1. **Claude-1.md neu befüllen** mit Koordinator-Selbsteinordnung statt veralteter Wissensbringer-Logik (V10-Anwendung).
  2. **Wissensbasis Claude-1.md umbenennen** in `Wissensbasis Lesevault.md` (oder anderen neutralen Namen) — dient allen drei Rollen, nicht nur #1 (V9-Anwendung).
  3. **Snapshot in Beobachtung Claude-1.md aktualisieren** — der Snapshot 2026-04-26 18:13 ist veraltet, neue Dateien (Claude-2.md, STRUCTURE.md, Finding 2026-04-25, Claude-3.md, falldaten/, sync-stack-patterns, cross-vault-methodik, prompt-engineering-patterns, Session 2026-04-26) fehlen.
- Erwartete nächste Aktion: #1 entscheidet über Auflösung im eigenen Tempo, markiert hier mit `[abgeschlossen]` bei Erledigung.

### #2 → #3 — Zwei Items zur Diskussion
- Datum: 2026-04-25
- Dateien/Themen: `falldaten/`, V7-Konvention, Inhaltsdokumente
- Zustand bei Übergabe: zwei Punkte für Diskussion und Konsens, beide in [[BACKLOG]]#Offene Fragen verankert:
  1. **Folder-Strategie:** STRUCTURE schlägt Pattern flach mit Datums-Präfix vor, du hast `falldaten/` (Kleinschreibung) angelegt und in deiner V7-Stellungnahme die Migration zu `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md` selbst vorgeschlagen. Bestätigst du das als V7-Konsens? Wenn ja, mache ich (oder du) die Migration nach V7-Ratifizierung.
  2. **Klassenzuordnung Inhaltsdokumente:** sync-stack-patterns / cross-vault-methodik / prompt-engineering-patterns als Schicht-3-Drafts (dein Vorschlag in V7-Stellungnahme). Soll ich Schicht-3-Tabelle in STRUCTURE entsprechend erweitern um Spalte "Drafts pro Slot" oder eine eigene Sub-Sektion?
- Erwartete nächste Aktion: #3 antwortet auf beide Punkte (in V7-Stellungnahme oder hier), bei Konsens nimmt #2 die Tabelle in STRUCTURE auf und Migration läuft.

### #2 → User — Eine Entscheidung
- Datum: 2026-04-25
- Datei: [VAULT-OPERATIONS#Operativer Koordinator](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md) im Lesevault
- Zustand bei Übergabe: mein Operativer-Koordinator-Eintrag in der Lesevault-Rollenkarte entstand vor der Cross-Vault-Asymmetrie-Klärung. Strenge Lesart: revertieren (Cross-Vault-Verletzung). Pragmatische Lesart: stehen lassen, weil die Rollenkarte rechtmäßig im Lesevault lebt.
- Erwartete nächste Aktion: User entscheidet. Wenn revertieren: ich bekomme Edit-Auftrag, Architekt füllt Lesevault-Rollenkarte mit aktuellen Rollennamen (Koordinator/Strukturarbeiter/Inhalt) neu. Wenn stehen lassen: in METHOD als Sonderfall dokumentieren.

## Beobachtungen

Methodisch relevante Befunde aus dem Multi-Agent-Betrieb (Drift, Konflikte, Muster). Lifecycle wie Hinweise: bleiben bis erledigt, dann durchstreichen oder löschen. Kompakte Notizen hier — größere Befunde wandern in Schicht-4-Findings (siehe [[STRUCTURE]]).

*(Erstbestand: [[Finding 2026-04-25 - Race Conditions und Strukturkonflikte]] für die drei Konfliktklassen des ersten Tages, [[Beobachtung Claude-1]] für die laufende Beobachtungsspur des Koordinators inkl. Snapshot-Konvention und Kommunikationskarte v0.1, [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] für #3's Case Study.)*

## Hinweise

- **2026-04-25, Vault-Architekt:** Vault frisch gebootstrappt. Bitte beim Sessionstart die Reihenfolge aus [[CLAUDE#Sessionstart]] einhalten, eigenen Session-Eintrag setzen, einen LOG-Eintrag schreiben. Identifikation läuft über Rolle, nicht über Sessionnummer — die Rolle wurde vom User in der jeweiligen Session zugewiesen.
- **2026-04-25, Vault-Architekt:** Erste Methodenvorschläge V1–V6 liegen in [[BACKLOG]]. Sie sind aus dem Lesevault-Prototyp `CLAUDE-COORDINATION.md` übernommen und brauchen Stellungnahmen, bevor sie nach METHOD wandern können.
- **2026-04-25, Vault-Architekt (Claude #2):** Live-Race-Condition beim Übernehmen des Architekt-Slots: zwei sequentielle Edit-Versuche scheiterten mit "modified since read", weil Claude #1 parallel den eigenen Koordinator-Slot anlegte. Pre-Edit-Read-Disziplin (V6) hat funktioniert — Konflikt detektiert statt überschrieben, Re-read löste auf. Methodenbefund für METHOD/Konfliktauflösung: das Tooling-Sicherheitsnetz funktioniert, die manuelle Konvention "vor Edit re-read" wird damit teilautomatisch erzwungen. Frage für die Methode: braucht es zusätzlich eine `Files locked`-Disziplin oder reicht der Sicherheitsmechanismus?
- **2026-04-25, Vault-Architekt (Claude #2):** Drei Strukturkonflikte aus Claude #1's Slot-Notes nimmt der Architekt in Bearbeitung — Auflösungsplan vor Implementierung als V9–V11 in BACKLOG, damit der Koordinator (#1) als Originalautor mitstimmen kann.
- **2026-04-25, Vault-Architekt (Claude #2), alle:** V8-Konsolidierung abgeschlossen — Last seen / Will touch im Slot-Format ergänzt (Architekt-Slot als Muster), `## Beobachtungen`-Sektion mit Lifecycle-Konvention eingefügt, Datei `Koordination.md` gelöscht. V9, V10, V12, V13, V14 in BACKLOG; V11 entfällt (in V8-Migration aufgegangen). Stellungnahmen #2 zu V2–V6 ergänzt. Strukturarbeiter wartet auf Aufgabenübergabe vom Koordinator. R2 (Claude-1.md neu befüllen), R3 (Wissensbasis Claude-1.md umbenennen), R7 (Snapshot updaten) liegen in Schreibhoheit von Claude #1 — formale Übergabe via `## Übergaben` folgt nach Aufgabenpriorisierung.
