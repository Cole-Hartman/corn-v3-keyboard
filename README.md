# crkbd-cherry-v3-build

My journey down the rabbit hole.  
Building from [foostan's archived V3 release](https://github.com/foostan/crkbd/releases/tag/v3-final)

## Check List:
- [ ] [Make parts list](#parts-list)
  - [ ] [Building and ordering the PCB](#building-and-ordering-the-pcb)
- [ ] [Install/Configure QMK](#installconfigure-qmk)
- [ ] [Compile/Flash Firmware](#compileflash-firmware)
- [ ] [Prepare the OLEDS](#prepare-oleds)
- [ ] [Prepare the PCB](#prepare-pcb)
- [ ] [Solder PCB top components](#solder-pcb-top-components)
- [ ] [Solder pro-micro](#solder-pro-micro)
- [ ] [Solder OLEDs](#solder-oleds)
- [ ] [Solder diodes](#solder-diodes)
- [ ] [Solder hot-swaps](#solder-hot-swaps)
- [ ] [Solder under-glow leds](#solder-under-glow-leds)
- [ ] [Solder per-key leds](#solder-per-key-leds)
- [ ] [Mount the case](#mount-the-case)

## Parts list
**Keyboard**
| Name | Count | Details | Price |
|:-|:-|:-|:-|
| PCB | 1x | [Corne PCB Printed on JLCPCB](https://jlcpcb.com/) | $40 |
| OLED | 2x | [OLED 128X32 OLED Display Module 0.91" IIC Communicate for ardunio](https://www.aliexpress.com/item/32777216785.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA) | $0.30 |
| DIODES | 100x | [1N4148W T4 SOD-123](https://www.aliexpress.us/item/2251832735176193.html?spm=a2g0o.cart.0.0.624d38dayf8uXk&mp=1&gatewayAdapt=glo2usa) | $1 |

**Tools**
| Name | Count | Details | Price |
|:-|:-|:-|:-|
| Soldering Kit | 1x | [Kit](https://www.amazon.com/Soldering-Kit-Temperature-Desoldering-Electronics/dp/B07GTGGLXN/ref=sr_1_5?crid=38MPRDWM5JBD2&dib=eyJ2IjoiMSJ9.bN2ArPTpgQRijAd577UAx2lb0lxJe9OJfvIrJ6Bhu94uZRdZ0QiOR1-KaozOEwvqRFJO6PmfGYfSgNX8FCBUUr7tF74wEkvH2oPiK_vOUmZ4kcyFUs1GxnhlBGenUVRiocpGicXoasYk4pn2j1hmV_uITJfg-8F86EbmyExxmN_qOA8LUu2XNpdrcps8dFHy3x6Vsxs0nPWFvIyXwVel8fIs0YaS7FLhzvMPE6c5Bm9Sv0gDM9kTUX6UC23l9WSCI8h0VyGKKpOtbs7h1YVjf3JVk5e2DfrIKZ26WudrKVE.zCvhrofR5D4P22aA3xQqujJoRpbFraz-JM9WFvdwxwk&dib_tag=se&keywords=soldering+kit&qid=1724294807&sprefix=soldering+ki%2Caps%2C181&sr=8-5#customerReviews) | $13 |

---

- [ ] 1x  Corne Case [Laser cut mine on Brazil](https://www.acrilicos60.com.br/)
- [ ] 42x Keycaps - 1u x 40, 1.5u x 2
- [ ] 2x  [Pro Micro ATmega32U4 5V/16MHz Module controller Mega32U4 Mini leonardo for Arduino with the bootloader](https://www.aliexpress.com/item/32768308647.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 42x [Kailh Hot-swappable PCB Socket Sip For Mechanical Keyboard](https://www.aliexpress.com/item/4001051840976.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 1M  [Round Copper Wire 0.5mm](https://www.aliexpress.com/item/4000781904492.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 4x  [2.54mm Pin Header Female Single Row 40](https://www.aliexpress.com/item/32817226478.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 2x  [PJ320D 3.5MM Headphone TRRS Jack Socket Female Connector](https://www.aliexpress.com/item/32785315917.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 1x  [1m 4 pole Stero audio cable Car AUX MP3/MP4 3.5mm male to male](https://www.aliexpress.com/item/32459681560.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 2x  [Micro Switch Push Button 3.5X6.0X4.3mm 1136-4.3 DIP Black](https://www.aliexpress.com/item/1068908059.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 42x [Holy Pandas switches](https://www.aliexpress.com/item/1005001465063863.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 24x [Screws M2 6mm](https://www.aliexpress.com/item/32661182311.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 10x [Spacers M2 7mm](https://www.aliexpress.com/item/32970573343.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 4x  [Spacers M2 10mm](https://www.aliexpress.com/item/32970573343.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 42x [Leds SK6812-mini-E](https://www.aliexpress.com/item/4000476037223.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)
- [ ] 12x [Leds ws2812b](https://www.aliexpress.com/item/4000750610574.html?spm=a2g0s.9042311.0.0.27424c4dlrgRjA)

## Building and ordering the PCB
**Convert archived V3 KiCad project files to Gerber files**  
[JLCPCB - How to generate Gerber and Drill files in KiCAD 8](https://jlcpcb.com/help/article/how-to-generate-gerber-and-drill-files-in-kicad-8)

**Order the PCB from JLCPCB**  
[GERBER Files](./GERBER-v3-cherry.zip)


