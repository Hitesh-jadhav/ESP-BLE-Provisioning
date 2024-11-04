
# ESP BLE Provisioning

This project demonstrates Bluetooth Low Energy (BLE) provisioning with an ESP32 device, using the ESP-IDF framework. BLE provisioning allows secure configuration of Wi-Fi credentials via a mobile app, making it ideal for IoT devices.

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Setup Instructions](#setup-instructions)
- [Provisioning Process](#provisioning-process)
- [Troubleshooting](#troubleshooting)
- [References](#references)

## Features
- Provision Wi-Fi credentials via BLE using the ESP BLE Provisioning App.
- Secure Wi-Fi setup without hardcoding credentials in code.
- Easy to connect and manage ESP32 devices in different network environments.

## Requirements
- **Hardware**: ESP32 development board with BLE and Wi-Fi support.
- **Software**:
  - [ESP-IDF](https://github.com/espressif/esp-idf) (version 4.0+)
  - [ESP BLE Provisioning App](https://play.google.com/store/apps/details?id=com.espressif.provble) (Google Play)

## Setup Instructions

### 1. Install ESP-IDF
Follow the [ESP-IDF setup guide](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html) to install ESP-IDF.

### 2. Download the Example Code
Clone the example code from ESP-IDF's provisioning directory:
```bash
cd $IDF_PATH/examples/provisioning/ble_prov
```

### 3. Configure the Project
Connect the ESP32 to your computer. Open ESP-IDF's menuconfig to configure the board:
```bash
idf.py set-target esp32
idf.py menuconfig
```
- Select a partition scheme like **No OTA (2MB app/2MB SPIFFS)** to allow sufficient space.
- Save and exit.

### 4. Build and Flash
Compile and upload the code to the ESP32 device:
```bash
idf.py build
idf.py flash monitor
```

## Provisioning Process

1. Install the **ESP BLE Provisioning App** on your smartphone.
2. Open the app and scan for devices. Select your ESP32 (default name: `PROV_1234`).
3. When prompted, enter the **Proof of Possession (POP)** code: `abcd1234`.
4. Enter the Wi-Fi SSID and password in the app to send credentials to the ESP32.

Once connected, the ESP32 will save these credentials and use them to reconnect to Wi-Fi in the future.

## Troubleshooting

- **Sketch Too Large**: If you receive a "Sketch too big" error, try changing the partition scheme in `menuconfig`.
- **BLE Connection Issues**: Ensure that BLE is enabled on the ESP32 and that your phone's Bluetooth is on.
- **Wi-Fi Connection Failure**: Double-check the Wi-Fi credentials and make sure the ESP32 is within range of the router.

## References
- [ESP-IDF BLE Provisioning Example](https://github.com/espressif/esp-idf/tree/master/examples/provisioning)
- [ESP BLE Provisioning App](https://play.google.com/store/apps/details?id=com.espressif.provble)
- [Random Nerd Tutorials - ESP32 BLE Provisioning](https://randomnerdtutorials.com/esp32-wi-fi-provisioning-ble-arduino/)

---

This guide provides step-by-step instructions to set up BLE provisioning on an ESP32 device, using the ESP-IDF framework and ESP BLE Provisioning App.
