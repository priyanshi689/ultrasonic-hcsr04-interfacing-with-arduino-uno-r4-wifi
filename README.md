# Ultrasonic Distance Sensor — Arduino Uno R4 WiFi

Project that measures distance using an HC\-SR04 (or compatible) ultrasonic sensor and an Arduino Uno R4 WiFi. The project code lives in `src/main.cpp` and the build configuration is in `platformio.ini`.

## Hardware
- Arduino Uno R4 WiFi
- HC\-SR04 ultrasonic sensor (or compatible)
- Jumper wires
- Breadboard (optional)
- USB cable to program the board

Pin connections (as used in `src/main.cpp`):
- `trig` → digital pin 9
- `echo` → digital pin 10
- `VCC` → 5V
- `GND` → GND

## How it works
- The code triggers a short ultrasonic pulse on the `trig` pin.
- It measures the time for the echo to return on the `echo` pin using `pulseIn`.
- Distance (in cm) is calculated as: (duration \* 0.034) / 2.
- Results are printed to the Serial Monitor at 9600 baud.

## Files
- `src/main.cpp` — Arduino sketch implementing trigger, echo timing, and serial output.
- `platformio.ini` — PlatformIO project configuration (example/template shown below).

## Example `platformio.ini`
Use the appropriate board id for Arduino Uno R4 WiFi in your PlatformIO installation. Replace `arduino_uno_r4_wifi` with the correct board identifier if needed.

```ini
[env:arduino_uno_r4_wifi]
platform = renesas
board = arduino_uno_r4_wifi
framework = arduino
monitor_speed = 9600
