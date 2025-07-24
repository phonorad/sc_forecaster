# Sage & Circuit Weather Forecast Display

A minimalist, network-connected weather display built using a Raspberry Pi Pico 2W and a 240x240 rounf color tft LCD display. It fetches real-time weather data from the National Weather Service (NWS) and displays the next 6 or 7 day forecast, and time in a compact, looped interface.

## Features

- 6 to 7 day weather forecast data from US National Weather Service (NWS)
- Auto-updating clock with timezone and DST support
- Wi-Fi connectivity via AP or Local WiFi Network
- In-place firmware updates using browser-based file upload (OTA)
- Compact interface optimized for gc9a01 240x240 round color tft lcd display

## Setup Instructions

1. Power on the device.
2. On first boot, it will create a captive Wi-Fi access point.
3. Connect to the access point (e.g., `S&C Forecaster`) from your computer or phone.
4. A setup page should open automatically. If not, go to `scforecaster.net` in your browser.
5. Enter your home Wi-Fi credentials, your U.S. ZIP code and your timezone.
6. Save settings. The device will reboot and connect to the internet.
7. Once connected, can go to settings mode to change location and check for software updates

## Web Interface (`/settings`)

There is a single configuration interface served at the `/settings` route. This page supports two modes:

- **Setup Mode (Captive Wi-Fi, no internet)**:
  - Prompts for Wi-Fi credentials and location info
  - Hides software update controls

- **Settings Mode (Connected to Wi-Fi)**:
  - Allows location or timezone changes
  - Enables OTA software updates via manifest.json and SHA256 checksum validation

## Software Update

After connecting to Wi-Fi, visit the <ip address> shown on display and check for software updates:

1. The page compares current device version (`version.txt`) with the GitHub manifest.
2. If updates are available, files are downloaded to your browser, then uploaded to the device.
3. Files are verified via SHA256 checksums and applied safely.
4. The device reboots automatically to apply updates.

## Requirements

- Raspberry Pi Pico 2W
- gc9a01 240x240 round color tft lcd display
- MicroPython firmware (latest stable)
- Internet access (for weather updates)
- U.S. ZIP code (ZIP is used for lat/lon lookup)

## License

This project uses open-source components and libraries (including `gc9a01py`, `phew`, etc.). Please refer to license files.

## Acknowledgments

- National Weather Service API (weather.gov)
- Micropython and Raspberry Pi Foundation
- gc9a01py` library for lcd display support
- phew web server framework for embedded HTTP handling (note that this project uses a modified version of phew server)
