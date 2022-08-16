[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/firstcontributions/first-contributions)
[![Discord](https://img.shields.io/discord/548530462419582996?style=flat-square&logo=discord&logoColor=white)](https://discord.gg/frjFXZB "Redirect to Keycapsss Discord")
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

# Puchi-BLE

## ToDo

- [ ] Status Led‘s (what they indicate)
- Bootloader
  - [ ] Which and what changes
  - [ ] How to enter bootloader mode
- [ ] Pinout
- [ ] How to compile/use [ZMK](https://zmk.dev/)
- [ ] Create a ZMK Puchi-BLE board
- [ ] How to compile/use QMK [nrf52 fork](https://github.com/sekigon-gonnoc/qmk_firmware/tree/nrf52)
- [ ] How to flash a firmware
- [x] What batteries are supported

## Battery (read carefully)

- Puchi-BLE supports 1S LiPo batteries (4.2V)
- Only use LiPo batteries with a protection circuit, because the Puchi-BLE has no low voltes (discharge) protection for batteries ![LiPo battery 301230 with protection circuit](./img/lipo-301230.jpg)
- A 301230 (3.0 x 12 x 30 mm) LiPo battery fit between 4.5mm tall pin sockets
- Connect the battery to B+ (red) and B- (black ), or RAW (red) and GND (black) (these pairs of pins are internally connected)
- __Avoid reverse polarity__ (nRF52840 chip is usually destroyed first)
- __Note that a few keyboards have RAW and VCC pins connected together (namely Helix and Gherkin), and will kill the controller__ (RAW pin is for the charger only). You may just not solder RAW pin to the keyboard as a workaround.

## FAQ

- Do i need a TRRS cable to connect the split keyboard halfs?
  - No, the slave side connects wireless to the master side. Optional you can use a cable (no charge over TRRS cable).
- What's the battery life?
  - Approximately 2weeks with a 100mAh battery (no oled, or led‘s).
- Is there a lag while typing?
  - Bluetooth devices can reach a latency of 1.3 ms. Lower latency means more power drain and reduce the battery life.
- Is it possible to switch between Bluetooth devices?
  - Yes, QMK and ZMK have support for up to 5 Bluetooth profiles.
- What batteries work with the Puchi-BLE?
  - LiPo batteries with 1S. Also important is that the LiPo batterie has a protection circuit
- Are batteries available in the shop?
  - No, due to the german law, i don’t offer batteries in the shop. You can get LiPo batteries on Ebay and Aliexpress.
- What are the EXT_VCC and EXT_GND? Are they the same pins as VCC and GND?
  - Yes. Power output is sofware-controlled to save battery (RGB LEDs draw up to 1 mA each when off).
