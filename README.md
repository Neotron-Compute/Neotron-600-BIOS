# Neotron-600-BIOS

This is the [Neotron](https://github.com/neotron-compute) BIOS for the [Neotron-600], which is based on the [Teensy 4.1].

[Neotron-600]: https://github.com/neotron-compute/neotron-600-hardware
[Teensy 4.1]: https://www.pjrc.com/store/teensy41.html


![Build Status](https://github.com/neotron-compute/neotron-600-bios/workflows/Build/badge.svg "Github Action Build Status")

![Format Status](https://github.com/neotron-compute/neotron-600-bios/workflows/Format/badge.svg "Github Action Format Check Status")

## Building

```console
$ cargo build --release
$ cargo objcopy --release -- -O ihex neotron-600-bios.hex
```

Now flash the `neotron-600-bios.hex` file with your favourite Teensy flash tool.

## Compatibility

This BIOS will run on the Teensy 4.1, but assumes you have a Neotron-600 baseboard fitted. Other Teensy 4.1 based systems can easily be supported.

## Features

The [Teensy 4.1] offers:

* 1024 KiB RAM 'chip' RAM
* 8192 KiB NOR Flash
* Optional QuadSPI PSRAM
* Optional QuadSPI Flash
* Cortex-M7 clocked at 600 MHz
* SD/MMC Slot
* USB Device port
* Hardware accelerated graphics (eLCDIF)
* USB Host PHY
* Ethernet PHY
* 42 through-hole GPIO pins

The Neotron 600 board adds:

* VGA output, running at 800x600 @ 60 Hz, in 128 colours
* 10/100 RJ45 Ethernet jack
* USB A Host port
* PS/2 Keyboard and Mouse ports
* MIDI In and MIDI Out
* Second SD/MMC Slot
* 2x Atari/Commodore joystick ports
* Parallel Printer Port
* RS-232 Port
* Power and Reset switch

## Memory Layout

TBD. We will allocate some of the Teensy 4.1 NOR flash chip to the BIOS, and some to the OS. We also need to decide how we divide up the 1024 KiB of internal RAM (lets call it 'internal RAM'), and how we detect whether a QuadSPI RAM has been fitted to the expansion port on the Teensy (lets call it 'external RAM'). We need some RAM set aside for a VGA frame buffer, some for OS things and stack, some for the USB driver, etc.

## Changelog

### Unreleased Changes ([Source](https://github.com/neotron-compute/neotron-600-bios/tree/master) | [Changes](https://github.com/neotron-compute/neotron-600-bios/compare/v0.1.0...master))

* None

### v0.1.0 ([Source](https://github.com/neotron-compute/neotron-600-bios/tree/v0.1.0))

* Can blink an LED

## Licence

    Neotron-600-BIOS Copyright (c) The Neotron Developers, 2020

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.

## Contribution

Unless you explicitly state otherwise, any contribution intentionally
submitted for inclusion in the work by you shall be licensed as above, without
any additional terms or conditions.
