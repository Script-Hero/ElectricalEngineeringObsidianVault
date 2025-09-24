```armasm
MOV X9, XZR // i = 0
loop1:
	LSL X10, X9, #3 // X10 = i * 8
	ADD X11, X0, X10 // X11 = &array[i]
	STUR XZR, [X11, #0] // array[i] = 0
	ADDI X9, X9, #1 // i = i + 1
	CMP X9, X1 // compare i to size
	B.LT loop1 // if (i < size) go to loop1
	MOV X9, X0 // p = & array[0]
	LSL X10, X1, #3 // X10 = size * 8
	ADD X11, X0, X10 // X11 = &array[size]
loop2:
	STUR XZR, [X9, #0] // Memory[p] = 0
	ADDI X9, X9, #8 // p = p + 8
	CMP X9, X11 // compare p to to &array[size]
	B.LT loop2 // if (p < &array[size]) go to loop2
```