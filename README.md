# sorting-of-numbers
## Aim
To write and execute an Assembly Language Program for sorting data in Ascending and  descending order using 8051 microcontroller on Keil software.
---

## Apparatus Required
- Personal Computer  
- Keil µVision software  
---

## Algorithm(ASCENDING ORDER)
1. Initialize the register **R7** with count (number of elements).  
2. Get the first two elements into two registers.  
3. Compare the two elements:  
   - If the value in register **R0** is lower, exchange **A** and **R0** data.  
   - Otherwise, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0** → if yes, move the register **R0 & A**.  
5. Increment pointer and decrement **R7**.  
6. If **R7 ≠ 0**, repeat from Step 2.  
7. Otherwise, stop the program.  
---

## Program (Ascending order)

```asm
ORG 0000H
MOV R4,#04H        
OUTER: MOV R3,#04H
MOV R0,#50H        
INNER: MOV A,@R0
MOV B,A
INC R0
CLR C
SUBB A,@R0         
JC NO_SWAP         
; Exchange elements
MOV A,@R0
XCH A,B
MOV @R0,A
DEC R0
MOV A,B
XCH A,B
MOV @R0,A
INC R0
NO_SWAP: DJNZ R3,INNER
DJNZ R4,OUTER
END



```
## OUTPUT(Ascending order)
![WhatsApp Image 2026-03-09 at 21 17 25](https://github.com/user-attachments/assets/b6729a94-53b6-468b-b331-fa55bb46c512)




---

## Algorithm(Descending order)
1. Initialize the register **R7** with count.  
2. Get first two elements in two registers.  
3. Compare the two elements of data:  
   - If the value of **R0** register is high, then exchange **A** and **R0** data.  
   - Else, increment pointer and decrement register **R7**.  
4. Check if **R7 = 0**, then move the contents of **R0** and **A**.  
5. Again increment pointer and decrement **R7**.  
6. Check if **R7 = 0**:  
   - If **No**, repeat the process from Step 2.  
   - If **Yes**, stop the program.  
---
## Program (Descending order)

```asm
ORG 0000H
MOV R1,30H     
DEC R1

LOOP1: MOV R0,#40H
       MOV R6,30H
       DEC R6

LOOP:  MOV A,@R0
       INC R0
       MOV B,@R0
       CJNE A,B,NEXT
NEXT:  JNC DOWN

       MOV @R0,A
       DEC R0
       MOV @R0,B
       INC R0

DOWN:  DJNZ R6,LOOP
       DJNZ R1,LOOP1  

END



```
## OUTPUT(Descending order)
![WhatsApp Image 2026-03-09 at 21 17 26](https://github.com/user-attachments/assets/18889a5e-1907-4c02-8308-6d302cafb6cb)




---
## RESULT:
Thus the sorting of given data was done using 8051 keil software.

