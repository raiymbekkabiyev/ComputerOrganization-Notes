# Computer Organization Notes
## Chapter 4 - The Processor 
### 4.1 Introduction 
* Compiler & Instruction Set Archi --> instruction count 
* Processor --> clock cycle time & clock cycles per instruction 
#### A basic MIPS Implementation
* The memory-reference instructions load word (lw) and store word (sw) \
* The arithmetic-logical instructions add, sub, AND, OR, and slt \
* The instructions branch equal (beq) and jump (j), which we add last \

For every instruction, the first two steps are identical: \
1. Send the program counter (PC) to the memory that contains the code and fetch the instruction from that memory. \
2. Read one or two registers, using fields of the instruction to select the registers to read. For the load word instruction, we need to read only one register, but most other instructions require that we read two registers.\ 

* All instruction classes, except jump, use the arithmetic-logical unit (ALU) after reading the registers.

Abstract implementation of the MIPS: 
* PC <-- can come from one of two adders
* The data written into the register file <-- ALU or the data memory
*  The second input to the ALU <-- a register or the immediate field of the instruction.
**Multiplexer decides on the selection**
* The data memory must read on a load and write on a store. 
* **A control unit, which has the instruction as an input, is used to determine how to set the control lines for the functional units and two of the multiplexors.**
* The third multiplexor, which determines whether PC+4 or the branch destination address is written into the PC, is set based on the Zero output of the ALU, which is used to perform the comparison of a beq instruction.  
* 

