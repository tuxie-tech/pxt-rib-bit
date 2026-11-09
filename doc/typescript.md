---
layout: layouts/catalog-page
title: Rib:bit Basics TypeScript Reference
---

## Overview

This page documents the TypeScript-facing API for Rib:bit Basics.

If you are learning, start with [Rib:bit Basics](../) and [Rib:bit Basics Blocks Guide](../blocks/).

## Quick call summary

- Buttons: `onButtonPress()`, `onButtonRelease()`, `onButtonEvent()`, `isButtonState()`, `buttonVar()`, `buttonState()`
- Lights: `setLedColor()`, `setAllLedColor()`, `setLedBrightness()`, `neopixels()`
- Time and date: `getTime()`, `getDate()`, `getDayOfWeek()`, `getHour()`, `getMinute()`, `getSecond()`, `getYear()`, `getMonth()`, `getDayOfMonth()`
- Setting the clock: `setTime()`, `setDate()`, `setDayOfWeek()`
- Helpers and extras: `monthVar()`, `dayVar()`, `readTemperature()`

## Example

```ts
RibBitBasics.onButtonPress(RibBit.Button.L1, function () {
    RibBitBasics.setLedColor(RibBit.Button.L1, NeoPixelColors.Red)
})

basic.forever(function () {
    basic.showString(RibBitBasics.getTime())
    basic.pause(1000)
})
```

## API details

- API index: [Rib:bit Basics API Index](../api/)
- Namespace details: [Rib:bit Basics Namespace](../namespace_ribbitbasics/), [Rib:bit Core Namespace](../namespace_ribbit/)
- Enum details: [Button Enum](../enum_button/), [Button State Enum](../enum_buttonstate/), [On Off Enum](../enum_onoff/), [Month Enum](../enum_month/), [Day Of Week Enum](../enum_dayofweek/), [Serial Baud Enum](../enum_serialbaud/)
