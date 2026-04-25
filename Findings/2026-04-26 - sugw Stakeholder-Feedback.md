---
type: finding
created: 2026-04-26
tags: [sugw, stakeholder, feedback]
status: complete
author: Claude B (Subagent — Stakeholder-Feedback-Analyst)
---

# Finding 2026-04-26 — sugw Stakeholder-Feedback (Meeting 23.4.2026)

## Zusammenfassung

Strukturierte Issue-Liste aus dem Stakeholder-Meeting vom 23.4.2026 zum sugw-Frontend, basierend auf Protokoll (DOCX) und PPT (12 annotierte Slides). 37 Stakeholder-Issues (S1–S37) gruppiert in zehn Themengruppen. Inhaltliche Schwerpunkte: terminologische Überarbeitung mit Glossar-Bedarf, gravierende Suchfunktions-Defekte (im Schnitt 2/3–3/4 fehlende Hits), fehlende Personen-Profile parallel zu Regesten, ausstehende Korpuskontrolle (geprüft = QGW + StB; alle anderen Korpora müssen aus Indizes/Statistiken gefiltert werden), Q-Kategorie zu intern, Verb-Browser zu kleinteilig, Exploration/Orte und Exploration/Transaktionen noch nicht ausgereift. Übergreifender Grundsatz aus dem Protokoll: DB-Qualität (Git-Repository) hat Vorrang, Interface-Zahlen müssen mit der DB-Wahrheit übereinstimmen.

## Stakeholder und Profile

Im Protokoll genannt: Gonaus, Handl, Lutter, Siegl, Steinböck. Individuelle Profile/Zuschreibungen einzelner Aussagen sind weder im Protokoll noch in den Slides explizit ausgewiesen — Aussagen werden im Folgenden kollektiv als Stakeholder-Position behandelt. Wo sich Protokoll und Slides decken, wird jeweils auf beide Quellen referenziert.

## Issues nach Themengruppen

### Terminologie und Glossar

#### S1 — Allgemeine terminologische Überarbeitung des Frontends

- **Quelle** — Protokoll Z.2 ("Terminologische Überarbeitung des Frontend"); Slide 1.
- **Stakeholder-Aussage** — "Terminologie zum Projekt muss überarbeitet werden." Dies betrifft das gesamte Frontend, nicht einzelne Begriffe.
- **Betroffene Page/Komponente** — Frontend-übergreifend, insbesondere Projektinfo-Bereich.
- **Technische Schicht** — Frontend-Templates / Inhalts-Strings.
- **Schweregrad** — Major (Querschnittsthema, Dach für S2–S11).
- **Lösungsrichtung** — Konsolidierte Begriffsliste erarbeiten, mit den anderen Terminologie-Issues abstimmen, einheitlich im Frontend ersetzen. Glossar als Single Source.
- **Querbezug** — S2, S3, S4, S5, S10, S11.

#### S2 — "Wiener Urkundenbuch" als Bezeichnung vermeiden

- **Quelle** — Slide 1 ("kein 'Wiener Urkundenbuch'!").
- **Stakeholder-Aussage** — Wörtlich: "kein 'Wiener Urkundenbuch'!"
- **Betroffene Page/Komponente** — Projektinfo, ggf. Landing.
- **Technische Schicht** — Frontend-Templates.
- **Schweregrad** — Minor.
- **Lösungsrichtung** — Vorkommen von "Wiener Urkundenbuch" identifizieren, durch korrekten Begriff ersetzen (im Glossar zu klären).
- **Querbezug** — S1.

#### S3 — Begriffe "Quellen", "Sammlungen", "Bestände" präzisieren

- **Quelle** — Protokoll Z.6 ("Was ist eine Quelle?"); Slide 1.
- **Stakeholder-Aussage** — "Was sind hier 'Quellen' oder 'Sammlungen'? Die Terminologie muss präzisiert werden." Plus Protokoll: "Was versteht das Projekt unter welchem Begriff?"
- **Betroffene Page/Komponente** — Frontend-übergreifend, besonders Projektinfo, Statistik, Tabellen-Header.
- **Technische Schicht** — Frontend-Templates / Glossar-Inhalt.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Begriffsdefinitionen im Glossar (Quelle, Sammlung, Bestand, Korpus). Konsistente Verwendung im Frontend.
- **Querbezug** — S1, S5, S11.

#### S4 — "Überlieferungslücke" → "Auswertungslücke"

- **Quelle** — Slide 1.
- **Stakeholder-Aussage** — "Außerdem handelt es sich um keine 'Überlieferungslücke'; wenn, um eine Auswertungslücke."
- **Betroffene Page/Komponente** — Projektinfo / Statistik (wo der Begriff erscheint).
- **Technische Schicht** — Frontend-Templates.
- **Schweregrad** — Minor.
- **Lösungsrichtung** — Begriff-Ersetzung. Glossar-Eintrag für "Auswertungslücke".
- **Querbezug** — S1, S12.

#### S5 — Glossar mit Mouse-Over-Funktion

- **Quelle** — Protokoll Z.4 ("Glossar für die Website wäre sinnvoll"); Slide 1; Slide 2 ("solche Tabellen brauchen Mouse-Over Informationen zu den einzelnen Spalten").
- **Stakeholder-Aussage** — "Ein allgemeines Glossar, dass aufrufbar oder mittels Mouse-Over für das gesamte Interface funktioniert, wäre sinnvoll."
- **Betroffene Page/Komponente** — Frontend-übergreifend; Glossar-Page; Tabellen-Header.
- **Technische Schicht** — Frontend-HTML/JS (Tooltip-Komponente), Glossar-Page-Struktur, Daten-Quelle (Begriffsliste).
- **Schweregrad** — Major.
- **Lösungsrichtung** — Aufrufbares Glossar plus Mouse-Over-Tooltips an relevanten Stellen (insbesondere Tabellen-Spalten-Header).
- **Querbezug** — S1, S6, S7, S11.

#### S6 — Mouse-Over für Tabellen-Spalten-Header

- **Quelle** — Slide 2 (Tabelle Regesten); Slide 2 (Tabelle Dokumente: "Mouse-Over essenziell für Kategorienbeschreibung").
- **Stakeholder-Aussage** — "Solche Tabellen brauchen Mouse-Over Informationen zu den einzelnen Spalten." "Mouse-Over essenziell für Kategorienbeschreibung."
- **Betroffene Page/Komponente** — Alle Tabellen-Views (Regesten, Dokumente, Personen-Index, etc.).
- **Technische Schicht** — Frontend-HTML/JS (Tooltip-Mechanik), Glossar-Daten-Quelle.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Tooltip-Komponente an Tabellen-`th`-Elementen, gespeist aus Glossar.
- **Querbezug** — S5, S7.

#### S7 — Erklärung pro Tabellen-Kategorie/-Spalte

- **Quelle** — Protokoll Z.10 ("Es muss auch bei jeder Kategorie in einer Tabelle eine Erklärung geben, was die Information bedeutet").
- **Stakeholder-Aussage** — "Es muss auch bei jeder Kategorie in einer Tabelle eine Erklärung geben, was die Information bedeutet."
- **Betroffene Page/Komponente** — Alle Tabellen-Views.
- **Technische Schicht** — Frontend-HTML/JS / Glossar-Inhalt.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Verbindet sich mit S5/S6: Glossar speist Mouse-Over an Spalten-Headern.
- **Querbezug** — S5, S6.

#### S8 — "Tod" → "als verstorben genannt"

- **Quelle** — Protokoll Z.11 ("Kategorie 'Tod' irreführend → 'als verstorben genannt'"); Slide 2 ("'Tod' hier irreführend, besser 'als verstorben genannt'").
- **Stakeholder-Aussage** — Wörtlich: "Kategorie 'Tod' irreführend → 'als verstorben genannt'."
- **Betroffene Page/Komponente** — Personen-Tabellen / Personen-Detail (Lebensdaten).
- **Technische Schicht** — Daten-Aggregation (Kategorie-Label) und/oder Frontend-Templates; ggf. TEI-Quelle (zu klären — abhängig von Pipeline-Architektur).
- **Schweregrad** — Major (häufig sichtbarer, irreführender Begriff).
- **Lösungsrichtung** — Label-Renaming entlang der Pipeline. Mit Daten-Architektur (Strang C) abstimmen.
- **Querbezug** — S1, S10.

#### S9 — Q-Kategorie im öffentlichen Frontend ausblenden oder erklären

- **Quelle** — Protokoll Z.21 ("Die Kategorie 'Q' ist für internes Review interessant, aber nicht sinnvoll, wenn die Hinweise/Warnungen nicht erklärt werden. Im Frontend sollte diese Kategorie so nicht sichtbar sein."); Slide 2 ("'Q' für Datenqualität für interne Checks nützlich, aber nicht für das öffentliche Frontend").
- **Stakeholder-Aussage** — Q-Kategorie zeigt Datenqualitäts-Hinweise/-Warnungen an, ist aber für das öffentliche Frontend ohne Erklärungen nicht sinnvoll.
- **Betroffene Page/Komponente** — Q-Page (`/project/quality.html`), ggf. Tabellen-Spalten an anderen Stellen.
- **Technische Schicht** — Frontend (Sichtbarkeits-Steuerung) oder Pipeline (Build-Filter).
- **Schweregrad** — Major (Stakeholder klar: aktueller Zustand nicht öffentlich tauglich).
- **Lösungsrichtung** — Entweder vollständig ausblenden oder mit verständlichen Erklärungen versehen. Stakeholder-Präferenz tendiert zu Ausblenden im öffentlichen Frontend, intern weiter nutzen.
- **Querbezug** — S1.

#### S10 — "Factoids" — falsche Bezeichnung

- **Quelle** — Protokoll Z.13 ("Kategorie Factoids ist eine gute Idee, aber die falsche Bezeichnung für eine Liste von im Regest vorkommenden Personen, Organisationen, etc. (und zum Teil falsche Nennungen)."); Slide 6 ("'Factoids' Button ist an sich eine gute Idee, aber hier die falsche Bezeichnung für das, was de facto dargestellt wird").
- **Stakeholder-Aussage** — Konzept gut, Bezeichnung "Factoids" passt nicht zum tatsächlich Dargestellten (Liste von im Regest vorkommenden Personen, Organisationen etc.). Zusätzlicher Hinweis: zum Teil falsche Nennungen.
- **Betroffene Page/Komponente** — Regest-Detail (Factoids-Button).
- **Technische Schicht** — Frontend-Templates / Daten-Aggregation / Glossar.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Alternative Bezeichnung im Stakeholder-Dialog finden (Vorschlag in V7 ausarbeiten). Begleitend Datenkorrektur (falsche Nennungen) — Letzteres ist out-of-scope für Frontend-Rework, gehört in TEI-Korrektur.
- **Querbezug** — S1, S29.

#### S11 — Begriffe wie "Quelle", "Untersuchungskategorie" erklären

- **Quelle** — Protokoll Z.6 ("Was ist eine Quelle? Untersuchungskategorien erklären, etc.").
- **Stakeholder-Aussage** — "Was ist eine Quelle? Untersuchungskategorien erklären, etc."
- **Betroffene Page/Komponente** — Glossar-Page; ggf. Mouse-Over an entsprechenden Stellen.
- **Technische Schicht** — Glossar-Inhalt.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Glossar-Einträge für "Quelle", "Untersuchungskategorie" und weitere Schlüsselbegriffe.
- **Querbezug** — S1, S3, S5.

### Statistik und Auswertung

#### S12 — Ausgewertete Bestände in Relation zum Gesamtbestand

- **Quelle** — Slide 2 ("Hier werden die bereits ausgewerteten Bestände gezeigt, besser wäre es, das in Relation zum Gesamtbestand anzuzeigen. Bsp: Grauer Balken im Hintergrund für alle Regesten, blauer Balken für bereits ausgewertete").
- **Stakeholder-Aussage** — Aktuell werden ausgewertete Bestände als absolute Werte gezeigt; besser wäre eine Relation zum Gesamtbestand. Konkreter Visualisierungsvorschlag: grauer Balken Gesamtbestand, blauer Balken ausgewerteter Anteil.
- **Betroffene Page/Komponente** — Statistik-Page, ggf. Landing.
- **Technische Schicht** — Pipeline-Aggregation (Verhältnis-Berechnung) plus Frontend-Visualisierung.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Pipeline berechnet Relation pro Dekade/pro Bestand; Frontend zeigt zwei-Balken-Visualisierung.
- **Querbezug** — S13, S15.

#### S13 — % statt absolute Quellenmenge pro Dekade

- **Quelle** — Protokoll Z.9 ("Es ist weniger wichtig auszuweisen, wie viele Quellen es pro Dekade gibt, sondern wichtiger, wie viel Prozent der Bestände in der jeweiligen Dekade ausgewertet wurden.").
- **Stakeholder-Aussage** — Prozent-Anteil der ausgewerteten Bestände pro Dekade ist wichtiger als absolute Quellenmenge.
- **Betroffene Page/Komponente** — Statistik-Page (Dekaden-Auswertung).
- **Technische Schicht** — Pipeline-Aggregation; Frontend-Charts.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Aggregation um Prozent-Berechnung pro Dekade erweitern; Default-Anzeige auf %, absolute Zahlen optional ergänzend.
- **Querbezug** — S12.

#### S14 — Regestentext-Spalte füllt nicht volle Breite

- **Quelle** — Slide 2 ("warum füllt der Regestentext hier nicht die volle Breite des Formats?").
- **Stakeholder-Aussage** — Frage, warum die Regestentext-Spalte das Format nicht ausnutzt.
- **Betroffene Page/Komponente** — Regesten-Tabelle (vermutlich `/documents.html`).
- **Technische Schicht** — Frontend-CSS / Tabellen-Layout.
- **Schweregrad** — Minor.
- **Lösungsrichtung** — CSS-Layout der Regesten-Tabelle prüfen; Spaltenbreite anpassen.

#### S15 — Projektinfo / Statistik / Editionsrichtlinien inhaltlich überarbeiten

- **Quelle** — Slide 3 ("Informationen über das Projekt / Statistik / Editionsrichtlinien sind strukturell ansehnlich aufbereitet, müssen aber inhaltlich überarbeitet werden. Wenn überarbeitet, kann es als Grundlage für die Mouse-Over Informationen und das angedachte Glossar dienen.").
- **Stakeholder-Aussage** — Struktur passt, Inhalt nicht. Überarbeiteter Inhalt kann als Grundlage für Mouse-Over und Glossar dienen.
- **Betroffene Page/Komponente** — `/project/about.html`, `/project/statistics.html`, `/project/edition-guidelines.html`.
- **Technische Schicht** — Frontend-Inhalts-Strings (Markdown, HTML, oder Templates).
- **Schweregrad** — Major.
- **Lösungsrichtung** — Inhalts-Refresh durch Stakeholder/Projektpartner; Frontend übernimmt aktualisierten Text. Anschließend als Glossar-Quelle nutzen.
- **Querbezug** — S1, S5.

### Suchfunktion

#### S16 — Personen-Auffindbarkeit zentrales Problem

- **Quelle** — Protokoll Z.12 ("Zentralstes Problem: alle Einträge zu Personen müssen auffindbar sein."); Slide 4.
- **Stakeholder-Aussage** — Wörtlich: "Zentralstes Problem: alle Einträge zu Personen müssen auffindbar sein."
- **Betroffene Page/Komponente** — Globale Suchleiste, Personen-Index, Dokumenten-Suche.
- **Technische Schicht** — Frontend-JS, Such-Index (Daten-JSON), ggf. Pipeline (Index-Generierung).
- **Schweregrad** — Blocker (vom Stakeholder als zentralstes Problem benannt).
- **Lösungsrichtung** — Suchindex über alle Personen-Nennungen (inkl. Schreibvarianten); robuste Treffer-Erschöpfung. Detail in V3.
- **Querbezug** — S17, S18, S19, S20.

#### S17 — Wonach sucht die Suchleiste?

- **Quelle** — Protokoll Z.12; Slides 4–5 ("Kernfrage: Wonach wird in den Suchleisten gesucht? Personen IDs, Fließtext, etc??").
- **Stakeholder-Aussage** — Suchverhalten ist undurchsichtig: IDs? Fließtext? Beides? Stakeholder will Klarheit über das Suchfeld-Verhalten.
- **Betroffene Page/Komponente** — Globale Suche, Dokumentensuche, Personensuche.
- **Technische Schicht** — Frontend-JS / Such-Index-Definition.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Suchverhalten dokumentieren (im Glossar/Hilfe-Bereich) UND Such-Engine so konfigurieren, dass alle relevanten Felder (ID, Vorname, Nachname, Schreibvarianten, Fließtext-Erwähnung im Regest) durchsucht werden.
- **Querbezug** — S16, S20, S22.

#### S18 — Umlaut-Behandlung in der Suche

- **Quelle** — Protokoll Z.12 ("Werden Umlaute verstanden?").
- **Stakeholder-Aussage** — Frage: "Werden Umlaute verstanden?"
- **Betroffene Page/Komponente** — Alle Suchleisten.
- **Technische Schicht** — Frontend-JS (Normalisierung) / Such-Index.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Unicode-Normalisierung beidseitig (Eingabe und Index): "Pötel" findet "Pötel" und "Poetel" und "Potel".
- **Querbezug** — S16, S17.

#### S19 — 2/3 bis 3/4 aller Hits fehlen

- **Quelle** — Protokoll Z.13 ("Anhand von Stichproben, bei denen die Anzahl der Nennungen bekannt ist, ist davon auszugehen, dass derzeit im Schnitt 2/3 bis 3/4 aller Hits bei den Nennungen nicht angezeigt werden.").
- **Stakeholder-Aussage** — Wörtlich (zentrales Defizit): im Schnitt fehlen 2/3 bis 3/4 aller Treffer.
- **Betroffene Page/Komponente** — Suchergebnisse, Personen-Detail (Liste der Erwähnungen).
- **Technische Schicht** — Such-Index-Vollständigkeit; Daten-Aggregation Person→Erwähnungen.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Vollständige Erwähnungs-Erfassung in der Pipeline (alle TEI-Mentions, nicht nur normalisierte ID-Treffer); Stichproben-basierte Verifikation gegen bekannte Stakeholder-Werte.
- **Querbezug** — S16, S20, S24.

#### S20 — Fallbeispiel "Simon Pötel" / "Anna Pötlin"

- **Quelle** — Slides 4–5 ("'Simon Pötel' hat 0 Treffer in der Dokumentensuche, aber 40 Treffer in der Personensuche. 'Anna Pötlin' (Simon Pötels 2. Frau) hat 1 Treffer in der Dokumentensuche und 3 in der Personensuche. Fallbeispiel — Regest, Nr. 3819. 'Anna Pötlin' wird hier sowohl über die Dokument- als auch die Personensuche gefunden (obwohl sie im Fließtext als 'Simon Pötlin' geschrieben wird). 'Simon Pötel', so im Fließtext als auch in der ID genannt, wird nur über die Personensuche gefunden.").
- **Stakeholder-Aussage** — Konkretes Fallbeispiel mit nachvollziehbaren Treffer-Zahlen, das die Inkonsistenz zwischen Dokumenten- und Personensuche belegt. Im Regest 3819 sind beide Personen genannt.
- **Betroffene Page/Komponente** — Dokumenten-Suche, Personen-Suche, Regest 3819 als Test-Anker.
- **Technische Schicht** — Such-Index-Aufbau pro Suchleiste; Verlinkung Person↔Regest-Volltext.
- **Schweregrad** — Blocker (als Smoking-Gun-Beispiel verwendet).
- **Lösungsrichtung** — Test-Anker in V3-Akzeptanzkriterien aufnehmen. Dokumentensuche muss Fließtext-Erwähnungen finden, auch wenn Schreibung von ID abweicht.
- **Querbezug** — S16, S17, S19, S22.

### Personen-Profile / Entitäten-View

#### S21 — Person-View parallel zu Regesten-View

- **Quelle** — Slide 7 ("Parallel zu dieser 'Regesten-View' muss es auch eine 'Person-View' geben."); Protokoll Z.15 ("Parallele Struktur zu den Regesten notwendig: Jede Entität braucht eine eigene Ansicht bzw. ein eigenes Profil, wie es auch die Regesten haben.").
- **Stakeholder-Aussage** — Jede Entität braucht ein eigenes Profil, äquivalent zu Regest-Detail-Seiten.
- **Betroffene Page/Komponente** — Personen-Detail-Page (neu), ggf. Organisationen-Detail, Orte-Detail.
- **Technische Schicht** — Build (neue Detail-Pages pro Person), Templates, Routing.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Detail-Page pro Person mit allen Regest-Verlinkungen, Beziehungen, Schreibvarianten. Detail in V4.
- **Querbezug** — S22, S23, S24.

#### S22 — Profil pro Entität: Beziehungen, Schreibvarianten, alle Daten

- **Quelle** — Slide 7 ("Jede Entität braucht also ein eigenes Profil, das sowohl auf alle Regesten verlinkt, als auch auf alle Beziehungen in der Datenbank ausgewiesen ist."); Slide 8 ("z.B.: verschiede Schreibungen, Beziehungen, etc.").
- **Stakeholder-Aussage** — Personen-Profil zeigt: alle Regest-Erwähnungen, alle Beziehungen aus der DB, Schreibvarianten, weitere strukturierte Information.
- **Betroffene Page/Komponente** — Personen-Detail-Page.
- **Technische Schicht** — Pipeline-Aggregation (Person→Beziehungen→Schreibvarianten); Templates.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Person-Aggregat als JSON pro Person, Template rendert Profil-Sektionen. Detail in V4/V5.
- **Querbezug** — S21, S23, S24.

#### S23 — Verwandtschaftsbeziehungen ausgewiesen, aber nicht einsehbar

- **Quelle** — Slides 7–8 ("Vgl. das Beispiel Simon Pötel / Anna Pötlin — ihre Verwandtschaftsbeziehung ist ausgewiesen, aber im Frontend nicht einsehbar.").
- **Stakeholder-Aussage** — Beziehungsdaten existieren in der DB, sind aber im Frontend nicht zugänglich.
- **Betroffene Page/Komponente** — Personen-Detail-Page (geplant), Regest-Detail.
- **Technische Schicht** — Pipeline (Beziehungs-Extraktion aus TEI); Templates (Beziehungs-Sektion).
- **Schweregrad** — Major.
- **Lösungsrichtung** — Beziehungs-Daten in Personen-Profil rendern, mit klickbarer Verlinkung zur verbundenen Person.
- **Querbezug** — S21, S22, S24.

#### S24 — Bidirektionale Verlinkung Person ↔ Urkunde

- **Quelle** — Protokoll Z.16 ("Die ID der Person ist zu jeder Urkunde verlinkt, in der sie vorkommt — umgekehrt wäre das auch notwendig für das Profil der Person.").
- **Stakeholder-Aussage** — Aktuell: Urkunde→Person verlinkt. Stakeholder fordert auch Person→Urkunde-Verlinkung im Personen-Profil.
- **Betroffene Page/Komponente** — Personen-Detail-Page; ggf. Personen-Index-Listen.
- **Technische Schicht** — Pipeline (inverser Index Person→Urkunden); Templates.
- **Schweregrad** — Blocker (zentral für die Personen-Profil-Idee).
- **Lösungsrichtung** — Pipeline baut inversen Index; Personen-Profil rendert Liste aller Erwähnungen mit Link auf Regest.
- **Querbezug** — S19, S21, S22.

### Korpuskontrolle und Datenintegrität

#### S25 — Personen-Liste nur aus geprüften Korpora

- **Quelle** — Slide 9 ("In der Personen Liste des Frontends dürfen nur Personen aufscheinen, die zumindest in einem der geprüften Korpora (QGW, StB) aufscheinen."); Protokoll Z.17 ("Die angezeigten Daten dürfen nur aus den bereits geprüften Korpora stammen (= QGW, StB) → Es dürfen nur die Personen aufscheinen, die in diesen Beständen genannt sind.").
- **Stakeholder-Aussage** — Wörtlich aus Slide 9: nur Personen aus geprüften Korpora (QGW, StB). Geprüft sind aktuell ausschließlich QGW und StB.
- **Betroffene Page/Komponente** — Personen-Index, alle Indizes (Organisationen, Orte), Suchergebnisse.
- **Technische Schicht** — Pipeline-Filter (Korpus-Approval-Marker), Frontend-Anzeige.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Korpus-Approval-Status pro Quelle in TEI-Header oder Pipeline-Konfiguration; Pipeline filtert Indizes auf approved=true. Detail in V1, V2.
- **Querbezug** — S26, S28, S29, S31.

#### S26 — Ungeprüfte Korpora nicht in Auswertungen/Gesamtzahlen

- **Quelle** — Protokoll Z.18 ("Alle anderen Quellen-Korpora sind nicht geprüft und freigeschaltet und dürfen auch nicht in den Nennungen, Gesamtanzahl an Einträgen, etc. miteingerechnet werden."); Slides 9–10.
- **Stakeholder-Aussage** — Statistiken, Nennungs-Zähler, Gesamtzahlen dürfen ausschließlich auf geprüfte Korpora referenzieren.
- **Betroffene Page/Komponente** — Statistik-Page, Personen-Detail (Anzahl Erwähnungen), Suchergebnis-Counter.
- **Technische Schicht** — Pipeline-Aggregation; Frontend-Anzeige.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Aggregations-Code respektiert Approval-Filter durchgehend; Test gegen bekannte Stakeholder-Stichproben.
- **Querbezug** — S25, S29, S37.

#### S27 — Personen mit 0 Dokumenten nicht anzeigen

- **Quelle** — Slide 9 ("In der Personen Liste des Frontends sollten auch keine Personen genannt sein, die in 0 Dokumenten aufscheinen, etwa 'Aaron der Jude'. Hier ist auf Datenbasis zu klären, was genau angezeigt wird.").
- **Stakeholder-Aussage** — Personen ohne Dokument-Bezug (z.B. "Aaron der Jude") sollten nicht im Personen-Index erscheinen. Datenbasis-Klärung erforderlich.
- **Betroffene Page/Komponente** — Personen-Index.
- **Technische Schicht** — Pipeline-Filter (mention_count > 0 nach Korpus-Filter).
- **Schweregrad** — Major.
- **Lösungsrichtung** — Index-Filter: nur Personen mit ≥1 Erwähnung in geprüften Korpora. Datenbasis-Klärung mit Projektpartnern (welche Datensätze ohne Erwähnung kommen woher?).
- **Querbezug** — S25.

#### S28 — Korbinian-Daten außerhalb QGW/StB gesperrt

- **Quelle** — Protokoll Z.30 ("Die Daten, die für die Dissertation von Korbinian außerhalb der QGW und StB erhoben wurden, bleiben bis zu einer Überprüfung für das Interface gesperrt.").
- **Stakeholder-Aussage** — Korbinian-Daten außerhalb QGW/StB sind gesperrt bis zur Überprüfung.
- **Betroffene Page/Komponente** — Frontend-übergreifend (Indizes, Detail-Pages, Statistik).
- **Technische Schicht** — Pipeline-Filter.
- **Schweregrad** — Blocker.
- **Lösungsrichtung** — Korbinian-Korpora als nicht-approved markieren. Sub-Fall von S25/S26.
- **Querbezug** — S25, S26, S31.

#### S29 — Indizes auf geprüfte Korpora filtern

- **Quelle** — Protokoll Z.31 ("Klärung, wie Personen in nicht freigeschalteten Quellen-Korpora und Gesamtnennungen aller Personen in nicht freigeschalteten Quellen-Korpora auch aus den Indizes gefiltert werden können.").
- **Stakeholder-Aussage** — Filterung auf Indizes-Ebene (nicht nur Statistik) ist offene Frage, Klärung erforderlich.
- **Betroffene Page/Komponente** — Personen-, Organisationen-, Orte-Index.
- **Technische Schicht** — Pipeline-Aggregations-Logik.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Filter-Mechanik in der Aggregation einheitlich anwenden, dokumentieren. Detail in V1/V2.
- **Querbezug** — S25, S26.

#### S30 — Klärung Verbindung Interface ↔ Git-Repository

- **Quelle** — Protokoll Z.29 ("Klärung, wie die geprüften Daten im alten Interface hinterlegt sind und in welcher Verbindung sie zum laufend aktualisierten Git-Repository stehen.").
- **Stakeholder-Aussage** — Offene Klärung: Wie ist der Daten-Fluss vom Git-Repository zum Interface?
- **Betroffene Page/Komponente** — Pipeline insgesamt.
- **Technische Schicht** — Pipeline + Build-Prozess + Edition-Repo.
- **Schweregrad** — Major (methodisch, nicht nur technisch).
- **Lösungsrichtung** — Daten-Architektur dokumentieren (wird durch Strang C / Knowledge/sugw Daten-Architektur abgedeckt).
- **Querbezug** — S25, S37; verweist auf Knowledge/sugw Daten-Architektur (Strang C).

#### S31 — Korpus-Approval-Markierung im System

- **Quelle** — Protokoll Z.27 ("Sofern es fachlich gerechtfertigt ist, werden die Korpora für die DB-interne Nutzung freigegeben; es wird markiert, inwieweit sie korrigiert und überprüft sind.").
- **Stakeholder-Aussage** — Approval-Status muss explizit markiert werden (DB-interne Nutzung vs. öffentliches Frontend; Stand der Korrektur/Prüfung).
- **Betroffene Page/Komponente** — TEI-Header bzw. Pipeline-Konfiguration; ggf. interne Doku-Page.
- **Technische Schicht** — Daten-Modell.
- **Schweregrad** — Major (Voraussetzung für S25/S26/S29).
- **Lösungsrichtung** — Approval-Marker im Datenmodell festlegen (z.B. TEI `<sourceDesc>`-Erweiterung oder Korpus-Manifest-Datei). Detail in V1.
- **Querbezug** — S25, S26, S28, S29.

### Exploration

#### S32 — Exploration/Orte weglassen

- **Quelle** — Protokoll Z.22 ("Exploration/Orte: Orte einstweilen ganz weglassen, da diese Kategorie noch ganz unsystematisch erfasst ist."); Slide 11 ("Diese Art der Auswertung ist einstweilen noch nicht möglich. Die Daten sind noch nicht systematisch erfasst.").
- **Stakeholder-Aussage** — Orte-Exploration aus dem Frontend entfernen, bis Daten systematisch erfasst sind.
- **Betroffene Page/Komponente** — `/exploration/places.html`, Navigations-Einträge.
- **Technische Schicht** — Frontend-Routing/Templates.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Page entfernen oder mit "in Arbeit"-Hinweis ausblenden. Detail in V10.
- **Querbezug** — S33, S34.

#### S33 — Siedlungskarte lädt nicht

- **Quelle** — Slide 11 ("Nebenbei: 'Siedlungskarte' lädt nicht.").
- **Stakeholder-Aussage** — Technischer Fehler: Siedlungskarte lädt nicht.
- **Betroffene Page/Komponente** — Siedlungskarte-Page (Pfad zu klären in Phase-1-Inspektion durch Claude A).
- **Technische Schicht** — Frontend-JS / Asset-Pfade / Daten-Quelle.
- **Schweregrad** — Major (defekt).
- **Lösungsrichtung** — Falls die Page mit S32 ohnehin entfernt wird, fällt dieses Issue weg. Sonst: Defekt beheben.
- **Querbezug** — S32.

#### S34 — Exploration/Transaktionen irreführend

- **Quelle** — Protokoll Z.23 ("Exploration/Transaktionen: Irreführende Daten, da keine Informationen über den Erarbeitungsgrad der Quellen und die Menge an verfügbaren Quellen angegeben werden."); Slide 12 ("Diese Art der Auswertung ist einstweilen noch nicht möglich. Die Daten sind noch nicht systematisch erfasst.").
- **Stakeholder-Aussage** — Transaktionen-Exploration ist irreführend ohne Kontext zu Erarbeitungsgrad und Quellenmenge. Slide 12: Auswertung "einstweilen noch nicht möglich".
- **Betroffene Page/Komponente** — `/exploration/transactions.html`.
- **Technische Schicht** — Frontend / Aggregation.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Entweder Page entfernen oder Kontext-Information ergänzen (Erarbeitungsgrad, geprüftes Korpus-Subset). Detail in V10.
- **Querbezug** — S32, S35, S26.

#### S35 — Verb-Browser zu kleinteilig

- **Quelle** — Protokoll Z.24 ("Verb-Browser interessant, aber in derzeitiger Form zu kleinteilig und irreführend: Viele der aufgelisteten 'Verben' sollten zusammengerechnet werden, wie etwa 'habent emphangen nucz und gewer / mit kauf an sy komen ist' und 'hat emphangen nucz und gewer | mit kauff an In komen ist'."); Slide 12 ("Auch der 'Verb-Browser' ist in seiner derzeitigen Form noch zu kleinteilig, um ihn öffentlich schalten zu können").
- **Stakeholder-Aussage** — Verb-Browser-Konzept gut, aktuelle Granularität zu fein. Verb-Phrasen mit identischer Bedeutung aber leichten Schreib-/Flexions-Unterschieden müssen aggregiert werden. Konkrete Beispiel-Paare im Protokoll genannt.
- **Betroffene Page/Komponente** — Verb-Browser-Page (Pfad in Phase-1-Inspektion zu identifizieren).
- **Technische Schicht** — Pipeline (Verb-Normalisierung/Lemmatisierung) plus Frontend-Anzeige.
- **Schweregrad** — Major.
- **Lösungsrichtung** — Aggregations-Heuristik für Verb-Phrasen entwickeln (Lemma- oder Cluster-basiert). Detail in V9.
- **Querbezug** — S34.

### DB-Vorrang und Konsistenz

#### S36 — DB-Qualität (Git-Repository) hat Vorrang

- **Quelle** — Protokoll Z.33 ("Die Qualität der Daten in der DB (Git-Repository) hat immer Vorrang; ihre Korrektur ist daher die Basis für die Korrektur der auf dem Interface wiedergegebenen Daten.").
- **Stakeholder-Aussage** — Wörtlich: DB hat Vorrang vor Interface. Korrektur erfolgt zuerst in der DB.
- **Betroffene Page/Komponente** — Methodisch übergreifend.
- **Technische Schicht** — Workflow-Konvention.
- **Schweregrad** — Methodisch (kein Frontend-Issue per se, sondern Leitprinzip für alle V-IDs).
- **Lösungsrichtung** — Frontend-Vorschläge dürfen keine Inhalts-Korrekturen am TEI vornehmen, die nicht aus dem DB-Workflow kommen. Strukturelle/aggregations-bezogene Pipeline-Änderungen bleiben in-scope.
- **Querbezug** — Out-of-Scope-Klausel der MISSION; betrifft S10, S33.

#### S37 — Interface-Zahlen müssen mit DB übereinstimmen

- **Quelle** — Protokoll Z.32 ("Ziel: Es muss erreicht werden, dass alle Zahlen des Interface mit jenen der überprüften Korpora in der DB (Git-Repository) übereinstimmen.").
- **Stakeholder-Aussage** — Wörtlich: Alle Interface-Zahlen müssen mit DB-Zahlen aus geprüften Korpora übereinstimmen.
- **Betroffene Page/Komponente** — Statistik-Page, Counter, Indizes.
- **Technische Schicht** — Pipeline-Aggregation; Verifikations-Schritt.
- **Schweregrad** — Blocker (zentrales Akzeptanz-Kriterium).
- **Lösungsrichtung** — Verifikations-Schritt: pro statistischem Wert im Frontend rückwärts-prüfen, ob er aus geprüften Korpora abgeleitet ist. Stichproben gegen bekannte DB-Werte.
- **Querbezug** — S25, S26, S29, S30.

## Priorisierungsempfehlung

### Top-5 Blocker (zentrale Stakeholder-Forderungen, ohne deren Erfüllung das Frontend nicht öffentlich tauglich ist)

1. **S19** — 2/3–3/4 aller Hits fehlen → Suchfunktion vollständig überarbeiten (V3).
2. **S25/S26** — Filterung auf geprüfte Korpora (QGW, StB) für Indizes UND Statistiken (V1, V2).
3. **S21/S22/S24** — Personen-Profile parallel zu Regesten + bidirektionale Verlinkung (V4, V5).
4. **S37** — Interface-Zahlen müssen mit DB-Zahlen übereinstimmen (V1, V2 + Verifikations-Schritt).
5. **S20** — Konkretes Test-Fallbeispiel "Simon Pötel"/"Anna Pötlin" / Regest 3819 als Akzeptanzanker für V3.

### Top-5 Major (wichtig, aber nicht alleiniger Blocker)

1. **S5–S7** — Glossar mit Mouse-Over für Tabellen-Spalten (V6).
2. **S8/S10** — Terminologie "Tod" → "als verstorben genannt"; "Factoids" → angemessener Begriff (V7).
3. **S9** — Q-Kategorie aus öffentlichem Frontend ausblenden (V7).
4. **S12/S13** — Statistik-Visualisierung (% statt absolut, Relation Gesamtbestand) (V8).
5. **S35** — Verb-Browser-Aggregation (V9).

## Visuelle Befunde aus den Slides

Die Slides enthalten Frontend-Screenshots mit Annotationen. Die wesentlichen Befunde aus den Annotations-Texten sind in den S-IDs oben aufgenommen. Tiefere visuelle Annotationen (Pfeile, Markierungen) auf den eingebetteten Screenshots werden in Phase 1 Strang A (Frontend-Inspektion durch Claude A) ergänzend abgeglichen, sobald dieser Output vorliegt.

Slide-Übersicht mit zugeordneten S-IDs:

- **Slide 1** — Terminologie / Wiener Urkundenbuch / Glossar-Idee → S1, S2, S3, S4, S5.
- **Slide 2** — Tabellen, Mouse-Over, "Tod", Q-Kategorie, Regestentext-Layout → S5, S6, S7, S8, S9, S12, S14.
- **Slide 3** — Projektinfo / Statistik / Editionsrichtlinien → S15.
- **Slides 4–5** — Suchleisten, Simon Pötel / Anna Pötlin, Regest 3819 → S16, S17, S18, S20.
- **Slide 6** — Factoids-Button → S10.
- **Slides 7–8** — Person-View, Profil pro Entität, Beziehungen → S21, S22, S23.
- **Slide 9** — Personen-Liste nur aus geprüften Korpora; "Aaron der Jude" → S25, S27.
- **Slide 10** — Korpus-Übersicht mit Approval-Hinweis → S25, S26, S31.
- **Slide 11** — Exploration/Orte; Siedlungskarte → S32, S33.
- **Slide 12** — Exploration/Transaktionen; Verb-Browser → S34, S35.

## Offene Fragen für Stakeholder-Klärung

- **Glossar-Begriffe konsolidiert** — Welche Liste von Schlüsselbegriffen soll das Glossar enthalten? Vorschlag in V6, abzustimmen mit Stakeholdern (Quelle, Sammlung, Bestand, Korpus, QGW, StB, Untersuchungskategorie, Factoid, Regest, Q-Kategorie, Approval-Status, Auswertungslücke, weitere?).
- **"Factoids" — Ersatzbegriff** — Stakeholder lehnt "Factoids" ab, schlägt aber keinen Ersatz vor. Mögliche Kandidaten (in V7 zu diskutieren): "Erwähnungen im Regest", "Strukturierte Nennungen", "Regest-Entitäten". Stakeholder-Präferenz einzuholen.
- **Q-Kategorie — Ausblenden vs. Erklären** — Stakeholder tendiert zu Ausblenden ("Im Frontend sollte diese Kategorie so nicht sichtbar sein"), nennt aber Erklärungen als Alternative. Endgültige Entscheidung mit Stakeholdern abstimmen (V7).
- **"Tod" → Pfad in der Pipeline** — Ist "Tod" in TEI-Quelle, in Aggregations-Skript, oder in Template fest verdrahtet? Klärung mit Strang C (Daten-Architektur) bzw. Claude A in Phase 1.
- **Approval-Marker — Ort im Datenmodell** — TEI-Header pro Quelle, Korpus-Manifest-Datei, oder Build-Konfiguration? Klärung in V1, abhängig von Pipeline-Architektur.
- **"Aaron der Jude" — Datenbasis-Klärung** — Stakeholder fordert explizit Klärung, woher Personen-Einträge ohne Dokument-Bezug kommen. Recherche in der Pipeline-/Daten-Architektur erforderlich (Strang C).
- **Siedlungskarte (Slide 11)** — Wenn S32 (Orte weglassen) umgesetzt wird, ist S33 erledigt. Klärung mit Stakeholdern, ob Siedlungskarte separat erhalten bleiben soll.
- **Personen-Profil — Pflichtfelder** — Slide 8 nennt "Schreibungen, Beziehungen". Vollständige Feldliste (Lebensdaten, Rollen, alle Erwähnungen mit Kontext, Bezugnahmen aus anderen Personen-Profilen, …) in V4 zu konsolidieren, mit Stakeholder-Review.
- **Test-Stichproben für Suchfunktion** — Über "Simon Pötel"/"Anna Pötlin" hinaus zusätzliche Stichproben mit bekannten Treffer-Zahlen einholen, um S19/S20-Akzeptanzkriterien quantitativ verifizierbar zu machen.

## Anschluss

- [[MISSION]] — Project-Fork-MISSION mit Forschungsfrage und Erfolgskriterien.
- [[Project/sugw-frontend-rework Roadmap]] — Phasen-Plan; dieses Dokument ist Phase-1-Output Strang B.
- [[Project/sugw-Subagent-Prompts]] — eigene Aufträge (Claude B).
- [[Findings/2026-04-26 - sugw Frontend-Inspektion]] — Strang A (Claude A), aktuell ausstehend; visuelle Annotations-Details auf Slide-Screenshots werden bei dortiger Inspektion abgeglichen.
- [[Knowledge/sugw Daten-Architektur]] — Strang C (Koordinator), aktuell ausstehend; Approval-Marker-Ort und Pipeline-Pfade für S8/S10/S31 dort zu klären.
- Phase 2 (Koordinator) wird die Traceability-Matrix aus diesem Findings + Strang A + Strang C aufbauen.

Quellen:

- Protokoll: `c:/Users/Chrisi/Downloads/Protokoll_SuG_23_04_Final.docx`, extrahierter Text: `C:/tmp/sugw-protokoll.txt`.
- PowerPoint: `c:/Users/Chrisi/Downloads/Protokoll_SuG_23_04_Frontend Änderungen_Final.pptx`, 12 Slides, extrahierter Annotationstext: `C:/tmp/sugw-slides-text.txt`.

## Bearbeitungs-LOG

- **2026-04-26 — Claude B (Subagent — Stakeholder-Feedback-Analyst):** Sessionstart, Pflicht-Lesungen (CLAUDE, MISSION, METHOD, Roadmap, Subagent-Prompts) durchgeführt. Branch `sugw-frontend-rework` bestätigt. Findings-Output existierte noch nicht → Phase-1-Modus. DOCX und PPTX entpackt; Volltext und Slide-Annotationen nach `C:/tmp/sugw-protokoll.txt` und `C:/tmp/sugw-slides-text.txt` extrahiert. 37 Stakeholder-Issues (S1–S37) systematisch aus beiden Quellen gezogen, in zehn Themengruppen organisiert (Terminologie/Glossar, Statistik, Suchfunktion, Personen-Profile, Korpuskontrolle/Datenintegrität, Exploration, DB-Vorrang). Top-5-Blocker- und Top-5-Major-Priorisierung gesetzt. Offene Fragen für Stakeholder-Klärung dokumentiert. V20-Disziplin: Stakeholder-Aussagen als wörtliche oder nahe-paraphrasierte Zitate erhalten, eigene Einschätzungen (Schweregrad, Lösungsrichtung) als solche markiert. Status `complete`. STOP für Koordinator-Synthese (Phase 2).
