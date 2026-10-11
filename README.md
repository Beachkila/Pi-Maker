# Makers Sandbox

A single-file, offline node-graph sandbox for planning electronics, code and generative art projects. Drop parts on a blank canvas, wire them together, and get checked wiring plus ready-to-run Python scripts.

Open `index.html` in any modern browser. There is nothing to install, no server and no network access.

## What it does

- **Blank canvas.** The app opens empty, and so does every new project.
- **Breadboard.** Mount a breadboard on a Pi and sensors, buttons and small screens are wired onto it automatically, with a drawing, a wiring table, voltage and pin-conflict checks, and a shopping list.
- **Connection key.** Power, I2C, SPI, UART, GPIO, PWM, ribbon, USB and HAT connections each have their own color, shape and label on every module, the pin map and the breadboard drawing.
- **PDF guide.** One button makes a PDF of the whole project: a setup walkthrough from flashing the SD card to autostart, then every script on its own page.
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

## Interface

Studio Wetware black-and-white skin with a menu bar (File, Edit, Add, View, Project, Help). The console is a docked sidebar on the right: drag its edge to resize, collapse it to the rail, and its width is remembered. On phones the menus fold into one hamburger and the console slides over the canvas. The single accent color is the `--accent` CSS variable at the top of the file.

## Run console

In the console sidebar, the **Run** tab is a virtual unit. Screens redraw on their refresh timing (partial and full e-ink refreshes, invert), and you can hold LCD keys, move simulated sensors and the PiSugar battery, fire actions and the mock camera, change the speed up to 60x, and read a log. Custom programs run in real Python after you press **Load Python engine** (a one-time download of about 10 MB from the Pyodide CDN, cached by the browser). The engine swaps the Waveshare, luma and LCD drivers for stand-ins and ignores libraries it cannot simulate. It shows your logic and timing, not real e-ink ghosting, refresh speed or driver behavior.
