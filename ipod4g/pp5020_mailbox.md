# PP5020 Mailbox
The mailbox unit sits between CPU and COP and has a few registers for communication between the two. Does it not exist in PP5002?

| Address     | Access | Size | Name      |
| ----------- | ------ | ---- | --------- |
| 0x6000_1000 |        |      | Base addr |
| 0x00        | ro     | 4    | Status    |
| 0x04        | wo     | 4    | Set       |
| 0x08        | wo     | 4    | Clear     |
| 0x0c        | ?      | ?    | unused    |
| 0x10        | ro/rw? | 16?  | CPU queue |
| 0x20        | rw/ro? | 16?  | COP queue |

## Status
32bit read only. Mailbox Status register is used for mutual exclusion. Does it lock resources? Each bit refers to some resouce. Which resources?

| 31    | 30    | 29    | 28    | 27  | 26  | 25  | ... |
| ----- | ----- | ----- | ----- | --- | --- | --- | --- |
| IRAM? | IRAM? | IRAM? | IRAM? | ?   | ?   | ?   | ?   |

## Set
32bit write only. Either processor can write here to request setting a bit in Status.

## Clear
32bit write only. Either processor can write here to request clearing a bit in Status.

## Unused
"MBX_UNKNOWN1" in rockbox. I suspect that there's in fact nothing here.

## Queues
Haven't yet looked at exact contents and behaviour yet.
Read/write for sender, read only for recipient?

CPU queue: Messages from COP to CPU.
COP queue: Messages from CPU to COP.

Rockbox code:
/* COP can set bit 29 - only CPU read clears it */
/* CPU can set bit 29 - only COP read clears it */
