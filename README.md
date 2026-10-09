# Makers Sandbox

A single-file, offline node-graph sandbox for planning electronics, code and generative art projects. Drop parts on a blank canvas, wire them together, and get checked wiring plus ready-to-run Python scripts.

Open `index.html` in any modern browser. There is nothing to install, no server and no network access.

## What it does

- **Hardware-aware parts bin.** Hosts (Pi Zero 2, Pi 5, ESP32-S3) and add-ons (E-ink, LCD HAT, PiSugar, cameras, sensors, buttons) with pin, ribbon-cable and I2C address fit checks.
- **Typed ports and wires.** Wire sensors, logic, buttons and values into screens and actions.
- **Live screen previews.** Lay out text, shapes, icons and camera frames, and see the result on the canvas.
- **Actions.** Map a button or sensor to take a photo, show a photo, shut down and more.
- **Photo library.** Save, number, browse, favorite and delete photos.
- **Generated scripts.** Setup, controls, screen loops, `main.py` and an autostart service, shown in a sidebar console with Copy and Download.
- **Mock camera.** Generates `mock_camera.py` so the project can be tested on a computer with no Pi. Run `SANDBOX_MOCK=1 python3 controls.py` (needs `pip install gpiozero pillow`).
- **Starter projects**, multiple projects, and JSON export and import.

## Storage and privacy

Projects are saved in your browser's local storage (`makersandbox.v1`). Nothing is uploaded anywhere. Imported project files can contain custom SVG, so only import files you trust.

## Status

Early and experimental. The hardware code (Picamera2, gpiozero, luma.oled, Waveshare drivers and others) is generated from memory and is **not yet verified on real hardware**. Test one part at a time. Pull requests and corrections from people with the hardware are welcome.

## License

MIT. See `LICENSE`.
