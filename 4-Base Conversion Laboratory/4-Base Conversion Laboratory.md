# ACTIVITY 4 - BASE CONVERSION LABORATORY

**Name:** Mae Kyla G. Guelas  
**Course/Section:** BSCS 1-1  
**Date:** 09/30/26  
**Instructor:** Prof. John Mark Gabrentina  

---

## Page 1: Base Conversions and Place Value Evaluations

### Problem 1
*   **Target/Given:** $1 \times 1^{\frac{3}{8}} \times 127$ (Binary / Place Value Breakdown)

| Digital Place Value | Calculation | Place Value Exponential |
| :--- | :--- | :--- |
| $\underline{2^{7} = 128}$ | $1 \times 64 = \underline{64}$ | $2^{6} = 64$ |
| | $1 \times 32 = 32$ | $2^{5} = 32$ |
| | $0 \times 16 = 0$ | $2^{4} = 16$ |
| | $1 \times 8 = 8$ | $2^{3} = 8$ |
| | $1 \times 4 = 4$ | $2^{2} = 4$ |
| | $0 \times 2 = 0$ | $2^{1} = 2$ |
| | $1 \times 1 = 1$ | $2^{0} = 1$ |

**Sum:** $128 + 64 + 32 + 0 + 8 + 4 + 0 + 1 = 237$  
$\text{Sum} = 128$

---

### Problem 2 (Octal Evaluation)

| Digital Place Value | Calculation | Place Value Exponential |
| :--- | :--- | :--- |
| $1 \times 512$ | $1 \times 512 = 512$ | $8^{3} = 512$ |
| $2 \times 64 = 128$ | $2 \times 64 = 128$ | $8^{2} = 64$ |
| $2 \times 8 = 16$ | $2 \times 8 = 16$ | $8^{1} = 8$ |
| $5 \times 1 = 5$ | $5 \times 1 = 5$ | $8^{0} = 1$ |

**Sum:** $512 + 128 + 16 + 5 = 661$

---

### Problem 3 (Hexadecimal Evaluation)

*   **Digits:** `3`, `7`, `15` (`F`)
*   **Place Values:** $16^{2} = 256$, $16^{1} = 16$, $16^{0} = 1$

| Digital Place Value | Calculation |
| :--- | :--- |
| $3 \times 256$ | $3 \times 256 = 768$ |
| $7 \times 16$ | $7 \times 16 = 112$ |
| $15 \times 1$ | $15 \times 1 = 15$ |

**Sum:** $768 + 112 + 15 = 895$

---

## Page 2: Successive Division and Grouping Conversions

### Problem 4: Division Method (Decimal to Binary)
Convert $185_{10}$ to Binary:

* $185 = 2 \times 92 + 1$
* $92 = 2 \times 46 + 0$
* $46 = 2 \times 23 + 0$
* $23 = 2 \times 11 + 1$
* $11 = 2 \times 5 + 1$
* $5 = 2 \times 2 + 1$
* $2 = 2 \times 1 + 0$
* $1 = 2 \times 0 + 1$

**Answer:** $185_{10} = 10111001_{2}$

---

### Problem 5: Division Method (Base 8 / Octal)
Convert $2693_{10}$ to Octal:

* $2693 = 8 \times 336 + 5$
* $336 = 8 \times 42 + 0$
* $42 = 8 \times 5 + 2$
* $5 = 8 \times 0 + 5$

**Answer:** $5205_{8}$

---

### Problem 6: Division Method (Base 16 / Hexadecimal)
Convert $3878_{10}$ to Hexadecimal:

* $3878 = 16 \times 242 + 6$
* $242 = 16 \times 15 + 2$
* $15 = 16 \times 0 + 15 \text{ (F)}$

**Quotient / Remainder Sequence:** `15 (F)`, `2`, `6`  
**Answer:** $\text{F26}_{16}$

---

### Problem 7: Binary to Hexadecimal Grouping

* **Original Binary:** `11011001101`
* **Grouping (4-bit groups):** `0110 1100 1101`

1. $0110_{2} = (0 \times 8) + (1 \times 4) + (1 \times 2) + (0 \times 1) = 6$
2. $1100_{2} = (1 \times 8) + (1 \times 4) + (0 \times 2) + (0 \times 1) = 12 \rightarrow \text{C}$
3. $1101_{2} = (1 \times 8) + (1 \times 4) + (0 \times 2) + (1 \times 1) = 13 \rightarrow \text{D}$

**Answer:** $11011001101_{2} = \text{6CD}_{16}$

---

### Problem 8: Octal to Binary & Binary Grouping

* **Octal Digit Conversion:**
  * $1_{8} = 001_{2}$
  * $6_{8} = 110_{2}$
  * $2_{8} = 010_{2}$
  * $3_{8} = 011_{2}$

* **Combined Binary:** `001110010011`
* **Grouped into 4-bit sets (Hexadecimal Conversion):**
  * $0001_{2} = 1$
  * $1001_{2} = 9$
  * $0011_{2} = 3$

**Answer:** $193_{16}$

---

### Problem 9: Miscellaneous Conversions & Properties

1. $\text{F}_{16} = 15 = 1111_{2}$
2. $8_{8} = 1000_{2}$
3. $0_{16} = 0000_{2}$
4. $2^{6} = 64$
5. $2^{6} - 1 = 63$ (Maximum value represented by 6 bits)
6. 16 bits all set to 1:
   * $0011 \ 1111_{2} = \text{3F}_{16}$