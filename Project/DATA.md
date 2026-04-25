---
type: knowledge
promptotyping-type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [promptotyping, knowledge, data]
status: active
---

# DATA — Datengrundlagen

Kontext-Dokument nach [Promptotyping-Taxonomie](https://github.com/DigitalHumanitiesCraft/Promptotyping). Beschreibt, *womit* das Forschungsprojekt arbeitet — welche Daten, Quellen und empirischen Grundlagen die Methodenentwicklung trägt. Knowledge Document: deklarativ, erweitert den epistemischen Horizont.

## Drei Datenklassen

Das Projekt arbeitet mit drei klar unterschiedenen Datenklassen, die unterschiedliche Schreibrechte und Drift-Risiken haben.

### Klasse 1 — Lesevault als Wissensquelle (read-only)

Pfad: `c:\Users\Chrisi\Documents\obsidian` (User-Wissensvault, ca. 458 Dokumente, Stand April 2026).

Inhaltlich:
- Steuerungsdokumente: ACTIVE-WORK, CLAUDE, VAULT-OPERATIONS, HOME, TAG-TAXONOMY.
- Konzeptkorpus: Applied Generative AI, Digital Humanities, Knowledge, Literature, Projects, Teaching, Writing.
- Querkonzepte: Promptotyping, Forschungsleitstelle, Epistemic Infrastructure, Scholar-Centered Design, anchor-project, Critical Collaborator for Academic Writing, Context-Engineered Writing, EIL-Workflow, CEI, Vogeler-Ringe, Editopia, EQUALIS.
- Projektlandschaft: SZD, DIA-XAI, Klawiter-Rescue, M³GIM, SuGW, zbz-ocr-tei, FemPrompt-SozArb, Forschungsleitstelle.
- Paper-Landschaft 2026 mit anchor-project-Konvention.
- Dissertation Pollin (Modelling, Operationalising and Exploring Historical Information) und atomar-extrahierte Wissensdokumente daraus.

Zugriff: nur Lesen. Cross-Vault-Asymmetrie ist methodisch verankert (siehe [[Cross-Vault-Methodik]]). Verweise als absolute Markdown-Pfade, nie als Wikilinks. Reflux-Verbote: keine 1:1-Kopien, kein Editieren im Lesevault, kein Erfinden, kein implizites Übertragen.

Drift-Risiko: Lesevault verändert sich kontinuierlich (User pflegt aktiv). Schreibvault muss bei Verweisen Pfad-Stempel und Extraktionsdatum mitführen, damit Drift sichtbar wird.

Konstitutive Lesevault-Knoten für die Methodenentwicklung (erste Welle für Concepts/-Extraktion nach V19-Ratifizierung):
- **Forschungsleitstelle** — Lane-Konzept und Sessions-Format. Direktes Vorbild für unsere Lage-Notizen. MISSION nennt explizit den Anschluss als Validierungsmaterial.
- **Promptotyping** — K/P/A-Taxonomie, Vier-Phasen-Schema, Promptotyping Documents als Source of Truth. Methodisches Substrat unserer eigenen Arbeit.
- **anchor-project Konvention** — Vorbedingung für Phase D Paper im Lesevault unter `Writing/Paper/`.

Zweite-Welle-Knoten (bei Phase-C/D-Eintritt):
- Critical Collaborator for Academic Writing, Context-Engineered Academic Writing — Schreib-Methode für das Paper.
- Knowledge Curation, Prozesstransparenz, Modell-Selbsteinschätzung — Methodenanreicherung.
- Scholar-Centred Design, Information Visualization, Coordinated Views — Phase C Visualisierung.

Eine kompakte Schnellreferenz auf den Lesevault liegt in [[Wissensbasis Lesevault]] (V9-Anwendung — vault-übergreifend zugängliches Referenzdokument für alle drei Rollen).

### Klasse 2 — Schreibvault als Methoden-Werkstatt (read-write)

Pfad: `C:\Users\Chrisi\Documents\GitHub\multi-claude-vault\` (dieses Repo).

Datenklassen darin (V7 Vier-Schichten-Architektur plus Erweiterungen):
- **Schicht 1 — Stabile Anker:** MISSION, CLAUDE, METHOD, STRUCTURE.
- **Schicht 2 — Lebende Koordination:** COORDINATION, LOG, BACKLOG.
- **Schicht 3 — Beiträge der Instanzen:** Claude-1, Claude-2, Claude-3, plus instanzgebundene Methoden-Dokumente (Beobachtung Claude-1, sync-stack-patterns, cross-vault-methodik, prompt-engineering-patterns).
- **Schicht 4 — Forschungsmaterial:** Sessions (Lage-Notizen), Findings (methodische Befunde), Falldaten/Experiments. Aktuell flach im Root mit Klassen-Präfix bzw. im `falldaten/`-Sub-Ordner.
- **Schicht 5 — Concepts/ (V19 vorgeschlagen, in Ratifikation):** vault-übergreifendes Source-Material aus dem Lesevault, atomar extrahiert mit Pfad-Stempel und Extraktionsdatum.
- **Knowledge/-Bündel (Promptotyping-Documents):** projekteigene Wissensbasis nach K/P/A-Taxonomie, quer zur V7-Hierarchie.

Schreibrechte: differenziert nach Rolle und Schicht (siehe [[Project/DESIGN]]). V6 (Pre-Edit-Read) als reaktive Konfliktdetektion. V13 (Files locked) als opt-in für mehrstufige Eingriffe.

### Klasse 3 — Empirische Falldaten aus eigenem Betrieb

Die drei Instanzen produzieren während der Methodenentwicklung empirische Daten *über* die Methodenentwicklung — Race-Conditions, Konflikte, Konvergenzen, Drift, Reassignments. Diese Daten sind primärer Forschungsoutput, weil sie die Untersuchungsgegenstände der MISSION sind.

Bisherige Falldaten:
- [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] — drei Konfliktklassen (A Doppelungen, B Fehl-Klassifizierung, C Race Conditions) mit Adressierungs-Vorschlägen V12, V13, V14.
- [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] — Bootstrap-Tag als Fallstudie mit sieben methodischen Auffälligkeiten und sechs Lessons Learned. Migration nach `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md` pendent (V14b nach V7-Ratifikation).
- [[Beobachtung Claude-1]] — laufende Beobachtungsspur des Koordinators mit zwei Snapshots, Beobachtungsmethode (sieben Quellen), Snapshot-Konvention, Lage-Notiz-Format, Kommunikationskarten-Lifecycle, Eskalations-Schwelle, Kommunikationskarte v0.1.
- [[Sessions/2026-04-26 - Synchronisation 1]] — erste Lage-Notiz mit Rollen-Stand, Aktiver Synthese, Offenen Fragen F6-F13, Quality Flags.
- [[LOG]] — append-only Audit-Spur einzelner Aktionen.
- [[Project/JOURNAL]] — chronologisch-reflexives Tagebuch der Methodenentwicklung.

Datenmodell: Markdown mit Frontmatter, Wikilinks vault-intern, Markdown-Pfade cross-vault. Alle Falldaten haben mindestens `type`, `created`, `tags`, `status`. Findings und Falldaten markieren methodische Befunde als belegbare Aussagen mit Quelle und Operationalisierung.

## Was diese Daten *nicht* sind

- **Keine Inhaltsdaten in der Methode.** Die Methode untersucht *wie drei Claude-Instanzen koordinieren*, nicht *was sie inhaltlich erforschen*. Inhalte des Lesevaults sind Kontext, nicht Untersuchungsgegenstand.
- **Keine User-Daten.** Persönliche Daten des Users (Adresse, Telefon, Privat-E-Mails) werden nicht im Schreibvault gespeichert. DSGVO-Hinweise im Lesevault-CLAUDE.md gelten analog.
- **Keine Geldbeträge.** Auch hier analog Lesevault-Konvention.
- **Keine Lesevault-Reflux-Daten.** Falldaten und Findings beschreiben den Schreibvault-Betrieb, nicht den Lesevault-Inhalt.

## Datenpipeline (informell)

User-Aufträge und User-Korrekturen → Konversation einer Instanz → Edit am Schreibvault → V6-Detektion gegenüber parallelen Edits → bei Konflikt: Re-Read und ggf. COORDINATION-Hinweis → bei methodischer Relevanz: BACKLOG-Vorschlag oder Falldaten-Eintrag → Diskussion über Stellungnahmen → Konsens → METHOD-Ratifikation → Snapshot/Lage-Notiz als Synthese → Folge-Iteration.

Validation-Loop (V17, in Ratifikation): pro Lage-Notiz Quality Flags gegen die drei MISSION-Erfolgskriterien mit Operationalisierung, Status, Beleg, Course-Correction.

## Anschluss

- [[Project/INDEX]] — Knowledge-Hub mit Promptotyping-Taxonomie.
- [[Project/REQUIREMENTS]] — User Stories aus MISSION abgeleitet.
- [[Project/DESIGN]] — Designrationale.
- [[MISSION]] — Forschungsfrage, Scope, Erfolgskriterien.
- [[METHOD]] — Vault-Topologie.
- [[Wissensbasis Lesevault]] — Schnellreferenz auf den Quell-Vault.
- [[Cross-Vault-Methodik]] — Cross-Vault-Asymmetrie und Reflux-Verbote.
