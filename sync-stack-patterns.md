---
type: methode-pattern
created: 2026-04-25
updated: 2026-04-25
version: 0.2
author: Claude #3 (Inhalt)
status: draft
basiert-auf: Claude-1 (Sync-Stack v0.1)
tags: [sync, patterns, methode]
---

# Sync-Stack Patterns

Ausarbeitung der sieben Sync-Schichten aus [[Claude-1]] (Sync-Stack v0.1) zu konkreten Patterns. Pro Schicht: was wird getauscht, in welcher Form, mit welchem Auslöser, mit welchen Antipatterns, welche Voraussetzungen. Eventually consistent über geteilte Dateien — kein Echtzeit-Channel.

Klassenzuordnung nach [[STRUCTURE]]: Methoden-Draft ohne eigene V7-Klasse. Lebt provisorisch im Root, bei Ratifizierung Migration nach [[METHOD]] oder als eigene Methode-Sektion (siehe V7-Stellungnahme im [[BACKLOG]]).

## Schicht 1 — Scope-Sync (Rollen)

**Was wird getauscht:** Wer ist welche Rolle, mit welcher Verantwortlichkeit. Aktive Identitäten der Instanzen.

**Form:** Stabile Rollendefinitionen in [[METHOD]] (oder [[CLAUDE]] bei provisorischen). Aktive Rolle pro Session in [[COORDINATION]] unter `## Aktive Sessions`. Cross-Reference per Rollenname.

**Auslöser:** Sessionstart (jede Instanz trägt sich ein). Rollenwechsel (User-Reassignment). Neue Rolle (Konsens nötig).

**Antipatterns:**
- Rolle aus Sessionnummer ableiten (instabil über Sessions hinweg).
- Mehrere Instanzen beanspruchen dieselbe Rolle ohne Suffix-Differenzierung.
- Rolle wird im Sessionseintrag selbst neu definiert statt referenziert.

**Voraussetzungen:** Stabile Rollenliste in METHOD oder CLAUDE. User vergibt Rollen explizit, oder Konvention ist hinreichend selbsterklärend.

## Schicht 2 — State-Sync (Bulletin Board)

**Was wird getauscht:** Wer arbeitet gerade woran, welche Dateien werden angefasst, auf welchem Stand wurde begonnen.

**Form:** Eintrag pro aktiver Instanz in [[COORDINATION]]. Pflichtfelder: `last-touch` (Datum), `Last seen`, `Working on`, `Will touch` oder `Files locked`, `Notes`. Konvention seit V8-Implementierung (2026-04-25).

**Auslöser:** Sessionstart (Eintrag setzen). Substanzielle Aktivitätsänderung (Eintrag aktualisieren). Sessionende (Eintrag entfernen oder `[abgeschlossen]` markieren).

**Antipatterns:**
- Eintrag bleibt nach Sessionende stehen (Stale-Session — andere wissen nicht, ob die Instanz noch aktiv ist).
- `Files locked` zu großzügig (blockiert andere unnötig).
- `Notes` enthält Methodensubstanz statt aktuellem Status (gehört in METHOD oder BACKLOG, nicht in den Sessionseintrag).

**Voraussetzungen:** COORDINATION ist *die* eine kanonische Datei (kein paralleles Koordinationsdokument — siehe [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] zur Race Condition).

## Schicht 3 — Edit-Sync (Pre-flight Read)

**Was wird getauscht:** Implizit — der aktuelle Dateistand. Konflikterkennung läuft über das Tooling ("modified since read").

**Form:** Konvention. Vor jedem Edit eines geteilten Dokuments: re-read, wenn letzter Read mehr als ~10 min her ist. Bei "modified since read"-Fehler: re-read, *nicht* überschreiben, prüfen ob die fremde Änderung den eigenen Edit obsolet macht.

**Auslöser:** Vor jedem Schreibzugriff auf geteilte Dokumente.

**Antipatterns:**
- Stur erneuter Edit nach "modified since read" mit identischem Inhalt — überschreibt fremde Änderung blind.
- Re-Read nur des relevanten Abschnitts — verpasst strukturelle Änderungen am Rest.
- Konvention nur für CLAUDE.md anwenden, nicht für andere Steuerungsdokumente.

**Voraussetzungen:** Tooling unterstützt "modified since read"-Detection (in dieser Umgebung gegeben).

**Falldaten-Bezug:** mehrfach validiert in [[falldaten/2026-04-25-bootstrap-und-rollenwechsel#Phase 3 — Konflikterkennung]]. Der Mechanismus funktioniert reaktiv. Was er nicht leistet: Vorwarnung, dass eine andere Instanz dieselbe Datei *gerade jetzt* öffnet. Schicht 2 (Bulletin Board mit `Files locked` als opt-in, V13 in [[BACKLOG]]) muss diese Lücke schließen.

## Schicht 4 — Synthese-Sync (Lage-Notizen)

**Was wird getauscht:** Periodische Zusammenfassung des kollektiven Standes — was alle drei Instanzen wissen, was Konsens, was offen, was Quality-Flag. Damit nach Pausen alle wieder auf gemeinsamem Stand sind.

**Form:** Lage-Notiz analog zu den Forschungsleitstelle-Sessions im Lesevault ([Projects/Forschungsleitstelle/Sessions/](c:/Users/Chrisi/Documents/obsidian/Projects/Forschungsleitstelle/)). Sektionen: Lane States (was tut jede Rolle), Active Synthesis (was ist konsolidiert), Open Questions (was ist offen mit Rollen-Zuordnung), Quality Flags (Risiken, Konflikte). Ablage in `Sessions/`, Dateiname `YYYY-MM-DD - Kurztitel.md`.

**Auslöser:** Nach längerem Aktivitätsblock. Bei methodischer Wendung (Rollenwechsel, neue Konvention). Vor User-Pause.

**Antipatterns:**
- Lage-Notiz schreibt nur eine Instanz allein (verzerrte Sicht).
- Lage-Notiz wird editiert statt neu angelegt (verliert Audit-Spur).
- Lage-Notiz verlangt Konsens vor Veröffentlichung (entstehen nie).

**Voraussetzungen:** Eine Instanz übernimmt Synthese-Verantwortung pro Notiz, typisch Koordination ([[Claude-1]]). Andere reagieren durch Folge-Notizen, nicht Edits.

**Anschluss Forschungsleitstelle:** Format und Konvention 1:1 von der Sessions-Konvention im Lesevault übernommen, dort als `forschungsleitstelle-session` typisiert. Validierungspotenzial für die Spec v0.5.

**Erste Lage-Notiz:** [[Session 2026-04-26 - Synchronisation 1]] — Synthese-Sync funktioniert.

## Schicht 5 — Beobachtungs-Sync (Loop)

**Was wird getauscht:** Beobachtungen zweiter Ordnung — Drift, Konventionslücken, neue Muster, Antipatterns, die jenseits des aktuellen Aufgaben-Standes auffallen.

**Form:** Eintrag in [[COORDINATION]] unter `## Beobachtungen` (oder `## Hinweise` bei Dringlichkeit). Format: `- YYYY-MM-DD <Rolle>: <Beobachtung>`. Bei substantiellen Beobachtungen: Migration in `Findings/` oder `falldaten/`-Dokument.

**Auslöser:** Wenn eine Instanz auffallendes Verhalten bemerkt — eigenes oder fremdes. Wenn Konvention nicht greift. Wenn etwas Unerwartetes passiert.

**Antipatterns:**
- Beobachtungen nur in `Notes` der eigenen Session (verschwinden mit Sessionende).
- Beobachtungen direkt in METHOD eintragen (stören die Ratifizierung).
- Beobachtungen ohne Datum/Rolle (nicht nachvollziehbar).

**Voraussetzungen:** Klare Trennung zwischen `Notes` (eigene Session) und `Beobachtungen` (für andere relevant). V5 bestätigt diese Trennung.

## Schicht 6 — Konversations-Sync (User als Bus)

**Was wird getauscht:** Semantische Information, die der User zwischen den drei Konversationen trägt. User wechselt Konversation und überträgt Stand.

**Form:** Userinstruktionen, die alle drei betreffen, knapp in [[COORDINATION]] unter `## Hinweise` mit Datum und Markierung "alle". Vermeidet, dass der User dieselbe Information dreifach eintippen muss.

**Auslöser:** User trifft eine Entscheidung, die alle Instanzen betrifft (z.B. Rollen-Reassignment). User signalisiert eine Phasenänderung. User vergibt einen gemeinsamen Auftrag.

**Antipatterns:**
- Instanz vergisst, eine User-Instruktion in COORDINATION zu übertragen — andere arbeiten mit veraltetem Stand.
- Ergänzungen ohne klare Markierung "alle" vs. "nur an mich".
- Semantik wird im Prozess der Übertragung verfälscht (Telefon-Spiel).

**Voraussetzungen:** Vertrauen, dass der User-Bus nicht der einzige Sync-Pfad ist (sonst zu viel Last auf User).

**Falldaten-Bezug:** das Rollen-Reassignment des Users wurde in COORDINATION und Koordination.md weitergegeben, andere Instanzen haben es danach gelesen — funktioniert. Siehe [[falldaten/2026-04-25-bootstrap-und-rollenwechsel#Phase 4 — Mid-Stream-Rollenwechsel]].

## Schicht 7 — Cross-Vault-Sync (Asymmetrie)

**Was wird getauscht:** Wissen aus dem Lesevault als Zitat oder Referenz, *nicht* als Synchronisation.

**Form:** Markdown-Links mit absolutem oder relativem Pfad zum Lesevault-Dokument. Niemals Wikilink (greift nur intra-vault). Niemals Re-Implementierung von Lesevault-Inhalt im Schreibvault — Referenz statt Kopie.

**Auslöser:** Wenn eine Methode-Aussage Lesevault-Inhalt benötigt (z.B. Forschungsleitstelle-Spec, Promptotyping-Definition).

**Antipatterns:**
- Lesevault editieren — verletzt read-only-Disziplin.
- Lesevault-Inhalt im Schreibvault duplizieren — Drift garantiert.
- Wikilink statt Markdown-Link cross-vault — broken link.
- Schreibvault-Inhalt als Quelle für Lesevault-Edits — Untersuchungsobjekt umschreiben.

**Voraussetzungen:** Asymmetrie ist konstitutiv: Lesevault read-only, Schreibvault read-write. Klar in [[CLAUDE]] verankert. Detail in [[cross-vault-methodik]].

## Querbeziehungen zwischen den Schichten

- **State-Sync (2) braucht Scope-Sync (1):** ohne klare Rollen sind Sessions-Einträge mehrdeutig.
- **Edit-Sync (3) schützt State-Sync (2):** ohne Pre-Read würde COORDINATION selbst zur Konfliktquelle.
- **Synthese-Sync (4) verdichtet State + Beobachtungs-Sync (2 + 5):** Lage-Notizen zitieren Bulletin und Beobachtungen.
- **Konversations-Sync (6) ist Eskalationskanal für alle Schichten:** wenn niedrigere Schichten brechen, geht's über User.
- **Cross-Vault-Sync (7) ist orthogonal:** betrifft nicht die Inter-Instanz-Kommunikation, sondern die Vault-Topologie.

## Anschluss

- [[Claude-1]] — Sync-Stack v0.1 als Skizze, Quelle dieser Ausarbeitung.
- [[falldaten/2026-04-25-bootstrap-und-rollenwechsel]] — Falldaten-Quelle für Schicht 2, 3, 6.
- [[Finding 2026-04-25 - Race Conditions und Strukturkonflikte]] — Strukturarbeiter-Sicht auf Race Conditions.
- [[Session 2026-04-26 - Synchronisation 1]] — erste Lage-Notiz, Schicht-4-Validierung.
- [[Beobachtung Claude-1]] — Snapshot-Konvention und Kommunikationskarte v0.1.
- [[cross-vault-methodik]] — Schicht 7 detailliert.
- [[prompt-engineering-patterns]] — Patterns, die auf diesen Sync-Schichten operieren.
- [[BACKLOG]] — V13 (Files locked opt-in) und V14 (Edit-Granularität) als Adressen für Schicht-2-/Schicht-3-Lücken.

## Offene Fragen

- Synthese-Sync: wer schreibt Lage-Notizen — Konvention (immer Koordination) oder rotierend?
- State-Sync: sollten `Files locked` und `Will touch` zwei verschiedene Felder sein, oder reicht eines?
- Beobachtungs-Sync: bei welcher Frequenz und in welcher Tiefe — wann ist es zu viel?
- Konversations-Sync: wie verhindern wir, dass User-Instruktionen verloren gehen, wenn sie nur an eine Instanz adressiert werden?
- Edit-Sync: braucht es eine zweite Schicht (Soft Locks proaktiv via `Files locked`), oder reicht "modified since read" reaktiv? Aktuelle Position #1: reicht. Position #2/#3: opt-in für mehrstufige Eingriffe.
