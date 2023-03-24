# Ipod 4G GPIO Map

| Address Range             | Content     |
| ------------------------- | ----------- |
| 0x6000_d000..=0x6000_d07f | gpio_abcd   |
| 0x6000_d080..=0x6000_d0ff | gpio_efgh   |
| 0x6000_d100..=0x6000_d17f | gpio_ijkl   |
| 0x6000_d800..=0x6000_d97f | GPIO mirror |

From *some* pp soc:
| Address     | size | type | Content               |
| ----------- | ---- | ---- | --------------------- |
| 0x6000_d000 | 8b   | rw   | GPIO SPIO selection   |
| 0x6000_d010 | 8b   | rw   | GPIO out enable       |
| 0x6000_d020 | 8b   | rw   | GPIO out register     |
| 0x6000_d030 | 8b   | ro   | GPIO in register      |
| 0x6000_d040 | 8b   | ro   | GPIO interrupt status |
| 0x6000_d050 | 8b   | rw   | GPIO interrupt enable |
| 0x6000_d060 | 8b   | rw   | GPIO interrupt level  |
| 0x6000_d070 | 8b   | clr  | GPIO interrupt clear  |




# Ipod 4G GPIO
 
| Pin |      | Function                      |
| --- | ---- | ----------------------------- |
| A0  |      |                               |
| A1  |      |                               |
| A2  |      | jack input/output??           |
| A3  |      |                               |
| A4  |      |                               |
| A5  |      | hold sw?                      |
| A6  |      |                               |
| A7  |      | jack inserted?                |
| B0  | in   | Charger                       |
| B1  | out  | Charger enable                |
| B2  | out  | LCD2 Backlight something?     |
| B3  | out  | LCD2 Backlight?               |
| B4  | out? | OPTO                          |
| B5  | ?    | OPTO                          |
| B6  |      |                               |
| B7  |      | Disabled for serial OPTO init |
| C0  | in   |                               |
| C1  | in   | FireWire detect?              |
| C2  | in   | FireWire power                |
| C3  | in   |                               |
| C4  |      |                               |
| C5  |      |                               |
| C6  | out  |                               |
| C7  |      |                               |
| D0  | in   |                               |
| D1  |      | Tx/Rx?                        |
| D2  |      | Tx/Rx?                        |
| D3  | in   | USB power / detect            |
| D4  | out  |                               |
| D5  | out  |                               |
| D6  | out  |                               |
| D7  | out  |                               |
| E   |      |                               |
| F   |      |                               |
| G   |      |                               |
| H   |      |                               |
| I0  |      |                               |
| I1  |      |                               |
| I2  |      |                               |
| I3  |      |                               |
| I4  |      |                               |
| I5  |      |                               |
| I6  |      | jack input/output??           |
| I7  |      |                               |
| J0  |      |                               |
| J1  |      |                               |
| J2  |      | ide_powered?                  |
| J3  |      |                               |
| J4  |      |                               |
| J5  |      |                               |
| J6  |      |                               |
| J7  |      |                               |
| K   |      |                               |
| L   |      |                               |
