# Cult of Cthulhu Badge

**A BLE-based RPG set at DEF CON 34.**

Connect to other acolyte badges to grow your cult, find the glyphs of power scattered throughout the con, solve challenges, seek knowledge from the elder god badges, summon Cthulhu, and compromise all technology.

The badge has a main quest, an unlockable side quest, and four unlockable modes.

[![Join the Discord](https://img.shields.io/badge/Discord-Join_the_Cult-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/eUE9ZC9fFf)

---

## Badge Types

| Type | Where to find it |
| --- | --- |
| **Acolyte** | Your badge. You must find other badges to level up and complete the story. |
| **Glyph** | Found at various villages, community spaces, vendor booths, and parties around the con. |
| **Elder God** | Given to the DEF CON elite. Find them throughout the conference halls. |
| **Cthulhu** | `REDACTED` |

---

## Hardware

- **ESP32**
- **USB-C**
- **Rechargeable Li-Po**

---

## Getting Started

### Startup

A new animation shows badge progress: 10 LEDs, 4 levels, and 6 side quest challenges to complete the badge.

### Choose Your Name

First boot requires your name. You can change it at any time.

One button:
- **Short press** — scroll
- **Long press** — select

### Progress

The top scrolling bar displays your name, rank, and level. It also shows the badges left to connect to in order to complete the main quest.

---

## The Ritual

The main quest, broken into 13 chapters, each with its own story, screen, and LED animation. Upon entering, you'll see a pop-up detailing the badges you need to level up.

Progress through the chapters with a short button press, read the auto-scrolling story, find the animation you like, and long press to select the pattern.

---

## Menu

### Séance

Enter séance mode along with 3 other badges to complete the circuit. They will beacon out, sacrificing all badges in the vicinity. They too will propagate the signal.

### Sacred Text

A short help/menu screen explaining some of the badge mechanics.

### Cult Members

Tracks the badges you've connected with.

### LED Brightness

Change how intensely the lights are seared into the retinas of the faithful.

### Screen Flip

For when you're wearing the badge around your neck, the way it was intended to be worn.

---

## Unlockable Modes

### Bling

10+ unlockable screen and LED patterns, featuring some of your favorite characters.

### The Corrupt Ritual

The unlockable side quest. A new story and challenges across 6 chapters, with LED and screen animations to unlock.

### R'lyeh Arena

Yes, a battle mode. I kept it simple, hopefully reliable. Search for heretics to battle and challenge them to an RNG fight to the death.

### Another Adventure

Similar to R'lyeh Arena, but with an R&M story arc. Hunt for baby Cthulhu, unlock more bling.

### Exploit

Beacon out and exploit all badges.

### Rick Roll

Similar to Exploit. You get the idea.

---

## Updating Firmware

Patching the app keeps your badge progress intact. Everything runs in the browser.

> **Note:** the flasher uses Web Serial, which means you'll need Chrome or Edge. Firefox and Safari won't work.

### Enter bootloader mode

1. Switch the badge to the **off** position, then connect USB-C.
2. On the back of the badge, hold down **BOOT_BTN1**.
3. Switch the badge **on**, then release **BOOT_BTN1**.

The badge is now in bootloader mode and ready to flash.

### Flash the new firmware

1. Go to **[esptool-js](https://espressif.github.io/esptool-js/)**.
2. Set **Baudrate** to `115200` and click **Connect**.
3. Select the serial port connected to your badge in the pop-up, then click **Connect**.
4. Under **File**, click **Choose File** and select the appropriate `app_xxx.bin` file.
5. Set **Flash Address** to `0x10000`.
6. Click **Program**, leaving everything else at its default.

Your unlocks, name, and progress all survive this.

### Full firmware flash

> **Warning:** this erases your badge progress.

If you need to start from a clean slate, set **Flash Address** to `0x0` and flash `full_cult_v3.bin`. Once that completes, you can flash app files over the top of it at `0x10000` as above.

---

## Cultist Hacks

Cultists who have contributed their own badge hacks.

### [Cargo Cult](https://github.com/ray-goldman/cargo-cult) — *ray-goldman*

A serial-first BLE role emulator for classic ESP32/WROOM boards. Emulates Acolyte, Glyph, Elder God, and Cthulhu roles so badge owners can keep playing and finish the story after the con. Tested on the Society of Shenanigans DEF CON 32 DEFMON badge. Optional OLED and button support, or run it headless over serial.

### [Cargo Cult Multi-Adv](https://github.com/ray-goldman/cargo-cult-multiadv) — *ray-goldman*

The ESP32-C3 companion to Cargo Cult, using concurrent BLE advertising to broadcast three simultaneous Acolyte identities — or three Séance peers, which the classic ESP32 build can't do.

Built something of your own? Open an issue or drop it in the [Discord](https://discord.gg/eUE9ZC9fFf) and it'll get added here.

---

*Ph'nglui mglw'nafh Cthulhu R'lyeh wgah'nagl fhtagn.*
