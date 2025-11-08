# Module I - Final Check & Polish-Up Quiz

**Objective:** To quickly test and reinforce the most important concepts and skills from all topics in Module I.

---

**Instructions:** Answer these questions in your notebook without referring back to the detailed notes if possible. This will test your recall.

### **Section A: Conversions and Arithmetic (Speed & Accuracy)**

1.  **Binary to Hex:** Convert the binary number `1110101.11`₂ to Hexadecimal.
    *(Hint: Handle the integer and fractional parts separately when grouping by four.)*

2.  **Gray Code:** What is the Gray code equivalent of the binary number `1001`?

3.  **BCD & Excess-3:** Represent the decimal number `59` in both:
    *   a) BCD
    *   b) Excess-3

4.  **2's Complement Subtraction:** Perform `20 - 45` using 8-bit 2's complement arithmetic. Show all the steps clearly.

### **Section B: Concepts and Definitions (Recall)**

5.  **Parity:** A byte of data `10110101` is received along with an **even** parity bit set to `1`. Is the data correct or has an error occurred? Why?

6.  **Logic Families:** What is the **single biggest advantage** of CMOS logic over TTL logic?

7.  **Fixed vs. Floating Point:** Which representation scheme (Fixed or Floating) would be better suited for a scientific calculator application? Briefly state why.

### **Section C: Diagrams (Visual Memory)**

8.  **TTL NAND Gate:** In the "Totem-Pole" output stage of a TTL NAND gate, what prevents both the top (`Q3`) and bottom (`Q4`) transistors from being ON at the same time, which would cause a short circuit?
    *(Hint: It's the role of a specific component.)*

9.  **CMOS NOR Gate:** In the internal diagram of a 2-input CMOS NOR gate, are the PMOS transistors connected in **series** or **parallel**? What about the NMOS transistors?

10. **Draw It:** Without looking at your notes, sketch a rough diagram of the 2-input CMOS NOR gate. Don't worry about perfection, just get the main structure (pull-up and pull-down networks) correct.

---

### **Answer Key**

*(Complete the quiz first, then check your answers below.)*

1.  **Answer:** `(75.C)₁₆`
    *   Integer `0111 0101` → `7 5`
    *   Fraction `.1100` → `C`
2.  **Answer:** `1101` (Gray)
    *   G₃=1; G₂=1⊕0=1; G₁=0⊕0=0; G₀=0⊕1=1
3.  **Answer:**
    *   a) BCD: `0101 1001`
    *   b) Excess-3: `1000 1100` (`5+3=8`, `9+3=12`)
4.  **Answer:** `-25`
    *   +20 = `00010100`; +45 = `00101101`
    *   2's comp of 45 = `11010011`
    *   `00010100 + 11010011 = 11101001`
    *   No carry -> Negative. 2's comp of result is `00011011` = 25. So, -25.
5.  **Answer:** An **error has occurred**.
    *   The data `10110101` has five `1`s (odd). For even parity, the parity bit should have been `1` to make the total count of ones six (even). The received word `101101011` has six `1`s. Wait, the question states the even parity bit *is* 1. So the transmitted word was `10110101` `1`. The number of `1`s is six, which is even. The data is **correct** based on the parity check. *Correction*: Let me re-read the question carefully. The data is `10110101`, it has five '1's. The parity bit is `1`. Total number of `1`s is six. Six is an even number. For an **even parity system**, this is a **valid** transmission. **No error is detected.**
6.  **Answer:** Extremely **low static power consumption**.
7.  **Answer:** **Floating-Point**, because it supports a huge dynamic range of numbers needed for scientific calculations.
8.  **Answer:** The **Phase Splitter** transistor (`Q2`). It provides complementary signals to the bases of `Q3` and `Q4`, ensuring one is turning ON while the other is turning OFF.
9.  **Answer:** PMOS are in **series**; NMOS are in **parallel**.
10. **Answer:** Check your sketch against your notes. Key points are two PMOS in series for pull-up and two NMOS in parallel for pull-down.
