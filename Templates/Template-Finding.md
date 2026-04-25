---
type: template
template-for: finding
created: 2026-04-26
tags: [template, schicht-4]
status: template
---

# Template-Finding

Vorlage für einen Befund in [[Findings/]] nach V7+V14b. Methodenrelevante Beobachtungen aus dem Multi-Agent-Betrieb (Konflikte, Drift, Muster). Schreibhoheit beim Finding-Autor; andere Rollen reagieren in Stellungnahmen oder Folge-Findings.

**Beim Anlegen:** Template kopieren, Frontmatter ausfüllen, `[X]`-Platzhalter ersetzen.

---

```yaml
---
type: finding
finding-date: YYYY-MM-DD
created: YYYY-MM-DD
author: [Rolle (Claude #N)]
status: aktiv  # aktiv | abgeschlossen | obsolet
adressiert-durch: [V-Item-Liste, falls vorhanden]
tags: [finding, ...]
---
```

# Finding YYYY-MM-DD - [Kurztitel]

[1-2 Sätze: Was wurde beobachtet, warum methodisch relevant.]

## Beobachtung

[Was ist konkret passiert. Wann, wer war beteiligt, welche Dateien/Items waren betroffen. Möglichst belegt mit LOG-Verweis oder Datei-Pfad+Zeile.]

## Methodische Klassifikation

[Welche Konfliktklasse (A/B/C/D nach [[Findings/2026-04-25 - Race Conditions und Strukturkonflikte]]) oder welcher Pattern-Bruch. Verbindung zu bestehenden V-Items im BACKLOG.]

## Adressierungsvorschlag

[Welche V-Items adressieren diesen Befund? Sind neue V-Items nötig? Wenn ja, kompakter Vorschlag mit Stichworten — die volle Diskussion läuft im BACKLOG.]

## Lessons Learned

1. [Konkrete methodische Lehre — möglichst handlungsorientiert.]
2. [...]

## Anschluss

- BACKLOG-Items, die diesen Befund adressieren: [V-Liste].
- Verwandte Findings: [[...]].
- Lage-Notizen, die den Befund aufgenommen haben: [[Sessions/...]].
