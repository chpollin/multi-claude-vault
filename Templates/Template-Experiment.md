---
type: template
template-for: experiment
created: 2026-04-26
tags: [template, schicht-4]
status: template
---

# Template-Experiment

Vorlage für ein Methodenexperiment in [[Experiments/]] nach V7+V14b. Gezielte Erprobung einer Methodenfrage mit Hypothese, Aufbau, Durchführung, Auswertung. Schreibhoheit beim Experiment-Autor; andere Rollen kommentieren in Stellungnahmen.

**Beim Anlegen:** Template kopieren, Frontmatter ausfüllen, `[X]`-Platzhalter ersetzen.

---

```yaml
---
type: experiment
experiment-number: N
created: YYYY-MM-DD
author: [Rolle (Claude #N)]
status: planung  # planung | durchführung | auswertung | abgeschlossen | abgebrochen
hypothese-id: [Verweis auf BACKLOG-Item oder Forschungsfrage]
tags: [experiment, ...]
---
```

# Experiment N - [Kurztitel]

[1-2 Sätze: Was wird untersucht, warum.]

## Hypothese

[Was wird geprüft. Klar formulierbar als Wenn-Dann oder Erwartung.]

## Aufbau

[Welches Setup, welche Beteiligten (Rollen), welche Files, welche Konventionen werden angewandt oder bewusst variiert. Ggf. Anti-Bedingung formulieren — was würde die Hypothese widerlegen.]

## Durchführung

[Was passiert tatsächlich. Chronologie, Beobachtungen, Abweichungen vom Aufbau.]

## Auswertung

[Hypothese bestätigt / verworfen / teilweise. Welche neuen Fragen entstehen. Welche Methode-Items werden bestätigt, in Frage gestellt, neu vorgeschlagen.]

## Anschluss

- BACKLOG-Items aus dem Experiment: [V-Liste].
- Verwandte Findings: [[...]].
- Lage-Notizen, die das Experiment einbetten: [[Sessions/...]].
