# Decentred Tech Gift Guide

This guide presents the gadgets from the [Gadgets For People Who Don't Trust The Government](https://www.youtube.com/watch?v=W_F4rEaRduk) video and links to useful documentation, tutorials and guides to build or customize them.

***

## 1. Solar Meshtastic Lawn Light Node

Low‑power LoRa mesh messenger hidden in a garden light, using Meshtastic firmware.

### Concept

- Use a cheap solar lawn light with a 18650 cell and drop in a Meshtastic‑compatible LoRa board (RAK WisBlock, Heltec, LilyGO, etc.).
- Connect via Bluetooth to the Meshtastic app and join a local encrypted mesh without SIM, subscription, or central server.


### Hardware

- Meshtastic‑capable board (RAK WisBlock, Heltec Meshtastic device, LilyGO T‑Beam, etc.).
- Solar lawn light with 18650 battery and integrated charge controller.
- Optional: higher‑capacity 18650 cells, extra antenna from an old Wi‑Fi router, silicone sealant, USB battery holder.


### Build (high level)

1. Open the light, identify the 3.7 V battery and charge board, and drill a hole for the LoRa antenna.
2. Wire the LoRa board’s power input to the battery (correct polarity), mount the board inside the housing, and re‑assemble.
3. Optionally upgrade battery capacity and add external Bluetooth/LoRa antennas, sealing all holes with silicone.
4. Pair with the Meshtastic app and configure the node.

### Docs and Guides

- Meshtastic – Getting Started:
https://meshtastic.org/docs/getting-started/
- Meshtastic – Hardware overview:
https://meshtastic.org/docs/hardware/
- RAK WisBlock / WisMesh Meshtastic setup:
https://docs.rakwireless.com/product-categories/meshtastic/meshtastic-basic-device-setup/
- Meshtastic firmware repository:
https://github.com/meshtastic/meshtastic

***

## 2. Solar Meshtastic Repeater / Base Station

Static rooftop or mast‑mounted node with a big antenna, acting as a long‑range repeater.

### Concept

- Use a 12 W solar panel, waterproof box, large 915 MHz antenna, and a Meshtastic radio (Heltec, etc.) plus a ~7000 mAh battery pack configured as a fixed repeater.
- Optionally flash MeshCore instead of Meshtastic to match your local network.


### Hardware

- 12 W (or larger) solar panel with mounting hardware and charge controller.
- Weatherproof enclosure and high‑gain 915 MHz antenna with suitable coax.
- Heltec Meshtastic‑compatible device and 2× 18650 cells around 3500 mAh each.


### Build (high level)

1. Mount panel and antenna with proper grounding; route the antenna feed into the box.
2. Wire panel → charge controller → battery pack → Meshtastic device.
3. Configure the device as a repeater node in the Meshtastic app.
4. Tune region and radio settings and verify extended node reach after deployment.

### Docs and Guides

- Meshtastic – Settings and device roles:
https://meshtastic.org/docs/settings/
- Heltec + Meshtastic documentation:
https://docs.heltec.org/en/node/esp32/esp32_general_docs/meshtastick.html
- Unofficial Meshtastic guide:
https://meshtastic.letstalkthis.com

***

## 3. WiiSpy ESP32S3 Multi‑Tool (Flock U, Drone Tracker, etc.)

ESP32S3‑based handheld tool with custom firmware for detecting Flock cameras and other RF‑devices.

### Concept

- A custom PCB built around an ESP32‑S3 with buzzer and controls, flashed with firmware such as Flock U for Flock Safety camera detection or other RF‑hunting tools.
- The same hardware can be reflashed as a direction finder, drone tracker, or robot exploit tool.


### Hardware

- ESP32‑S3 development board or custom WiiSpy PCB.
- Buzzer, buttons, battery, optional display and 3D‑printed enclosure.


### Build / Firmware (high level)

1. Assemble or purchase a WiiSpy PCB and solder the ESP32‑S3, buzzer, connectors and power.
2. Install Python and PlatformIO Core on your computer.
3. Clone or download the project, then build and flash the firmware using the provided script.
4. Access the web GUI in a browser to configure datasets, mapping and logging.

### Docs and Guides

- ESP32 official documentation:
https://docs.espressif.com
- PlatformIO Core installation (for building/flashing):
https://docs.platformio.org/en/latest/core/installation.html
- For Flock U and WiiSpy details, search for the project’s GitHub repository (e.g. “FlockU WiiSpy GitHub”) and follow its README.

***

## 4. DIY NOAA / GOES Satellite Weather Station (SDR)

Permanent or semi‑permanent satellite downlink using an SDR, dish, and SatDump.

### Concept

- Aim a dish or L‑band patch antenna at a geostationary GOES satellite, feed it into a low‑noise amplifier and filter, then into a software‑defined radio (SDR) and decode images with SatDump.
- A GOES kit (e.g. NooElec GOES bundle) simplifies dish, LNA and SDR selection.


### Hardware

- Satellite dish or L‑band patch with mount and clear sky view.
- LNA+filter such as NooElec SAWbird+ GOES placed at the feed, plus an SDR (RTL‑SDR, NooElec NESDR, Airspy, etc.).
- Laptop, desktop or SBC running SatDump.


### Software and Setup

1. Use a satellite tracker (e.g. GPredict or similar) to find GOES position/elevation and select a mounting location.
2. Point the dish based on azimuth and elevation from a site like DishPointer.
3. Install and run SatDump, select your SDR, set the GOES RF frequency (e.g. around 1694.1 MHz for HRIT) and adjust alignment while watching SNR.
4. Let SatDump record and decode; images and other products are written to disk automatically.

### Docs and Guides

- SatDump official website and documentation:
https://www.satdump.org
- GOES receiving with SatDump (Windows‑oriented but broadly applicable):
https://usradioguy.com/goes-receiving-in-windows-for-satdump/
- SatDump for Meteor/NOAA decoding:
https://usradioguy.com/satdump-for-meteor-noaa-decoding/
- Collection of satellite‑weather SDR tutorials:
https://www.rtl-sdr.com/multiple-comprehensive-tutorials-on-weather-satellite-decoding/

***

## 5. RayHunter IMSI‑Catcher Detector (Orbic Hotspot Mod)

A cheap 4G hotspot reflashed to detect fake cell towers (IMSI catchers / Stingrays).

### Concept

- Use a compatible Orbic mobile hotspot and flash EFF’s RayHunter firmware so it passively inspects cellular signaling and flags suspicious base stations.
- The interface shows a status indicator (typical green/white/red) and can send alerts to your phone.


### Hardware

- Orbic hotspot model supported by RayHunter (for example, RC400L), often found second‑hand at low cost.
- Computer with USB connection (Linux, macOS or Windows) for installation.


### Install / Use (high level)

1. Download the RayHunter release bundle from the EFF GitHub repository.
2. Connect the hotspot via USB, put it into the specified install mode, and run the provided install script.
3. After reboot, open the RayHunter web UI hosted on the device and configure notifications and thresholds.
4. Carry or mount the hotspot in your car or bag during protests, events or travel.

### Docs and Guides

- RayHunter main repository and documentation:
https://github.com/EFForg/rayhunter
- RayHunter overview / demo video:
https://www.youtube.com/watch?v=SbSYSNuAetI
- Step‑by‑step RayHunter install on Orbic RC400L:
https://www.youtube.com/watch?v=miIIdVokQGY

***

## 6. Hackable GL.iNet Travel Router (VPN / Tor / Ad‑Block)

Router used in the video as an attempted Jellyfin music server, but more realistically a flexible, low‑power network tool.

### Concept

- Use a GL.iNet travel router (Shadow, Slate AX, etc.) running OpenWrt‑based firmware as a low‑power always‑on network appliance.
- Typical roles: VPN client/router, DNS‑level ad‑blocker, or Tor gateway for all LAN devices.


### Hardware

- GL.iNet travel router such as:
    - GL‑AR300M “Shadow”
    - GL‑AXT1800 “Slate AX”
- USB power supply and optional USB storage.


### Useful Configurations

- Encrypted VPN gateway for all devices on the subnet.
- DNS‑level ad‑blocking with built‑in features or add‑on services.
- Tor gateway for anonymised browsing across the network.


### Docs and Guides

- GL.iNet official documentation (firmware, VPN, Tor, recovery, pinouts):
https://docs.gl-inet.com
- OpenWrt main docs (for building and customizing firmware and packages):
https://openwrt.org/docs/start
- GL.iNet community forum (user HOWTOs and scripts):
https://forum.gl-inet.com