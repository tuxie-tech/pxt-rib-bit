---
layout: layouts/catalog-page
title: Rib:bit Basics
hero: rib-bit-hero.png
info: >-
    Rib:bit Basics adds button events, status lights, and real-time clock blocks for the Rib:bit, and is the foundation the other Rib:bit extensions build on.
plugins:
    - ts-to-blocks
tags:
    - software
    - api
    - makecode
    - blocks
---

## Overview

Rib:bit Basics lets you react to the six Rib:bit buttons, colour the lights beside them, and read or set the on-board clock using beginner-friendly blocks.

This page is the learner-first starting point. If you are new, begin with blocks and only jump into TypeScript when you need deeper control.

The other Rib:bit extensions (GPS, LoRa, MikroBUS) depend on this one, so MakeCode loads it automatically when you add them.

## Add to MakeCode

1. Open [MakeCode for micro:bit](https://makecode.microbit.org/) and start a **New Project** (or open an existing one).
2. Click the **gear** menu at the top right, then choose **Extensions**.
3. Paste `https://github.com/tuxie-tech/pxt-rib-bit` into the search box and press Enter.
4. Click the **Rib:Bit Basics** tile that appears. The extension is added and a **Rib:Bit Basics** category shows up in the block toolbox.

To edit the extension itself, choose **Import** on the MakeCode home screen, then **Import URL**, and paste the same address.

## What you can build

- Button-triggered games and controllers
- Coloured status lights for each button
- Clocks, timers, and timestamped displays
- Classroom projects that use the Rib:bit as a simple input panel

## Learning path

- Start with blocks: [Rib:bit Basics Blocks Guide](blocks/)
- Use TypeScript when ready: [Rib:bit Basics TypeScript Reference](typescript/)
- Browse the full API structure: [Rib:bit Basics API Index](api/)

## Example

This example lights every light green while button L1 is held, and switches them off again when it is released.

```ts
RibBitBasics.onButtonPress(RibBit.Button.L1, function () {
    RibBitBasics.setAllLedColor(NeoPixelColors.Green)
})

RibBitBasics.onButtonRelease(RibBit.Button.L1, function () {
    RibBitBasics.setAllLedColor(NeoPixelColors.Black)
})
```

## More resources

- TypeScript namespace docs: [Rib:bit Basics Namespace](namespace_ribbitbasics/), [Rib:bit Core Namespace](namespace_ribbit/)
- TypeScript enum docs: [Button Enum](enum_button/), [Button State Enum](enum_buttonstate/), [On Off Enum](enum_onoff/), [Month Enum](enum_month/), [Day Of Week Enum](enum_dayofweek/), [Serial Baud Enum](enum_serialbaud/)
