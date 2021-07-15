# Sydney - 15 points

Author: [Aarchie](https://github.com/aarchie-r)

Problem Page: [microcorruption](https://microcorruption.com/)

## Walkthrough

```
448a <check_password>
448a:  bf90 724c 0000 cmp	#0x4c72, 0x0(r15)
4490:  0d20           jnz	$+0x1c
4492:  bf90 5846 0200 cmp	#0x4658, 0x2(r15)
4498:  0920           jnz	$+0x14
449a:  bf90 3966 0400 cmp	#0x6639, 0x4(r15)
44a0:  0520           jne	#0x44ac <check_password+0x22>
44a2:  1e43           mov	#0x1, r14
44a4:  bf90 4e62 0600 cmp	#0x624e, 0x6(r15)
44aa:  0124           jeq	#0x44ae <check_password+0x24>
44ac:  0e43           clr	r14
44ae:  0f4e           mov
```
In the `check_password` breakpoint checking 2 bytes at a time by comparing it with a value. Converting it to hex we get-
due to endianness of system
4c72 to 724c 
4658 to 5846
6639 to 3966
624e to 3966
So,
724c 5846 3966 4e62 in hex is password 


## Password
`724c 5846 3966 4e62`

