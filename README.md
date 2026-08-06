# Hamster Fitness — Hardware

[![License](https://img.shields.io/badge/license-CC%20BY--NC%204.0-lightgrey.svg)](LICENSE)

> **This is the hardware repository.** It contains the physical wheel
> sensor, 3D-printed enclosure, PCB/wiring notes, and ESPHome firmware for
> [Hamster Fitness](https://github.com/GpsM2/ha-hamster-fitness-integration)
> — a free Home Assistant integration that turns your hamster's running
> wheel into a health score, distance tracking, and more. **The Home
> Assistant integration itself lives in a separate repository:
> [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration).**

## License

This project uses the
[Creative Commons Attribution-NonCommercial 4.0 International license](LICENSE)
(CC BY-NC 4.0): anyone can use, adapt, and share these designs and this
firmware for free, for **non-commercial** purposes (personal use, hobby
projects, schools, research) — with attribution. The author (GpsM2)
keeps full rights and may also use or license the project commercially.
(The software repo uses a different, permissive license — see its
README.)

## What's here

- **`esphome/`** — ESPHome YAML firmware for the wheel-rotation sensor.
- **`cad/`** — OpenSCAD/STL/STEP files for the 3D-printed enclosure
  (nothing here yet).
- **`pcb/`** — schematics/KiCad files, if this ever moves past a
  hand-wired build (nothing here yet).
- **`docs/`** — build guides and bills of materials.

## Build the wheel sensor

1. Get a cheap ESP8266 board (like a "D1 Mini") and an optical sensor
   (a small light sensor that notices when something passes by it).
2. Open `esphome/hamster-wheel-sensor.yaml` in ESPHome and flash it to
   your board.
3. In your ESPHome `secrets.yaml` file, add these four entries:
   `wifi_ssid`, `wifi_password`, `esphome_web_d027a9__encryption_key`,
   `esphome_web_d018de__ota_password`.
4. Attach the sensor to the wheel so it "sees" one mark or magnet once
   per full turn.
5. Once it's flashed, Home Assistant should find it automatically
   through the ESPHome integration.
6. Install [ha-hamster-fitness-integration](https://github.com/GpsM2/ha-hamster-fitness-integration)
   and point it at this sensor's rotation-count entity.

## Support this project

Hamster Fitness is free and always will be. If it's useful to you and you
want to say thanks, you can [buy me a coffee on Ko-fi](https://ko-fi.com/R8O124JOD1).
Not required — just appreciated.
