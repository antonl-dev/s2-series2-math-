# STUDY BLOCK 1: 4-Variable K-Map Simplification

**OBJECTIVE:** To correctly solve any 4-variable K-map problem with "don't cares" in under 10 minutes.

---

### **The Procedure (Memorize This!)**

**Step 1: Draw the Grid.**
*   Always draw a 4x4 grid.
*   Label the top `CD` and the side `AB`.
*   Label the columns `00, 01, 11, 10` (Gray Code order!).
*   Label the rows `00, 01, 11, 10`.
*   Fill in the cell numbers (0 to 15) to avoid mistakes.

| AB\CD | 00 | 01 | 11 | 10 |
| :---- | :- | :- | :- | :- |
| **00**  | 0  | 1  | 3  | 2  |
| **01**  | 4  | 5  | 7  | 6  |
| **11**  | 12 | 13 | 15 | 14 |
| **10**  | 8  | 9  | 11 | 10 |

**Step 2: Fill the Map.**
*   Place a `1` in the squares corresponding to the minterms (`∑m`).
*   Place an `X` in the squares for the "don't cares" (`Σd`).

**Step 3: Group the Ones.**
*   **Goal:** Cover all the `1`s using the largest possible groups.
*   **Rules of Grouping (Highest Priority First):**
    1.  **Look for an Octet (8):** Can you group eight `1`s or `1`s-and-`X`s?
    2.  **Look for Quads (4):** Find any groups of four. These can be 2x2 squares, 1x4 lines, or wraparounds.
    3.  **Look for Pairs (2):** Group any remaining `1`s into pairs.
    4.  **Isolate (1):** If a `1` cannot be grouped, circle it by itself.
*   **Crucial:** You can reuse `1`s in multiple groups, but every group must contain at least one `1` that isn't covered by any other group. An `X` can be used to make a group bigger, but you don't *have* to cover all the `X`s.

**Step 4: Write the Simplified Expression.**
*   For each group, find the variables that do **not** change.
*   If a variable is `0` in the group, write it as `A'`.
*   If a variable is `1` in the group, write it as `A`.
*   The final expression is the sum (OR) of all the terms from your groups.

---

### **WORKED EXAMPLE (From your Series Test II Paper)**

Let's solve `F(A,B,C,D) = ∑m(2,5,7,9,12,13,15) + Σd(4,10,11)`.

**1. Fill the Map:**
| AB\CD | 00 | 01 | 11 | 10 |
| :---- | :- | :- | :- | :- |
| **00**  |    |    |    | 1  |
| **01**  | X  | 1  | 1  |    |
| **11**  | 1  | 1  | 1  |    |
| **10**  |    | 1  | X  | X  |

**2. Group the Ones:**
*   **Group 1 (Quad):** Cells 5, 7, 13, 15.
    *   `A` changes (0 -> 1).
    *   `B` is always `1`. So we have `B`.
    *   `C` changes (0 -> 1).
    *   `D` is always `1`. So we have `D`.
    *   **Term 1 = BD**
*   **Group 2 (Quad):** Cells 4, 5, 12, 13. (Using the 'X' at cell 4).
    *   `A` changes (0 -> 1).
    *   `B` is always `1`. So we have `B`.
    *   `C` is always `0`. So we have `C'`.
    *   `D` changes (0 -> 1).
    *   This is incorrect. Let's re-examine. For cells 4,5,12,13:
    *   A changes (0 -> 1). B is 1 for 12,13 but 0 for 4,5. This is not a valid group.
    
Let's re-group correctly.
*   **Group 1 (Quad):** Cells 5, 7, 13, 15. **Term = BD** (As calculated before).
*   **Group 2 (Quad):** Cells 9, 11, 13, 15. (Using 'X' at 11, and re-using 13 and 15).
    *   `A` is always `1`. Term is `A`.
    *   `B` changes (0 -> 1).
    *   `C` changes (0 -> 1).
    *   `D` is always `1`. Term is `D`.
    *   This is also incorrect. B is 0 for 9,11 but 1 for 13,15.
    
**Let's try again, carefully. This is part of the process.**

**Correct Grouping Strategy:**
| AB\CD | 00 | 01 | 11 | 10 |
| :---- | :- | :- | :- | :- |
| **00**  |    |    |    | 1 (2)|
| **01**  | X (4)| 1 (5)| 1 (7)|    |
| **11**  | 1 (12)| 1 (13)| 1 (15)|    |
| **10**  |    | 1 (9)| X (11)| X (10)|

*   **Group 1 (Red Quad):** Cells 5, 7, 13, 15. This covers `1`s at 5, 7, 13, 15.
    *   A changes from 0 to 1. Ignore.
    *   B is always 1. Keep `B`.
    *   C changes from 0 to 1. Ignore.
    *   D is always 1. Keep `D`.
    *   **Term 1 = BD**
*   **Group 2 (Blue Quad):** Cells 2, 10. These don't form a quad. Let's check wraparound.
*   **Group 2 (Blue Pair):** Cells 2, 10. (Wraparound).
    *   A changes from 0 to 1. Ignore.
    *   B is always 0. Keep `B'`.
    *   C is always 1. Keep `C`.
    *   D is always 0. Keep `D'`.
    *   **Term 2 = B'CD'**
*   **Group 3 (Green Pair):** Cells 9, 11. (Using 'X' at 11). This covers `1` at 9.
    *   A is always 1. Keep `A`.
    *   B is always 0. Keep `B'`.
    *   C changes from 0 to 1. Ignore.
    *   D is always 1. Keep `D`.
    *   **Term 3 = AB'D**
*   **Group 4 (Purple Pair):** Cells 12. This one is left. Can we group it with `X` at 4? No. Can we group with 13? Yes, but 13 is already covered. We can still use it. But a better group is with cell 4, no, that's not adjacent. Let's group `12` with `4` - this is not possible. Let's group `12` with `13`.
*   Let's restart the whole grouping to find the optimal one.
    1.  Cover 7 and 15 with **BD**. Also covers 5, 13.
    2.  Cover 2 with 10. **B'CD'**.
    3.  Cover 9 with 11. **AB'D**.
    4.  Cover 12. Can group with 13 (re-use). This gives **ABC'**.
    *   Is this optimal? All 1s are covered.
    *   Final Answer = **BD + B'CD' + AB'D + ABC'**

---

### **YOUR TURN (In your Notebook NOW)**

Simplify the function: `F(A,B,C,D) = ∑m(0, 1, 2, 8, 9, 10) + Σd(3, 7, 15)`

(Take 10 minutes. Do it now. The solution is below.)

.
.
.

**Solution:**
*   **Group 1 (Octet):** Cells 0, 1, 3, 2, 8, 9, 11, 10 (using 'X' at 3 and 'd's). Wait, 11 is not a 'd'. Okay, let's group again.
*   **Group 1 (Quad):** Cells 0, 1, 8, 9. Term = `B'C'`.
*   **Group 2 (Quad):** Cells 0, 2, 8, 10. Term = `B'D'`.
*   **Group 3 (Pair):** Cells 2, 3. Term = `A'B'C`. No, this is wrong. Let's look again at the map.
| AB\CD | 00 | 01 | 11 | 10 |
| :---- | :- | :- | :- | :- |
| **00**  | 1  | 1  | X  | 1  |
| **01**  |    |    | X  |    |
| **11**  |    |    | X  |    |
| **10**  | 1  | 1  |    | 1  |
*   **Group 1 (Quad):** Cells 0, 2, 8, 10. Term = `B'D'`.
*   **Group 2 (Quad):** Cells 0, 1, 8, 9. Term = `B'C'`.
*   All `1`s are covered. **Final Answer: F = B'D' + B'C'**

---

### **Session 2 (1:30 PM - 3:30 PM): 2's Complement & Flip Flops**

Grab lunch, then come back for this.

```markdown
# STUDY BLOCK 2: 2's Complement & Flip-Flop Conversion

---

### **Part A: 2's Complement Subtraction**

**OBJECTIVE:** To subtract binary numbers correctly using 2's complement.

**PROCEDURE for (X - Y):**
1.  Ensure both numbers have the same number of bits (e.g., 8-bit). Pad with leading zeros if needed.
2.  Find the 2's Complement of Y:
    *   Invert all bits of Y (1's complement).
    *   Add 1 to the result.
3.  Add the result to X: `X + (2's comp of Y)`.
4.  **Interpret the Result:**
    *   **Case 1: A final carry is generated.** Discard the carry. The answer is positive and in normal binary form.
    *   **Case 2: No final carry.** The answer is negative and is in 2's complement form. To get the magnitude, take the 2's complement of the result.

**WORKED EXAMPLE (From your paper: 14 - 45)**
1.  **Binary (8-bit):**
    *   +14 = `00001110`
    *   +45 = `00101101`
2.  **2's Complement of 45:**
    *   1's Complement: `11010010`
    *   Add 1: `11010011`
3.  **Add to 14:**
    ```
      00001110  (14)
    + 11010011  (-45)
    -----------
      11011101
    ```
4.  **Interpret:**
    *   There is **no final carry**. The answer is negative.
    *   The result `11011101` is the 2's complement of the answer.
    *   Find its magnitude: Invert (`00100010`) -> Add 1 (`00100011`).
    *   `00100011` in decimal is 32 + 2 + 1 = 35.
    *   **Final Answer: -35**

---

### **Part B: Flip-Flop Conversion (T from SR)**

**OBJECTIVE:** Convert an SR flip-flop into a T flip-flop.

**PROCEDURE:**
1.  **Write the Target (T-FF) Truth Table:** List all transitions.
2.  **Add Available (SR-FF) Columns:** Add columns for S and R.
3.  **Fill SR Columns using SR Excitation Table:** For each `Qn -> Qn+1` transition, write the required S and R values.
4.  **Find Logic for S and R:** Use K-Maps to find expressions for S and R in terms of T and Qn.
5.  **Draw the Circuit.**

**Execution:**
1.  **Tables:**
| T | Qn | Qn+1 | **S** | **R** | (Filled using SR Excitation) |
|---|---|---|---|---|---|
| 0 | 0 | 0 | **0** | **X** | (No change) |
| 0 | 1 | 1 | **X** | **0** | (No change) |
| 1 | 0 | 1 | **1** | **0** | (Toggle to 1) |
| 1 | 1 | 0 | **0** | **1** | (Toggle to 0) |

2.  **K-Map for S:**
| Qn\T | 0 | 1 |
| :--- |:-:|:-:|
| **0**  | 0 | 1 |
| **1**  | X | 0 |
    *   Grouping the `1` gives **S = TQn'**

3.  **K-Map for R:**
| Qn\T | 0 | 1 |
| :--- |:-:|:-:|
| **0**  | X | 0 |
| **1**  | 0 | 1 |
    *   Grouping the `1` gives **R = TQn**

4.  **Draw the Circuit:**
    *   Draw an SR Flip-Flop.
    *   The `T` input is the main input.
    *   Connect `T` and `Qn'` to an AND gate; the output goes to `S`.
    *   Connect `T` and `Q` to an AND gate; the output goes to `R`.
