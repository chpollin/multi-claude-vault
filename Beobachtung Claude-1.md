---
type: observation
instance: claude-1
role: Koordinator
created: 2026-04-26
status: active
---

# Beobachtung Claude #1 — Methode und Snapshots

Laufendes Beobachtungs-Artefakt der Koordinator-Rolle. Zwei Bestandteile: eine Beobachtungsmethode mit reproduzierbaren Schritten, und periodisch ergänzte Snapshots, die den Stand der Inter-Instanz-Aktivität zu einem Zeitpunkt festhalten. Forschungs-Output für [[MISSION]] (was funktioniert, was bricht in der Multi-Claude-Kollaboration?).

## Beobachtungsmethode

Sieben Quellen, in dieser Reihenfolge konsultiert. Die ersten drei zusammen liefern den Tagesstand in unter dreißig Sekunden, die anderen vier liefern Tiefe.

**Filesystem-Snapshot.** `ls -la` über den Vault, sortiert nach mtime. Liefert objektives Signal: welche Datei existiert, wie groß, wann zuletzt verändert. Unabhängig von Selbstauskunft — und damit Korrektiv, falls eine Instanz ihren Status nicht aktualisiert hat.

**COORDINATION.md.** Kanonische Selbstauskunft pro Rolle. Felder: `last-touch`, `Working on`, `Files locked`, `Notes`. Aktuell, aber nur so frisch wie der letzte Update. Vergleich zur mtime der Datei zeigt, ob der Eintrag nachhängt.

**LOG.md.** Append-only Audit-Spur. Verlässlichste Quelle für *was wurde tatsächlich getan*, weil unedierbar. Letzte zehn Einträge geben den jüngsten Verlauf.

**Beitragsdateien pro Rolle.** Aktuell `Claude-1.md` (überholt, siehe Konflikt 2 unten), perspektivisch `Claude-2.md` und Inhaltsdateien von Claude #3. Sie zeigen den inhaltlichen Stand, nicht nur den Statusausweis.

**METHOD.md, BACKLOG.md, MISSION.md.** Stand der gemeinsamen Methode: was ratifiziert, was vorgeschlagen, was offen. Differenz zwischen METHOD und BACKLOG ist die Reibungsfläche, an der die drei Instanzen aktuell arbeiten.

**Diff über Snapshots.** Zwischen zwei Snapshots zeigt sich, welche Rolle in welchem Zeitfenster welche Dateien angefasst hat — Kommunikationsfluss als Zeitreihe. Dafür Snapshots datiert in dieses Dokument schreiben und nicht überschreiben.

**User als Bus.** Du wechselst zwischen den Konversationen und trägst semantische Information mit, die nicht im Vault landet. Hinweise von dir, die alle drei betreffen, kommen in COORDINATION.md unter `## Hinweise` mit Datum und Markierung "alle".

## Snapshot-Konvention

Snapshots sind ereignisgesteuert, nicht uhrgesteuert. Trigger: Sessionstart nach dem Lese-Ritual aus CLAUDE.md, detektierter Konflikt (file-modification-Konflikt, Rollen-Drift, divergente Konvention), Userprompt nach dem aktuellen Stand, oder Schlüsselereignis wie Rollen-Reassignment, METHOD-Ratifizierung, Vault-Bootstrap. Maximalabstand zwischen Snapshots: zwei Stunden Vault-aktive Zeit.

Format: Header `## Snapshot YYYY-MM-DD HH:MM — kurzer Anlass`. Pflichtfelder im Body sind Dateibestand-Tabelle (Datei, Größe, mtime, Eigentümer), Per-Rolle-Stand aus COORDINATION und LOG, offene Konflikte nummeriert, Methodenstand mit METHOD/BACKLOG/MISSION-Kennzahlen, Anomalien. Optional: Diff zum vorherigen Snapshot, wenn substanziell.

Persistenz: append-only in dieses Dokument, niemals überschreiben — die Diff-Achse ist der Hauptwert. Sobald mehr als zehn Snapshots akkumuliert sind, ältere in `Sessions/Snapshots-YYYY-MM.md` auslagern, hier die letzten drei plus Verweis behalten.

## Lage-Notiz-Format

Lage-Notizen sind die Synthese-Ebene über den Snapshots — sie verdichten den Stand der drei Rollen zu einem gemeinsam lesbaren Bild. Trigger: erste Lage-Notiz, sobald alle drei Rollen substanziell beigetragen haben (eigenes Beitragsdokument oder klar erkennbarer Output in METHOD/BACKLOG). Folgenotizen nach METHOD-Ratifizierungen, nach Eskalation an den User, oder bei nachhaltigem Konflikt. Anlassbezogen, nicht regelmäßig.

Ablage: `Sessions/YYYY-MM-DD - Kurztitel.md`. Frontmatter:

```yaml
---
type: synthesis
instance: claude-1
session-date: YYYY-MM-DD
roles: [Koordinator, Strukturarbeiter, Inhalt]
status: active | closed | superseded
---
```

Struktur, nach dem Forschungsleitstelle-Session-Vorbild im Lesevault: `## Rollen-Stand` mit einem Absatz pro Rolle (was sie tut, was zuletzt erreicht, was blockiert); `## Aktive Synthese` mit dem, was die drei gemeinsam vorantreiben und woran sich Konflikte reiben; `## Offene Fragen` mit Punkten, die Konsens oder User-Entscheidung brauchen; `## Quality Flags` mit methodisch wichtigen Befunden — validierte Konventionen, gescheiterte Versuche, Hinweise für METHOD.

Lifecycle: `active` während der Synthese, `closed` wenn alle Open Questions beantwortet sind, `superseded` durch nachfolgende Lage-Notiz mit explizitem `supersedes`-Link im Frontmatter.

## Kommunikationskarten-Lifecycle

Die Kommunikationskarte ist Forschungs-Output und wächst inkrementell. Versionierung: v0.1 bis v0.4 bleibt als Sektion in diesem Dokument, solange Skizze. Ab v0.5 — mindestens zwei vollständige Iterationen mit echten Konflikt-Beobachtungen — Auslagerung in ein eigenes Dokument `Kommunikationskarte.md` mit Frontmatter `type: research-output` und Verweis zurück hierher als Beobachtungsquelle. Version v1.0 markiert die Karte, die als Methoden-Vorschlag in BACKLOG wandert und bei Konsens nach METHOD migriert.

Update-Trigger: neu beobachtete Bruchstelle, neuer Nachrichtentyp (etwa wenn ein Format wie Lage-Notiz aktiv wird), Eintritt einer neuen Rolle, oder ratifizierte Konvention in METHOD, die Schreibflüsse oder Protokolle ändert.

Update-Form: Versionsnummer hochzählen (v0.1 → v0.2), Diff-Notiz im Versions-Header mit Stichworten zur Änderung. Keine Löschung alter Inhalte — bei Auslagerung wandert die letzte Vorgängerversion als Anhang in das neue Dokument, damit die Entwicklungslinie sichtbar bleibt.

## Eskalations-Schwelle

Drei Stufen, von leicht nach schwer. Schwellen-Logik: Stufe 1 immer zuerst. Stufe 2, wenn Stufe 1 zweimal ohne Reaktion blieb oder die Frage offensichtlich Konsens braucht. Stufe 3 nur, wenn Stufe 2 ohne Konvergenz blieb oder das Problem das Setup als ganzes betrifft.

**Stufe 1 — Hinweis in COORDINATION.md unter `## Hinweise`.** Für Konflikte zwischen Rollen, die durch Beobachtung sichtbar gemacht werden müssen, und für Beobachtungen, die andere Rollen wissen sollen. Kein User-Eingriff nötig. Form: Datum, Rolle, Adressaten-Markierung ("alle" oder konkrete Rolle), kompakter Befund.

**Stufe 2 — Eintrag in BACKLOG.md unter `## Offene Fragen`.** Für methodische Lücken, die Konsens unter den drei Rollen brauchen. User-Eingriff nicht zwingend, aber moderierend möglich. Form: Frage mit Kontext, Anker zu betroffenen Dokumenten oder Vorschlägen, vorhandene Stellungnahmen kurz referenziert.

**Stufe 3 — explizite Eskalation an den User in der Konversation.** Für wiederkehrende Konflikte, die durch Hinweise nicht aufgelöst werden, für Rollen-Drift mit Reassignment-Bedarf, für Methoden-Ratifizierungen im Schwebezustand, für Beobachtungen über das Setup als ganzes. Form: Verweis auf Vault-Artefakt mit Pfad, kurze Begründung, klare Frage oder Entscheidungsanforderung — keine offenen Erörterungen, sondern Entscheidungspunkt.

## Snapshot 2026-04-26 18:13 — Vault-Stand

**Dateibestand (mtime aufsteigend):**

| Datei | Größe | mtime | Eigentümer |
| --- | --- | --- | --- |
| MISSION.md | 1913 | 18:07 | Claude #3 (vormals Architekt) |
| METHOD.md | 631 | 18:07 | Claude #3 (vormals Architekt) |
| Claude-1.md | 4814 | 18:07 | Claude #1 (Wissensbringer-Phase) |
| BACKLOG.md | 3819 | 18:08 | Claude #3 (vormals Architekt) |
| CLAUDE.md | 2970 | 18:09 | Claude #3 (vormals Architekt) |
| COORDINATION.md | 1972 | 18:12 | Claude #3 (vormals Architekt), zuletzt #1 + #3 ergänzt |
| Koordination.md | 3137 | 18:13 | Claude #1 (parallele Anlage) |
| LOG.md | 1489 | 18:13 | Claude #3 (vormals Architekt), neue Einträge folgen |
| Wissensbasis Claude-1.md | 18783 | 18:13 | Claude #1 (Wissensbringer-Phase) |

**Per-Rolle-Stand (aus COORDINATION):**

- **Vault-Architekt-Slot** — frei. User-Reassignment: Claude #2 übernimmt die Rolle als "Struktur".
- **Operativer Koordinator** — Slot existiert, alter Eintrag von Claude #2 vor Reassignment. Nicht aktiv.
- **Claude #3 — Inhalt** — eingelesen, bereitet inhaltliche Methodenarbeit vor. Hat zuvor das Vault-Skelett gebaut.
- **Claude #1 — Koordinator** — diese Session, Sessionstart-Ritual durchlaufen, Erst-Snapshot in dieser Notiz.

**Offene Konflikte:**

1. *Doppelte Coordination-Datei*. `COORDINATION.md` (kanonisch laut CLAUDE.md, Großschreibung) und `Koordination.md` (Kleinschreibung, von Claude #1 vor CLAUDE.md angelegt). Auflösung: Strukturarbeit Claude #2.
2. *Veraltete Selbsteinordnung in Claude-1.md*. Dort steht "inhaltliche Kuration / Wissensbringer", die Rolle ist seit User-Reassignment "Koordinator". Auflösung: Strukturarbeit Claude #2 (Re-Fit oder Rückbau), oder Entscheidung, ob die Datei generell als Rollen-Beitrag bleibt.
3. *Wissensbasis Claude-1.md ist Vault-Resource, nicht Rollen-Beitrag*. Inhaltlich gehört das Dokument unter Claude #3 (Inhalt) oder als allgemeine Referenz, nicht unter Claude #1's Rolle. Auflösung: Strukturarbeit Claude #2 in Abstimmung mit Claude #3.

**Methoden-Stand (METHOD, BACKLOG, MISSION):**

- METHOD: 0 ratifizierte Methodenelemente, wartet auf Konsens.
- BACKLOG: 6 Methodenvorschläge V1–V6 (alle mit Stellungnahme-Status `—`), 5 offene Fragen, keine Experimente.
- MISSION: Forschungsfrage und Erfolgskriterien klar, Anschluss an Forschungsleitstelle definiert.

## Kommunikationskarte v0.1

Beschreibt, wie die drei Instanzen miteinander reden — beobachtet, nicht vorgeschrieben. Differenz zur Soll-Vorgabe in CLAUDE.md ist der eigentliche Forschungsbefund.

**Schreibflüsse (Rolle × Dokument):**

| Dokument | Architekt/Struktur (#2) | Inhalt (#3) | Koordinator (#1) |
| --- | --- | --- | --- |
| MISSION.md | Edit | Lesen | Lesen |
| METHOD.md | Edit (nach Konsens) | Vorschlag, Ratifizierung | Vorschlag, Ratifizierung |
| BACKLOG.md | Edit (Aufnahme) | Vorschlag, Stellungnahme | Vorschlag, Stellungnahme |
| COORDINATION.md | Edit (Pflege) | Eigene Slot-Pflege | Eigene Slot-Pflege, Synthese |
| LOG.md | Append eigene Einträge | Append eigene Einträge | Append eigene Einträge |
| CLAUDE.md | Edit | Lesen | Lesen |
| Claude-N.md (Beitrag pro Rolle) | Eigenes Beitrags-File | Eigenes Beitrags-File | Eigenes Beitrags-File |
| Beobachtung Claude-1.md | — | — | Edit (eigenes Artefakt) |

**Nachrichtentypen:**

- *Stand* — Self-Report, in COORDINATION-Slots.
- *Aktion* — Tatsächlich getane Arbeit, in LOG.
- *Vorschlag* — Methodenidee, in BACKLOG mit Status `vorgeschlagen`.
- *Stellungnahme* — Reaktion auf Vorschlag, in BACKLOG-Item-Sektion `Stellungnahmen`.
- *Ratifizierung* — Konsens, Migration nach METHOD.
- *Beobachtung* — Befund, in COORDINATION unter `## Beobachtungen` (im aktuellen Bestand nicht vorhanden, in Koordination.md von Claude #1 angelegt — Sektion gehört normalisiert).
- *Hinweis/Eskalation* — bei Konflikten oder User-relevanten Punkten, in COORDINATION unter `## Hinweise`.
- *Übergabe* — strukturierter Handover, in COORDINATION unter `## Übergaben`.

**Protokolle (Soll laut CLAUDE.md):**

- Sessionstart: Lese-Reihenfolge CLAUDE → MISSION → METHOD → COORDINATION → LOG (letzte 10) → BACKLOG, dann Slot-Setzung in COORDINATION, dann LOG-Eintrag.
- Pre-Edit-Read: bei Read >10 min vor Edit erneut lesen, bei "modified since read"-Konflikt nicht überschreiben sondern Hinweis setzen.
- Sessionende: Slot austragen oder als `[abgeschlossen]` markieren, LOG-Eintrag.
- Konflikt: nicht überschreiben, nicht überreden — Hinweis in COORDINATION, Eskalation an User.

**Beobachtete Bruchstellen (Ist-Stand):**

- *Vorab-Aktion ohne CLAUDE-Lese.* Claude #1 (ich) hat vor Lesen von CLAUDE.md drei Dateien angelegt, die jetzt Strukturkonflikte erzeugen. Ursache: User-Pfadangabe wurde als Aufforderung interpretiert, nicht als Einstieg in ein bestehendes Setup. Lehre: Sessionstart-Read auch dann durchführen, wenn der Vault scheinbar leer ist.
- *Doppelte Konvention durch Sprachwahl.* Großschreibung+Englisch (COORDINATION) versus Mischschreibung+Deutsch (Koordination) als Datei-Naming-Schema sind inkompatibel und erzeugen Doppelungen, sobald zwei Instanzen unabhängig anlegen. Konvention zur Naming-Sprache muss explizit sein.
- *Rollen-Drift.* In zwei Stunden gab es zwei User-Reassignments. Die Rollennamen in COORDINATION (Vault-Architekt, Operativer Koordinator, Inhalt) und im neuen User-Frame (Koordinator, Struktur, Inhalt) divergieren, weil Slots und Bezeichnungen nicht gleichzeitig geupdatet wurden. Rollen-Update muss kanonisch durch eine Rolle laufen (Struktur).
- *V6 in der Praxis.* Pre-Edit-Read-Konvention hat heute beim ersten echten Konflikt direkt gegriffen — Edit wurde abgewiesen, nicht stillschweigend überschrieben. Das ist Validierung des Vorschlags V6 unter Realbedingungen.

**Loss/Distortion:**

- Selbstauskunft in COORDINATION ist nur so genau wie die Disziplin der Instanz. Stale-Marker (`last-touch`-Datum) hilft, aber nur, wenn andere Instanzen auf das Datum achten.
- LOG.md ist verlässlich, aber chronologisch — Querverweise zwischen Aktionen verschiedener Rollen sind nicht aufgelöst.
- Inhaltliche Beiträge stehen in eigenen Dateien (Claude-N.md), die andere lesen müssen — keine automatische Sichtbarkeit.

## Nächste Snapshots

Geplant: nach Stellungnahmen von #2 und #3 zu den Konflikten, nach erstem Eintrag von Struktur-Rolle, nach erster Ratifizierung in METHOD.
