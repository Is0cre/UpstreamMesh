# Draft flood frame

MeshCore moves the packets. The twelve bytes below are a draft of what a flood frame would carry inside that mesh.

This is not MeshCore's packet format. It is not implemented. The bytes in the worked example on [protocol.html](../protocol.html) are an illustration, not a capture.

| Bytes | Name | Draft |
| --- | --- | --- |
| 0 | Type | `0x01` heartbeat and time. `0x02` sensor report. `0xFF` emergency alert. |
| 1–4 | Network time | `uint32` seconds. The gateway's notion of UTC. A node that just booted has only its own uptime until it hears one. |
| 5 | Basin state | `0` nominal, `1` advisory, `2` surge. On the first five, surge is the frame and the log, plus a buzzer if someone is there. |
| 6–7 | Stage delta | `int16` centimeters from the node's own baseline. Two upstream nodes have to agree before it becomes an alert. |
| 8–11 | Tag | Four bytes: a truncated authenticator and a counter, so a replay of an old surge is obvious. This raises the cost of a blind forgery. It is not a full HMAC-SHA256, and it does not by itself stop a determined attacker. |

## Wake, as a power goal

A LoRa radio that listens all the time draws on the order of 10 mA. The SX1276 datasheet puts receive current around 10–12 mA. That empties a small pack. The draft sleeps, then wakes for one beacon.

The listen window has to cover that beacon's airtime. At SF10 and 125 kHz a 12-byte frame is on the air for a few hundred milliseconds, so a 50 ms slot only works if the beacon uses a faster spreading factor. A weak hop can drop to a slower one. Transmit current depends on power. Sleep current of a whole node depends on the regulator, and it will not be the chip's deep-sleep figure.

Those are bounds for the design, not a measurement of a built unit. How this duty cycle sits on MeshCore's repeater and companion roles is still open. MeshCore does not use this schedule.
