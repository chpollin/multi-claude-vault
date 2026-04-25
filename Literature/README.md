---
type: vault-resource
created: 2026-04-26
tags: [literature, bibliography]
status: active
---

# Literature

Annotated bibliography. Externe Forschungsliteratur, gegen die unsere Methode argumentiert. Pro Werk ein Dokument im Lesevault-Konvention-Format.

## Konvention

**Dateiname:** `Author Year - Kurztitel.md` (z.B. `Wu 2023 - AutoGen.md`, `Dourish Bellotti 1992 - Awareness and Coordination.md`).

**Frontmatter:**
```yaml
---
type: literature
authors: [Wu Q., et al.]
year: 2023
venue: Microsoft Research
created: YYYY-MM-DD
tags: [forschungsfeld-tag-1, forschungsfeld-tag-2]
status: stub | annotated | reviewed
---
```

**Dokumentstruktur:**
1. `# Author Year - Title` (Vollreferenz)
2. `## Volltext-Referenz` mit DOI/URL falls verfügbar
3. `## Kernargument` (1–3 Absätze, kompakt)
4. `## Schlüssel-Konzepte` (Liste der zentralen Begriffe für die eigene Argumentation)
5. `## Bezug zur Multi-Claude-Methode` (warum lesen wir das, was nehmen wir mit)
6. `## Querverweise` (`[[Knowledge/...]]`-Links zu eigenen Synthesen)

## Verhältnis zu Knowledge/ und Concepts/

Drei verwandte, klar unterschiedene Klassen:

- **Knowledge/** — eigene Wissenssynthesen über Forschungsfelder, integrieren mehrere Quellen.
- **Literature/** (hier) — externe Quellen pro Werk, annotated bibliography.
- **Concepts/** — Lesevault-Extrakte mit Reflux-Verboten (Schicht 5, V19 Konsens pendent).

Eine Literature-Datei zitiert man aus Knowledge-Synthesen via `[[Author Year - Title]]`. Knowledge-Synthese benennt 4–6 Schlüssel-Literature-Stubs unter `## Sources`.

## Erste Welle (priorisiert nach [[Multi-Claude Theoretical Framework]])

Die folgenden Stubs sind als Top-15-Welle priorisiert; Anlage erfolgt sukzessive bei Bedarf.

- Wu 2023 - AutoGen
- Hong 2023 - MetaGPT
- Park 2023 - Generative Agents
- Wooldridge 2009 - An Introduction to MultiAgent Systems
- Dourish Bellotti 1992 - Awareness and Coordination in Shared Workspaces
- Gutwin Greenberg 2002 - A Descriptive Framework of Workspace Awareness
- Malone Crowston 1994 - The Interdisciplinary Study of Coordination
- Schmidt Bannon 1992 - Taking CSCW Seriously
- Lamport 1978 - Time Clocks and the Ordering of Events
- Shapiro 2011 - Conflict-Free Replicated Data Types
- Hevner 2004 - Design Science in Information Systems Research
- Schön 1983 - The Reflective Practitioner
- Horvitz 1999 - Principles of Mixed-Initiative User Interfaces
- Madaan 2023 - Self-Refine
- Shinn 2023 - Reflexion

## Anschluss

- [[Knowledge/Multi-Claude Theoretical Framework]] — sieben Forschungsfelder mit Schlüssel-Referenzen.
- [[METHOD]] — ratifizierte Methode (Schicht 1).
- [[MISSION]] — Forschungsfrage, Scope.
