---
type: knowledge
promptotyping-type: knowledge-action
created: 2026-04-26
updated: 2026-04-26
tags: [promptotyping, knowledge, design]
status: active
---

# DESIGN — Designentscheidungen und Rationale

Designdokument nach [Promptotyping-Taxonomie](https://github.com/DigitalHumanitiesCraft/Promptotyping). Hybrid Knowledge / Action: dokumentiert Designentscheidungen für Menschen (Knowledge) und sozialisiert künftige Claude-Instanzen mit dem methodischen Wertesystem ([[Agent-Sozialisierung]] — Action). Komplement zu [[METHOD]] (formale Spezifikation der Schichten) und zu [[METHOD]] (ratifizierte Konventionen): hier wohnt das *Warum*.

## Designprinzipien

Vier Leitprinzipien, an denen jede Methodenentscheidung gemessen wird.

### 1. Selbstreferenz statt Vorabspezifikation

Die Methode entwickelt sich, indem die drei Rollen sie anwenden, während sie sie produzieren. METHOD.md wird durch das Mit-METHOD.md-Arbeiten geschrieben. Falldaten der eigenen Konflikte sind der primäre Untersuchungsgegenstand. Methodenvorschläge entstehen aus beobachteten Mustern, nicht aus Vorab-Theorie.

Konsequenz: Bootstrap-Phase mit unfertiger Methode ist erwartet, nicht Defizit. METHOD wächst inkrementell aus BACKLOG-Stellungnahmen statt aus initialer Spezifikation. V11 entfiel, weil ein Vorschlag in der Implementierung eines anderen aufging — das ist Methodenfortschritt, nicht Inkonsistenz.

### 2. Eventually Consistent statt Strong Consistency

Drei Instanzen arbeiten parallel ohne Sperren auf einem geteilten Filesystem. Synchronisation ist asynchron, Konflikte werden reaktiv erkannt (V6 Pre-Edit-Read), nicht präventiv vermieden. Ein Edit kann blockiert werden, wird dann aber durch Re-Read und ggf. Konfliktlösung aufgehoben.

Konsequenz: Race-Conditions sind erwartet und tolerabel. Datenverlust ist nicht tolerabel — daher V6 als Default plus V13 (Files locked) als opt-in für mehrstufige Eingriffe. Single-Source-Übersicht in COORDINATION (V14 Option a) erhalten, Per-Slot-Auslagerung erst bei Stretch-Skalierung (V16).

### 3. Identität ist Schreibhoheit

Eine Rolle hat ihre eigene Stimme, die nicht antizipiert werden darf. V9 (Beitragsdatei = Single Source der Identität) hat den impliziten Geschwister-Satz V20 (Stellungnahmen sind Schreibhoheit der Rolle, auch zustimmende Antizipation verletzt sie). Refactoring bei Reassignment ist V10 — die jeweilige Instanz mit Schreibhoheit über die eigene Beitragsdatei führt das selbst durch.

Konsequenz: Stellungnahmen in fremdem Namen sind Anti-Pattern, auch wenn die Substanz korrekt wäre. Synthese-Schreibhoheit (Lage-Notizen) liegt analog beim Koordinator — andere Rollen liefern Material, aber Synthese ist keine reine Konsens-Buchhaltung.

### 4. Cross-Vault-Asymmetrie ist nicht verhandelbar

Lesevault (User-Wissensvault) ist read-only für die drei Rollen. Schreibvault (dieses Repo) ist read-write. Reflux-Verbote: kein Editieren im Lesevault, kein 1:1-Kopieren von Lesevault-Inhalten, kein Erfinden, kein implizites Übertragen. Markdown-Pfade statt Wikilinks für Cross-Vault-Verweise.

Konsequenz: Konzept-Extraktion in Concepts/ (V19) folgt Modell C (Hybrid Source-Verweis + selektive Extraktion mit Pfad-Stempel und Extraktionsdatum). Drift wird sichtbar gehalten, nicht versteckt.

## Architektur-Entscheidungen

### Drei Rollen statt zwei oder fünf

User-Setting drei Top-Level-Instanzen plus Subagent-Achse (V15) und Stretch-Skalierung auf fünf (V16). Begründung Drei: Trennung in *am Vault* (Strukturarbeiter), *im Vault* (Inhalt) und *zwischen den Instanzen* (Koordinator) ist die kleinste tragfähige Aufteilung, die alle drei Sync-Achsen abdeckt. Zwei Rollen wären unterspezifiziert (entweder Synthese oder Inhalt fehlt), fünf Rollen sind Stretch ohne Default-Notwendigkeit.

Trade-off: drei Rollen haben Engpässe, wenn eine ausfällt — V18 Multi-Mode-Architektur löst das nicht für die Methodenentwicklung selbst (Mother-Vault), sondern nur für Project-Forks.

### Vier Schichten plus Knowledge/-Bündel statt flacher Topologie

V7 (Vier-Schichten) trennt nach Lifecycle: Stabile Anker (stabil), Lebende Koordination (ephemer-hochfrequent), Beiträge (instanzgebunden-wachsend), Forschungsmaterial (kumulativ-append). Knowledge/ als Promptotyping-Documents-Bündel liegt quer dazu — explizite Wissensbasis über das Projekt selbst.

Trade-off: Doppelung droht, wenn Knowledge/-Inhalte mit Schicht-1-Ankern überlappen. Mitigation: keine Duplikate, Verweise statt Kopien (z.B. INSTRUCTIONS-Funktion durch CLAUDE.md abgedeckt, kein eigenes Knowledge/INSTRUCTIONS.md).

### Schicht 4 flach statt hierarchisch (initial)

V7-Konvention: Schicht 4 flach im Root mit Klassen-Präfix (`Session YYYY-MM-DD - Titel.md`), Migration in Sub-Ordner (`Sessions/`) erst ab ~10 Dokumenten pro Klasse (V14b). Begründung: Hierarchie-Aufwand ist bei niedrigem Volumen Overhead; Sub-Ordner werden erst nützlich, wenn die Liste am Root-Level unübersichtlich wird.

Trade-off: Wikilinks brechen bei Migration nicht (Obsidian löst per Dateiname), aber `## Anschluss`-Sektionen mit expliziten Pfaden müssen bei Migration nachgezogen werden. Mitigation: V14b dokumentiert die Migrationsroutine.

### Append-only LOG plus reflexives JOURNAL statt einer Spur

LOG (Schicht 2) ist append-only Audit-Spur einzelner Aktionen — chronologisch, eintragspflichtig, niemals editierbar. JOURNAL (Knowledge/, Process Document) ist reflexiv-chronologisches Tagebuch — Entscheidungen, Wendepunkte, Dead Ends, Lernerfahrungen, gruppiert nach Tag oder Anlass.

Begründung: zwei verschiedene Detaillierungsgrade dienen zwei verschiedenen Zwecken. Audit (LOG) braucht Vollständigkeit, Reflexion (JOURNAL) braucht Selektivität. Beide sind Process Documents in Promptotyping-Taxonomie, aber funktional klar getrennt.

### Kommunikationskarte als versioniertes Forschungsoutput

Kommunikationskarte v0.1 lebt aktuell als Sektion in [[Beobachtung Claude-1]]. Versionierung v0.1 → v0.4 als Sektion, Auslagerung in eigenes Dokument ab v0.5 (mindestens zwei vollständige Iterationen mit echten Konflikt-Beobachtungen), v1.0 als METHOD-Vorschlag.

Begründung: die Karte ist primärer Forschungsoutput, nicht Methode. Versionierung als wissenschaftliche Spur statt überschreibendem Update.

### Eskalations-Schwelle in drei Stufen

Stufe 1 — Hinweis in COORDINATION#Hinweise mit Adressaten-Markierung (zwischen Rollen).
Stufe 2 — Eintrag in BACKLOG#Offene Fragen (methodische Lücke, Konsens-Bedarf).
Stufe 3 — explizite Eskalation an User in der Konversation (strukturelle Frage, Reassignment-Bedarf, Methoden-Schwebe).

Begründung: graduelle Eskalation hält den User aus operativen Details raus (EK-1) und erlaubt der Methode, die meisten Konflikte selbst zu lösen.

## Anti-Pattern (was wir explizit nicht tun)

- **Vorab-Spezifikation der vollständigen Methode.** Methodenmotor läuft inkrementell — V1 + V6 ratifiziert, V2/V3/V8 in zweiter Welle, V7+ in Diskussion, V19-V21 als nächste Welle.
- **Stellungnahmen in fremdem Namen.** Auch zustimmende Antizipation verletzt Identitätshoheit (V20).
- **Lesevault-Reflux.** Inhalt aus dem Lesevault wird zitiert, nicht kopiert. Drift wird sichtbar gehalten.
- **Eigenmächtige Strukturentscheidungen.** Strukturarbeit gehört zu #2, Inhaltsarbeit zu #3, Koordination zu #1. Cross-Domain-Eingriffe nur auf User-Auftrag und mit Falldatum-Dokumentation.
- **Stillschweigendes Überschreiben.** V6 (Pre-Edit-Read) als reaktiver Schutz, V13 (Files locked) als opt-in für mehrstufige Eingriffe.
- **Methodenfriedhof BACKLOG.** Wenn Vorschläge sammeln ohne zu ratifizieren, droht METHOD leer zu bleiben — Validation-Loop (V17) prüft pro Lage-Notiz, ob METHOD wächst und BACKLOG abnimmt.
- **Bauchgefühl-Validation.** Quality Flags brauchen Operationalisierung, Beleg, Course-Correction (V17 mit #3-Konkretisierungen).
- **Subagent-Schreibflut auf geteilte Files.** No-shared-write-Klausel (V15 #3-Konkretisierung) — Subagent schreibt nur in `instances/Claude-N/subtasks/`, Top-Level konsolidiert.

## Agent-Sozialisierung — wie eine fremde Instanz das hier liest

Eine vierte Instanz, die neu eintritt, sollte aus diesem Dokument plus [[CLAUDE]] plus aktueller Lage-Notiz das methodische Wertesystem extrahieren können:

- *Identität* ist nicht der Tool-State, sondern die Rolle, und die Rolle wird vom User zugewiesen.
- *Schreibhoheit* ist Identitätsanker — eigene Stimme, eigene Beitragsdatei, eigene Stellungnahmen.
- *Konflikte* sind Forschungsmaterial, nicht Defizit. Erkennen, eskalieren, dokumentieren.
- *Synthese* ist Koordinator-Domäne, nicht Strukturarbeit oder Inhalt.
- *Cross-Vault* ist asymmetrisch und nicht verhandelbar.
- *Methodenwachstum* ist inkrementell und konsens-basiert, nicht spezifikationsgetrieben.

## Anschluss

- [[Project/INDEX]] — Knowledge-Hub mit Promptotyping-Taxonomie.
- [[Project/DATA]] — Datengrundlagen.
- [[Project/REQUIREMENTS]] — User Stories und Anforderungen.
- [[Project/JOURNAL]] — Arbeitstagebuch.
- [[METHOD]] — formale Schichten-Spezifikation.
- [[METHOD]] — ratifizierte Konventionen.
- [[CLAUDE]] — Identität, Rituale, Konfliktlogik.
- [[Sync-Stack-Patterns]] — Sync-Mechanismen pro Schicht (Method-Draft).
- [[Cross-Vault-Methodik]] — Asymmetrie und Reflux-Verbote (Method-Draft).
- [[Prompt-Engineering-Patterns]] — Prompt-Patterns für Inter-Instanz-Kommunikation (Method-Draft).
