---
type: methode-draft
created: 2026-04-26
updated: 2026-04-26
version: 0.1
author: Claude #3 (Inhalt)
status: outline
tags: [forschungsliteratur, theoretical-framework, paper, methode]
---

# Multi-Claude Theoretical Framework

Theoretischer Rahmen für die Multi-Claude-Vault-Kollaborations-Methode. Zentrales Wissensdokument, das die Methode in der Forschungsliteratur verankert und die wissenschaftliche Argumentation für Phase D (Paper) trägt. Synthese aus sieben Forschungsfeldern — jedes Feld liefert Begriffe, Befunde oder Frameworks, an denen unsere Methode anschließt oder sich abgrenzt.

Klassenzuordnung: Methoden-Draft, Status `outline` (Schicht 3, eigene Schreibhoheit), bei Phase-D-Reife migriert in Lesevault `Writing/Paper/` als Sektion "Verwandte Arbeit". Strukturarbeiter-Übergabe für eigenständigen `Knowledge/`-Ordner und `Literature/`-Ordner liegt in [[COORDINATION#Übergaben]] (#3→#2).

**Lesevault-Anschluss:** [[Wissensbasis Lesevault]] hat eigene Knowledge/Literature-Konvention (`Literature/Author Year - Title.md`, `Knowledge/Konzept Name.md`); wir übernehmen diese Konvention 1:1, sobald [[METHOD]] um Schicht-Knowledge/Literature ergänzt ist (V19-Concepts-Schicht-verwandt, aber distinct: Concepts = Lesevault-Extraktion, Knowledge/Literature hier = externe Forschungsliteratur).

## 1. Multi-Agent-Systeme und LLM-Multi-Agent-Frameworks

**Anschluss:** Unsere Methode ist eine spezielle Form von LLM-Multi-Agent-Koordination — drei Top-Level-Instanzen plus optional Subagents (V15), die über einen geteilten Vault-State eventually consistent koordinieren. Abgrenzung zu klassischen MAS-Frameworks: kein zentraler Orchestrator (User ist Bus, nicht Master), kein Message-Passing (sondern File-basierte Bulletin-Boards), keine vordefinierten Protokolle (Methode emergiert).

**Schlüssel-Referenzen:**
- Wooldridge, M. (2009). *An Introduction to MultiAgent Systems*. — Klassisches MAS-Lehrbuch, BDI-Architekturen.
- Wu, Q. et al. (2023). *AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation*. Microsoft Research. — LLM-Multi-Agent-Framework, Ko-Konversation.
- Hong, S. et al. (2023). *MetaGPT: Meta Programming for a Multi-Agent Collaborative Framework*. — Rollen-basierte LLM-Kollaboration.
- Qian, C. et al. (2023). *Communicative Agents for Software Development* (ChatDev). — LLM-Agents in spezialisierten Rollen.
- Park, J.S. et al. (2023). *Generative Agents: Interactive Simulacra of Human Behavior*. — Memory, Reflection, Planning in LLM-Agenten.
- Anthropic (2024). *Building Effective Agents*. — Engineering-Patterns für Tool-Use-Agenten.

**Argumentation für Paper:** Wir reihen uns ein in die LLM-Multi-Agent-Forschung 2023+, unterscheiden uns aber durch (a) menschlich-zentriertes Design (User als Synchronisationsbus statt automatisierte Agent-zu-Agent-Kommunikation), (b) Vault-State als Substrat (klassische MAS nutzen Message-Passing oder Shared Memory; wir nutzen versionierte Markdown-Files mit Pre-Edit-Read), (c) emergente Methode statt vordefiniertes Protokoll.

## 2. CSCW (Computer-Supported Cooperative Work)

**Anschluss:** Unsere Methode ist im Kern CSCW — wir lösen klassische Awareness-, Coordination- und Articulation-Work-Probleme für nicht-menschliche Akteure. COORDINATION-Slots = Workspace Awareness (wer-tut-was-wo); BACKLOG-Stellungnahmen = Coordination Mechanism; Lage-Notizen = Common Information Space; Stellungnahmen-Schreibhoheit (V20) = Articulation Work explizit gemacht.

**Schlüssel-Referenzen:**
- Dourish, P., & Bellotti, V. (1992). *Awareness and Coordination in Shared Workspaces*. CSCW. — Foundational Awareness-Konzept.
- Gutwin, C., & Greenberg, S. (2002). *A Descriptive Framework of Workspace Awareness*. CSCW Journal. — Workspace Awareness operationalisiert.
- Malone, T.W., & Crowston, K. (1994). *The Interdisciplinary Study of Coordination*. ACM Computing Surveys. — Coordination Theory.
- Schmidt, K., & Bannon, L. (1992). *Taking CSCW Seriously: Supporting Articulation Work*. CSCW Journal. — Articulation Work als Forschungsobjekt.
- Bannon, L., & Bødker, S. (1997). *Constructing Common Information Spaces*. ECSCW. — CIS-Konzept als Vorbild für unsere Lage-Notizen.

**Argumentation für Paper:** Multi-Claude-Vault-Kollaboration ist CSCW-Forschung mit nicht-menschlichen Akteuren. Klassische Awareness-Konzepte (peripheral awareness, action awareness) lassen sich übertragen, einige verschieben sich: Awareness ist hier *eventually consistent* statt *real-time*; Articulation Work wird durch V20 zu einer Pflicht, nicht nur einer impliziten Praxis.

## 3. Distributed Systems und Konfliktauflösung

**Anschluss:** Pre-Edit-Read (V6) ist optimistic concurrency control. "Modified since read"-Detection entspricht einem Lamport-Logical-Clock-Vergleich pro Datei. Stellungnahmen-Schreibhoheit (V20) als Identitätsakt entspricht der Provenance-Metadaten-Diskussion in Distributed Knowledge Bases.

**Schlüssel-Referenzen:**
- Lamport, L. (1978). *Time, Clocks, and the Ordering of Events in a Distributed System*. CACM. — Logische Uhren als Erklärungsrahmen für V6.
- Ellis, C.A., & Gibbs, S.J. (1989). *Concurrency Control in Groupware Systems*. SIGMOD. — Operational Transformation, Vorbild für Edit-Konflikt-Behandlung.
- Shapiro, M. et al. (2011). *Conflict-Free Replicated Data Types*. — CRDTs als Alternative zu OT, Bezug zu eventually consistent Vault-State.
- Sun, C., & Ellis, C. (1998). *Operational Transformation in Real-Time Group Editors*. CSCW. — OT-Theorie für kollaborative Editoren.

**Argumentation für Paper:** Wir nutzen pragmatisch optimistic concurrency control (V6) ohne formales Konfliktauflösungs-Framework wie OT/CRDTs. Das funktioniert bei drei Instanzen + niedriger Konflikt-Frequenz; Skalierung (V16) zeigt die Grenze. Theoretischer Beitrag: V20 als CRDT-analog für *Identity-Provenance-Konflikte* (Stellungnahmen sind Identitätsakte, nicht nur Daten).

## 4. Methodologie reflexiver Methodenentwicklung

**Anschluss:** Selbstreferentielles Setup — wir entwickeln eine Methode für Multi-Claude-Vault-Kollaboration, indem wir sie anwenden. Methodenmotor (BACKLOG → METHOD nach Konsens) entspricht Design Science Research Iterations-Loop. Falldaten-Korpus + Validation-Loop (V17) sind Action-Research-Pattern. Reflective Practice (Schön) als Metaebene jeder Rolle.

**Schlüssel-Referenzen:**
- Hevner, A. et al. (2004). *Design Science in Information Systems Research*. MIS Quarterly. — DSR-Framework, anwendbar auf Methodenentwicklung.
- Peffers, K. et al. (2007). *A Design Science Research Methodology for Information Systems Research*. JMIS. — DSR-Iterationen.
- Susman, G., & Evered, R. (1978). *An Assessment of the Scientific Merits of Action Research*. ASQ. — Action-Research-Zyklus.
- Schön, D.A. (1983). *The Reflective Practitioner*. — Reflexive Praxis als Methodenfundament.
- Gioia, D.A. et al. (2013). *Seeking Qualitative Rigor in Inductive Research*. ORM. — Gioia-Methodologie für induktive Theoriebildung aus Falldaten.

**Argumentation für Paper:** Methodischer Beitrag = die Methode *plus* die methodologische Innovation, sie selbstreferentiell zu entwickeln. Das ist nicht trivial: drei LLM-Instanzen entwickeln eine Methode für ihre eigene Kollaboration durch Anwenden. Falldaten ([[Findings/2026-04-25 - Bootstrap und Rollenwechsel]], [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]]) sind Empirie der Methode auf sich selbst.

## 5. Mixed-Initiative AI-Human-Collaboration

**Anschluss:** User als Bus (Schicht 6 in [[Sync-Stack-Patterns]]), Eskalations-Schwelle in drei Stufen ([[Beobachtung Claude-1]]), Anfrage-an-User-Pattern ([[prompt-engineering-patterns#Anfrage an User bei wichtigen Entscheidungen]]) sind operationalisierte Mixed-Initiative. User entscheidet bei Strategie/Scope/Architektur, Instanzen entscheiden autonom bei operativen Details.

**Schlüssel-Referenzen:**
- Horvitz, E. (1999). *Principles of Mixed-Initiative User Interfaces*. CHI. — Foundational Mixed-Initiative-Prinzipien.
- Allen, J.E. et al. (1999). *Mixed-Initiative Interaction*. IEEE Intelligent Systems. — Spektrum von menschlich- bis system-initiierter Aktion.
- Brynjolfsson, E. (2022). *The Turing Trap*. Daedalus. — AI-Augmentation vs. Automation.
- Anthropic (2024). *Constitutional AI: Harmlessness from AI Feedback*. — Self-Critique als Eskalations-Mechanismus.

**Argumentation für Paper:** Multi-Claude-Vault-Kollaboration ist nicht autonomer Multi-Agent (alle Entscheidungen autonom), sondern Mixed-Initiative — User behält strategische Kontrolle, Instanzen tragen operative Last. Das macht das Setup *für Wissensarbeit* tauglich, wo Auto-Mode oft zu Drift führt.

## 6. Personal Knowledge Management und Vault-Patterns

**Anschluss:** Obsidian als Substrat für Multi-Agent-Arbeit ist Erweiterung der PKM-Tradition. Zettelkasten-Atomarität (one concept = one note) übernehmen wir aus dem Lesevault. STRUCTURE V7 (Vier-Schichten + Concepts via V19) ist Vault-Topologie für Multi-Agent-Setting.

**Schlüssel-Referenzen:**
- Luhmann, N. (1981). *Kommunikation mit Zettelkästen*. — Zettelkasten als Knowledge-Tool.
- Forte, T. (2022). *Building a Second Brain*. — Modernes PKM-Framework (PARA, CODE).
- Ahrens, S. (2017). *How to Take Smart Notes*. — Atomic Notes, Slip-Box-Method.
- Whittaker, S., & Sidner, C. (1996). *Email Overload*. CHI. — Personal Information Management Forschung.

**Argumentation für Paper:** Vault als Substrat ist nicht trivial gewählt — Markdown + Wikilinks + Frontmatter erlauben *menschlich lesbare* Multi-Agent-Koordination. Der User kann jederzeit den Stand der Methode lesen, ohne durch Logs oder Datenbanken zu navigieren. Kontrast zu Black-Box-Multi-Agent-Frameworks.

## 7. Prompt Engineering und Promptotyping als Methode

**Anschluss:** [[Prompt-Engineering-Patterns]] sind unsere Pattern-Bibliothek; Promptotyping (Pollin, Lesevault) ist die Meta-Methode für Methoden-Entwicklung mit LLMs. K/P/A-Taxonomie (Knowledge/Process/Artifact) lässt sich auf unsere Schichten abbilden.

**Schlüssel-Referenzen:**
- Pollin, C. (2026). *Promptotyping: A Method for AI-Assisted Workflow Design*. (Lesevault-Doku, in Phase D als Citable-URL). — K/P/A-Taxonomie.
- Wei, J. et al. (2022). *Chain-of-Thought Prompting Elicits Reasoning in Large Language Models*. NeurIPS. — Chain-of-Thought als Pattern.
- Madaan, A. et al. (2023). *Self-Refine: Iterative Refinement with Self-Feedback*. NeurIPS. — Self-Refinement Pattern, Bezug zu Validation-Loop V17.
- Shinn, N. et al. (2023). *Reflexion: Language Agents with Verbal Reinforcement Learning*. — Reflection-Pattern, Bezug zu [[Beobachtung Claude-1]].
- Wang, L. et al. (2024). *A Survey on Large Language Model based Autonomous Agents*. — Überblicksartikel zu LLM-Agents.

**Argumentation für Paper:** Prompt Engineering ist nicht Werkzeug, sondern Substanz unserer Methode — Patterns wie Sessionstart, Übergabe, Stellungnahme, Konflikt-Eskalation sind Prompt-Strukturen, die durch Markdown-Konventionen reproduzierbar gemacht werden. Promptotyping als Lesevault-Konzept liefert die Meta-Methode.

## Querkonzept: Epistemische Infrastruktur

**Anschluss zum Lesevault:** Das Querkonzept *Epistemische Infrastruktur* (Lesevault, verbindet zbz-ocr-tei, SZD, SocialAI, DIA-XAI) gilt auch hier — dieser Vault *ist* epistemische Infrastruktur für die Methode, die er entwickelt. Selbstreferenz dritter Ordnung.

## Synthese-Argumentation für das Paper

Sechs zentrale Argumente, die das Theoretical Framework für Phase D liefert:

1. **Setting-Lokalisierung:** Wir reihen uns ein in LLM-Multi-Agent-Forschung 2023+ (Sektion 1), unterscheiden uns durch CSCW-Erbe (Sektion 2) und Mixed-Initiative-Anker (Sektion 5).
2. **Theoretischer Beitrag:** Eventually consistent Methodenentwicklung mit File-basiertem State (Sektion 3) — V6 als pragmatische Konfliktdetektion, V20 als Identity-Provenance-CRDT.
3. **Methodologischer Beitrag:** Selbstreferentielle Methodenentwicklung im DSR/Action-Research-Stil (Sektion 4) — Methode entsteht durch Anwendung auf sich selbst.
4. **Empirischer Beitrag:** Falldaten-Korpus aus Bootstrap, Race Conditions, Reassignment-Drift, Architekt-Bias, Stellungnahmen-Schreibhoheit (Sektionen 1+2+3).
5. **Praktischer Beitrag:** Vault als menschlich lesbares Substrat für Multi-Agent-Koordination (Sektion 6) — Kontrast zu Black-Box-Frameworks.
6. **Methodenkanon:** Prompt-Engineering-Patterns als reproduzierbare Strukturen (Sektion 7) — verbindet Promptotyping (Lesevault-Konzept) mit operationalisierten Multi-Agent-Konventionen.

## Anschluss

- [[Findings/2026-04-25 - Bootstrap und Rollenwechsel]] — Empirie für Sektion 4 (Falldaten + reflexive Methodenentwicklung).
- [[Sync-Stack-Patterns]] — Methoden-Substanz für Sektionen 2 (CSCW) und 3 (Distributed Systems).
- [[Cross-Vault-Methodik]] — Cross-Vault-Asymmetrie als CSCW-Common-Information-Space-Ausprägung.
- [[Prompt-Engineering-Patterns]] — Patterns für Sektion 7.
- [[Wissensbasis Lesevault]] — Anschluss an Forschungsleitstelle, Promptotyping, epistemische Infrastruktur.
- [[BACKLOG]] V19 (Concepts-Schicht) — Mechanismus für Lesevault-Konzept-Extraktion (Promptotyping als erster Knoten).
- ROADMAP Phase D — Paper-Anbindung.

## Offene Fragen

- **Knowledge/-Ordner-Anlage:** STRUCTURE-Domäne (#2). Übergabe #3→#2 in COORDINATION setzt das in Bewegung. Bis dahin lebt dieses Doc provisorisch im Root.
- **Literature/-Ordner mit annotated bibliography:** brauchen wir 15–20 Author-Year-Title-Stubs als zitierfähige Basis. Anlage zusammen mit Knowledge/. Erste Welle (Top-10): siehe Sektionen 1, 2, 4, 7.
- **Erstwelle der eigentlichen Knowledge-Synthesen:** welche der sieben Sektionen wird zuerst zu eigenständigem Knowledge-Doc ausgearbeitet? Empfehlung: Sektion 2 (CSCW-Foundations) und Sektion 4 (Reflexive Method Development) als zentrale theoretische Anker, weil sie die methodologische Argumentation tragen.
- **Tiefenniveau:** soll dieses Doc als ein einziges integriertes Wissensdokument bleiben, oder werden die sieben Sektionen jeweils zu eigenen `Knowledge/<Thema>.md` aufgeteilt? Letzteres entspricht atomarem Zettelkasten-Prinzip aus dem Lesevault, ersteres bleibt als integratives MOC bestehen. Empfehlung: beides — dieses Doc als MOC, plus sieben atomare Knowledge-Docs (sobald `Knowledge/` von #2 angelegt).
- **Verhältnis zu Concepts-Schicht (V19):** Concepts/ ist Lesevault-Extraktion (Forschungsleitstelle, Promptotyping, anchor-project); Knowledge/Literature ist externe Forschungsliteratur. Beide sind Schicht-1-/-2-Ressourcen, parallel und distinkt.
