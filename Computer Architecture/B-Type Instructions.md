Unconditional branch instructions. 

```armasm
B address
```

You can combine with ```CMP``` to create conditionals.

### Example
```armasm
CMP X1, X2
B.EQ equal // bracnh to equal if X1 == X2
B.GT greater_than 
B.LT less_than
```



# Format

| **opcode** | **address** |
| :--------: | :---------: |
|   6 bits   |   26 bits   |
## Decimal
For the example branch command
```armasm
B 10000
```
The decimal equivalent is 

|  5  | 10000 |
| :-: | :---: |

