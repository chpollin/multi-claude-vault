---
type: coordination
created: 2026-04-25
updated: 2026-04-26
tags: [coordination, ephemeral, sugw]
status: active
---

# COORDINATION

Laufende Koordination zwischen den Instanzen. Ephemer (V2): Inhalte werden bei Erledigung gelöscht oder wandern bei Stabilisierung nach [[METHOD]] oder Schicht-4-Findings. Lifecycle-Konvention in [[METHOD#Lifecycle pro Sektion explizit (V3)]].

Single Bulletin-Board (V8). Slot-Format pro aktiver Session: `### Rolle (— optional Slot-Hinweis)`, mit `last-touch`, `Last seen`, `Working on`, `Files locked`, `Will touch`, `Notes`. Andere Felder optional.

## Aktive Sessions

### Koordinator — Single-Curator (Branch sugw-frontend-rework)
- last-touch: 2026-04-26
- Last seen: **Phase 1+2+3 abgeschlossen.** Phase-1-Setup, Synthese (Phase 2 mit vollständiger Traceability-Matrix für 37 S-IDs → 11 V-IDs, Quality-Flag-Lage-Notiz V17-Pilot), Phase 3 (alle 11 V-Docs V1-V11 mit Akzeptanzkriterien und Verifikations-Plan), Phase-5-Setup (Verifikations-Master-Skeleton + PR-Stub), Phase-6-Vorbereitung (Reflux-Finding für Mother mit 5 methodischen Lessons). Vollständigkeitsprinzip eingehalten: keine S-ID abgewählt; S30/S33/S36 als methodisch-dokumentarisch markiert. Drei User-Klärungspunkte vor Phase 4 dokumentiert (V1 Korpus-Liste, V7 Factoid-Ersatz/Q-Hybrid, V8 Datenbasis-Definition, weitere in PR-Stub).
- Working on: Sessionende. Phase 4 (Implementation in sugw-Pipeline-Repo Branch frontend-rework-2026-04) wartet auf User-Klärungen (a)-(h) im PR-Stub plus User-Freigabe für sugw-Pipeline-Repo-Branch-Erzeugung.
- Files locked: keine.
- Will touch in Phase 4 (gemäß V-Dokumenten — Subagent-Phase): Implementation in sugw-Pipeline-Repo (NICHT in diesem Vault, hier nur Status-Updates der V-Docs und Traceability-Matrix). 
- Will touch in Phase 5: V-Verifikations-Docs konsolidieren in Verifikations-Master, PR-Stub finalisieren.
- Will touch in Phase 6: Reflux-Finding ggf. um Phase-4-Lessons erweitern, Branch-Merge in main nach User-Freigabe.
- Notes: V15-Pilot erfolgreich, V20-Externalisierung validiert, V18-Light-Mode (Branch statt Repo) tragfähig, Vollständigkeitsprinzip-Pattern bewährt — alle in [[Findings/2026-04-26 - Phase-E-Pilot Reflux zur Mother]] dokumentiert.

## Übergaben

Format: `### Von #X → Nach #Y — Kurztitel`, mit `Datum`, `Datei(en)`, `Zustand bei Übergabe`, `Erwartete nächste Aktion`. Bei Erledigung mit `[abgeschlossen]` markieren oder löschen.

### Koordinator → Claude A — Phase-1-Frontend-Inspektion
- Datum: 2026-04-26
- Dateien: [[Project/sugw-Subagent-Prompts]] Sektion "Claude A", [[Knowledge/sugw Daten-Architektur]] als Referenz, Live-Server `http://127.0.0.1:8765/`
- Zustand bei Übergabe: Branch sugw-frontend-rework eingerichtet. Server läuft. Pipeline-Repo-Approval-Mechanismus dokumentiert. Output-Pfad reserviert: `Findings/2026-04-26 - sugw Frontend-Inspektion.md`.
- Erwartete nächste Aktion: User startet Claude-A-Konversation mit Prompt aus Subagent-Prompts.md. A führt Inspektion durch, schreibt Output-Datei, setzt `status: complete`, eskaliert Sessionende-Statement.

### Koordinator → Claude B — Phase-1-Stakeholder-Feedback
- Datum: 2026-04-26
- Dateien: [[Project/sugw-Subagent-Prompts]] Sektion "Claude B", Protokoll `c:\Users\Chrisi\Downloads\Protokoll_SuG_23_04_Final.docx`, PowerPoint `c:\Users\Chrisi\Downloads\Protokoll_SuG_23_04_Frontend Änderungen_Final.pptx`
- Zustand bei Übergabe: Slide-Bilder bereits extrahiert nach `/tmp/sugw-ppt/ppt/media/` und `c:\tmp\sugw_slide_*.png`. Output-Pfad reserviert: `Findings/2026-04-26 - sugw Stakeholder-Feedback.md`.
- Erwartete nächste Aktion: User startet Claude-B-Konversation mit Prompt aus Subagent-Prompts.md. B führt Analyse durch, schreibt Output-Datei mit S-IDs, setzt `status: complete`.

## Beobachtungen

Methodisch relevante Befunde aus dem Multi-Agent-Betrieb. Lifecycle wie Hinweise.

- **2026-04-26, Koordinator, V15-Pilot-Beobachtung 1.** Subagent-Briefing-Aufwand: die zwei Prompts plus Pfad-Cheat-Sheet plus Templates plus Daten-Architektur summieren auf ~1000 Zeilen Vorbereitungs-Material vor dem ersten Subagent-Lauf. Trade-off: hoher initialer Aufwand vs. Selbsterklärung im Subagent-Sessionstart. Wert für Mother-Reflux: das ist die Realität des V15-Subagent-Spawn-Patterns. Konvention im Mother dokumentieren — "Subagent-Briefing-Größe ist nicht Bug, sondern Feature der Methode".

## Hinweise

- **2026-04-26, Koordinator, an Claude A + Claude B:** Beim Sessionstart unbedingt `git status` und `git branch --show-current` prüfen. Branch muss `sugw-frontend-rework` sein. Wenn nicht: STOP und User fragen — auf falschem Branch zu schreiben verschmutzt die Mother oder den falschen Fork.
- **2026-04-26, Koordinator, an alle:** Vollständigkeitsprinzip ist explizit. Kein Stakeholder-Feedback-Punkt darf still abgewählt werden. Lieber `abgelehnt mit Begründung` als weglassen. Tracking in [[Project/sugw-Traceability-Matrix]].
- **2026-04-26, Koordinator, Pfad-Hinweis Phase 4:** Pipeline-Repo-Branch `frontend-rework-2026-04` legt Claude A in Phase 4 an, NICHT vorher. User-Freigabe für Phase 4 ist explizit erforderlich (kein Auto-Mode für Branch-Erzeugung im fremden Repo).
