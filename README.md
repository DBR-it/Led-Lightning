# Ceiling LED Lighting Control System

## Project Overview
This project is a smart LED ceiling lighting control system using an ESP32 microcontroller and the ESPHome firmware. The system is designed to control eight monochromatic LED channels with dynamic dimming, effects, and automation through a GPIO push button. The configuration is modular and supports future expansion through additional sensors or control modules.

## Features
- **Individual Control of 8 LED Channels:** Each LED can be independently controlled with dimming and light effects.
- **Dimming Automation:** Smooth transition dimming controlled by a push button.
- **Advanced Light Effects:** Flicker and pulse effects for dynamic lighting.
- **Temperature Monitoring:** Integrated Dallas temperature sensor.
- **Web Server & API:** Remote control via a built-in web server and API.
- **Modular Configuration:** Simplifies updates and expansions using ESPHome's `packages` feature.
- **Future Expansion Ready:** Designed to integrate additional sensors, switches, and expansion boards.

## File Structure
### Main Configuration (`ceiling.yaml`)
This file includes all the essential components for controlling the ceiling lights. It is modularized for easier maintenance and expansion.

### Key Components
1. **ESPHome Setup:**
    - Initializes the ESP32 board with the Arduino framework.
    - Sets up the web server and OTA updates.

2. **Wi-Fi Configuration:**
    - Connects to a Wi-Fi network with a fallback access point mode for safe configuration access.

3. **Global Variables:**
    - Manages light states and dimming logic using `std::vector` and boolean flags.

4. **Switch & Scripts:**
    - Includes a restart switch and a dimmer script that smoothly transitions light brightness.

5. **Light Output Configuration:**
    - Configures eight LEDC PWM outputs at 40kHz for precise light control.

6. **Light Effects:**
    - Provides pre-defined and custom light effects including flicker and pulse modes.

7. **Binary Sensor (Button Control):**
    - Configures a GPIO button to trigger dimming and toggle lights on/off.

8. **Temperature Sensor:**
    - Integrates a Dallas temperature sensor using a one-wire GPIO pin.

## Usage
1. **Installation:**
    - Flash the ESP32 with the `ceiling.yaml` configuration using ESPHome.
    - Connect to Wi-Fi or use the fallback hotspot for initial setup.

2. **Control Options:**
    - Use the push button to control dimming and light states.
    - Access the web server on port 80 for remote management.

3. **Automation Integration:**
    - The API allows integration with home automation platforms like Home Assistant.

## Future Expansion
- Additional GPIOs and modular connectors are available for more sensors or lighting channels.
- The configuration supports the `packages` feature to include new components easily.

## Troubleshooting
- If the device is not responsive, use the restart switch via the web server.
- Check the serial logs through the logger integration for debugging information.

## License
This project is licensed under the GNU General Public License (GPL-3.0). Feel free to use, modify, and distribute it as needed.
