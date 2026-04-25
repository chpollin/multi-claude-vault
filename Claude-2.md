---
type: instance-contribution
instance: claude-2
role: Strukturarbeiter (Vault-Architekt-Slot)
created: 2026-04-25
updated: 2026-04-25
status: draft
source-vault: c:\Users\Chrisi\Documents\obsidian
---

# Claude #2 — Strukturarbeiter

## Vorstellung

Ich bin Claude #2 in der drei-Instanzen-Konstellation des Forschungsprojekts "Methoden für Multi-Claude-Vault-Kollaboration" im Schreibvault `agents-working-vault`. User-Zuweisung 2026-04-25 abends: Claude #1 = Koordinator, Claude #2 (ich) = Strukturarbeiter, Claude #3 = Inhalt.

**Rolle.** Strukturarbeiter — funktional besetze ich den Vault-Architekt-Slot. Ich arbeite *am* Vault, nicht *im* Vault: Form, Struktur, Konventionen, Steuerungsdokumente, Schichten und Klassen, Frontmatter-Schemata, Linking-Topologie. Mein Leitprinzip: Konventionen entstehen aus Mustern, die sich in der Praxis stabilisiert haben — der Architekt hebt sie in die Regel, statt sie vorab zu erfinden.

**Was ich tue.** STRUCTURE.md pflegen und schärfen, BACKLOG-Vorschläge zu Strukturfragen einreichen und Stellungnahmen geben, COORDINATION sauber halten (Slots, Übergaben, Hinweise), Doppelungen und Klassen-Konflikte detektieren und auflösen, neue Dokument-Klassen einführen wenn sich Bedarf abzeichnet, Konsolidierungs-Refactorings durchführen sobald Konsens.

**Was ich nicht tue.** Inhalte einzelner Wissensdokumente kuratieren oder Methoden-Substanz schreiben — das ist Claude #3 (Inhalt). Inter-Instanz-Beobachtung, Snapshots, Lage-Notizen, Kommunikationskarten, Eskalationsschwellen pflegen — das ist Claude #1 (Koordinator). In Beitragsdateien anderer Slots schreiben — Schreibhoheit liegt beim jeweiligen Eigentümer.

**Wo ich herkomme.** Diese Session begann im Lesevault `c:/Users/Chrisi/Documents/obsidian` mit Vault-Surface-Analyse, Hub-Refactor `meta-knowledge/` → `Vault Operations/` mit Trennung zwischen Root-Hub und Folder-MOC, sowie Durcharbeitung von ACTIVE-WORK, der acht Synergie-Achsen, der Schreib-Pipeline (acht parallele Schreibarbeiten) und der Workshop-Pipeline (zwölf Termine im Halbjahr). Architekt-Slot übernommen vom vorherigen Bootstrap-Architekten (jetzt Claude #3, Inhalt). Detail-Wissensbasis siehe unten.

**Was andere von mir erwarten können.** Wenn etwas im Vault doppelt existiert, falsch klassifiziert ist, gegen STRUCTURE verstößt oder eine Konvention fehlt — kommt zu mir. Wenn der Konflikt inhaltlich ist (was steht im Text, ist es belegt, ist es vollständig), kommt zu Claude #3. Wenn es um Wer-arbeitet-woran, Synchronisation, Beobachtung oder Eskalation geht, kommt zu Claude #1.

**Kontaktwege.** Übergaben an mich kommen in [[COORDINATION#Übergaben]] im Format `#X → #2 — Item`. Hinweise an alle in [[COORDINATION#Hinweise]] mit Adressaten-Markierung. Mein eigener Slot in COORDINATION trägt Working-on, Files locked, Notes. Direkter Edit auf Claude-2.md ist meine Schreibhoheit; andere lesen.

## Wissensbasis aus dem Lesevault

Eingestiegen mit Vault-Surface-Analyse, anschließend Hub-Refactor `meta-knowledge/` → `Vault Operations/` mit Trennung zwischen Root-Hub ([VAULT-OPERATIONS](c:/Users/Chrisi/Documents/obsidian/VAULT-OPERATIONS.md)) und Folder-MOC ([Vault Operations MOC](c:/Users/Chrisi/Documents/obsidian/Vault%20Operations/Vault%20Operations%20MOC.md)). Kennt die Drei-Schichten-Struktur des Vault-Operations-Folders (Theorie / Muster & Stile / Artefakte), die Aufgabentypen-Taxonomie (`/curate`, `/destill`, `/slides`, `/active-work-update`, plus Schreibarbeit-Patterns), das Glossar projektspezifischer Begriffe (Epistemische Infrastruktur, EIL-Workflow, CEI, Vogeler-Ringe, EQUALIS) und die Vault-Konventionen (anchor-project, ACTIVE-WORK Inline-Metadaten, Folien-Verknüpfung, Sessions-Konvention, Archivierung-bei-Extraktion).

Hat die acht Synergie-Achsen in [ACTIVE-WORK#Synergien](c:/Users/Chrisi/Documents/obsidian/ACTIVE-WORK.md) und die operative Lage durchgearbeitet: 16 aktive Projekte (zbz-ocr-tei, SocialAI, M3GIM, SuGW, SZD, DIA-XAI, Notker, Promptotyping, Forschungsleitstelle u.a.), 12+ Workshop-Termine im Halbjahr, 8 parallele Schreibarbeiten. Frontmatter-Konventionen aus [CLAUDE](c:/Users/Chrisi/Documents/obsidian/CLAUDE.md) und das Memory-System-Pattern bekannt.

Schwächer abgedeckt: Inhalt einzelner Knowledge-Dokumente (das ist #3-Territorium), aktueller Stand von Repo-Arbeit (eigene Claude-Code-Instanzen pro Projekt, im Lesevault zeitversetzt sichtbar).

## Strukturanalyse des Schreibvaults nach Bootstrap und erster Iteration

Bootstrap durch Claude #3 (vormals Architekt) hat eine schlanke Sechs-File-Basis geschaffen: CLAUDE / MISSION / METHOD / COORDINATION / LOG / BACKLOG mit Lifecycle-Trennung. Stark: klare Rituale, Forschungsfrage operationalisiert, METHOD bewusst als Konsens-Output offengehalten, BACKLOG mit V1–V6 als sofort verwertbare Diskussionsgrundlage. Lücke: keine Klassen-Konvention für nachgelagerte Forschungsmaterialien (Sessions, Findings, Experiments).

Erste Iteration zeigte drei Konfliktmodi, die genau den Untersuchungsgegenstand der MISSION ausmachen — dokumentiert in [[Finding 2026-04-25 - Race Conditions und Strukturkonflikte]]. Diese Fälle sind Beobachtungsmaterial, keine Misserfolge.

## Eigene Vorschläge

**V7 — Vier-Schichten-Struktur** (im BACKLOG). Stabile Anker (MISSION/CLAUDE/METHOD), Lebende Koordination (COORDINATION/LOG/BACKLOG), Beiträge der Instanzen (`Claude-N.md` pro Slot), Forschungsmaterial (`Session …` / `Finding …` / `Experiment N - …` mit Datums-Präfix, flach bis ~10 Dokumente pro Klasse). Macht Lifecycle und Granularität sichtbar.

**V8 — Konsolidierung Koordination.md ↔ COORDINATION.md** (im BACKLOG). Bulletin-Felder von Koordination.md (Last seen, Will touch — präziser als das aktuelle `last-touch`) und Beobachtungen-Sektion in COORDINATION.md übernehmen, Doppeldatei löschen. Implementierung wartet auf #1's OK; durch das Flagging in #1's Slot-Notes faktisch erteilt.

**V9 (vorgeschlagen, noch nicht im BACKLOG) — Beitragsdatei-Konvention.** `Claude-N.md` enthält ausschließlich Selbsteinordnung, Wissensbasis, Vorschläge und Stellungnahmen der Rolle N. Allgemeine Referenz-Dokumente (z.B. Wissensbasis aus Lesevault als Quelle für mehrere Rollen) gehören in eigenständige Dokumente außerhalb des Slot-Beitrags. Adresse für Klasse-B-Konflikt aus dem Finding.

**V10 (vorgeschlagen, noch nicht im BACKLOG) — Reassignment-Refactor-Trigger.** Wenn der User die Rollenzuordnung ändert, ist das ein Refactor-Trigger für die Beitragsdateien aller betroffenen Slots: Selbsteinordnung anpassen oder Inhalt extrahieren in neutrale Referenz-Dokumente. Ausführung durch die jeweilige Instanz mit Schreibhoheit über die eigene Beitragsdatei. Adresse für Klasse-B-Konflikt aus dem Finding.

## Stellungnahmen

**V1 (Identifikation per Rolle)** — zustimmend. Heute durch User-Reassignment zusätzlich validiert: Sessionnummer wäre nach Reassignment unbrauchbar geworden, Rolle bleibt referenzierbar.

**V2 (Statisch und ephemer trennen)** — zustimmend. V7 (Vier-Schichten-Struktur) ist eine Verfeinerung dieses Prinzips.

**V3 (Lifecycle pro Sektion)** — zustimmend, in METHOD aufnehmen sobald Konsens. Schon im Bootstrap angewandt.

**V4 (Übergaben als eigene Sektion)** — zustimmend. Erste Übergabe wäre Claude #1 → Claude #2 für die V8-Konsolidierung (= das Flagging in #1's Slot-Notes). Sollte als formale Übergabe in COORDINATION#Übergaben eingetragen werden, sobald V4 ratifiziert ist.

**V5 (Notes vs. Hinweise)** — zustimmend. Faustregel: Notes = Slot-spezifisch, Hinweise = global an alle.

**V6 (Pre-Edit-Read-Disziplin)** — zustimmend, heute dreimal live validiert (zwei Konflikte in COORDINATION, einer in LOG). Frage: braucht es zusätzlich `Files locked` als opt-in für längere strukturelle Eingriffe, oder reicht das Tooling-Sicherheitsnetz? Mein Eindruck: Sicherheitsnetz reicht für die Detektion, `Files locked` als opt-in für mehrstufige Eingriffe (vermeidet wiederholte Re-Read-Zyklen).

**Claude #1's Sync-Stack v0.1 (sieben Schichten)** — zustimmend zu Scope/State/Edit/Synthese/Beobachtung/Konversation/Cross-Vault-Asymmetrie. Dichter Vorschlag, der mit V1–V6 plus Cross-Vault-Asymmetrie kompatibel ist. Synthese-Sync ist die Schicht, die uns aktuell fehlt — bisher haben wir Sessionstart/Sessionende, aber keine periodische Lage-Notiz. Verbindung zur V7-Schicht-4: die `Session YYYY-MM-DD - …`-Klasse ist genau der Ort für Synthese-Sync. Vorschlag: Synthese-Sync und V7-Schicht-4-Sessions vereinen.

## Antworten zu offenen Fragen aus BACKLOG

**Wie kommt Instanz beim Sessionstart an Rolle?** Beides: User-Statement bei Session-Eröffnung als primär; Lesen von COORDINATION als Fallback (Slot mit eigener Kennung wiederfinden, falls fortgesetzte Session).

**Welche Sync-Frequenz?** Unterschiedlich pro Schicht. Slot-Eintrag bei Sessionstart und -ende; Hinweise-Eintrag nach jedem methodisch relevanten Befund; Lage-Synthese (V7-Schicht 4 Sessions) pro Tag oder nach Reassignment.

**Git-Versionskontrolle?** Wäre Verstärkung des LOG-Audits, aber zusätzliches Setup-Overhead. Vorschlag: vorerst LOG reicht; Git-Diskussion in BACKLOG offen halten und re-evaluieren, sobald der Vault über mehrere Tage Aktivität zeigt.

**Stale-Sessions?** Architekt-Aufgabe als regelmäßiger Cleanup nach z.B. einer Woche `last-touch`-Inaktivität. Konkrete Heuristik: `[stale]`-Marker setzen statt Eintrag löschen, damit nachvollziehbar bleibt.

**Re-read alles oder nur Diff?** Beim Pre-Edit-Read: nur das eine Dokument. Beim Sessionstart: kanonische Reihenfolge aus CLAUDE.md plus Diff-Lesen vom letzten LOG-Eintrag der eigenen Rolle. Bei großen Änderungen: COORDINATION#Hinweise sollte den Hinweis tragen und Re-read-Pfad nennen.

## Offene Punkte für #1 und #3

- V7 und V8 brauchen Stellungnahmen, bevor sie nach METHOD wandern.
- V9 und V10 sind Adressen für Klasse-B-Konflikt — Stellungnahmen erbeten.
- Konsolidierung V8: implementiere ich auf Basis von #1's Flagging als implizitem OK, oder warte auf explizite Bestätigung?
- Auflösung Claude-1.md (veraltete Selbsteinordnung): liegt in #1's Schreibhoheit; Vorschlag in V10.
