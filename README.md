# EXPERIMENT NO. 2

# DESIGN AND VERIFICATION OF COMBINATIONAL CIRCUIT: HALF AND FULL ADDERS, HALF AND FULL SUBTRACTORS

### Submitted By

**GOPAL B**
B.E. Electronics and Communication Engineering (ECE)
Saveetha Engineering College, Chennai

### Course

**EC1801 – Digital Logic Circuits Design Laboratory**

---

## AIM

To design and verify Half Adder, Full Adder, Half Subtractor, and Full Subtractor circuits using VHDL and verify their truth tables through simulation. Based on the laboratory experiment on combinational circuits. 

---

## SOFTWARE REQUIRED

1. Xilinx Vivado / Xilinx ISE
2. ModelSim
3. GHDL (Optional)

---

## THEORY

### Half Adder

A Half Adder is a combinational circuit used to add two binary bits. It has two inputs (A, B) and two outputs (SUM, CARRY).

**Boolean Expressions**

```text
SUM = A ⊕ B
CARRY = A · B
```

### Full Adder

A Full Adder adds three binary inputs (A, B, Cin) and produces Sum and Carry outputs.

**Boolean Expressions**

```text
SUM = A ⊕ B ⊕ Cin
CARRY = AB + BCin + ACin
```

### Half Subtractor

A Half Subtractor performs subtraction of two binary bits.

**Boolean Expressions**

```text
DIFFERENCE = A ⊕ B
BORROW = A'B
```

### Full Subtractor

A Full Subtractor subtracts three bits (A, B, Bin).

**Boolean Expressions**

```text
DIFFERENCE = A ⊕ B ⊕ Bin
BORROW = A'B + BBin + A'Bin
```

The above equations are consistent with the truth tables and K-map expressions given in the lab manual. 

---

# PROGRAM

## HALF ADDER

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity half_adder is
    Port(
        A, B : in STD_LOGIC;
        SUM, CARRY : out STD_LOGIC
    );
end half_adder;

architecture Behavioral of half_adder is
begin
    SUM <= A xor B;
    CARRY <= A and B;
end Behavioral;
```

---

## FULL ADDER

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity full_adder is
    Port(
        A, B, Cin : in STD_LOGIC;
        SUM, CARRY : out STD_LOGIC
    );
end full_adder;

architecture Behavioral of full_adder is
begin
    SUM <= A xor B xor Cin;
    CARRY <= (A and B) or (B and Cin) or (A and Cin);
end Behavioral;
```

---

## HALF SUBTRACTOR

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity half_subtractor is
    Port(
        A, B : in STD_LOGIC;
        DIFF, BORROW : out STD_LOGIC
    );
end half_subtractor;

architecture Behavioral of half_subtractor is
begin
    DIFF <= A xor B;
    BORROW <= (not A) and B;
end Behavioral;
```

---

## FULL SUBTRACTOR

```vhdl
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity full_subtractor is
    Port(
        A, B, Bin : in STD_LOGIC;
        DIFF, BORROW : out STD_LOGIC
    );
end full_subtractor;

architecture Behavioral of full_subtractor is
begin
    DIFF <= A xor B xor Bin;
    BORROW <= ((not A) and B) or (B and Bin) or ((not A) and Bin);
end Behavioral;
```

---

# TRUTH TABLE

## HALF ADDER

| A | B | SUM | CARRY |
| - | - | --- | ----- |
| 0 | 0 | 0   | 0     |
| 0 | 1 | 1   | 0     |
| 1 | 0 | 1   | 0     |
| 1 | 1 | 0   | 1     |

---

## FULL ADDER

| A | B | Cin | SUM | CARRY |
| - | - | --- | --- | ----- |
| 0 | 0 | 0   | 0   | 0     |
| 0 | 0 | 1   | 1   | 0     |
| 0 | 1 | 0   | 1   | 0     |
| 0 | 1 | 1   | 0   | 1     |
| 1 | 0 | 0   | 1   | 0     |
| 1 | 0 | 1   | 0   | 1     |
| 1 | 1 | 0   | 0   | 1     |
| 1 | 1 | 1   | 1   | 1     |

---

## HALF SUBTRACTOR

| A | B | DIFF | BORROW |
| - | - | ---- | ------ |
| 0 | 0 | 0    | 0      |
| 0 | 1 | 1    | 1      |
| 1 | 0 | 1    | 0      |
| 1 | 1 | 0    | 0      |

---

## FULL SUBTRACTOR

| A | B | Bin | DIFF | BORROW |
| - | - | --- | ---- | ------ |
| 0 | 0 | 0   | 0    | 0      |
| 0 | 0 | 1   | 1    | 1      |
| 0 | 1 | 0   | 1    | 1      |
| 0 | 1 | 1   | 0    | 1      |
| 1 | 0 | 0   | 1    | 0      |
| 1 | 0 | 1   | 0    | 0      |
| 1 | 1 | 0   | 0    | 0      |
| 1 | 1 | 1   | 1    | 1      |

---

## OUTPUT

Simulation waveforms verify the correct operation of:

* Half Adder
* Full Adder
* Half Subtractor
* Full Subtractor

*(Insert waveform screenshots here)*

---

## RESULT

Thus, the Half Adder, Full Adder, Half Subtractor, and Full Subtractor circuits were designed using VHDL and their truth tables were successfully verified through simulation. The functionality matches the combinational circuit experiment specified in the laboratory manual. 

---

## AUTHOR DETAILS

**Name:** GOPAL B
**Department:** Electronics and Communication Engineering (ECE)
**College:** Saveetha Engineering College
**Course Code:** EC1801 – Digital Logic Circuits Design Laboratory
**Experiment No.:** 2

---

## REPOSITORY STRUCTURE

```text
EXP-03-Combinational-Circuits/
│
├── README.md
├── half_adder.vhd
├── full_adder.vhd
├── half_subtractor.vhd
├── full_subtractor.vhd
├── testbench.vhd
└── waveform.png
```
