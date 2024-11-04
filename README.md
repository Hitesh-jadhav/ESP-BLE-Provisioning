# ESP BLE Provisioning

This project demonstrates BLE-based Wi-Fi provisioning for ESP32 using ESP-IDF. The example showcases how to connect an ESP32 device to a Wi-Fi network by provisioning it with credentials from a mobile device using BLE (Bluetooth Low Energy).

## Table of Contents
- [Overview](#overview)
- [Getting Started](#getting-started)
- [Hardware Requirements](#hardware-requirements)
- [Installation](#installation)
- [Usage](#usage)
- [References](#references)
- [License](#license)

## Overview

ESP BLE Provisioning allows an ESP32 device to be configured over BLE to connect to a Wi-Fi network. This eliminates the need to hardcode Wi-Fi credentials, enabling flexibility for devices in changing network environments.

## Getting Started

To get started, make sure you have the following:
- [ESP-IDF](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html) environment set up on your development machine.
- An ESP32 development board.
- The [ESP BLE Provisioning App](https://play.google.com/store/apps/details?id=com.espressif.provble) (available on the Google Play Store).

## Hardware Requirements

- ESP32 Development Board (e.g., ESP32-WROOM, ESP32-WROVER)
- USB Cable
- Mobile Device with BLE support

## Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Hitesh-jadhav/ESP-BLE-Provisioning.git
   cd ESP-BLE-Provisioning
   ```

2. **Setup ESP-IDF**
   Make sure ESP-IDF is installed and set up according to the [ESP-IDF Installation Guide](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/index.html).

3. **Build and Flash the Code**
   - Navigate to the project directory and use the following commands:
     ```bash
     idf.py set-target esp32
     idf.py build
     idf.py flash
     ```

## Usage

1. After flashing the code, open the serial monitor to observe the logs.
   ```bash
   idf.py monitor
   ```

2. The ESP32 device will start advertising its BLE service for provisioning. You should see a message like:
   ```
   Provisioning started. Connect with the ESP BLE Provisioning App.
   ```

3. **Using the Mobile App for Provisioning**
   - Open the [ESP BLE Provisioning App](https://play.google.com/store/apps/details?id=com.espressif.provble) on your mobile device.
   - Connect to the ESP32 by selecting the advertised service.
   - Enter the Wi-Fi credentials (SSID and Password) in the app.
   - Upon successful provisioning, the ESP32 will attempt to connect to the Wi-Fi network.

4. Once connected, the device will display its IP address in the serial monitor.

## References

- [ESP-IDF BLE Provisioning Documentation](https://github.com/espressif/esp-idf/tree/master/examples/provisioning)
- [ESP BLE Provisioning Mobile App](https://play.google.com/store/apps/details?id=com.espressif.provble)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to contribute to this project by submitting pull requests or reporting issues!

Happy provisioning!
