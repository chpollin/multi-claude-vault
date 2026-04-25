---
type: knowledge
created: 2026-04-26
updated: 2026-04-26
tags: [sugw, verifikation, master, user-anleitung]
status: phase-2-skeleton
author: Koordinator (Single-Curator)
---

# sugw Verifikations-Master

Konsolidierte User-Anleitung zum 1:1-Vergleich des überarbeiteten Frontends gegen das Original. Geschrieben so, dass User (Christopher) und Stakeholder Schritt-für-Schritt jede Änderung verifizieren können — niemand muss in Source-Code schauen.

**Status:** Skeleton (Phase 2). Wird in Phase 5 nach Implementation aller V-IDs befüllt mit konkreten Test-Schritten und Beleg-Stichproben.

## Setup für die Verifikation

**Voraussetzung:** Beide Server laufen lokal:

```bash
# Original (main-Branch des sugw-Edition-Repos)
cd "C:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions_edition"
python -m http.server 8765 --bind 127.0.0.1 &

# Neu (Build-Output von frontend-rework-2026-04-Branch im Pipeline-Repo)
cd "C:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions"
git checkout frontend-rework-2026-04
python -m pipeline transform --validate
python -m edition build
cd docs && python -m http.server 8766 --bind 127.0.0.1 &
```

Dann zwei Browser-Tabs aufmachen, einer auf `http://127.0.0.1:8765/`, einer auf `http://127.0.0.1:8766/`. Vergleich Seite-für-Seite.

## Top-Level-Checkliste

Pro V-ID einen Block. User markiert nach Verifikation `[x]` oder eskaliert `[!]` mit Notiz.

### V1 — Korpus-Approval-Marker im Datenmodell

- [ ] Korpus-Chips in `/documents.html` zeigen nur freigegebene Korpora (gemäß User-Klärung, ob QGW II/2 1415-1417 freigegeben ist).
- [ ] `data/persons_search.json` enthält ein `c` (corpus) Feld pro Eintrag.
- [ ] Build-Audit `pipeline/output/approval_audit.md` existiert.

Detail: [[Project/sugw-Verifikation/V1-Verifikation]]

### V2 — Filterung der Indizes auf geprüfte Korpora

- [ ] Personen-Index zeigt deutlich weniger Einträge als Original (Original 16.084).
- [ ] Personen aus QGW II/2 nicht im Index (Stichprobe).
- [ ] "Aaron der Jude" verifiziert (Datenbasis-Klärung — entweder mit Quelle aus released Korpus erscheint, oder gar nicht).
- [ ] Keine Personen mit `dc == 0` im Index.

Detail: [[Project/sugw-Verifikation/V2-Verifikation]]

### V3 — Suche: Volltext + ID + Diakritika-Normalisierung

- [ ] **Test-Anker S20 Pötel/Pötlin:** Suche "Simon Pötel" auf `documents.html` findet Regest 3819. Suche "Anna Pötlin" auf `documents.html` findet ebenfalls Regest 3819.
- [ ] Suche "Schoenberg" findet 9+ Treffer (entspricht "Schönberg").
- [ ] Suche "Müller" und "Mueller" findet identische Treffermenge.
- [ ] Suche per Person-ID (z.B. `pe__hadmar_von_schoenberg_QGW_II_I_1`) findet exakte Person.

Detail: [[Project/sugw-Verifikation/V3-Verifikation]] und [[Project/sugw-Verifikation/S20-Verifikation]]

### V4 — Personen-Profile parallel zu Regesten

- [ ] Aus `register/persons.html` Klick auf eine Person → eigene Detail-Page (statt Anker).
- [ ] URL `register/persons/<pe_id>.html` erreichbar.
- [ ] Detail-Page zeigt: Stammdaten, Erwähnungen-Liste mit Klick-Through, Beziehungen, Schreibvarianten.
- [ ] Aus Urkunden-Detail Klick auf `<rs type="person">` führt zur Detail-Page.

Detail: [[Project/sugw-Verifikation/V4-Verifikation]]

### V5 — Bidirektionale Verlinkung + Beziehungen

- [ ] Personen-Profil zeigt Erwähnungen mit Doc-ID + Datum + Rolle + Excerpt.
- [ ] Personen-Profil zeigt Beziehungen gruppiert nach Typ.
- [ ] Test-Anker: Simon-Pötel-Profil zeigt Regest 3819 + Anna Pötlin als Beziehung; Anna-Pötlin-Profil symmetrisch.
- [ ] Klick auf Beziehungs-Partner navigiert zu Partner-Profil.

Detail: [[Project/sugw-Verifikation/V5-Verifikation]]

### V6 — Glossar mit Mouse-Over

- [ ] `project/glossary.html` enthält ≥14 Einträge (vom Stakeholder bestätigte Liste).
- [ ] Hover über Spalten-Header in Tabellen → Tooltip mit Definition.
- [ ] Tooltip-Klick führt zum Glossar-Eintrag.
- [ ] Tooltip auf Touch-Device per Tap funktional.

Detail: [[Project/sugw-Verifikation/V6-Verifikation]]

### V7 — Terminologie-Refactoring

- [ ] grep "Wiener Urkundenbuch" im gerenderten HTML → 0 Treffer.
- [ ] grep "Überlieferungslücke" → 0 Treffer.
- [ ] Personen-Tabelle zeigt "als verstorben genannt" statt "Tod".
- [ ] Factoid-Toggle hat User-bestätigtes neues Label.
- [ ] `quality.html` aus Top-Nav entfernt; via Direktlink erreichbar.

Detail: [[Project/sugw-Verifikation/V7-Verifikation]]

### V8 — Statistiken: % statt absolut, Relation Gesamtbestand

- [ ] Statistik-Page Default-Anzeige ist %.
- [ ] Toggle "% / absolut" funktional.
- [ ] Timeline zeigt zwei Layer (Hintergrund Gesamt grau, Vordergrund Released blau).
- [ ] KPI-Header gefiltert (released-konsistent zu V1+V2).
- [ ] Datenstand-Fußzeile prominent.

Detail: [[Project/sugw-Verifikation/V8-Verifikation]]

### V9 — Verb-Browser-Aggregation

- [ ] Stakeholder-Beispielphrasen aus S35 sind im selben Cluster (das `habent emphangen`-Paar).
- [ ] Verb-Browser zeigt Cluster mit Display-Label und Count.
- [ ] Klick auf Cluster expandiert Original-Varianten.
- [ ] `pipeline/output/verb_clusters_audit.md` existiert.

Detail: [[Project/sugw-Verifikation/V9-Verifikation]]

### V10 — Exploration aufräumen

- [ ] `exploration/places.html` entfernt oder mit "in Bearbeitung"-Hinweis (gemäß User-Klärung).
- [ ] Top-Nav Exploration-Dropdown ohne "Orte"-Link (oder als disabled).
- [ ] Top-Nav Exploration-Dropdown mit Hub-Link.
- [ ] `exploration/transactions.html` zeigt prominent Datenstand-Banner.

Detail: [[Project/sugw-Verifikation/V10-Verifikation]]

### V11 — Frontend-Polish

- [ ] Regestentext-Spalte nutzt volle Breite.
- [ ] Wiener-Neustadt-Dublette im Ort-Filter behoben.
- [ ] Nav-Disabled-Konsistenz (keine Pages disabled-aber-erreichbar).
- [ ] Datenstand-Fußzeile prominent.

Detail: [[Project/sugw-Verifikation/V11-Verifikation]]

## Stakeholder-Aussagen-Checkliste (S-IDs)

Pro Stakeholder-Issue: ist sie adressiert? Wenn nicht, mit Begründung markiert.

| S-ID | Adressiert durch | Status |
|---|---|---|
| S1 Terminologie allgemein | V7 | offen |
| S2 "Wiener Urkundenbuch" vermeiden | V7 | offen |
| S3 Quellen/Sammlungen/Bestände | V6, V7 | offen |
| S4 "Auswertungslücke" | V7 | offen |
| S5 Glossar mit Mouse-Over | V6 | offen |
| S6 Mouse-Over Spalten-Header | V6 | offen |
| S7 Erklärung pro Tabellen-Kategorie | V6 | offen |
| S8 "Tod" → "als verstorben genannt" | V7 | offen |
| S9 Q-Kategorie ausblenden | V7 | offen |
| S10 "Factoids" Bezeichnung | V7 | offen |
| S11 Quelle/Untersuchungskategorie erklären | V6 | offen |
| S12 Relation zum Gesamtbestand | V8 | offen |
| S13 % statt absolut pro Dekade | V8 | offen |
| S14 Regestentext-Spalte voller Breite | V11 | offen |
| S15 Projektinfo überarbeiten | V6 (Substrat) | offen, Inhalt durch Stakeholder |
| S16 Personen-Auffindbarkeit | V3 | offen |
| S17 Suchsemantik dokumentieren | V3, V6 | offen |
| S18 Umlaut-Behandlung | V3 | offen |
| S19 2/3-3/4 fehlende Hits | V3, V4 | offen |
| S20 Pötel/Pötlin/Regest 3819 | V3 | offen |
| S21 Person-View parallel zu Regesten | V4 | offen |
| S22 Profil mit Beziehungen, Schreibvarianten | V4, V5 | offen |
| S23 Verwandtschaftsbeziehungen einsehbar | V5 | offen |
| S24 Bidirektionale Verlinkung | V5 | offen |
| S25 Personen-Liste nur aus geprüften Korpora | V1, V2 | offen |
| S26 Ungeprüfte Korpora nicht in Auswertungen | V1, V2, V8 | offen |
| S27 Personen mit 0 Dokumenten ausblenden | V2 | offen |
| S28 Korbinian-Daten gesperrt | V1 | offen |
| S29 Indizes filtern | V1, V2 | offen |
| S30 Verbindung Interface ↔ Git | dokumentiert in [[Knowledge/sugw Daten-Architektur]] | dokumentiert |
| S31 Korpus-Approval-Markierung | V1 | offen |
| S32 Exploration/Orte weglassen | V10 | offen |
| S33 Siedlungskarte | V10 | offen (entfällt mit V10 wenn Page entfernt) |
| S34 Exploration/Transaktionen kontextualisieren | V10 | offen |
| S35 Verb-Browser-Aggregation | V9 | offen |
| S36 DB-Vorrang (methodisch) | dokumentiert in [[MISSION#Out-of-Scope]] | dokumentiert |
| S37 Interface-Zahlen = DB-Zahlen | V1, V2, V8 | offen |

## Wenn Verifikation fehlschlägt

- [Issue dokumentieren in Lage-Notiz `Sessions/2026-04-MM - sugw User-Verifikation.md` mit S-ID + Beobachtung].
- Eskalation: User → Koordinator (zur Re-Implementation oder Eskalation an Stakeholder bei methodischer Frage).

## Anschluss

- [[MISSION]] — Erfolgskriterien.
- [[Project/sugw-Traceability-Matrix]] — vollständige S-ID/V-ID-Matrix.
- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan.
- `Project/sugw-Verifikation/V*-Verifikation.md` — Tech-Verifikations-Docs pro V-ID.
- `Project/sugw-Verifikation/S*-Verifikation.md` — Stakeholder-zentrierte Verifikations-Docs (Phase 5).
- [[Findings/2026-04-26 - sugw Stakeholder-Feedback]] — Originale Stakeholder-Aussagen für Re-Check.
