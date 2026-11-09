---
layout: layouts/catalog-page
title: Rib:bit Basics Namespace
---

## Namespace `RibBitBasics`

User-facing namespace with button, light, and clock calls. Appears in MakeCode as **Rib:Bit Basics**.

## Buttons

### `buttonVar(button)`

- **Parameters:**
  - `button`: Button to return (default `RibBit.Button.L1`).
- **Returns:** `RibBit.Button`
- **Description:** Passes a button value through, so it can be dropped into other blocks.

### `buttonState(state)`

- **Parameters:**
  - `state`: State to convert (default `RibBit.ButtonState.Pressed`).
- **Returns:** `boolean`
- **Description:** Returns `true` for `Pressed` and `false` for `Released`.

### `onButtonPress(button, cb)`

- **Parameters:**
  - `button`: Button to watch.
  - `cb`: Callback run when the button is pressed.
- **Returns:** `void`
- **Description:** Registers a press handler. Only one handler is kept per button.

### `onButtonRelease(button, cb)`

- **Parameters:**
  - `button`: Button to watch.
  - `cb`: Callback run when the button is released.
- **Returns:** `void`
- **Description:** Registers a release handler. Only one handler is kept per button.

### `onButtonEvent(cb)`

- **Parameters:**
  - `cb`: Callback receiving `(button, state)` for every change.
- **Returns:** `void`
- **Description:** Registers a handler for any button change. Advanced.

### `isButtonState(button, state)`

- **Parameters:**
  - `button`: Button to check.
  - `state`: State to compare against.
- **Returns:** `boolean`
- **Description:** Reports whether the button is currently in the given state.

## Lights

### `setLedColor(button, color)`

- **Parameters:**
  - `button`: Button whose light to set.
  - `color`: NeoPixel colour.
- **Returns:** `void`
- **Description:** Colours the light beside one button and updates the strip.

### `setAllLedColor(color)`

- **Parameters:**
  - `color`: NeoPixel colour.
- **Returns:** `void`
- **Description:** Colours all six lights and updates the strip.

### `setLedBrightness(brightness = 64)`

- **Parameters:**
  - `brightness`: Brightness from 0 to 255.
- **Returns:** `void`
- **Description:** Sets the strip brightness and updates the strip.

### `neopixels()`

- **Parameters:** None
- **Returns:** `neopixel.Strip`
- **Description:** Returns the underlying six-light NeoPixel strip (on pin P16). Advanced.

## Time

### `getTime()`

- **Parameters:** None
- **Returns:** `string`
- **Description:** Returns the clock time as `hh:mm:ss`.

### `getDate()`

- **Parameters:** None
- **Returns:** `string`
- **Description:** Returns the clock date as `year-month-day`. Month and day are not zero-padded.

### `getDayOfWeek()`

- **Parameters:** None
- **Returns:** `string`
- **Description:** Returns the weekday name, such as `Monday`.

### `getHour()`, `getMinute()`, `getSecond()`

- **Parameters:** None
- **Returns:** `number`
- **Description:** Return a single clock value. Advanced.

### `getYear()`, `getMonth()`, `getDayOfMonth()`

- **Parameters:** None
- **Returns:** `number` (`getMonth()` returns `RibBit.Month`)
- **Description:** Return a single calendar value. Years are returned as four digits. Advanced.

### `monthVar(month = RibBit.Month.January)`

- **Parameters:**
  - `month`: Month to return.
- **Returns:** `RibBit.Month`
- **Description:** Passes a month value through, for use in the set-date block.

### `dayVar(day = RibBit.DayOfWeek.Monday)`

- **Parameters:**
  - `day`: Weekday to return.
- **Returns:** `RibBit.DayOfWeek`
- **Description:** Passes a weekday value through, for use in the set-weekday block.

### `setTime(hour = 0, minute = 0, second = 0)`

- **Parameters:**
  - `hour`: Hour in 24-hour time.
  - `minute`: Minute.
  - `second`: Second.
- **Returns:** `void`
- **Description:** Sets the clock time.

### `setDate(year = 2000, month = 1, day = 1)`

- **Parameters:**
  - `year`: Four-digit year (2000 or later).
  - `month`: Month number, 1 to 12.
  - `day`: Day of the month.
- **Returns:** `void`
- **Description:** Sets the clock date.

### `setDayOfWeek(day = 1)`

- **Parameters:**
  - `day`: Weekday number, 1 (Monday) to 7 (Sunday).
- **Returns:** `void`
- **Description:** Sets the clock weekday.

## Extra

### `readTemperature()`

- **Parameters:** None
- **Returns:** `number`
- **Description:** Reads the clock chip's temperature in degrees Celsius, in 0.25 degree steps. Advanced.

## Used by

- [Rib:bit Basics TypeScript Reference](../typescript/)
