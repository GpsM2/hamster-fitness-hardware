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

**Status:** 📋 Planned.

- **Target audience:** end customers with no soldering experience or
  technical background.
- **Hardware base:**
  - Custom all-in-one PCB (turnkey PCBA via PCBWay)
  - Chip: [ESP32-S31](https://www.espressif.com/en/products/socs/esp32-s31)
    (Wi-Fi 6, Bluetooth 5.4, and native 802.15.4 for Thread/Zigbee —
    a genuine Matter/Thread foundation — plus significantly more
    compute for rendering the data directly on its own "web page" on
    the chip. Not yet available per Espressif, which fits this
    phase's "planned" status.)
  - Sensors on the main PCB: SHT40 SMD (climate) and a reed contact
    (lid-open detection) — the board sits right in the glass-rim
    mount for this, so it's outside the bedding and needs no extra
    cable to the lid
  - IR head: relocated onto an adjustable mount close to the wheel,
    connected to the main PCB by a short protected cable — still
    just **one** PCB and no loose wiring
  - Enclosure: hamster-safe 3D-printed housing with protected internal
    USB-C cable routing, a rattle-free glass-rim mount (felt pads as
    spacers), and a telescoping IR arm

**Milestones:**

- [ ] Schematic & layout for the all-in-one PCB (KiCad, [`pcb/`](pcb/))
- [ ] Turnkey PCBA manufacturing order (PCBWay), assembled
- [ ] Port/extend the ESPHome config to the ESP32-S31 and wire up the
      additional sensors (SHT40, reed contact)
- [ ] Adjustable mount for the IR head (telescoping/rail mechanism,
      at least 2 axes: distance to the wheel + height) — accommodates
      different cage sizes, wheel positions, and changing bedding
      depth without tools
- [ ] Short, protected cable between the IR head and the main PCB,
      routed inside the mount instead of exposed (chew safety)
- [ ] Rattle-free glass-rim mount for the main PCB: adjustable clamp
      for different glass thicknesses, felt pads as spacers against
      both glass and enclosure
- [ ] Magnet-holder counterpart for the reed contact, clip- or
      stick-on for the movable lid
- [ ] Protected internal USB-C cable routing ([`cad/`](cad/))
- [ ] Beta testing phase with community testers

### 💎 Phase 3: Deluxe Standalone Edition

**Status:** 💭 Concept / outlook.

- **Hardware:** an integrated, glare-free E-paper/E-ink display right
  on the enclosure — shows the key stats (e.g. distance, speed)
  without needing to open Home Assistant.

**Milestones:**

- [ ] Choose an E-paper/E-ink panel (size, resolution, driving)
- [ ] Power budget/supply for a permanently active display
- [ ] UI concept for the display layout
- [ ] Enclosure adaptation for glare-free display integration

---

## 2. How the phases relate

All three phases share the same data path: ESPHome on the
microcontroller → Home Assistant → [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).
Phases 2 and 3 build on the sensing principles established in Phase 1
and progressively replace breadboard/jumper wiring with integrated,
consumer-ready hardware — the DIY Edition remains available as the
cheap, open, build-it-yourself path.
