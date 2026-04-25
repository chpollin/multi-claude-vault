---
type: research-mission
created: 2026-04-25
tags: [meta, mission]
status: active
---

# MISSION

## Forschungsfrage

Wie arbeiten parallele Claude-Instanzen sinnvoll in einem geteilten Wissens- und Arbeitsraum zusammen? Konkret: Welche Strukturen, Rituale und Prompt-Engineering-Konventionen ermöglichen produktive, redundanzfreie und konfliktarme Multi-Agent-Kollaboration auf einem Obsidian-Vault?

## Scope

- Identitäts- und Rollenmodell für parallele Instanzen.
- Synchronisationsmechanismen auf vier Ebenen: Identität, Mission/Methode, aktiver Stand, Konfliktvermeidung.
- Kontextinformations-Austausch zwischen Instanzen — was wird geteilt, in welcher Form, in welcher Granularität.
- Sessionstart-, Pre-Edit-, Sessionende-Rituale.
- Konfliktauflösung und Eskalationsmechanismen.
- Output: dokumentierte Methode in METHOD.md, übertragbar auf andere Vault-Setups.

## Nicht-Ziele

- Keine inhaltliche Kuration des Lesevaults — der bleibt unangetastet.
- Keine allgemeine Theorie der Multi-Agent-Architektur unabhängig vom Vault-Setup.
- Keine Re-Implementierung der Forschungsleitstelle-Spezifikation, sondern *Simulation* an unserem eigenen Setup.

## Anschluss an die Forschungsleitstelle

Die Forschungsleitstelle (Lesevault: `Projects/Forschungsleitstelle/Forschungsleitstelle MOC`) formalisiert Multi-Agent-Koordination als Methode. Unsere Simulation liefert Validierungsmaterial: Was funktioniert in der Spezifikation, was bricht, was fehlt? Befunde werden für die Spezifikation v0.5+ aufbereitet.

## Erfolgskriterien

- Drei Instanzen koordinieren sich über mehrere Sessions hinweg ohne wiederholten User-Eingriff in operative Details.
- Konflikte werden detektiert und sauber eskaliert, nicht stillschweigend überschrieben.
- METHOD.md enthält am Projektende eine Methode, die eine vierte neu eintretende Claude-Instanz allein durch Lesen des Vaults verstehen und anwenden kann.
