# OLED Binary Video Converter

A browser-based tool that converts any video into 1-bit C++ bitmap arrays for monochrome OLED displays on ESP32 / Arduino.

**[Try it live →](https://we1chj.github.io/OLED-Binary-Video-Converter/)**

## What it does

Extracts frames from a video, converts each to a 1-bit black & white bitmap, and generates ready-to-upload Arduino code (`VideoFrame.h` + `Main.ino`) that plays the animation on an OLED screen.

## Features

- **Dithering modes** — Solid Threshold, Bayer 8×8, Floyd-Steinberg, Atkinson
- **Scale modes** — Best Fit, Fill/Cover (with pan), Stretch, Custom
- **Adjustable output resolution** — presets (128×64, 128×32, 96×32, 64×48) or any custom W×H
- **Image controls** — contrast, brightness, threshold bias, text/line thickness, invert
- **Live OLED preview** — see the exact 1-bit output in real time as you adjust settings
- **One-click copy** — `VideoFrame.h` PROGMEM array and `Main.ino` sketch ready to paste
- Supports **SSD1306** and **SH1106** OLED controllers

## Usage

1. Open the tool in a browser (no install needed)
2. Upload a video
3. Set your output resolution to match your OLED (default 128×64)
4. Adjust dithering, scale, and image settings — preview updates live
5. Click **Extract All Frames**
6. Copy `VideoFrame.h` into a new Arduino IDE tab with that filename
7. Copy `Main.ino` into your main sketch
8. Upload to your ESP32/Arduino

## Arduino libraries required

- [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library)
- [Adafruit SSD1306](https://github.com/adafruit/Adafruit_SSD1306) or [Adafruit SH110X](https://github.com/adafruit/Adafruit_SH110x)

## Tips

- **Bayer 8×8** dithering gives the smoothest results for most videos
- Set `Wire.setClock(800000)` (already in the generated code) for higher frame rates
- Shorter videos and lower FPS = smaller array size = less flash memory used
- Use **Cover + pan** mode to zoom into a specific part of the video

## License

MIT
