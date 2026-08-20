# Hamster Fitness Hardware – Projektregeln für Claude

Diese Datei enthält verbindliche Arbeitsanweisungen für Claude in diesem
Repository.

## Scope dieses Repos (STRIKT EINHALTEN)

Dieses Repository (`hamster-fitness-hardware`) verwaltet **ausschließlich**:

- ESPHome-Firmware (`esphome/`),
- CAD-/3D-Druck-Dateien (`cad/`: OpenSCAD, STL, STEP),
- Platinen-/Schaltplan-Dateien (`pcb/`: z. B. KiCad),
- Bauanleitungen und Stücklisten (`docs/`).

Der Python-Code der Home-Assistant-Integration, die Lovelace-Karten und
die Software-Tests gehören **nicht** hierher, sondern ins separate Repo
[ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).
Falls eine Anfrage Software-/Integrations-Code in diesem Repo anlegen
oder ändern würde, bitte nachfragen statt es hier einzufügen – vermutlich
gehört es ins Software-Repo.

## Workflow

- Änderungen nicht direkt auf `main` committen. Für jede nichttriviale
  Änderung einen neuen Branch erstellen (`git checkout -b <kurzer-branch-name>`)
  und einen Pull Request öffnen.
- Commit-Messages beschreiben das "Warum", nicht nur das "Was".

## Release-Regel (STRIKT EINHALTEN)

Sobald ein Befehl zur Erstellung eines Releases oder Git-Tags erteilt
wird, MUSS Claude den Nutzer zuerst explizit fragen:

> „Soll dieses Release als Beta-Version (Pre-release z. B. v1.0.0-beta.1)
> für Tester oder als finale Standard-Release (z. B. v1.0.0)
> veröffentlicht werden?“

Kein Release/Tag wird erstellt, bevor diese Frage gestellt und eindeutig
beantwortet wurde – unabhängig davon, wie der ursprüngliche Befehl
formuliert war.
