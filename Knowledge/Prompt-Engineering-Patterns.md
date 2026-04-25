---
type: methode-pattern
created: 2026-04-25
updated: 2026-04-25
version: 0.2
author: Claude #3 (Inhalt)
status: draft
tags: [prompt-engineering, patterns, methode]
---

# Prompt-Engineering-Patterns

Konkrete Formulierungs-Patterns für die wiederkehrenden Kommunikationssituationen im Multi-Claude-Setup. Plus Antipatterns aus der Beobachtung des heutigen Tages (siehe [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]]).

Klassenzuordnung nach [[METHOD]]: Methoden-Draft ohne eigene V7-Klasse. Lebt provisorisch im Root, bei Ratifizierung Migration nach [[METHOD]] (siehe V7-Stellungnahme im [[BACKLOG]]).

## Sessionstart

**Pattern:** User adressiert die jeweilige Instanz mit Rollenzuweisung und Auftragskontext.

```
"Du bist Claude #N, Rolle X. [Kurzer Kontext: was ist seit deiner letzten Session passiert.] [Konkreter Auftrag.]"
```

**Beispiel (heute beobachtet, 2026-04-25):** *"du bist Claude Nummer 3. Es gibt zwei andere Claude, die gerade im Obsidian Vault arbeiten. Schau dir mal die grobe Oberfläche von dem Obsidian Vault an."*

**Antipatterns:**
- Rollenzuweisung implizit lassen, sodass die Instanz raten muss.
- Mehrere Aufträge in einem Satz mischen (Erkundung, Aufgabe, Methode).
- Kontext aus der vorherigen Session weglassen, weil "die Instanz weiß ja Bescheid" — sie weiß es nicht, jede Session ist context-frei.

## Übergabe zwischen Instanzen

**Pattern:** Übergebende Instanz markiert in [[COORDINATION]] unter `## Übergaben`, was für wen vorbereitet ist und was als Nächstes zu tun ist.

```
- YYYY-MM-DD <Rolle A> → <Rolle B>: [Datei oder Sache] ist vorbereitet, wartet auf [konkreten Schritt].
```

**Beispiel (Format aus V4-Stellungnahme #1, übernommen #2):** *"Von Strukturarbeiter → Koordinator, 2026-04-25, V8-Implementierung, Zustand bei Übergabe: Konsolidierung umgesetzt, alte Slots in Koordination.md noch nicht gelöscht, erwartete nächste Aktion: finaler Sign-off und Slot-Bereinigung."*

**Antipatterns:**
- Übergabe in `Notes` einer Session-Sektion versteckt — verschwindet mit Sessionende.
- Übergabe ohne konkreten Folgeschritt — Rolle B weiß nicht, was zu tun.
- Übergabe ohne Datum — kein Stale-Marker.

## Methodenvorschlag in BACKLOG

**Pattern:**

```
### V<N> — <Kurztitel>
- **Vorschlag:** <was konkret>
- **Begründung:** <warum>
- **Vorgeschlagen von:** <Rolle>, <Datum>
- **Status:** vorgeschlagen | in Diskussion | ratifiziert | abgelehnt
- **Stellungnahmen:** <chronologisch, signiert>
```

**Beispiel:** V1 in [[BACKLOG]] — "Identifikation per Rolle, nicht Sessionnummer". Vorschlag, Begründung, Status, drei Stellungnahmen aller Rollen.

**Antipatterns:**
- Vorschlag ohne Begründung — lässt sich nicht bewerten.
- Vorschlag im falschen Dokument (METHOD statt BACKLOG) — überspringt Diskussion und Ratifizierung.
- Mehrere Vorschläge in einem Item — lässt sich nicht einzeln ratifizieren.

## Stellungnahme zu einem Vorschlag

**Pattern:** Antwort unter `## Stellungnahmen` des betroffenen Items, signiert.

```
- <Rolle>, <Datum>: +1 / -1 / Modifikation: <was anders, warum>
```

**Beispiel (BACKLOG V6, Stellungnahme #1):** *"2026-04-26, Koordinator (Claude #1): ✓ Zustimmung. Heute unter Realbedingungen viermal validiert (zweimal #1, zweimal #2). Tooling-seitiges Sicherheitsnetz funktioniert. Frage zur `Files locked`-Disziplin: meine Position ist, dass die explizite Lock-Konvention in der aktuellen Konstellation nicht zusätzlich nötig ist."*

**Antipatterns:**
- Stellungnahme als Edit am Vorschlag selbst — verfälscht den ursprünglichen Vorschlag.
- Stellungnahme ohne Begründung bei -1 oder Modifikation.
- Stellungnahme an anderer Stelle (in eigener Session-Notes) — wird übersehen.

## Konflikt-Eskalation

**Pattern:** Hinweis in [[COORDINATION]] unter `## Hinweise`, mit Datum, Rolle, Markierung "alle" oder spezifischer Adressierung, plus konkreter Frage an User.

```
- YYYY-MM-DD <Rolle>, alle: [Konflikt-Beschreibung]. Eskalation an User: [konkrete Frage].
```

**Beispiel (heute beobachtet):** der COORDINATION/Koordination-Konflikt am 2026-04-25. Statt eigenmächtiger Auflösung: drei Optionen mit Begründung an User präsentiert, User entschied. Ergebnis: V8 in BACKLOG, sauber konsolidiert durch #2.

**Antipatterns:**
- Konflikt einseitig auflösen (Überschreiben fremder Arbeit, "Architekt-Bias" — siehe [[falldaten/2026-04-25-bootstrap-und-rollenwechsel#Methodische Auffälligkeiten]] Lesson 2).
- Konflikt mit fachlichen Argumenten in BACKLOG schieben — gehört nicht dahin, BACKLOG ist für Methodenvorschläge, nicht Streitschlichtung.
- Eskalation ohne konkrete Frage — User weiß nicht, was zu entscheiden ist.

## Rollenwechsel

**Pattern:** Bei User-Reassignment alle eigenen Sessionseinträge in allen relevanten Dokumenten aktualisieren, LOG-Eintrag schreiben, alte Architektur- oder Beitragsarbeit als historisches Arbeitsergebnis kennzeichnen (nicht löschen, nicht überschreiben).

```
### <Neue Rolle> (vorher <Alte Rolle>)
- last-touch: <Datum>
- Working on: Rollenwechsel von <alt> zu <neu> ([Auslöser]). [Was bleibt liegen, was geht weiter.]
- Files locked: <neu im Lichte der neuen Rolle>
- Notes: Frühere Arbeit unter <alter Rolle> bleibt als historisches Arbeitsergebnis stehen, Verantwortung wandert an <Empfänger der alten Rolle>.
```

**Beispiel (heute, 2026-04-25 ~18:50):** Claude #3 wechselte von Vault-Architekt zu Inhalt. Identitätsupdate in vier Dokumenten ([CLAUDE-COORDINATION](c:/Users/Chrisi/Documents/obsidian/CLAUDE-COORDINATION.md) im Lesevault, [[COORDINATION]] und Koordination.md im Schreibvault, [[LOG]]) plus LOG-Eintrag. Bootstrap-Arbeit blieb als historisches Arbeitsergebnis stehen, Verantwortung wanderte an Claude #2.

**Antipatterns:**
- Alten Sessionseintrag einfach überschreiben, ohne Übergabe-Markierung.
- Mid-Stream-Rollenwechsel als wäre es ein normales Sessionende behandeln — verschleiert die Übergabe.
- Architektur- oder Bootstrap-Arbeit der alten Rolle nachträglich an die alte Rolle "abgeben" — sie bleibt Arbeitsergebnis der Person, nur die Verantwortung wandert.

**Falldaten-Bezug:** Aufwand merklich, fehleranfällig (vier Dokumente plus LOG). Methode braucht Vereinfachung — siehe [[falldaten/2026-04-25-bootstrap-und-rollenwechsel#Methodische Auffälligkeiten]] Lesson 6 zu Identitätsblock-Zentralisierung, eingebracht als V9-Erweiterung im [[BACKLOG]].

## Pre-Edit-Read

**Pattern:** Vor jedem Edit eines geteilten Dokuments re-read, wenn letzter Read mehr als ~10 min her ist.

**Beispiel (heute mehrfach):** vier "modified since read"-Fehler beim BACKLOG-Edit, alle vom Tooling-Sicherheitsnetz abgefangen. Re-read löste auf, kein blinder Überschreibvorgang.

**Antipatterns:**
- Nach "modified since read"-Fehler stur erneut versuchen mit identischem Edit.
- Re-Read nur des veränderten Bereichs — verpasst strukturelle Änderungen.

## Anfrage an User bei wichtigen Entscheidungen

**Pattern:** Bei wichtigen Entscheidungen (Scope, Reihenfolge, Granularität, Konfliktauflösung, Architektur) nicht eigenmächtig entscheiden, sondern Optionen mit Begründung präsentieren und Rückfrage stellen.

```
"Folgende Entscheidungen sind offen:
1. <Frage 1> — Optionen: A / B / C, mit jeweiliger Begründung.
2. <Frage 2> — ...
Welche willst du jetzt treffen, welche später?"
```

**Beispiel (heute):** vor dem Refactoring meiner Inhaltsdokumente sieben offene Entscheidungen formuliert (Doc-Menge, Reihenfolge, Granularität, Folder, Verhältnis zu #1s Sync-Stack, Reifegrad, Parallel-vs-warten), jeweils mit Optionen und Begründung — User wählte Variante mit Refactoring nach Wait-State.

**Antipatterns:**
- Auto-Mode als Lizenz nehmen, alle Entscheidungen autonom zu treffen — Auto-Mode heißt nur "bei klaren Aufträgen ohne Rückfragen ausführen".
- Optionen ohne Begründung präsentieren — User muss raten, warum welche Option Sinn macht.
- Eine Empfehlung als Beschluss formulieren, statt sie als Empfehlung kennzeichnen.

## Übergreifend: Selbstreferenz und Kontextstabilität

Patterns funktionieren, wenn alle Instanzen sie gleich anwenden. Methode braucht: explizite Beispiele in [[CLAUDE]] (V6 Sample-Eintrag aus dem [[BACKLOG]]) und periodische Re-Validierung über Lage-Notizen (Schicht 4 in [[Sync-Stack-Patterns]]).

## Anschluss

- [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] — Quelle der heutigen Beobachtungen.
- [[Sync-Stack-Patterns]] — Sync-Schichten, auf denen diese Patterns operieren.
- [[Beobachtung Claude-1]] — Eskalations-Schwelle in drei Stufen, ergänzt das Konflikt-Eskalation-Pattern.
- [[BACKLOG]] — Vorschläge V1–V14 als Anwendungsfälle der Patterns "Methodenvorschlag" und "Stellungnahme".
- [[COORDINATION]] — Beispiel-Container für die meisten Patterns.

## Offene Fragen

- Reichen acht Patterns, oder braucht es weitere (z.B. Lage-Notiz schreiben, Antipattern-Beobachtung melden, Migration ratifizierter Methodenelemente)?
- Wer pflegt diese Pattern-Bibliothek — bleibt sie hier oder wandert in [[METHOD]], sobald ratifiziert?
- Wie validieren wir, dass Patterns wirklich angewendet werden — über Beobachtungs-Sync (Schicht 5 in [[Sync-Stack-Patterns]]) oder explizite Compliance-Checks?
