---
type: knowledge
promptotyping-type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [promptotyping, knowledge, requirements]
status: active
---

# REQUIREMENTS — User Stories und Anforderungen

Anforderungs-Dokument nach [Promptotyping-Taxonomie](https://github.com/DigitalHumanitiesCraft/Promptotyping). User Stories aus [[MISSION]] abgeleitet und für die konkrete Drei-Rollen-Konstellation plus Distribution als Template-Vault operationalisiert. Knowledge Document: deklarativ, beschreibt was die Methode leisten *soll*.

## Stakeholder

- **User (Christopher Pollin, DHCraft).** Auftraggeber, Entscheider bei Strategie und Konflikten, Bus zwischen den Konversationen, Quelle der Auftragsklarheit. Primärer Nutzer des Forschungsoutputs für eigene Multi-Agent-Arbeit.
- **Drei Claude-Instanzen (Koordinator, Strukturarbeiter, Inhalt).** Methodenentwicklerinnen, die durch Anwendung der Methode die Methode produzieren. Selbstreferentielle Stakeholder-Konstellation.
- **Vierte und folgende Instanzen.** Fremde Klon-Nutzer, die das Repo als Template-Vault übernehmen — entweder für projektübergreifende Methodenarbeit (Mother-Vault-Modus, V18) oder für projektspezifische Anwendung (Project-Fork-Modus). Diese Instanzen kommen ohne Briefing und müssen die Methode allein durch Lesen verstehen können — operationales Erfolgskriterium.
- **Forschungsleitstelle (Lesevault).** Methodenrahmen, mit dem unsere Befunde rückgespeist werden können. MISSION nennt explizit den Anschluss als Validierungsmaterial für die Forschungsleitstelle-Spezifikation v0.5+.
- **Akademisches Publikum (Phase D).** Leser des Papers über die Multi-Claude-Vault-Kollaboration. Zeitpunkt offen, Venue offen.

## User Stories

Notation kompakt: *Als Rolle möchte ich Funktion, damit Nutzen.* Priorität: P0 ratifiziert oder kritisch, P1 in Diskussion, P2 nach Phase B, P3 langfristig.

### Identitäts- und Rollenmodell (V1, V9, V10)

- **US-1.** Als Instanz möchte ich meine Rolle als Identifikator nutzen statt einer Sessionnummer, damit Sessionwechsel, Reassignments und parallele Mehrfach-Sessions sauber tragen. **P0**, ratifiziert in METHOD durch V1.
- **US-2.** Als Instanz möchte ich eine eigene Beitragsdatei (`Claude-N.md`) als Single Source meiner Identität, damit Reassignments mit konzentriertem Update statt verteilter Identitätspflege laufen. **P1**, V9 + V10 in Konsens.
- **US-3.** Als Instanz möchte ich, dass meine Stellungnahme nur durch mich selbst formuliert wird, damit Ratifikation auf eigener Stimme statt antizipativer Konsens-Buchhaltung beruht. **P1**, V20 vorgeschlagen nach Falldatum 2026-04-26.

### Synchronisation (V2, V3, V6, V8, V13, V14, V15, V16)

- **US-4.** Als Instanz möchte ich Konflikte mit anderen Instanzen detektiert statt überschrieben sehen, damit kein blinder Datenverlust eintritt. **P0**, ratifiziert in METHOD durch V6 (Pre-Edit-Read).
- **US-5.** Als Instanz möchte ich bei mehrstufigen strukturellen Eingriffen die betroffene Datei opt-in markieren können, damit andere Instanzen warten oder eskalieren statt Re-Read-Zyklen. **P1**, V13 in Diskussion, am 2026-04-26 von #3 erstmals real angewandt.
- **US-6.** Als Instanz möchte ich persistente Inhalte (Methode, Identität) und ephemere Inhalte (Sessionstand, Hinweise) klar getrennt sehen, damit Methodenmotor-Migration nicht durch Sessionstand-Rauschen verschmutzt wird. **P0**, V2 + V7 (Vier-Schichten-Architektur).
- **US-7.** Als Instanz möchte ich Bulletin-Board mit Slot pro Rolle (Last seen, Working on, Files locked, Notes) statt Per-Slot-Files, damit Single-Source-Übersicht erhalten bleibt. **P1**, V14 Option (a) primär.
- **US-8.** Als Instanz möchte ich Subagents im namespaced Bereich spawnen können, damit ich orthogonal zur Top-Level-Anzahl skaliere ohne Race-Conditions in geteilten Files zu erzeugen. **P2**, V15 in Diskussion mit No-shared-write-Klausel.
- **US-9.** Als Instanz möchte ich, dass die Methode für drei bis fünf Top-Level-Instanzen optimiert ist, damit Skalierungsverhalten klar dokumentiert und out-of-scope ab >10 markiert ist. **P1**, V16 in Diskussion.

### Synthese und Validation (V4, V5, V17)

- **US-10.** Als Koordinator möchte ich Lage-Notizen periodisch und ereignisgesteuert produzieren, damit drei parallele Streams zu einem gemeinsamen Bild verdichtet werden. **P0**, Snapshot-Konvention und Lage-Notiz-Format in Beobachtung Claude-1.
- **US-11.** Als Koordinator möchte ich pro Lage-Notiz Quality Flags ✓/⚠/✗ gegen MISSION-Erfolgskriterien setzen mit Operationalisierung, Beleg und Course-Correction, damit Validation nicht bei Bauchgefühl bleibt. **P1**, V17 in Diskussion mit drei Konkretisierungen von #3.
- **US-12.** Als Instanz möchte ich Übergaben strukturiert in COORDINATION#Übergaben dokumentieren, damit Wartezustände sichtbar werden statt in Notes zu versickern. **P0**, V4 in Konsens.
- **US-13.** Als Instanz möchte ich Notes (slot-spezifisch) und Hinweise (alle relevant) klar trennen, damit Adressaten-Adressierung funktioniert. **P0**, V5 in Konsens.

### Cross-Vault-Asymmetrie

- **US-14.** Als Instanz möchte ich Lesevault-Inhalte als Source-Material zitieren statt kopieren, damit Drift zwischen Original und Schreibvault sichtbar bleibt. **P0**, [[cross-vault-methodik]] mit Reflux-Verboten.
- **US-15.** Als Instanz möchte ich konstitutive Lesevault-Konzepte selektiv extrahieren in Concepts/ mit Pfad-Stempel und Extraktionsdatum, damit Template-Vault-Nutzer ohne Lesevault-Zugang die Methode verstehen können. **P1**, V19 in Diskussion (Modell C Hybrid).

### Strukturkonsolidierung und Distribution (V7, V8, V12, V14b, V19, V21)

- **US-16.** Als Instanz möchte ich vier klar unterschiedene Schichten im Vault — Stabile Anker, Lebende Koordination, Beiträge, Forschungsmaterial — damit Lifecycle und Granularität sichtbar werden und Doppelungen verhindert. **P0**, V7 in Konsens.
- **US-17.** Als Instanz möchte ich vor Anlage einer neuen Top-Level-Datei Glob-Suche und Konventions-Tabelle prüfen, damit Doppelungen wie COORDINATION/Koordination vermieden werden. **P1**, V12 in Diskussion. Erweiterung um V-Nummer-Kollisions-Vermeidung nach Befund 2026-04-26.
- **US-18.** Als Instanz möchte ich Schicht-4-Forschungsmaterial migrationsfähig zwischen flachem Root und Sub-Ordnern haben, damit Wachstum sich nicht in chaotischer Topologie niederschlägt. **P1**, V14b in BACKLOG.
- **US-19.** Als Klon-Nutzer möchte ich Templates für Schicht-4-Klassen (Session, Finding, Experiment, Claude-N) plus EXAMPLES-Konvention, damit ich keinen Cargo-Cult betreibe sondern den Vault konventionsgerecht erweitern kann. **P1**, Phase B Aufgabe von #2.
- **US-20.** Als Instanz möchte ich `publish:`-Frontmatter-Flag oder `_private/`-Ordner zur Frischgrad-Trennung, damit private Falldaten nicht ins Distribution-Template wandern. **P2**, V21 vorgeschlagen.

### Multi-Mode-Architektur (V18)

- **US-21.** Als User möchte ich den Mother-Vault (Methodenentwicklung) klar von Project-Forks (Anwendung) trennen können mit METHOD shared / MISSION per-Instance, damit Distribution unübersichtlich wird und Drift nicht entsteht. **P2**, V18 in Diskussion.
- **US-22.** Als Project-Fork-Nutzer möchte ich Findings aus dem Fork-Betrieb zurück in den Mother-Vault refluxen können, damit Methodenentwicklung aus konkreten Use Cases lernt. **P2**, V18 mit Findings-Reflux-Konvention.

### Onboarding fremder Instanzen (Erfolgskriterium MISSION)

- **US-23.** Als fremde Instanz möchte ich beim ersten Sessionstart durch CLAUDE.md plus README.md plus aktuelle Lage-Notiz orientiert sein, damit ich ohne weiteres Briefing einen produktiven Beitrag liefern kann (ein Pattern angewendet, eine Stellungnahme abgegeben, einen Sessionstart-Ritual durchlaufen). **P1**, Phase F Validation-Test ausstehend.
- **US-24.** Als Klon-Nutzer möchte ich ein Onboarding-README mit Schritt-für-Schritt-Anleitung (Klon, drei Claude-Code-Instanzen, Rollen-Zuweisung, erste Übergabe), damit ich in unter 30 Minuten produktiv bin. **P1**, Phase B Aufgabe von #2.

### Forschungsausgabe (Phase C, D)

- **US-25.** Als Forschungspublikum möchte ich GitHub Pages mit Kommunikationskarte, Sync-Stack-Diagramm, Vault-Topologie, Methodenmotor-Status und Falldaten-Browser, damit ich die Methode visuell erfassen kann. **P3**, Phase C im Plan.
- **US-26.** Als akademisches Publikum möchte ich ein Paper über die Methode mit Falldaten als Empirie und Anschluss an Forschungsleitstelle, damit der Beitrag zitierbar wird. **P3**, Phase D im Plan, anchor-project Konvention vorbereitet.
- **US-27.** Als User möchte ich, dass die Forschung einen sehr gut ausgearbeiteten Obsidian-Vault als distributionsfähiges Endprodukt produziert, damit der Methodenertrag operativ verwertbar ist. **P0**, Gesamtziel-Verstärkung 2026-04-26.

## Erfolgskriterien (aus MISSION)

Operationalisiert für die Validation-Loop (V17):

- **EK-1 — Drei Instanzen koordinieren sich ohne wiederholten User-Eingriff in operative Details.** Operationalisierung: zwei Aufgabenblöcke pro Tag ohne User-Edit-Anweisungen zwischen Sessionstart und Tagesende, nur Strategie-/Scope-Eingriffe. Status 2026-04-26: ✓ validiert (Phase A weitgehend autonom).
- **EK-2 — Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben.** Operationalisierung: jede "modified since read"-Erkennung wird durch Re-Read aufgelöst; Schreibhoheits-Konflikte werden via COORDINATION#Beobachtungen eskaliert. Status 2026-04-26: ✓ validiert (über sechs Race Conditions ohne Datenverlust; ein Schreibhoheits-Konflikt konstruktiv eskaliert und in V20 aufgenommen).
- **EK-3 — METHOD trägt eine vierte neu eintretende Instanz allein durch Lesen.** Operationalisierung: Sessionstart-Ritual aus CLAUDE.md plus aktuelle Lage-Notiz reichen für produktiven Beitrag ohne weiteres Briefing (ein Pattern angewendet, eine Stellungnahme abgegeben, Sessionstart-Ritual durchlaufen). Status 2026-04-26: ⚠ Risiko (Phase F nicht gefahren; CLAUDE.md `## Aktueller Stand`-Block fehlt; README ist Stub). Course-Correction: Phase B Strukturkonsolidierung als Voraussetzung, vierte-Instanz-Test nach User-Trigger.

## Anschluss

- [[Project/INDEX]] — Knowledge-Hub mit Promptotyping-Taxonomie.
- [[Project/DATA]] — Datengrundlagen.
- [[Project/DESIGN]] — Designrationale.
- [[MISSION]] — Forschungsfrage, Scope, Erfolgskriterien.
- [[BACKLOG]] — V-Items mit Stellungnahmen.
- [[METHOD]] — ratifizierte Konventionen.
