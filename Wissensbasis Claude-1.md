---
type: instance-contribution
instance: claude-1
role: inhaltliche Kuration / Wissensbringer
created: 2026-04-26
status: complete
source-vault: c:\Users\Chrisi\Documents\obsidian
---

# Wissensbasis Claude-1 (vollständig)

Diese Notiz fasst zusammen, was Claude #1 als Wissensbringer aus dem Quell-Vault `c:\Users\Chrisi\Documents\obsidian` für das Methoden-Forschungsprojekt verfügbar machen kann. Referenz, nicht Erzählung — gegliedert nach Sachgebieten, scanbar von oben nach unten. Tiefenstand: Frühjahr 2026, Schwerpunkt April. Was hier nicht steht, ist entweder im Quell-Vault belegbar aber nicht akut präsent, oder mir schlicht nicht bekannt (siehe `## Lücken`).

## Schnellstart für #2 und #3

Christopher Pollin betreibt unter der Marke DHCraft ein digital-humanistisches Forschungs- und Dienstleistungsumfeld mit zwei Hauptachsen: erstens kulturwissenschaftliche Erschließung mit LLM-gestützten Methoden (Editionen, OCR/HTR, semantische Modellierung, Datenrettung), zweitens Methodenarbeit zu Promptotyping, epistemischer Infrastruktur und Scholar-Centered AI. Der Quell-Vault ist als zentraler Wissensspeicher organisiert — rund 458 Dokumente, eine Hub-Triade aus ACTIVE-WORK (operativ), CLAUDE (formal) und VAULT-OPERATIONS (strategisch-methodisch), eine TAG-TAXONOMY und klare Konventionen für Frontmatter, Naming und Archivierung. Aktiv laufen rund ein Dutzend Projekte plus eine ausdifferenzierte Paper-Landschaft 2026 mit vier venue-fixierten und vier konzeptionellen Beiträgen. Die wichtigsten Querkonzepte, die in mehreren Projekten und Papers gleichzeitig relevant sind: Epistemische Infrastruktur, Promptotyping, Editor-in-the-Loop, Continuous Editorial Integration, Vogeler-Ringe, Bookkeeping Ontology. Der User arbeitet ausschließlich über Claude — manuelles Vault-Browsing findet nicht statt, was die Anforderungen an Konventionen und Auffindbarkeit hochzieht. Diese Notiz dient als Konsultations-Layer für #2 und #3, damit beide nicht den Quell-Vault leerlesen müssen, um sich zu orientieren.

## User und Geschäftskontext

Christopher Pollin, DHCraft (`office@dhcraft.org`, dhcraft.org). Profil: Digital-Humanities-Forschung mit operativem Standbein, Promotion zu *Modelling, Operationalising and Exploring Historical Information*, Lehraufträge an Uni Graz und in Wien (Data Librarian), Workshops und Vorträge im DH- und KI-Kontext. Geschäftliche Pricing-Logik intern: 150 €/h netto plus 40% Overhead in sichtbare Stunden eingerechnet plus 20% USt. Konkrete Geldbeträge bleiben aus Datenschutzgründen aus dem Vault.

Arbeitsstil-Präferenzen, soweit sie für Multi-Claude-Kollaboration relevant sind: kompakt-direkt statt ausführlich, kein Filler ("interestingly", "importantly"), präzise Verifikation statt TODO-Listen, keine Zeitplanungen, Inhalte werden nach vollständiger Extraktion gelöscht statt archiviert, in Workflows Rollen statt Namen, ACTIVE-WORK ist primär für Claude geschrieben (User liest es nie direkt), Synergien-Sektionen werden diskriminierend gehalten (nur Wiederverwendung, keine breiten Ähnlichkeiten). Mehrere Mitarbeiter:innen mit klar abgegrenzten Aufgaben — operative ACTIVE-WORK-Einträge listen jedoch nur Christophers eigene Termine, fremde Einheiten werden komplett weggelassen.

## Quell-Vault: Architektur und Konventionen

Hub-Triade als oberste Steuerungsebene: [[ACTIVE-WORK]] (Projektstand, Termine, nächste Schritte, Dataview-Inline-Metadaten), [[CLAUDE]] (formale Schreib- und Strukturregeln), [[VAULT-OPERATIONS]] (strategisches Steuerungsdokument mit Aufgabentypen, Glossar projektspezifischer Begriffe, Vault-strategische Entscheidungen, Rollen paralleler Claude-Instanzen). Daneben [[HOME]] als Navigationshub und [[TAG-TAXONOMY]] als kontrolliertes Vokabular.

Ordner-Topologie auf oberster Ebene: `Applied Generative AI/`, `Projects/`, `Teaching/`, `Digital Humanities/`, `Business/`, `Writing/`, `Presentations & Workshops/`, `Research Data and Open Science/`, `Vault Operations/`, `Coding/`, `_archive/`. Folder-Naming: Leerzeichen für mehrteilige Namen, keine numerischen Präfixe, beschreibend.

Frontmatter ist Pflicht. Kerntypen: `research`, `literature`, `concept`, `knowledge`, `workshop`, `course`, `vault-organisation`, `daily-note`, `contact`, `business`, `archived-project`, `specification`, `design-document`, `academic-writing`, `use-case`, `forschungsleitstelle-session`. Status-Werte: `idea`, `draft`, `stub`, `complete`, `reviewed`, `archived`, `released`, `wartend`. Für Lane-Konsumation durch die Forschungsleitstelle: `lane-readable: true` plus `query-topics: [...]`.

Naming: Daily Notes und Research mit Datumspräfix (`YYYY-MM-DD - Topic.md`), Literatur als `Author Year - Title.md`, Konzepte als `Concept Name.md` (Singular, Capitalized).

Linking-Strategie: erste Erwähnung eines Konzepts immer als `[[Wikilink]]`, immer auf relevante MOCs verlinken, Aliase im Frontmatter für Abkürzungen, bidirektionale Links bevorzugt, präzise Heading-Verlinkung über `[[Doc#Section]]`. Tags lowercase-hyphenated, 2–4 pro Dokument, kontrolliertes Vokabular aus [[TAG-TAXONOMY]].

Sonderkonventionen: `anchor-project` koppelt konzeptionelle Papers ohne Venue an ein Projektdokument (Frontmatter-Feld plus `## Paper-Anbindung`-Abschnitt). ACTIVE-WORK Inline-Metadaten: `folder::`, `status::`, `repo::`, `summary::`, `updated::`, `invoice::`, `milestone::`. Folien-verknüpfte Dokumente bekommen einen `## Folien`-Abschnitt mit Google-Slides-URLs und Repo-Zeile. Forschungsleitstelle-Sessions in `Projects/Forschungsleitstelle/Sessions/` mit Status-Lifecycle `active` → `closed`/`superseded`.

Archivierung: `_archive/` mit Prefix `ARCHIVED_`, Archivierungsvermerk `# ARCHIVED on YYYY-MM-DD - Reason`. Bei vollständiger Extraktion in atomare Dokumente wird die Quelle gelöscht statt archiviert (Feedback-Pattern, gegen die Standardregel "nie löschen, immer archivieren" als Sonderfall). Datenschutz: keine persönlichen Kontaktdaten, keine konkreten Geldbeträge, Rollen statt Namen.

## Aktive Projekte

| Projekt | Fokus | Stand |
| --- | --- | --- |
| [[Project Overview Stefan Zweig Digital]] | Digitale Edition, SZD-Ontologie (SZDO), HTR-Batch | aktiv, EIL-Workflow auf Exilbriefkonvolut übertragen |
| [[DIA-XAI – Wissensdokument]] | Explainable AI für digitale Archive, FWF-Folgeantrag | aktiv, Antrag April 2027 |
| Klawiter-Rescue | Datenrettung, 6.296 Einträge, DIA-XAI Showcase | live, Pipeline am Regex-Limit, Multi-Edition per LLM |
| [[Project Overview M³GIM]] | Mobilität und Musiktheaterwissen Graz Nachkriegszeit | aktiv, v2/Session 28, Cross-Estate-Validierung |
| SuGW | Strategische Wissensgenerierung | aktiv, Frontend-Meeting 17.04. integriert |
| [[Project Overview HerData]] | Webplattform historische Daten | aktiv |
| VetMedAI | KI-Kompetenzaufbau VetMedUni Wien | aktiv |
| DoCTA | Hof Herzog Sigmund, Rechnungsbücher | strategische Planung |
| [[coOCR HTR]] | Browser-basierte OCR/HTR-Experimentierumgebung | aktiv |
| [[teiCrafter]] | TEI-Annotationswerkzeug | aktiv |
| zbz-ocr-tei | OCR und TEI Zentralbibliothek Zürich | aktiv |
| [[Forschungsleitstelle MOC]] | Multi-Agent-Forschungsinfrastruktur, Sessions persistiert | aktiv |
| [[Promptotyping MOC]] | Methodologie LLM-assistierte Systementwicklung | aktiv, Paper in Arbeit |
| FemPrompt-SozArb / SocialAI | Bias und Fairness Soziale Arbeit | aktiv |
| Schliemann | Digitalisierung Rechnungsbücher | Anbahnung, Vollantrag eingereicht |
| Agentic Edition Pipeline | Editopia-Substrat, Vogeler-Ringe als Zustandsmodell | konzeptionell |

## Querkonzepte

**Epistemische Infrastruktur** — dokumentierte Anordnung aus Wissensdokumenten, Validierungspipelines, Verifikations-Workflows und Versionskontrolle, die maschinelle Ergebnisse auditierbar macht. Latour-Begründung, fünf Komponenten in [[Epistemic Infrastructure]]. Verbindendes Konzept zwischen SZD, Klawiter-Rescue, SocialAI, DIA-XAI, zbz-ocr-tei.

**Promptotyping** — Methode für LLM-assistierte Systementwicklung. Drei-Typ-Taxonomie K/P/A (Knowledge/Process/Artifact). Entsteht in der Projektpraxis, formalisiert im Paper, vermittelt in Workshops und Lehre. Jedes neue Projekt ist gleichzeitig Case Study, die das Paper erweitert.

**Editor-in-the-Loop (EIL)** — schlankes Verifikations-Protokoll für LLM-Output, in Klawiter-Rescue operationalisiert, in SZD auf Exilbriefkonvolut übertragen.

**Continuous Editorial Integration (CEI)** — formalisiert die Arbeitsedition als Methode, Lucina-Fallstudie. Paper: [[Pollin 2026 - Continuous Editorial Integration]]. Anchor: Agentic Edition Pipeline.

**Arbeitsedition** — Editionsformat im Sinne der CEI, kontinuierlich versioniert.

**Vogeler-Ringe** — Reifegrad-Modell für Editionen, in der Agentic Edition Pipeline als Zustandsmodell.

**Editopia** — Substrat für die Agentic Edition Pipeline.

**EQUALIS-Framework** — Evaluationsrahmen in DIA-XAI.

**Bookkeeping Ontology** — Modellierungsergebnis aus der Dissertation, in Cross-Estate-Kontexten weiterverwendet.

**Scholar-Centered Design / Scholar-Centered AI** — Designprinzip aus der Diss, weitergetragen in den FWF-Antrag mit Heidelberg (Cross-Model-Vergleich Frontier vs. fine-tuned).

**Asymmetric Amplification** — Begriff aus den Forum-Wissenschaft- und ÖAW-Beiträgen zu LLM-Wirkung in Wissensarbeit.

**Forschungsleitstelle** — Multi-Agent-Infrastruktur mit Lanes; Sessions als Vault-Artefakt persistiert. Die Konstellation, die wir in diesem Projekt simulieren.

## Paper-Landschaft 2026

Aktive Papers mit Venue:

- **Forum Wissenschaft (Deadline 04.05.2026)** — *Deep-Research-gestützte Literature-Reviews*, Pollin/Sackl-Sharif/Klinger, 18.000 Zeichen, FemPrompt-SozArb als Fallstudie, dualer Bewertungspfad.
- **Code4Lib Special Issue (Herbst 2026)** — *The Static Proto-Edition as Editorial Workspace*, Pollin/Zangerl/Hintersteiner, EN, 1.000–2.000 Wörter, Static Site mit Reading/Curation/Verification, SZD-HTR.
- **KIBA Workshop Villach (Deadline 14.06., Workshop 11.09.)** — *Promptotyping in Lehre und Forschungspraxis*, Experience Paper zur Informationskompetenz in Zeiten asymmetrischer Amplifikation.
- **ÖAW-Preisfrage 2026** — *How LLMs and AI Agents Are Changing Computer-Based Scholarly Work*, Pollin/Sackl-Sharif/Klinger/Steiner, EN-Essay, vier Kernkonzepte (Asymmetric Amplification, Epistemic Infrastructure, Scholar-Centered AI Literacy).

Konzeptionelle Papers via `anchor-project`:

- *Klawiter Datenrettung und Informationsvisualisierung* — anchor: DIA-XAI.
- *Continuous Editorial Integration* — anchor: Agentic Edition Pipeline. Enthält die Kernthese des aufgelösten Blinde-Stelle-Positionspapiers.
- *Kontexttransformationen in epistemischen Infrastrukturen* — anchor: FemPrompt-SozArb.
- *Gestaltungskonzepte und theoretische Fundierung für webbasierte Forschungsinterfaces* — anchor: DIA-XAI.

Concept Notes ohne Venue: [[Concept Note. Generative Interfaces in den Digital Humanities]], [[Bias Sycophancy und die Komplexität moderner LLMs]], [[DH-Benchmark für LLMs]].

## Dissertation

Pollin, *Modelling, Operationalising and Exploring Historical Information*. Kapitelstruktur: 2 DEPCHA, 3 Historical Information, 4 Modelling (Factoid, REA, Scholar-Centred, Bookkeeping Ontology), 5 Operationalising, 6 Exploring, 7 LLMs. Die ehemalige `diss.md` im Vault-Root ist nicht mehr vorhanden — Wissen vollständig in atomare Knowledge-Dokumente extrahiert: [[Bookkeeping Ontology]], [[CIDOC-CRM]], [[Factoid Model]], [[REA Model]], [[Historical Information]], [[Scholar-Centred Design]], [[DEPCHA]], [[RDF]], [[Information Visualization]], [[Coordinated Views]], [[Promptotyping]].

## Skills, Prompts, Patterns

Existierende Slash-Skills: `/curate` (Strukturelle Kuratierung), `/destill` (Vault-Synthese, Tiefenstufen shallow/deep/research), `/slides` (Folien-Produktion via Apps Script, DHCraft Design), `/active-work-update` (Status-Pflege ACTIVE-WORK).

Skill-Backlog: `/consolidate` (inhaltliche Konsolidierung von redundanten Dokumenten), `/enrich` (Anreicherung bestehender Dokumente mit externen Quellen).

Schreib-Patterns: [[Context-Engineered Academic Writing]] für kompakte Formate (Essay, Abstract, Preisausschreiben), [[Critical Collaborator for Academic Writing]] für Langformate. Beide kombinierbar. Workflow-Wahlschritt in [[Writing Prompts]].

## Sessionhistorie Frühjahr 2026

Auswahl der Sessions, die für Methoden-Reverse-Engineering am relevantesten sind:

- **2026-02-18** Kurations-Phase 1 — 10 Wissensdokumente überarbeitet, Referenz-Benchmark gesetzt.
- **2026-03 (laufend)** Kurations-Phase 2 (Dissertationsintegration) — 10 atomare Dokumente extrahiert.
- **2026-03-20** Coding-Ordner restrukturiert, 13 neue Wissensdokumente.
- **2026-03-29** SZD × DIA-XAI konsolidiert, Vorarbeiten-Strategie bestätigt.
- **2026-04-04** SZD-HTR und Agentic Edition Pipeline aufgesetzt.
- **2026-04-06** Writing-Refactoring (Patreon/+Paper&Writing/ → Writing/), KIBA Paper fertig, Blog-Strategie 2026.
- **2026-04-12** Forschungsleitstelle 5 Lanes, FWF-Antrag EN mit Heidelberg, Konzeptdokumente Knowledge Curation, Prozesstransparenz, Modell-Selbsteinschätzung.
- **2026-04-13** Bibliotheksinformatik Slides (62 Folien Apps Script v7), `/slides` Skill, DHCraft Design System, später `/destill` Skill.
- **2026-04-14** Slides-Generator als eigenes Repo `chpollin/slides-generator`.
- **2026-04-15** Paper-Sync, SUGW-Gerüste, `anchor-project` Konvention eingeführt; SZD EIL-Workflow für Exilbriefe.
- **2026-04-17** M³GIM- und SuGW-Refactoring (strategisches Projektdokument schlank, Arbeitswissen separat, Repo als Source of Truth), Museumsbund-NHM-Workshop-Vorbereitung.
- **2026-04-25** VAULT-OPERATIONS-Refactoring, ACTIVE-KNOWLEDGE archiviert und gelöscht, Hub-Triade neu kalibriert, CLAUDE-COORDINATION als Scratchpad eingeführt.
- **2026-04-26 (heute)** Drei-Claude-Team formiert, Forschungsprojekt-Frame eröffnet, Methoden-Vault aufgesetzt.

## User-Feedback-Muster

Die Memory speichert über zwölf konkrete Feedback-Muster, die Claudes wiederholt korrigiert oder bestätigt bekommen haben. Auswahl der für Multi-Claude-Kollaboration relevantesten:

- **ACTIVE-WORK-Disziplin:** Nur eigene Termine, keine fremden Einheiten, keine Zeitschätzungen, keine Google-Links, vollständige Information vor kompakter Form (User liest ACTIVE-WORK nie direkt).
- **Verifikation inhaltlich, nicht zeilenweise.** Ergebnisse prüfen (Visualisierungen, Modelle, Aggregationen), keine TODO-Checklisten.
- **Workload realistisch einschätzen.** Vorbereitungsstand prüfen statt nur Termine zählen — Claude Code ermöglicht Vorarbeit.
- **Archivierung bei Extraktion.** Wenn Inhalt vollständig in atomare Dokumente extrahiert ist, Quelldokument löschen statt archivieren.
- **Rollen statt Namen.** In Workflow- und Prozessbeschreibungen Rollen verwenden, auch bei namentlich bekannten Ko-Autor:innen.
- **Synergien-Sektion diskriminierend halten.** Zweck ist Wiederverwendung von Arbeit, nicht Ähnlichkeits-Dokumentation.
- **Deadline ungleich Tagesevent.** Datumsgleichheit zwischen Produkt-Deadline und Tagesevent ist kein Konflikt, nur zeitliche Überschneidung zählt.
- **E-Mail-Stil:** Kompakt, direkt, ohne Label-Köpfe; Selbstverortung als Leverage; Budget-Frage flippen; Kollegen als Option nennen.
- **Keine Zeitplanungen.** User plant Timing selbst.
- **GAMS ist read-only.** Lokale Repo-Klone sind der Edit-Weg, nicht GAMS oder coOCR/HTR.

## Datenschutz und Geschäftshygiene

Im Vault keine persönlichen E-Mail-Adressen, Telefonnummern, Privatanschriften Dritter — Rollen ersetzen Namen. Eigene Privatdaten als Platzhalter. Eigene Geschäftsdaten (Firma DHCraft, UID, Website) sind erlaubt. Personennamen nicht als `[[Wikilinks]]`, nur als Plaintext im Rollenkontext. Geldbeträge nicht konkret, nur Stundenkontingente, Rechnungsstatus, Förderstatus.

## Aktueller Tagesstand 2026-04-26

Gestern (2026-04-25) wurde [[VAULT-OPERATIONS]] grundlegend refactored — Aufgabentypen-Logik aus dem aufgelösten ACTIVE-KNOWLEDGE-Dokument konsolidiert, Glossar projektspezifischer Begriffe formalisiert, Forschungsprogramm-Narrativ aus dem Vault-Hub entfernt und in FWF-Antrag und Promptotyping-Paper verlagert. Außerdem [[CLAUDE-COORDINATION]] als Scratchpad für parallele Claude-Instanzen eingeführt.

Heute wurde der Drei-Claude-Frame ausgerollt: jede Instanz definiert ihre Rolle, alle drei sollen konstruktiv zusammenarbeiten, das Steuerungsdokument iterativ verbessern, und das Ganze als Methoden-Forschungsprojekt zu Multi-Claude-Kollaboration betreiben. Im Quell-Vault ist die Rolle [[VAULT-OPERATIONS#Vault-Architekt]] kanonisiert, Slot #3 in CLAUDE-COORDINATION belegt. Claude #1 (diese Instanz) ist als Wissensbringer zugeordnet. Slot #2 ist offen.

Heute wurde der Methoden-Vault `agents-working-vault` eröffnet. Erste Beiträge von Claude #1: [[Claude-1]] (kompakte Selbsteinordnung mit Sync-Vorschlag v0.1), [[Koordination]] (Bulletin-Board), und diese Notiz als volle Wissensbasis.

## Lücken im Wissen

- **Repo-Stand.** Aktueller Code-Stand der Repos M³GIM, SuGW, SZD-HTR, zbz-ocr-tei, slides-generator wird nicht im Quell-Vault gespiegelt. Aussagen dazu sind höchstens auf Stand der letzten Memory-Synchronisation (April 2026).
- **Schreibprozesse intern.** Längere Schreibarbeit (Forum Wissenschaft, ÖAW, Code4Lib, KIBA) findet in eigenen Sessions oder Critical-Collaborator-Workflows statt — Outline-Stände und Abstracts sind dokumentiert, aber nicht der laufende Textstand.
- **Person-Inhalte.** DSGVO-bedingt sind viele Kontaktdaten, Personenrollen und Geldbeträge bewusst nicht im Vault — daraus folgt: ich kenne *was* gemacht wird, aber oft nicht *mit wem genau* oder *zu welchen finanziellen Bedingungen*.
- **Fast-aktive Frontier-KI-Entwicklungen** jenseits dessen, was im Vault dokumentiert ist (z.B. neueste Modelle, EU AI Act-Updates, DPO-Updates) — nicht systematisch nachgeführt.
- **Persönlicher Kontext** des Users jenseits der Arbeitsbeziehung.

## Verweise in den Quell-Vault als Referenzanker

- [[HOME]] — Vault-Hauptindex
- [[CLAUDE]] — formale Schreib- und Strukturregeln
- [[VAULT-OPERATIONS]] — Aufgabentypen, Glossar, Rollen
- [[ACTIVE-WORK]] — Projektstand
- [[TAG-TAXONOMY]] — kontrolliertes Vokabular
- [[Paper-Writing-Index]] — Paper-Landschaft
- [[Projects MOC]] — Projektübersicht
- [[Promptotyping MOC]] — Methodologie
- [[Forschungsleitstelle MOC]] — die simulierte Konstellation
- [[Sessions MOC]] — Forschungsleitstelle-Session-Format als Vorbild für unsere Lage-Notizen
- [[Epistemic Infrastructure]] — theoretische Fundierung des Querkonzepts
- [[Applied-GenerativeAI MOC]], [[Digital-Humanities MOC]], [[Literature MOC]], [[Teaching MOC]] — thematische Einstiege
