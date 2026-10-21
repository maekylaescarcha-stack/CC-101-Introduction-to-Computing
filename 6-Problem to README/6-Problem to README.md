Republic of the Philippines  
**Sorsogon State University**  
**COLLEGE OF INFORMATION AND COMMUNICATIONS TECHNOLOGY**  
Bulan Campus  
Zone 8, Bulan, Sorsogon  
Tel. No.: 056 311-0103; Email Address: cict@sorsu.edu.ph  

**Course:** CC 101 - Introduction to Computing  
**Activity:** "From Problem to README": Designing a Number-System Converter and Documenting It in Markdown  

**Name:** Mae Kyla G. GUELAS  
**Block:** BSCS 1-1  
**Computer Unit Used (Desktop/Laptop, brand):** LAPTOP / DELL  
**Date:** OCTOBER 17, 2026  

---

### I. Objectives

At the end of this activity, you should be able to:
* Analyze a number-system conversion problem by identifying its inputs, processes, loop condition, and outputs.
* Write pseudocode using sequence, selection, and iteration.
* Draw flowcharts using standard symbols and check them by tracing and testing with sample data.
* Create a properly formatted `README.md` file in Markdown using Notepad, without an Internet connection.
* Upload the `README.md` to your CC 101 GitHub Computing Portfolio repository (take-home part).

---

### II. Materials Needed

* A computer running Windows 11 with Notepad (no network or Internet connection is needed in the laboratory)
* This worksheet, a pencil, and a ruler (or a flowchart template) for drawing flowcharts
* A USB flash drive, to bring your `README.md` home for uploading
* For Part G only (outside the laboratory): any device with Internet access and a free GitHub account
* Week 7 lecture notes, for reference on pseudocode, flowchart symbols, and Markdown syntax

---

### III. Background

Programmers do not start by typing code. They first analyze the problem, plan the solution as pseudocode and a flowchart, and check it by hand. In this activity, you will design a program that converts numbers between the decimal and binary number systems you learned in Week 5. An algorithm can be written as pseudocode (English-like steps) or drawn as a flowchart (standard symbols connected by arrows). Good work is also documented. On GitHub, the standard way to introduce a project is a `README.md` file written in Markdown, a plain-text format that uses symbols such as `#`, `*`, and `-` for headings, emphasis, and lists. Because Markdown is plain text, you can write it in Notepad with no Internet connection and upload it to GitHub later.

---

### IV. Procedure

#### Part A - Analyze the Problem (Problem 1)

**Problem 1: Decimal-to-Binary Converter.** Design a program that asks the user for a whole number in decimal (base 10) that is 0 or greater, converts it to binary (base 2), and displays the binary result.

*Worked example (13 in decimal):*  
$13 \div 2 = 6\text{ r }1$  
$6 \div 2 = 3\text{ r }0$  
$3 \div 2 = 1\text{ r }1$  
$1 \div 2 = 0\text{ r }1$  
Reading the remainders from bottom to top gives `1101`.

1. Convert 13 and 25 to binary by hand using the method above, so you understand every step before writing the pseudocode.
2. Complete Table 1: list the input, the output, the processes (operations), the decision or loop condition, and the variables you will need.

#### Part B - Write the Pseudocode

3. In Box 1, write the pseudocode for Problem 1. Use `START`, `INPUT`, `SET`, `WHILE ... DO ... ENDWHILE`, `IF ... THEN ... ELSE ... ENDIF`, `DISPLAY`, and `END`, and indent the steps inside the loop.  
*Tip:* Use `MOD` for the remainder of a division ($13 \text{ MOD } 2 = 1$) and `DIV` for whole-number division ($13 \text{ DIV } 2 = 6$). Each new remainder must be placed at the left of the binary digits found so far, for example `SET binary = remainder + binary`. Also decide what your algorithm should display when the input is 0.

#### Part C - Draw the Flowchart and Desk Check

4. In Figure 1, draw the flowchart for Problem 1 using the standard symbols: oval (start/end), parallelogram (input/output), rectangle (process), and diamond (decision). Show the loop with an arrow going back to the decision, and label every decision exit Yes or No.
5. Trace your pseudocode with the input 13 and fill in one row of Table 2 for each pass through the loop. The last column should end with 1101.
6. Test your pseudocode and flowchart with the five inputs in Table 3. First convert each number by hand, then follow your pseudocode or flowchart step by step. If the two results do not match, find and correct the error in your pseudocode and flowchart.

#### Part D - Reverse Conversion (Problem 2)

**Problem 2: Binary-to-Decimal Converter.** Design a program that asks the user for a binary number (entered as digits 0 and 1, such as 1101) and displays its decimal value. Use the positional (place value) method from Week 5: starting from the rightmost digit, multiply each digit by its place value (1, 2, 4, 8, 16, ...) and add the products.

*Worked example (1101 in binary):*  
$(1 \times 1) + (0 \times 2) + (1 \times 4) + (1 \times 8) = 1 + 0 + 4 + 8 = 13.$

7. In Box 2, write the pseudocode. You can take the rightmost digit with `binary MOD 10` and remove it with `binary DIV 10`; the place value starts at 1 and doubles after each digit.
8. In Figure 2, draw its flowchart.
9. Test your pseudocode with the inputs in Table 4, comparing hand computation with the result of following your pseudocode.
10. *Optional / Bonus:* Extend Problem 1 so the user can choose the target base (2, 8, or 16). For base 16, remainders 10 to 15 must be displayed as the letters A to F. Write the extended pseudocode in the Bonus box.

#### Part E - Create Your README.md Offline

11. Show file extensions so that you can see the real file name. Press `Windows + E` to open File Explorer, then click **View** $\rightarrow$ **Show File name extensions** (make sure it is checked).
12. In File Explorer, click **Documents**, then click **New Folder**. Name the folder `cc101-portfolio` (all lowercase, with a hyphen) and press Enter. Open it and create two more folders inside: `week07-algorithms` and `images`.
13. Press the Windows key, type `Notepad`, and press Enter. If your Notepad shows a formatting toolbar, open the View menu and switch to the Markdown syntax view so the symbols you type stay visible.
14. Type the README template content provided in the instructions.
15. Save the file. Click **File** $\rightarrow$ **Save as**. Go to `Documents\cc101-portfolio`. Type `README.md` as the File name, set **Save as type** to **All files**, make sure **Encoding** is **UTF-8**, and click **Save**.
16. Verify the file. In File Explorer, open the `cc101-portfolio` folder and confirm the file is named `README.md`, not `README.md.txt`. Open `cmd` and verify with:
    ```cmd
    cd %USERPROFILE%\Documents\cc101-portfolio
    dir
    type README.md
    ```
17. Optional preview: switch to formatted view if available in Notepad.
18. Copy the whole `cc101-portfolio` folder to your USB flash drive.

#### Part F - Peer Review

19. Exchange seats with a classmate. Open their `README.md` in Notepad and complete the checklist in Table 6. Write your name as the reviewer and return the worksheet.

#### Part G - Take-Home: Upload to GitHub

20. Go to `github.com` and sign up or sign in.
21. Create a new repository named `cc101-portfolio` set to **Public**.
22. Upload `README.md` (and any folder contents).
23. Commit changes with the message `Add initial README`.
24. Copy your repository URL, record it in Table 7, and submit it through the LMS.

---

### V. Data and Findings

#### Table 1. Problem Analysis for Problem 1 (Part A)

| Item | Your Answer |
| :--- | :--- |
| **Restated problem (your own words)** | Create a program that accepts a non-negative whole number in decimal (base 10) format from the user, converts that value into its binary (base 2) equivalent, and outputs the final binary result. |
| **Input** | A whole number in decimal (base 10) that is 0 or greater. |
| **Output** | The corresponding binary of the input number, displayed as a result. |
| **Processes (operations)** | Division by 2 to find quotients, modulo operation (or finding remainders) to extract binary digits (0 or 1), and string concatenation or accumulation to reverse/order the remainders correctly. |
| **Loop condition (when the loop stops)** | The loop continues as long as the decimal number is greater than 0 (stops when the decimal number reaches 0). |
| **Variables needed** | `decimal_number`: Stores the user's input value.<br>`binary_result`: Stores or accumulates the resulting binary digits.<br>`remainder`: Holds the remainder of each division step. |
| **13 and 25 in binary (computed by hand)** | **13 to Binary:**<br>$13 \div 2 = 6$, remainder 1<br>$6 \div 2 = 3$, remainder 0<br>$3 \div 2 = 1$, remainder 1<br>$1 \div 2 = 0$, remainder 1<br>**Answer:** `1101`<br><br>**25 to Binary:**<br>$25 \div 2 = 12$, remainder 1<br>$12 \div 2 = 6$, remainder 0<br>$6 \div 2 = 3$, remainder 0<br>$3 \div 2 = 1$, remainder 1<br>$1 \div 2 = 0$, remainder 1<br>**Answer:** `11001` |

---

#### Box 1. Pseudocode for Problem 1 (Part B)

```text
START
  INPUT Decimal_number
  SET Binary_string = ""
  SET N = Decimal_number
  WHILE N > 0 DO
    SET R = N MOD 2
    SET Binary_string = String(R) + Binary_string
    SET N = N DIV 2
  ENDWHILE
  DISPLAY Binary_string
END
```

---

#### Figure 1. Flowchart for Problem 1 (Part C)

*(Transcribed from hand-drawn diagram)*

```text
       ( Start )
           │
           ▼
 / Input Decimal_number /
           │
           ▼
[ Binary_string = "" ]
           │
           ▼
     [ N = D ] ◄──────────┐
           │             │
           ▼             │
      /  N > 0  \  F/N   │
     <   (Dec)?  > ────► / Display Binary_string / ──► ( END )
      \         /
           │ T/Y
           ▼
     [ R = N % 2 ]
           │
           ▼
    [ N = N / 2 ] ───────┘
```

---

#### Table 2. Trace of Problem 1 with Input 13 (Part C)

| Pass | n (before) | n MOD 2 (remainder) | n DIV 2 (new n) | binary (so far) |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 13 | 1 | 6 | 1 |
| **2** | 6 | 0 | 3 | 01 |
| **3** | 3 | 1 | 1 | 101 |
| **4** | 1 | 1 | 0 | 1101 |
| **5** | 0 | STOP | STOP | STOP - Loop ends |

**Value displayed at the end:** `1101`

---

#### Table 3. Test Cases for Problem 1 (Part C)

| Case | Decimal Input | Binary (by hand) | Binary From Your Pseudocode | Match? (Y/N) |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 0 | 0 | 0 | Y |
| **2** | 5 | 101 | 101 | Y |
| **3** | 13 | 1101 | 1101 | Y |
| **4** | 25 | 11001 | 11001 | Y |
| **5** | 255 | 11111111 | 11111111 | Y |

---

#### Box 2. Pseudocode for Problem 2 (Part D)

*(Blank in source document)*

---

#### Figure 2. Flowchart for Problem 2 (Part D)

*(Blank in source document)*

---

#### Table 4. Test Cases for Problem 2 (Part D)

| Case | Binary Input | Decimal (by hand) | Decimal From Your Pseudocode | Match? (Y/N) |
| :---: | :---: | :--- | :---: | :---: |
| **1** | 1101 | $1 \times 1 = 1$<br>$0 \times 2 = 0$<br>$1 \times 4 = 4$<br>$1 \times 8 = 8$<br>$1 + 0 + 4 + 8 = 13$ | 13 | Y |
| **2** | 101010 | $0 \times 1 = 0$<br>$1 \times 2 = 2$<br>$0 \times 4 = 0$<br>$1 \times 8 = 8$<br>$0 \times 16 = 0$<br>$1 \times 32 = 32$<br>$2 + 8 + 32 = 42$ | 42 | Y |
| **3** | 11111111 | $1 \times 1 = 1$<br>$1 \times 2 = 2$<br>$1 \times 4 = 4$<br>$1 \times 8 = 8$<br>$1 \times 16 = 16$<br>$1 \times 32 = 32$<br>$1 \times 64 = 64$<br>$1 \times 128 = 128$<br>$1+2+4+8+16+32+64+128 = 255$ | 255 | Y |
| **4** | 10000000 | $0 \times 1 = 0$<br>$0 \times 2 = 0$<br>$0 \times 4 = 0$<br>$0 \times 8 = 0$<br>$0 \times 16 = 0$<br>$0 \times 32 = 0$<br>$0 \times 64 = 0$<br>$1 \times 128 = 128$<br>Total: $128$ | 128 | Y |

---

#### Bonus Box. Extended Pseudocode: Decimal to Base 2, 8, or 16 (Optional)

*(Blank in source document)*

---

#### Table 5. README.md File Check (Part E)

| Item | Your Findings |
| :--- | :--- |
| **Full folder path of cc101-portfolio** | `C:\Users\guelas\OneDrive\Documents\cc101-portfolio` |
| **File name shown in File Explorer** | `README.md` |
| **Type shown in File Explorer (Details view)** | Markdown File or MD File |
| **Size of README.md shown by dir (bytes)** | 1,221 bytes |
| **Does type README.md show your Markdown text? (Y/N)** | Y |
| **Notepad formatted view available? (Y/N)** | Y |
| **Elements that appeared formatted in Notepad (if available)** | Headings, bold text, and lists (tables, images, and code blocks remain plain text) |

---

#### Table 6. Peer Review Checklist (Part F)

**Reviewer's name:**  
**Owner of the README:**  

| Element | Markdown Used | Present and Correct? (Y/N) |
| :--- | :--- | :---: |
| **Level-1 heading** | `#` | Y |
| **Level-2 headings** | `##` | Y |
| **Paragraph** | Text with a blank line before and after | Y |
| **Bold and italic text** | `**bold**` `*italic*` | Y |
| **Bulleted list** | `- item` | Y |
| **Numbered list** | `1. item` | Y |
| **Table** | `\| --- \|` header separator | Y |
| **Link** | `[text](url)` | Y |
| **Image** | `![alt](path)` | Y |
| **Code block** | Lines between two lines of three backticks | Y |
| **Horizontal rule** | `---` | Y |
| **File saved as README.md (not .txt)** | | Y |

---

#### Table 7. GitHub Submission (Part G, Take-Home)

| Item | Your Answer |
| :--- | :--- |
| **GitHub username** | Maekyla-Guelas |
| **Repository URL** | `https://github.com/MaeKyla-Guelas/cc101-portfolio` |
| **Date uploaded (YYYY-MM-DD)** | 2026-10-17 |
| **Does the README display formatted on GitHub? (Y/N)** | Y |
| **Elements that did not display as expected, and why** | None |

---

### VI. Realization (Reflection)

*In two to four sentences each, answer the following in your own words.*

1. **Which was easier for you to create, the pseudocode or the flowchart? Why?**  
   Pseudocode was easier for me to create because it is like writing step-by-step instructions in English. Flowchart is more difficult because I need to draw shapes and connect them properly.

2. **Did tracing and testing reveal any errors in your pseudocode or flowcharts? Describe what you found and how you corrected it.**  
   Yes, during tracing I found an error in my loop. At first my loop did not stop when the quotient became zero. I corrected it by adding a condition to stop the loop and by reversing the remainders to get the correct binary.

3. **How is writing a README in Markdown different from typing a document in Microsoft Word?**  
   Writing in Markdown uses simple codes like `#` and `*` to format text, while in Word you just click buttons. README in Markdown is plain text and good for GitHub, while Word is WYSIWYG and saves as docx file.

4. **How can a GitHub portfolio help you as a future computing professional?**  
   A GitHub portfolio can show my projects and coding skills to future employers. It serves as proof of what I can do and helps me get hired as a programmer or IT professional.

---

### VII. Scoring Guide

| Criteria | Description | Points |
| :--- | :--- | :---: |
| **Problem Analysis & Pseudocode** | Table 1 is complete; the pseudocode for both conversions is correct (correct use of MOD, DIV, and the loop), uses proper keywords, and is indented. | 25 |
| **Flowcharts & Testing** | Both flowcharts use the correct symbols with labeled decisions and a clear loop; the trace (Table 2) and test cases (Tables 3 and 4) are correct. | 25 |
| **README.md** | The file is saved correctly as `README.md`, uses all required Markdown elements, and passes the peer review in Table 6. | 25 |
| **GitHub Upload** | The README is uploaded to a public `cc101-portfolio` repository and the URL is submitted (Table 7). | 10 |
| **Realization / Reflection** | Answers are thoughtful, specific to the student's own work, and well written. | 10 |
| **Neatness & Timeliness** | Worksheet is legible/well-formatted and submitted on time. | 5 |
| **Total** | | **100** |