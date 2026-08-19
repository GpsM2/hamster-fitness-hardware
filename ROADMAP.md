# Roadmap

This roadmap describes the strategic product phases of
**Hamster Fitness Hardware** — from the current DIY build to a deluxe
edition with its own display. It complements the technical build
guides in [README.md](README.md) and [docs/](docs/) and serves as an
overview of where the project is headed.

## 1. Strategic product phases

### 🚀 Phase 1: The DIY Edition (DIY starter kit for families & makers) — CURRENT / MVP

**Status:** ✅ Fully functional. Current focus is on gathering
feedback, growing the community (HACS), and refining the sensor data
analysis.

- **Target audience:** parents building with their kids, DIY makers,
  smart-home hobbyists, and HACS early adopters.
- **Hardware base:** cheap, widely available standard components:
  - Microcontroller: ESP8266 (ESP-12F / D1 Mini) — see the
    [parts list](docs/diy-edition-parts-list.md) for sources
  - Sensor: TCRT5000 infrared reflective sensor (optical detection,
    chew-safe — no magnets needed)
  - Wiring: jumper wires / breadboard / simple 3D-printed enclosure
- **Software & integration:**
  - Uses the proven ESPHome code already provided in this repo
    ([`esphome/hamster-wheel-sensor.yaml`](esphome/hamster-wheel-sensor.yaml)).
  - Full integration into Home Assistant via auto-discovery & a
    custom component (HACS).

> **The DIY Edition is the primary entry point into the project.**
> The existing ESPHome code is written and tested first and foremost
> for exactly this setup (ESP8266 + TCRT5000) — get these parts and
> you're up and running with no soldering skills and no wait for
> custom hardware. See the main README for a short walkthrough:
> [DIY Getting Started Guide](README.md#-diy-getting-started-guide-diy-edition).

### 🏭 Phase 2: Commercial Plug-and-Play Edition (all-in-one PCB)

**Status:** 📋 Planned — tracked as issues in the
[hamster-fitness-product](https://github.com/GpsM2/hamster-fitness-product)
repo, milestone
["Phase 2: Plug-and-Play Edition"](https://github.com/GpsM2/hamster-fitness-product/milestone/1).

- **Target audience:** end customers with no soldering experience or
  technical background.
- **Hardware base:** custom all-in-one PCB (turnkey PCBA via PCBWay,
  chip: [ESP32-S31](https://www.espressif.com/en/products/socs/esp32-s31)),
  SHT40 climate sensor and a reed contact for lid detection on the main
  board, an IR head relocated onto its own adjustable mount, and a
  hamster-safe 3D-printed enclosure. Still just **one** PCB and no loose
  wiring.

### 💎 Phase 3: Deluxe Standalone Edition

**Status:** 💭 Concept / outlook — tracked as issues in the
[hamster-fitness-product](https://github.com/GpsM2/hamster-fitness-product)
repo, milestone
["Phase 3: Deluxe Standalone Edition"](https://github.com/GpsM2/hamster-fitness-product/milestone/2).

- **Hardware:** an integrated, glare-free E-paper/E-ink display right
  on the enclosure — shows the key stats (e.g. distance, speed)
  without needing to open Home Assistant.

---

## 2. How the phases relate

All three phases share the same data path: ESPHome on the
microcontroller → Home Assistant → [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).
Phases 2 and 3 build on the sensing principles established in Phase 1
and progressively replace breadboard/jumper wiring with integrated,
consumer-ready hardware — the DIY Edition remains available as the
cheap, open, build-it-yourself path.
