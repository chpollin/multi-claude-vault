---
type: knowledge
vorschlag-id: V11
github-issue: 11
created: 2026-04-26
tags: [sugw, vorschlag, frontend, polish]
stakeholder-issues: [S14]
zusatz-befunde: [Claude-A im Protokoll NICHT stehende Befunde]
betroffene-files:
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/base.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/templates/documents.html
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/static/css/main.css
  - c:/Users/Chrisi/Documents/GitHub/DHCraft/sugw/db_for_medieval_legal_transactions/edition/aggregator.py
aufwand: "4-6h"
status: ready-for-implementation
author: Koordinator
implementation-commits: []
---

# V11 — Frontend-Polish

Sammelvorschlag für kleinere Inkonsistenzen und Bugs aus Strang A's Inspektion (Sektion "Befunde im Protokoll NICHT stehen") plus S14.

## Problem

- **S14:** Regestentext-Spalte füllt nicht volle Breite in Tabelle.
- **Inkonsistenz Nav-disabled vs. Pages erreichbar.** `register/organisations.html` und `register/places.html` sind im Top-Nav als `nav-disabled` markiert, aber direkt aufrufbar.
- **Doppelter Eintrag im Ort-Filter:** "Wiener Neustadt" (9) und "Wiener-Neustadt" (6) als getrennte Werte. Normalisierungsbug.
- **Exploration-Hub fehlt im Dropdown.** `exploration/index.html` nur über Direkt-Klick auf Trigger-Element erreichbar.
- **Datenstand-Fußzeile** dezent. Stakeholder-Sicht: Datenstand sollte prominenter sein, weil Auswertung per Korpus zeitabhängig.
- **Korpus-Mismatch zwischen Indizes.** Quellen-Index zählt QGW II/2, Personen-Index potentiell auch — Konsistenz nicht gegeben (V1+V2 lösen das datenseitig; V11 bezieht sich auf UI-Anzeige des Stands).

## Lösungsansatz

### Pro Befund

1. **S14 Regestentext-Breite.** CSS-Audit `documents.html`-Tabelle. Regestentext-Spalte mit `width: auto` oder explizitem Anteil. Test mit verschiedenen Viewport-Breiten.

2. **Nav-Disabled-Konsistenz.** Wenn eine Page `aria-disabled` ist:
   - Entweder Page aus Build entfernen (build.py Routing) und 404 + Stakeholder-Hinweis-Page,
   - Oder aria-disabled aufheben (wenn Page tatsächlich nutzbar ist).
   - Aktueller Mittelweg "disabled in Nav, aber erreichbar via URL" ist verwirrend.
   - **Empfehlung:** Build-time-Entscheidung — wenn Korpus für Org/Places nicht freigegeben (V1), Pages nicht bauen, Top-Nav-Eintrag entfernen statt disabled.

3. **Wiener-Neustadt-Dublette.** In `aggregator.py` Ort-Filter: Normalisierungs-Mapping `Wiener Neustadt = Wiener-Neustadt`. Pflegbar in `normalisation_lists/`.

4. **Exploration-Hub-Dropdown.** In `base.html` Dropdown-Template: Hub-Link `/exploration/` als ersten Eintrag ergänzen.

5. **Datenstand-Fußzeile prominenter.** Position in Site-Footer überarbeiten (ggf. ins Header oder als Banner unter Top-Nav). Zeigt: Datum, Versionierungs-Hash (Git-Commit-Hash), Stand der released Korpora.

6. **Korpus-Mismatch-Audit.** Build-Zeit-Konsistenz-Check zwischen `search.json` (Quellen-Counts) und `persons_search.json` (Personen-Counts) → Korpus-Verteilung muss übereinstimmen. Bei Diff: Build-Warnung. Wird mit V1+V2-Implementation als Konsistenz-Test integriert.

## Akzeptanzkriterien

- [ ] Regestentext-Spalte nutzt verfügbare Breite ohne Text-Abbruch (Stichprobe 1280px, 1024px, 768px Viewport).
- [ ] Nav-Disabled-Konsistenz: keine Page ist disabled-im-Nav-aber-erreichbar.
- [ ] Ort-Filter zeigt einen einzigen Eintrag für "Wiener Neustadt" (Counts addiert).
- [ ] Exploration-Dropdown enthält Hub-Link.
- [ ] Datenstand-Fußzeile prominent.
- [ ] Build-Konsistenz-Check zwischen Quellen- und Personen-Korpus-Verteilung.

## Verifikations-Plan

| Schritt | Alt (Port 8765) | Neu (Port 8766) | Erwarteter Unterschied |
|---|---|---|---|
| 1 | `documents.html` Regestentext-Spalte | gleiche URL | Alt: schmal mit Abbruch. Neu: volle Breite |
| 2 | `register/organisations.html` direkt | gleiche URL | Alt: erreichbar trotz Disabled. Neu: konsistent (entweder 404 oder Nav-Eintrag enabled) |
| 3 | `documents.html` Ort-Filter | gleiche URL | Alt: 2 Einträge "Wiener Neustadt" / "-Neustadt". Neu: 1 Eintrag (15) |
| 4 | Top-Nav Exploration-Dropdown | gleiche Aktion | Alt: 4 Sub-Pages. Neu: zusätzlich Hub-Link |
| 5 | Site-Footer | gleiche URL | Alt: dezent. Neu: prominent mit Datum + Commit-Hash |

## Risiken / Antipatterns

- Niedriges Risiko-Profil — alles kosmetische und konsistenz-orientierte Änderungen.

## Anschluss

- Stakeholder-Issue: S14 plus zusätzliche Strang-A-Befunde.
- Synergie mit V1+V2 (Korpus-Filter — Pages nicht-released-Korpora bauen).

## Bearbeitungs-LOG

- 2026-04-26 — Koordinator: Skizziert. Sammeldoku für Polish-Items.
