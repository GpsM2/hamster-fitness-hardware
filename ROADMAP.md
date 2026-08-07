# Roadmap

Diese Roadmap beschreibt die strategischen Produkt-Phasen von
**Hamster Fitness Hardware** — vom aktuellen DIY-Selbstbau bis zur
Deluxe-Edition mit eigenem Display. Sie ergänzt die technischen
Bauanleitungen in [README.md](README.md) und [docs/](docs/) und dient
als Übersicht, wohin sich das Projekt entwickelt.

## 1. Strategische Produkt-Phasen

### 🚀 Phase 1: Die Bastler-Edition (DIY-Starter-Kit für Familien & Maker) — AKTUELL / MVP

**Status:** ✅ Voll funktionsfähig. Fokus liegt aktuell auf
Feedback-Sammlung, Community-Aufbau (HACS) und Feinschliff der
Sensordaten-Analyse.

- **Zielgruppe:** Eltern mit Kindern, DIY-Maker, Smart-Home-Bastler
  und HACS-Early-Adopter.
- **Hardware-Basis:** günstige, frei verfügbare Standard-Komponenten:
  - Mikrocontroller: [ESP8266 (ESP-12F / D1 Mini)](https://www.az-delivery.de/products/esp8266-12e)
  - Sensorik: TCRT5000 Infrarot-Reflexionssensor (optische Erfassung,
    knabbersicher — kommt ohne Magnete aus)
  - Verkabelung: Jumper-Kabel / Breadboard / einfaches 3D-Druck-Gehäuse
- **Software & Integration:**
  - Nutzt den bereits im Hardware-Repo bereitgestellten, erprobten
    ESPHome-Code ([`esphome/hamster-wheel-sensor.yaml`](esphome/hamster-wheel-sensor.yaml)).
  - Vollständige Einbindung in Home Assistant via Auto-Discovery &
    Custom Component (HACS).

> **Die Bastler-Edition ist der primäre Einstiegspunkt ins Projekt.**
> Der vorhandene ESPHome-Code ist in erster Linie für genau dieses
> Setup (ESP8266 + TCRT5000) geschrieben und getestet — wer diese
> Teile besorgt, ist ohne Lötkenntnisse und ohne Wartezeit auf
> Custom-Hardware startklar. Eine kurze Einstiegsanleitung dazu gibt
> es im Haupt-README: [DIY Getting Started Guide](README.md#-diy-getting-started-guide-bastler-edition).

### 🏭 Phase 2: Commercial Plug-and-Play Edition (All-in-One PCB)

**Status:** 📋 In Planung.

- **Zielgruppe:** Endkunden ohne Löterfahrung oder technischen
  Hintergrund.
- **Hardware-Basis:**
  - Custom All-in-One-PCB (Turnkey PCBA via PCBWay)
  - Chip: ESP32-S3 (native Matter-Vorbereitung & erhöhte
    Rechenleistung für die direkte Darstellung der Daten auf einer
    eigenen "Webseite" auf dem Chip)
  - Integrierte Sensorik: SHT40 SMD (Klima), Reed-Kontakt
    (Deckelöffnung), IR-Kopf auf einem Board
  - Gehäuse: hamstersicheres 3D-Druck-Gehäuse mit geschützter
    interner USB-C-Kabelführung und Glasrand-Halterung

**Meilensteine:**

- [ ] Schaltplan & Layout für das All-in-One-PCB (KiCad, [`pcb/`](pcb/))
- [ ] Turnkey-PCBA-Fertigungsauftrag (PCBWay) inkl. Bestückung
- [ ] Portierung/Erweiterung der ESPHome-Konfiguration auf ESP32-S3
      sowie Anbindung der zusätzlichen Sensorik (SHT40, Reed-Kontakt)
- [ ] Gehäusedesign mit geschützter USB-C-Kabelführung und
      Glasrand-Halterung ([`cad/`](cad/))
- [ ] Beta-Testphase mit Community-Testern

### 💎 Phase 3: Deluxe Standalone Edition

**Status:** 💭 Konzept / Ausblick.

- **Hardware:** integriertes, blendfreies E-Paper-/E-Ink-Display
  direkt am Gehege — zeigt die wichtigsten Werte (z. B. Distanz,
  Geschwindigkeit) an, ganz ohne dafür Home Assistant öffnen zu
  müssen.

**Meilensteine:**

- [ ] Auswahl E-Paper-/E-Ink-Panel (Größe, Auflösung, Ansteuerung)
- [ ] Energiebudget/Stromversorgung für ein dauerhaft aktives Display
- [ ] UI-Konzept für die Displaydarstellung
- [ ] Gehäuseanpassung für blendfreie Display-Integration

---

## 2. Einordnung

Alle drei Phasen teilen sich dieselbe Datenbasis: ESPHome auf dem
Mikrocontroller → Home Assistant → [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).
Phase 2 und 3 bauen auf den in Phase 1 etablierten Sensor-Prinzipien
auf und ersetzen Schritt für Schritt Breadboard/Jumper-Kabel durch
integrierte, endkundentaugliche Hardware — die Bastler-Edition bleibt
dabei als günstiger, offener Selbstbau-Weg erhalten.
