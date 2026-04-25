---
type: finding
created: 2026-04-25
updated: 2026-04-26
version: 0.3
author: Claude #3 (Inhalt)
status: draft
tags: [falldaten, bootstrap, rollenwechsel, konflikterkennung]
---

# Falldaten 2026-04-25 — Bootstrap und Rollenwechsel

Erster Tag der Multi-Claude-Vault-Kollaboration. Drei Instanzen plus User. Lesevault [c:/Users/Chrisi/Documents/obsidian](c:/Users/Chrisi/Documents/obsidian) als Wissensquelle, Schreibvault zum Zeitpunkt der Beobachtung als `agents-working-vault` (am 2026-04-26 nach `multi-claude-vault` umbenannt und in [chpollin/multi-claude-vault](https://github.com/chpollin/multi-claude-vault) migriert). Dieses Dokument hält die Beobachtungen fest, bevor sie verblassen.

Klassen-Zuordnung nach [[METHOD#Schicht 4 — Forschungsmaterial]]: dies ist faktisch ein Finding. Bei V7-Ratifizierung Migration zu `Findings/2026-04-25 - Bootstrap und Rollenwechsel.md` vorgesehen.

## Phasen

### Phase 1 — Setup im Lesevault

Anlage von CLAUDE-COORDINATION.md im Lesevault als Scratchpad für parallele Claudes. Iterative Erweiterung in mehreren Schritten: Konvention → Aktive Sessions → Mission/Arbeitsweise → Methodenvorschläge → Ratifizierte Methode. Erweiterung der CLAUDE.md (Lesevault) um die Sektion "Parallele Claude-Instanzen". Erweiterung der VAULT-OPERATIONS.md (Lesevault) um die Sektion "Parallele Claude-Instanzen" mit Rollen-Subsektion und Vault-Architekt-Definition.

Beobachtung: parallel zu meiner Architekt-Arbeit hat eine andere Instanz die VAULT-OPERATIONS.md grundlegend refactored — Forschungsprogramm-Narrativ ausgelagert, Aufgabentypen umstrukturiert, Glossar geschärft. Wenig später hat dieselbe oder eine andere Instanz die Rollendefinition für Operativer Koordinator beigetragen. Die Race Condition wurde durch das Tooling sichtbar gemacht ("modified since read"), nicht durch eine vorab abgestimmte Konvention.

### Phase 2 — Bootstrap im Schreibvault

Anlage von sechs Skelettdokumenten: [[CLAUDE]], [[MISSION]], [[METHOD]], [[COORDINATION]], [[LOG]], [[BACKLOG]]. Initialer Backlog mit V1–V6 aus dem Lesevault-Prototyp. Provisorische Konventionen in CLAUDE.md (Identität, Dokumentstruktur, Rituale, Quellenbezug zum Lesevault).

Race Condition: parallel zu meinem Bootstrap hat Claude #1 zwei eigene Dokumente angelegt — [[Claude-1]] (Wissensbasis und Sync-Stack v0.1) und Koordination.md (alternative Bulletin-Board-Konvention, deutsch, Format `Claude #N — Rolle` mit `Last seen / Will touch`-Feldern). Ergebnis: zwei parallele Koordinationsdokumente mit divergierenden Konventionen.

| Achse | COORDINATION.md (mein Bootstrap) | Koordination.md (Claude #1) |
|---|---|---|
| Sprache | Englisch (Großschreibung) | Deutsch |
| Identifikator | Rolle | `Claude #N — Rolle` |
| Session-Felder | `Working on / Files locked / Notes` | `Last seen / Working on / Will touch / Notes` |
| Sektionen | `Aktive Sessions / Übergaben / Hinweise` | `Aktive Instanzen / Beobachtungen / Hinweise` |

Methodisch interessant: beide Bootstraps waren je für sich konsistent und an unterschiedliche Vorbilder angelegt (mein Bootstrap an die Lesevault-Konvention, Claude #1 an eine eigene Bulletin-Board-Logik). Es gab keinen Konvention-Konflikt, sondern eine Konvention-Verdoppelung. Konsolidiert per V8 (Strukturarbeiter) am 2026-04-25 abends.

### Phase 3 — Konflikterkennung

Mehrfach im Tagesverlauf: "modified since read"-Fehler beim Edit-Versuch. Das Tooling verweigert den Schreibzugriff, wenn die Datei seit dem letzten eigenen Read durch andere Aktivität verändert wurde. Re-Read und neuer Edit-Versuch lösen das auf.

Beobachtung: V6 (Pre-Edit-Read-Disziplin) wird durch das Tooling reaktiv erzwungen. Die Konvention ist also tatsächlich wirksam, aber sie wirkt erst im Schadensfall. Sie verhindert nicht, dass zwei Instanzen *gleichzeitig* an derselben Datei arbeiten — sie verhindert nur, dass sie sich gegenseitig überschreiben. Insgesamt heute mindestens zehn validierte Race Conditions über alle drei Instanzen.

### Phase 4 — Mid-Stream-Rollenwechsel

User-Anweisung im laufenden Betrieb: Rollen werden neu zugeschnitten — Claude #1 = Koordination, Claude #2 = Struktur (Architekt), Claude #3 (mich) = Inhalt. Vorher: Claude #3 war Vault-Architekt, Claude #1 hatte sich als "inhaltliche Kuration / Wissensbringer" selbst eingeordnet.

Identitätsupdate musste in mehreren Dokumenten gleichzeitig nachgezogen werden: CLAUDE-COORDINATION (Lesevault), [[COORDINATION]] (Schreibvault), Koordination.md (Slot bei Claude #1), [[LOG]] (Schreibvault). Aufwand merklich, fehleranfällig.

Beobachtung: die bisherige Sessionende-Konvention ("Eintrag entfernen oder mit `[abgeschlossen]` markieren") deckt Mid-Stream-Rollenwechsel nicht ab. Die Konvention muss erweitert werden um den Fall "Rolle wechselt, Session läuft weiter". Adressiert in V10 (Reassignment-Refactor-Trigger) im BACKLOG.

## Methodische Auffälligkeiten

1. **Race Conditions sind kontinuierlich, nicht punktuell.** Annahme war: jede Instanz arbeitet sequenziell, V6 schützt vor Konflikten. Realität: parallele Arbeit ist die Norm, V6 wirkt nur lokal pro Edit, nicht über die Session hinweg. Fehlende Schicht: proaktive "wer arbeitet jetzt woran"-Sichtbarkeit. Adressiert in V13 (Files locked als opt-in) und V14 (Edit-Granularität).

2. **Architekt-Bias bei Konfliktauflösung.** In meiner früheren Architekt-Rolle war meine erste Reaktion auf den COORDINATION/Koordination-Konflikt ein Vorschlag, der die eigene Struktur erhält ("Variante 1: Merge unter meiner Struktur"). Das war keine objektive Bewertung, sondern Bias zugunsten der eigenen Vorarbeit. User-Eskalation hat das aufgefangen — Methode muss diese Bias-Falle ausdrücklich benennen.

3. **Bootstrap-Konvention reicht nicht für Race Conditions.** Beide Bootstraps waren sinnvoll, aber gleichzeitig produzierten sie inkompatible Container. Methodische Lücke: keine "wer fängt an"-Regel, kein "warte auf Architekt"-Signal vor dem ersten Strukturentscheid. Adressiert in V12 (Anti-Doppelungs-Konvention beim Sessionstart).

4. **Rollennamen sind nicht stabil.** Drei Iterationen am ersten Tag: emergente Selbstbenennung (Vault-Architekt, inhaltliche Kuration / Wissensbringer) → VAULT-OPERATIONS-Rollen aus Lesevault (Vault-Architekt, Operativer Koordinator, Rolle 3 offen) → User-Reassignment (Koordination, Struktur, Inhalt). Methode muss Rollenwechsel als Phänomen einplanen, nicht als Ausnahme.

5. **"Modified since read" ist Validierung von V6 — und gleichzeitig dessen Grenze.** Der Mechanismus funktioniert reaktiv. Was er nicht leistet: Vorwarnung, dass eine andere Instanz dieselbe Datei *gerade jetzt* öffnet. Vorschlag: Pre-Read-Pflicht nicht nur vor Edit, sondern bei jedem größeren Schritt; Soft Locks via `Files locked`-Feld in [[COORDINATION]].

6. **Identitätsupdates skalieren schlecht.** Mid-Stream-Rollenwechsel erforderte Edits in vier Dokumenten plus LOG-Eintrag. Bei drei Claudes mal N Identitätsangaben pro Dokument wird das fragil. Vorschlag: zentraler Identitätsblock pro Claude (in Claude-N.md), andere Dokumente referenzieren dorthin. Eingebracht als Erweiterung von V9 in [[BACKLOG]].

7. **Auto-Mode und User-Entscheidungen brauchen explizite Trennung.** Auto-Mode sagt "execute autonomously". User-Feedback heute: "bei wichtigen Entscheidungen Rückfrage statt Eigeninitiative". Methode muss die Entscheidungstypen klar benennen — was autonom, was an User. Pattern in [[prompt-engineering-patterns#Anfrage an User bei wichtigen Entscheidungen]] verankert.

## Lessons learned (vorläufig)

- Race-Condition-Erkennung als zweite Schicht zu V6 (Pre-Edit-Read).
- "Wer fängt an"-Konvention als Bootstrap-Schutz.
- Rollenwechsel als methodisches Phänomen explizit machen.
- Identitätsblock-Zentralisierung.
- Bias-Falle bei Konfliktauflösung benennen (besonders für Architekt-Rolle).
- Klare Liste autonom-zu-entscheidender vs. User-zu-entscheidender Fragen.

## Anschluss

- [[Sync-Stack-Patterns]] — Race Conditions und Pre-Read-Disziplin in Schicht 2 und 3.
- [[Prompt-Engineering-Patterns]] — Sessionstart, Rollenwechsel, Konflikt-Eskalation, Anfrage an User.
- [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] — Strukturarbeiter-Sicht auf dieselben Befunde, ergänzt diese Datei.
- [[BACKLOG]] — V8 (umgesetzt), V9, V10, V12, V13, V14 sind Adressen für die hier benannten Lücken.
- [[Beobachtung Claude-1]] — Koordinator-Sicht mit Snapshot-Konvention und Kommunikationskarte v0.1.

## Offene Fragen

- Soll diese Datei als Finding migriert werden (siehe F12 zur Datei-Naming-Konvention) oder als Falldaten-Genre eigenständig bleiben?
- Wo liegt die Grenze zwischen Falldaten (eigene Beobachtung) und Finding (strukturierter Befund mit Adresse-Vorschlägen)? Aktuell überlappt diese Datei mit [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]] — Konsolidierung sinnvoll?
- Wie häufig sollen Falldaten/Findings entstehen — pro Tag, pro Schlüsselereignis, pro Methodenfrage?
