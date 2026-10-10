# YM60JIS Trilingual macOS Build Guide

## 1. Introduction

This is the build guide for the YM60JIS Trilingual macOS keyboard PCB, a fork of [YM60JIS](https://github.com/ymkn/YM60JIS) by ymkn. It walks through every step for first-time builders. Search online for anything it doesn't cover.

Questions that aren't specific to this board (soldering technique, general keyboard building and so on) are out of scope.

**For experienced builders:** you only need to get Cherry MX hot-swap sockets and solder them on. The firmware is QMK, and you can change the key mapping with Vial. If that's all you need, you can stop reading here.

> [!NOTE]
> Photos in this guide show the original YM60JIS. The bottom row of this fork is different (see [2.2](#22-parts-you-need-to-get-separately)). Everything else is the same.

## 2. Preparation

### 2.1 Package contents

YM60JIS consists of the main PCB and a top plate that holds the switches. You need the other parts listed below before it works as a keyboard.

| Item | Qty |
|---|---|
| YM60JIS PCB | 1 |
| YM60JIS top plate | 1 |

![YM60JIS contents](../image/ym60jis_contents.jpg)

### 2.2 Parts you need to get separately

Buy these from keyboard shops or electronic parts suppliers.

| Item | Qty | Notes |
|---|---|---|
| MX-compatible switches | 69 | [Cherry MX](https://www.cherrymx.de/en/dev.html) or compatible |
| MX-compatible hot-swap sockets | 69 | [Kailh PCB Socket CPG151101S11](https://www.kailhswitch.com/mechanical-keyboard-switches/box-switches/mechanical-keyboard-switches-kailh-pcb-socket.html) or compatible |
| MX-compatible keycaps | - | [Cherry MX](https://www.cherrymx.de/en/dev.html) or compatible |
| 2u PCB-mount stabilizers | 3 | Stabilizers keep wide keys level when pressed. One each for Left Shift, Enter and the 2.5u spacebar |
| Poker-compatible 60% case | 1 | Top-mount cases sold as "Poker compatible", "60%" or "GH60 compatible" should work. Not every case is guaranteed to fit |

### 2.3 Choosing keycaps

#### JIS keycaps

Off-the-shelf keycap sets with Japanese JIS legends are rare.

Good options as of November 2023 were Salicylic Acid's [Acid Caps JP](https://salicylic-acid3.hatenablog.com/entry/acid-caps-v3) series and [Keychron's JIS keycap sets](https://www.keychron.com/collections/iso-ansi-jis-keycaps).

Reference (Japanese): [Japanese-layout keycaps for custom keyboards (December 2021) - NinthSky Studio](https://ninthsky.hatenablog.com/entry/keycap_JP)

Most builders buy an English ANSI/ISO set and use keycaps whose legends don't match the actual keys.

Some of those sets have hiragana or katakana printed on them. The symbols on some keys still follow ANSI/ISO, so the kana are only decoration and don't match JIS.

#### Required keycaps and sizes

The diagram below shows every keycap and its size. Key widths are measured in "u", where 1u is the width of a standard square key. A 2u key is twice that width. Sizes come in 0.25u steps.

![Layout](../image/ym60jis_layout_base.svg)

Unlike the original YM60JIS, the whole bottom row is 1u except the 2.5u spacebar. A 0.25u gap sits after the left Fn key and another before the ← key.

These keys are often missing from standard ANSI/ISO sets or only sold as add-ons. Buy the add-on, or use another keycap of the same size and row profile.

| Row | Size | Key in the default layout |
|---|---|---|
| Number row | 1u | Backspace (top right) |
| Top/home rows | ISO Enter | Enter |
| Shift row | 2u | Left Shift |
| Shift row | 1u | The `_` (ろ) key |
| Shift row | 1u | Right Shift |
| Bottom row | 1u × 12 | Fn, Lang3, Option, Command, 英数, かな, Command, Option, Fn, ←, ↓, → |
| Bottom row | 2.5u | Spacebar (about 46 mm, the same as the HHKB) |

Few keycap sets include a 2.5u spacebar, so you'll usually need a spacebar add-on or kit. Look for a 2.5u spacebar with an MX stem. Stock HHKB keycaps use Topre stems and do not fit.

### 2.4 Tools

| Item | Qty | Notes |
|---|---|---|
| Soldering iron and solder | 1 | For soldering the hot-swap sockets. A temperature-controlled iron and leaded solder are recommended |
| Tweezers | 1 | Handy for holding sockets while soldering |
| Phillips screwdriver | 1 | For screwing the PCB into the case |

## 3. Assembly

### 3.1 Soldering the hot-swap sockets

The sockets go on the back of the PCB, the side with the ICs. An L-shaped white outline marks each key position. Solder a socket onto every one.

When soldering sockets near the ICs, don't touch the nearby components with the iron.

Check that every socket sits flat on the PCB and that both pads of every socket are soldered. A socket that lifts off the board or has an unsoldered pad will make that key unreliable.

![YM60JIS back](../image/ym60jis_back.jpg)

> [!CAUTION]
> The two sockets at the top right face the opposite direction from all the others!

### 3.2 Installing the stabilizers

The stabilizers go on the front of the PCB, the side with the logo.

Install a 2u stabilizer for each of Left Shift, Enter and the spacebar. The 2.5u spacebar uses a standard 2u stabilizer. Mounting varies between stabilizers. Usually you hook the clip into the larger hole, then push the pin or drive the screw into the smaller hole.

![YM60JIS front](../image/ym60jis_front.jpg)

### 3.3 Installing the switches

Push each switch through the top plate and into the sockets on the PCB. If you fit all the switches to the plate first, pressing them into the PCB is hard. Start with a switch in each corner of the plate, press the plate onto the PCB, then add the rest.

### 3.4 Mounting in the case

Poker-compatible cases usually have about six screw holes. Only four of them line up with this PCB; the center and bottom-right holes are not used. Screw holes and USB cutouts vary slightly between cases, so some holes may not line up. Screwing in only the holes that line up is fine.

![YM60JIS screw holes](../image/ym60jis_front_holes.jpg)

Some cases, especially plastic ones, have posts or ribs close to the bottom of the PCB. The hot-swap sockets stick out about 1.8 mm below the PCB and can hit those parts. Trim the case or use longer screws.

Once the PCB is in the case, you're done!

## 4. Usage

### 4.1 Connecting to a computer

Plug it into a USB 2.0-compatible port on your computer. It works right away.

### 4.2 Customizing the key mapping

This keyboard supports [Vial](https://get.vial.today/), a key mapping editor. See the Vial documentation for details.

The default mapping follows the HHKB:

- **Control** is on the Caps Lock position, left of A.
- **Fn** is at both ends of the modifier block. Hold either one for the Fn layer: F-keys, navigation, media keys and so on. The full table is in the [README](../README.md#fn-layer-hold-either-fn-key).

### 4.3 Switching input languages on macOS

The bottom row has three language keys:

| Key | Sends | macOS behavior |
|---|---|---|
| 英数 (left of Space) | `LANG2` | Switches to the English (alphanumeric) input source, like the 英数 key on Apple JIS keyboards |
| かな (right of Space) | `LANG1` | Switches to Japanese kana input, like the かな key on Apple JIS keyboards |
| Lang3 (second from left) | Grave/Tilde (`KC_GRV`) | Set this as the shortcut for your third input source |

To set up Lang3, open **System Settings → Keyboard → Keyboard Shortcuts → Input Sources**. Give "Select the previous input source" or "Select next source in Input menu" the Lang3 key as its shortcut. An input-switching tool such as Karabiner-Elements also works.

When macOS first sees the keyboard, the Keyboard Setup Assistant may ask you to identify it. Choose **JIS (Japanese)**.

## 5. Other information

### 5.1 Entering boot mode

To enter RP2040 boot mode, hold the top-left key (Esc) while plugging in the USB cable.

You can also hold the BOOT switch on the back of the PCB while plugging in the USB cable.

### 5.2 Firmware

The QMK/Vial source for this layout is in this repository under [firmware/QMK](../firmware/QMK). Build it with `make ymkn/ym60jis:vial` in a [vial-qmk](https://get.vial.today/docs/porting-to-vial.html) tree. In boot mode, copy the resulting `.uf2` file to the `RPI-RP2` drive.

> [!WARNING]
> The prebuilt `firmware/QMK/ymkn_ym60jis_vial.uf2` is from the original YM60JIS and does not match this layout.

### 5.3 Source code and design files

Everything is published in this repository under the MIT License.

https://github.com/themrsung/YM60JIS-trilingual-macos

The original YM60JIS: https://github.com/ymkn/YM60JIS
