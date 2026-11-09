---
layout: layouts/catalog-page
title: Rib:bit Core Namespace
---

## Namespace `RibBit`

Shared core used by every Rib:bit extension. It holds the enums, I2C helpers, and the background loop that watches the Rib:bit board. Most projects only need [Rib:bit Basics](../namespace_ribbitbasics/); the calls below are for building new extensions.

## Constants

- `RIBBIT_ADDRESS = 0x10`: I2C address of the Rib:bit controller.
- `RIBBIT_RTC_ADDRESS = 0x68`: I2C address of the real-time clock.
- `HOST_SETTLE_US = 100`: Delay in microseconds after each I2C transaction.
- `leds`: The six-light NeoPixel strip on pin P16, cleared on start-up.

## Calls

### `reg_read(reg)`

- **Parameters:**
  - `reg`: `RibBit.Register` to read.
- **Returns:** `number`
- **Description:** Reads one byte from a controller register.

### `reg_write(reg, value)`

- **Parameters:**
  - `reg`: `RibBit.Register` to write.
  - `value`: Byte to store.
- **Returns:** `void`
- **Description:** Writes one byte to a controller register.

### `ribbit_cmd(device, command)`

- **Parameters:**
  - `device`: Target `RibBit.Device`.
  - `command`: `RibBit.Command` to send.
- **Returns:** `void`
- **Description:** Sends a power, reset, or select command for a device.

### `ribbit_serial_write(device, data)`

- **Parameters:**
  - `device`: Target `RibBit.Device`.
  - `data`: Buffer to send. It is split into 14 byte chunks.
- **Returns:** `void`
- **Description:** Writes serial data through the controller.

### `ribbit_set_baud(baud)`

- **Parameters:**
  - `baud`: `RibBit.SerialBaud` rate.
- **Returns:** `void`
- **Description:** Sets the MikroBUS serial baud rate.

### `bcdToDec(bcd)` and `decToBcd(dec)`

- **Parameters:**
  - `bcd` or `dec`: Value to convert.
- **Returns:** `number`
- **Description:** Converts between binary-coded decimal (used by the clock chip) and plain numbers.

### `dayToString(day = 1)`

- **Parameters:**
  - `day`: Weekday number, 1 (Monday) to 7 (Sunday).
- **Returns:** `string`
- **Description:** Returns the weekday name, or `???` for an unknown value.

### `isUsbPowered()` and `isCODAL()`

- **Parameters:** None
- **Returns:** `boolean`
- **Description:** Native helpers that report whether the board is on USB power and whether it runs the CODAL runtime.

## Background behaviour

When the extension loads, it switches off the GPS, MikroBUS, camera, LoRa, and SD devices, sets the lights to brightness 64, and starts a loop that runs every 50 ms. The loop:

- Detects the Rib:bit controller disconnecting or reconnecting and repeats the start-up setup on reconnect.
- On controller versions below 5, lowers the light brightness if the strip draws too much power.
- Reads pending interrupts on pin P8, updating button state, firing press and release handlers, and passing GPS text to the GPS extension.

## Enums

- [Button Enum](../enum_button/), [Button State Enum](../enum_buttonstate/), [On Off Enum](../enum_onoff/), [Month Enum](../enum_month/), [Day Of Week Enum](../enum_dayofweek/), [Serial Baud Enum](../enum_serialbaud/)
- Internal enums without blocks: `IRQ` (`NONE`, `BUTTON`, `GPS`, `MBUS`, `CAMERA`, `LORA`), `Command` (`POWER_ENABLE`, `POWER_DISABLE`, `RESET_DEVICE`, `SPI_SELECT`, `MBUS_BAUD_RATE`, `SERIAL_WRITE`, `REGISTER_WRITE`), `Device` (`GPS`, `MBUS`, `CAMERA`, `LORA`, `LORA_TXRX`, `SD`), and `Register` (`VERSION`, `TEST`, `LORA_TXRX`).
