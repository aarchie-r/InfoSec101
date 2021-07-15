# Hanoi - 20 points

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [microcorruption](https://microcorruption.com/)

## Walkthrough

First, started with breaking the breakpoint `login`  we get the instruction as-
`455a:  f290 2200 1024 cmp.b	#0x22, &0x2410`
Compares first byte in 2410 to be 22 in hex
When we put any password we got register 2400 being filled up
thus we put random number of 1s and saw after 16 bytes it started storing in 2410.

```
2400:   1111 1111 1111 1111 1111 1111 1111 1111   ................
2410:   1100 0000 0000 0000 0000 0000 0000 0000   ................
```

And filled it with the password as
1111 1111 1111 1111 1111 1111 1111 1111 22 in hex

## Password
`1111 1111 1111 1111 1111 1111 1111 1111 22`

