# Pin Map

This is a direct listing of every pin constant defined in `firmware/main_controller/main_controller.ino`, grouped the same way they are grouped in the source file. Variable names and pin numbers are taken as-is from the code.

## Shared DHT22

| Constant | Pin |
|---|---|
| `DHT_PIN` | 8 |

## Peltier Temperature Controller

| Constant | Pin |
|---|---|
| `PELTIER_PIN` | A4 |
| `PELTIER_LED_PIN` | 13 (Peltier active status indicator LED; default is the built-in LED on pin 13, per code comment) |

## Default / Left System

| Constant | Pin |
|---|---|
| `DEFAULT_MOTOR_IN3` | 36 |
| `DEFAULT_MOTOR_IN4` | 38 |
| `DEFAULT_LIMIT_OUT` | 41 |
| `DEFAULT_LIMIT_IN` | 42 |
| `DEFAULT_PTC_PIN` | A2 |
| `DEFAULT_FAN_PIN` | 12 |
| `DEFAULT_TEMP_PIN` | 17 |
| `DEFAULT_SERVO_PIN` | 16 |

## Standby / Right System

| Constant | Pin |
|---|---|
| `STANDBY_MOTOR_IN3` | 40 |
| `STANDBY_MOTOR_IN4` | 48 |
| `STANDBY_LIMIT_OUT` | 26 |
| `STANDBY_LIMIT_IN` | 30 |
| `STANDBY_PTC_PIN` | A1 |
| `STANDBY_FAN_PIN` | 11 |
| `STANDBY_TEMP_PIN` | 43 |
| `STANDBY_SERVO_PIN` | 6 |

## New Heating System (Top/Bottom Pre-Drying)

| Constant | Pin |
|---|---|
| `NEW_HEATING_BUTTON_PIN` | 35 |
| `TOP_PTC_PIN` | A3 |
| `BOTTOM_PTC_PIN` | 7 |
| `NEW_FAN_PIN` | 47 |
| `TOP_TEMP_PIN` | A10 |
| `BOTTOM_TEMP_PIN` | A11 |
| `AIR_CLEAN_FAN_PIN` | 14 |

## Weight Sensor (HX711)

| Constant | Pin |
|---|---|
| `HX711_DT_PIN` | 32 |
| `HX711_SCK_PIN` | 34 |

## Lock / Peltier Control Button

| Constant | Pin |
|---|---|
| `LOCK_BUTTON_PIN` | 45 |

## Buzzer / Alarm LEDs

| Constant | Pin |
|---|---|
| `BUZZER_PIN` | 5 |
| `ALARM_LED1_PIN` | A5 |
| `ALARM_LED2_PIN` | 39 |

## Electronic Lock

| Constant | Pin |
|---|---|
| `LOCK_PIN` | A0 |

## Tray Motor (Main)

| Constant | Pin |
|---|---|
| `MOTOR_IN1_PIN` | 22 |
| `MOTOR_IN2_PIN` | 23 |

## Limit Switches (Main Tray)

| Constant | Pin |
|---|---|
| `LIMIT_OUT_PIN` | 31 |
| `LIMIT_IN_PIN` | 29 |

## Manual Tray Button

| Constant | Pin |
|---|---|
| `OUT_BUTTON_PIN` | 33 |

## RFID (MFRC522)

| Constant | Pin |
|---|---|
| `RFID_SS_PIN` | 53 |
| `RFID_RST_PIN` | 49 |

Per the code comment, the Arduino Mega hardware SPI pins used alongside the RFID module are: SCK = 52, MOSI = 51, MISO = 50, SDA/SS = 53.

## Serial

| Link | Setting |
|---|---|
| Mega `Serial1` -> NodeMCU | `NODEMCU_BAUD` = 9600 |
