Similar to [[D-Type Instructions]].

![[byte_halfword_operations.png]]

# Unsigned
## Load byte
```armasm
LDURB Rt, [Rn, offset]
```
- Load to the least significant byte position, extend to the number of bits in Rt

## Store byte
```armasm
STURB Rt, [Rn, offest]
```
- Store just the rightmost bit of Rt into Rn

## Load halfword
```armasm
LDURH Rt, [Rn, offset]
```
- Load to the least significant halfword position, extend to the number of bits in Rt

## Store halfword
```armasm
STURH Rt, [Rn, offset]
```
- Store just rightmost halfword

# Signed

## Load byte
```armasm
LDURSB Rt, [Rn, offset]
```
- Load to the least significant byte position, extend to the number of bits in Rt
- *Sign extend to the 32 bits in rt*
	- $-8$ is $11111000$
## Load halfword
```armasm
LDURSH Rt, [Rn, offset]
```
- Load to the least significant halfword position, extend to the number of bits in Rt
- *Sign extend to the 32 bits in rt*
## Load word
```armasm
LDURSW Xt, [Rn, offset]
```
- Load to the least significant halfword position, extend to the number of bits in Rt
- *Sign extend to the 64 bits in wt*