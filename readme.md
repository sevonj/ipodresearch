This repo contains my notes on classic iPod hardware.
Trying to collect fragmented knowledge from public documents, ipodlinux wiki, ipodlinux/rockbox/ipodloader/etc. sources.


# iPod 4G
PP5020 SoC contains 2 arm cores: CPU and COP.
ARM7TDMI. Note that ARM7 is not the same thing as ARMv7. It uses ARMv4 ISA.
SoC components:
- CPU
- COP
- Mailbox
- IRAM (96KB)
- Interface controller?

Other hardware includes
- 32MB SDRAM chip
- LCD (Monochrome in 1st model, Color in "photo" and 3rd models) (LCD1 or LCD2)
- IDE hard drive (EIDE)
- Piezo clicker (PWM)
- Audio: Wolfson WM8975 (I2S)
- Clickwheel (I2C?)
- Buttons (I2C?)

Separate firmware partition before hfs/fat partition:
https://web.archive.org/web/20180501050730/http://www.ipodlinux.org/Firmware.html#Firmware_Partition_format

## Rough Memory Map

| Start addr  | Content                            |
| ----------- | ---------------------------------- |
| 0x0000_0000 | FLASH                              |
| 0x1000_0000 | DRAM                               |
| 0x4000_0000 | IRAM                               |
| 0x6000_0000 | Processor ID                       |
| 0x6000_1000 | Mailboxes                          |
| 0x6000_1038 | Mystery IRQ Controllers?           |
| 0x6000_3000 | Total mystery 1                    |
| 0x6000_4000 | Interrupt Controller               |
| 0x6000_5000 | Timers                             |
| 0x6000_6000 | Device Controller                  |
| 0x6000_7000 | CPU Controller                     |
| 0x6000_9000 | Total Mystery 2                    |
| 0x6000_A000 | DMA Controller                     |
| 0x6000_C000 | Cache Controller                   |
| 0x6000_D000 | GPIO Controller                    |
| 0x6000_F100 | Interrupt Vector Table             |
| 0x7000_0000 | PP Controller (PP50XX controller?) |
| 0x7000_2800 | I2S Controller                     |
| 0x7000_3000 | LCD1 Controller (monochrome)       |
| 0x7000_3800 | Total mystery 3                    |
| 0x7000_6000 | Serial Controller                  |
| 0x7000_8A00 | LCD2 Controller (color)            |
| 0x7000_A000 | PWM Controller                     |
| 0x7000_C000 | I2C Controller                     |
| 0x7000_C100 | OPTO?                              |
| 0xc031_b1d8 | mystery_flash_stub                 |
| 0xc031_b1e8 | mystery_flash_stub                 |
| 0xC300_0000 | EIDE Controller                    |
| 0xC500_0000 | USB Controller                     |
| 0xC600_0000 | FireWire Controller                |
| 0xF000_0000 | Memory Controller                  |
| 0xffff_FE00 | mystery_flash_stub                 |