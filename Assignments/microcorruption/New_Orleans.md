# New Orleans - 10 points

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [microcorruption](https://microcorruption.com/)

## Walkthrough

At first, looking at the Disassembly I got to see two important breakpoints – `create_password` and `main`. I breaked both to see whats happening.

In create_password breakpoint, it had nothing to do with changing or creating password.
In main break-point, while going step to step I got an instruction as 
`44c2:  ee9d 0024      cmp.b	@r13, 0x2400(r14)`
Which says to compare value stored in ‘r13’ with the register ‘r14’ by adding 0x2400 to it .  So, it compares value of first 8 bytes at 0x2400 and input. Which means the password is already there in memory.
Thus, reading command at 0x2400 we got the password.
`2400:   4e45 3e4e 7946 3500 0000 0000 0000 0000   NE>NyF5.........`

## Password
`NE>NyF5`

