---
layout: layouts/catalog-page
title: Rib:bit Basics Blocks Guide
---

## Overview

This page is a visual-blocks-first guide for learners. Every block lives in the **Rib:Bit Basics** category of the MakeCode toolbox, split into the groups below.

Block images are not generated automatically in this pass. Use the placeholders to insert transparent PNG block captures.

## Suggested block walkthrough order

1. React to a button press or release.
2. Colour the light next to a button.
3. Read the current time and date.
4. Set the clock if it is wrong.

## Buttons

| Block | What it does |
| --- | --- |
| `when $button is pressed` | Runs your blocks when the chosen button goes down. |
| `when $button is released` | Runs your blocks when the chosen button comes back up. |
| `is %button currently $state` | Reports whether a button is pressed or released right now. |
| `when any button changes state` | Advanced. Runs for every button change and tells you which button and its new state. |
| ` %button` | A button value (L1, L2, L3, R1, R2, R3) to plug into other blocks. |
| ` %state` | A pressed or released value to plug into other blocks. |

- Placeholder: insert transparent PNGs for the press, release, and "is currently" blocks.

## Lights

| Block | What it does |
| --- | --- |
| `set %button to %color` | Colours the light beside one button. |
| `set every light to %color` | Colours all six lights at once. |
| `set light brightness to $brightness` | Sets brightness from 0 to 255 (starts at 64). |
| `neopixel strip` | Advanced. Gives you the underlying NeoPixel strip for full control. |

- Placeholder: insert transparent PNGs for the colour and brightness blocks.

## Time

| Block | What it does |
| --- | --- |
| `the current time` | Text such as `13:05:09`. |
| `the current date` | Text such as `2025-9-30`. |
| `the current weekday` | Text such as `Tuesday`. |
| `the hour`, `the minute`, `the second` | Advanced. Single clock values as numbers. |
| `the year`, `the month`, `the date` | Advanced. Single calendar values as numbers. |
| `Set the clock to $hour-$minute-$second (hh:mm:ss)` | Sets the time (24-hour clock). |
| `Set the date to $year-$month-$day (yy:mm:dd)` | Sets the date. Year must be 2000 or later. |
| `Set the day of the week to $day` | Sets the weekday. |
| `$month`, `$day` | Month and weekday values to plug into the set blocks. |

- Placeholder: insert transparent PNGs for the time, date, and set-clock blocks.

## Extra

| Block | What it does |
| --- | --- |
| `read RTC temperature in °C` | Advanced. Reads the clock chip's temperature in 0.25 °C steps. |

## Next steps

- TypeScript docs: [Rib:bit Basics TypeScript Reference](../typescript/)
- Full API map: [Rib:bit Basics API Index](../api/)
