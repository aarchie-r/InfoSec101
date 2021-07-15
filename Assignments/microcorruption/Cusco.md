# Cusco - 25 points

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [microcorruption](https://microcorruption.com/)

## Walkthrough

looking at login breakpoint I saw various instructions but the thing changed after the instruction-

```
4528:  b012 4644      call	#0x4446 <unlock_door>
452c:  3f40 d144      mov	#0x44d1 "Access granted.", r15
```
for buffer overflow exploitation when entered more than 16 bytes, it altered the stack pointer. So calling `unlock_door` , due to endian- we tried password as
`1111 1111 1111 1111 1111 1111 1111 1111 4644` in hex and it worked.

## Password
`1111 1111 1111 1111 1111 1111 1111 1111 4644`

