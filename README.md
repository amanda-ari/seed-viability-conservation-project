# seed-viability-conservation-project
Portable Seed Viability Conservation System (IoT-Based Humidity and Temperature Controlled Seed Storage) 
Microcontroller Based Application Development Project
Year 1

# Portable Seed Viability Conservation System

IoT-based humidity and temperature controlled seed storage system, built around an Arduino Mega.

## Overview

Seed viability declines quickly when seeds are exposed to high temperature and humidity. This project is a self-contained, portable enclosure that automatically pre-dries seeds, then maintains a low-temperature, low-humidity environment for long-term storage, with remote monitoring through an IoT web dashboard.

The system pre-dries seeds using PTC/Nichrome heaters to bring moisture content below 5%, then maintains storage conditions (target ~8 degrees C, ~25% RH) using Peltier cooling and PTC-heated silica gel dehumidification, with fan-assisted airflow. Access is secured with an RFID lock, and per-tray weight sensors track seed inventory. Sensor data is sent over serial to an ESP8266 (NodeMCU) module for transmission to a web dashboard.

## Features

- **Dual silica-gel humidity control** - two independently controlled trays (default/left and standby/right), each with its own servo-operated vent, temperature probe, PTC heater, and fan. Humidity is read from a shared DHT22 sensor, and heating time is calculated from how long each tray's vent was open, not from temperature.
- **Peltier-based temperature control** - automatic cooling with hysteresis, plus a manual override button (quick press toggles automatic control, long press locks/unlocks the enclosure while the Peltier is off) with a status LED.
- **Top/bottom PTC pre-drying stage** - a separate seed pre-drying system that heats from the top then the bottom PTC element, driven by a weight sensor (HX711 load cell) that stops heating once the tray reaches a target percentage of its starting weight, with a 90 degree C safety cutoff on each element.
- **RFID access control** - MFRC522 reader checks against an authorized UID list to unlock the enclosure, with a timed automatic re-lock.
- **Motorized tray system** - gear-motor driven in/out trays with limit switches, homing on startup, and manual out/in buttons.
- **Air cleaning cycle** - a timed exhaust fan cycle that runs automatically after a heating cycle completes or is stopped.
- **LCD status display** - alternates between temperature/humidity and Peltier status screens.
- **Buzzer and alarm LEDs** - audible/visual alerts for unauthorized access and system warnings.
- **Serial telemetry to NodeMCU** - JSON-formatted status (humidity, temperatures, heating state, door/lock state, servo-open times, etc.) is streamed over `Serial1` for the ESP8266 to forward to the web dashboard.
- **Safety limits** - maximum door-open time and maximum heating duration guards to prevent runaway cycles.

## Hardware / Components

- Arduino Mega 2560 (main controller)
- ESP8266 (NodeMCU) - Wi-Fi/IoT connectivity and web dashboard
- DHT22 - temperature and humidity sensing
- DS18B20 (DallasTemperature/OneWire) probes - per-tray and top/bottom temperature sensing
- MFRC522 RFID module - access control
- HX711 load cell amplifier - tray weight sensing
- LiquidCrystal_I2C 16x2 LCD - local status display
- Servo motors - tray vent doors
- DC gear motors + limit switches - tray in/out mechanism
- Peltier modules - active cooling
- PTC ceramic heaters (x4: default, standby, top, bottom) - silica gel regeneration and seed pre-drying
- Relay-driven fans (tray fans, new-heating fan, air-cleaning fan)
- Buzzer and status/alarm LEDs
- Push buttons - lock/Peltier control, manual tray out, new-heating start/stop
