---
type: template
template-for: sugw-verifikation
created: 2026-04-26
tags: [template, sugw, verifikation]
status: template
---

# Template-sugw-Verifikation

Zwei Varianten: V-Verifikation (Tech, von Claude A) und S-Verifikation (Stakeholder, von Claude B). Beide sind User-orientierte Anleitungen — was zu testen, wo, wie.

**Beim Anlegen:** Template kopieren, eine der zwei Sektionen unten als Basis nehmen, restliche löschen, ausfüllen.

---

## Variante A — V-Verifikation (Tech, pro V-ID)

Ablage: `Project/sugw-Verifikation/V[N]-Verifikation.md`

```yaml
---
type: knowledge
verifikations-doc-für: V[N]
created: YYYY-MM-DD
tags: [sugw, verifikation]
status: ready-for-user  # ready-for-user | bestätigt-vom-user | korrektur-nötig
author: "Claude A (Subagent)"
---
```

# V[N]-Verifikation — [Kurztitel]

## Was wurde geändert

[Datei-Liste mit Diff-Stichworten, Commit-Hashes auf Branch frontend-rework-2026-04 im Pipeline-Repo.]

| Datei | Art der Änderung | Commit |
|---|---|---|
| [Pfad] | [hinzugefügt/geändert/entfernt] | [hash] |

## Adressierte Stakeholder-Issues

- **S[N]** — [Aussagen-Auszug]
- **S[N]** — [Aussagen-Auszug]

## Test-Schritte für den User

**Voraussetzung:** Beide Server laufen lokal:
- Original: `http://127.0.0.1:8765/`
- Neu: `http://127.0.0.1:8766/`

**Schritt 1:** [Aktion am Original-Frontend]
- URL: `http://127.0.0.1:8765/[pfad]`
- Beobachtung: [was IST-Zustand zeigt]

**Schritt 2:** [Aktion am neuen Frontend]
- URL: `http://127.0.0.1:8766/[pfad]`
- Erwartung: [was sich unterscheiden sollte]

**Schritt 3:** [ggf. weitere Aktion zum direkten Vergleich]

## Akzeptanzkriterien-Check

Aus [[Project/sugw-Vorschläge/V[N] - [Titel]]]:

- [x] [Kriterium 1] — Beleg: [URL/Screenshot/Test-Output]
- [x] [Kriterium 2] — Beleg: …
- [ ] [Kriterium 3] — offen, Begründung: …

## Bekannte Limits / Folge-Issues

- [Was wurde nicht abgedeckt]
- [Was kommt in späterer Iteration]

## Anschluss

- Vorschlag: [[Project/sugw-Vorschläge/V[N] - [Titel]]]
- Stakeholder-Sicht: [[Project/sugw-Verifikation/S[N]-Verifikation]]
- Verifikations-Master: [[Project/sugw-Verifikations-Master]]

---

## Variante B — S-Verifikation (Stakeholder-Mapping, pro S-ID)

Ablage: `Project/sugw-Verifikation/S[N]-Verifikation.md`

```yaml
---
type: knowledge
verifikations-doc-für: S[N]
adressiert-durch: [V[N], V[N]]
created: YYYY-MM-DD
tags: [sugw, verifikation, stakeholder]
status: ready-for-user
author: "Claude B (Subagent)"
---
```

# S[N]-Verifikation — [Stakeholder-Anliegen kurz]

## Stakeholder-Aussage

> [Wörtliches Zitat aus Protokoll oder Slide, mit Quelle.]

Quelle: [Protokoll-Abschnitt | Slide N | beide]

## Was sollte sich für den Stakeholder unterscheiden

[1–2 Sätze in einfacher Sprache: was war das Problem, was ist nun anders.]

## Test aus Stakeholder-Sicht

In Stakeholder-Sprache (kein Tech-Jargon). Der Stakeholder soll selbst verifizieren können.

**Was du brauchst:** Browser, ggf. zwei Tabs nebeneinander.

**Schritt 1:** Öffne das alte Frontend unter `http://127.0.0.1:8765/[pfad]`. Du siehst dort: [was].

**Schritt 2:** Öffne das neue Frontend unter `http://127.0.0.1:8766/[pfad]`. Du solltest dort sehen: [was — Unterschied benannt].

**Schritt 3:** [Spezifische Aktion, z.B. "Suche nach 'Pilgrim' im Personen-Index". Erwartung: …]

## Adressierende V-IDs (technische Details)

- [[Project/sugw-Verifikation/V[N]-Verifikation]] — [was diese V-ID adressiert hat]

## Wenn die Verifikation fehlschlägt

[Was tun: User-Feedback in welche Richtung erwarten, wer kontaktieren, in welche Datei eintragen.]

## Anschluss

- Stakeholder-Issue: [[Findings/2026-04-26 - sugw Stakeholder-Feedback#S[N]]]
- Tech-Verifikation: [[Project/sugw-Verifikation/V[N]-Verifikation]]
- Verifikations-Master: [[Project/sugw-Verifikations-Master]]
