**Republic of the Philippines**

**SORSOGON STATE UNIVERSITY**

**COLLEGE OF INFORMATION AND COMMUNICATIONS TECHNOLOGY**

Bulan Campus

Zone 8, Bulan, Sorsogon

Tel. No.: 056 311-0103; Email Address: cict@sorsu.edu.ph

### CC 101 Laboratory Activity: Exploring the Windows Command Line

| Item | Details |
| --- | --- |
| **Course** | CC 101 Introduction to Computing (BSCS 1st Year) |
| **Course Outcome** | CO2: Identify the functions and relationships of major hardware and software components |
| **Output** | Command Line Exploration Documentation (PDF) |
| **Estimated time** | 2 to 2.5 hours |
| **Reference** | CC 101 Lecture Notes: Exploring the Windows Command Line |

---

### Instructions

Follow every step in order, take the screenshots marked **[Screenshot]**, and answer the questions marked **[Answer]** in your documentation.

#### Before you start
* You need a Windows 10 or 11 computer. No administrator rights are needed.
* To take a screenshot, press `Windows + Shift + S`, drag over the terminal window, then paste it (`Ctrl + V`) into your documentation.
* Replace the sample values (Juan Dela Cruz, BSCS 1-1) with your own details.
* Type every command yourself. Do not copy and paste; typing is how you learn.

---

### Part A: Open the Two Shells

1. Press `Windows + R`, type `cmd`, and press Enter. Type `cls` and press Enter.
2. Type `echo Juan Dela Cruz, BSCS 1-1` (your own name and section) and press Enter. **[Screenshot] Figure A1**
3. Press `Windows + R`, type `powershell`, and press Enter. Type the same echo command, but put the text in quotation marks: `echo "Juan Dela Cruz, BSCS 1-1"`. PowerShell treats the comma as a list separator without them. **[Screenshot] Figure A2**

**[Answer] A-Q1.** Compare the two prompts. What is different, and what does each part of the Command Prompt prompt mean?

---

### Part B: Inspect Your System (Command Prompt)

*Use the Command Prompt window for Parts B to D.*

1. Run these commands one at a time: `whoami`, then `hostname`, then `ver`. **[Screenshot] Figure B1**
2. Run the command below. It may take 10 to 30 seconds. **[Screenshot] Figure B2**
   ```cmd
   systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type" /C:"Total Physical Memory"
   ```
3. Run `ipconfig`. Find the adapter that shows an IPv4 Address. **[Screenshot] Figure B3**

**[Answer] B-Q1.** Complete this table in your documentation using your results:

| Item | Your result |
| --- | --- |
| **Logged-in account (`whoami`)** | desktop-xxxx/mae kyla guelas |
| **Computer name (`hostname`)** | desktop-xxxx |
| **OS name** | microsoft windows 11 pro |
| **OS version** | 10.0.22631 Build 22631 |
| **System type (x64 or ARM)** | x64-based pc |
| **Total physical memory (RAM)** | 8,000 MB or 16,000 MB |
| **IPv4 address** | 192.168.1.xxx |

**[Answer] B-Q2.** The `|` symbol in step 2 is called a pipe. Run `systeminfo` alone and compare. In your own words, what did `| findstr` do?

---

### Part C: Build a Folder Structure

1. Go to your user folder and create the lab folders:
   ```cmd
   cd %USERPROFILE%
   mkdir CC101-Lab
   cd CC101-Lab
   mkdir Notes Projects Screenshots
   ```

2. Create a text file about yourself (use your own details):
   ```cmd
   echo Name: Juan Dela Cruz > profile.txt
   echo Section: BSCS 1-1 >> profile.txt
   echo Favorite app: YouTube >> profile.txt
   type profile.txt
   ```
   **[Screenshot] Figure C1** (show all commands and the output of `type`)

3. Run `tree /F` to display your folder structure. **[Screenshot] Figure C2**

4. Open File Explorer, go to `C:\Users\(your account)\CC101-Lab`, and open `profile.txt` in Notepad. **[Screenshot] Figure C3** (File Explorer and Notepad side by side)

**[Answer] C-Q1.** What would happen if you used `>` instead of `>>` in the second echo line? Test it on a new file (`test.txt`) and explain.

---

### Part D: Copy, Rename, and Delete Files

```cmd
copy profile.txt Notes\profile-copy.txt
cd Notes
ren profile-copy.txt about-me.txt
echo This file will be deleted > temp.txt
dir
del temp.txt
dir
cd ..
tree /F
```

**[Screenshot] Figure D1** (from `copy` to the first `dir`) and **[Screenshot] Figure D2** (from `del` to `tree /F`)

**[Answer] D-Q1.** After `del temp.txt`, check your Recycle Bin. Is `temp.txt` there? What does this tell you about deleting files from the command line?

---

### Part E: Explore PowerShell

*Switch to the PowerShell window.*

1. Go to your lab folder and list and read its files:
   ```powershell
   cd $HOME\CC101-Lab
   Get-ChildItem
   Get-Content profile.txt
   $PSVersionTable
   ```
   **[Screenshot] Figure E1**

2. Run `Get-Help Get-ChildItem`. If PowerShell asks whether to run `Update-Help`, type `N` and press Enter. **[Screenshot] Figure E2**

3. Take the last three digits of your student ID number (for example, `2025-00347` $\rightarrow$ `347`). Convert it with PowerShell:
   ```powershell
   [Convert]::ToString(347, 2)
   [Convert]::ToString(347, 8)
   '{0:X}' -f 347
   ```
   **[Screenshot] Figure E3**

**[Answer] E-Q1.** Write your number in decimal, binary, octal, and hexadecimal. Keep this; you will verify it by hand in Week 5.

---

### Part F: Discover a New Command

1. In Command Prompt, type `help` to see a list of commands.
2. Choose one command that was not taught in this lesson and is safe to run (for example: `date /t`, `time /t`, `tasklist`, `vol`, or `color 0A`).
3. Read its help with `command /?` (for example, `tasklist /?`), then run it. **[Screenshot] Figure F1** (help output) and **[Screenshot] Figure F2** (command result)

**[Answer] F-Q1.** What does your chosen command do, and when would it be useful?

---

### Part G: Reflection

*Answer in 3 to 5 sentences each:*

1. **G-Q1. Which task in this activity was faster in the CLI than in the GUI? Which was easier in the GUI? Explain why.**
   Creating folders and files was faster in the CLI because one command `mkdir Notes Projects Screenshots` can create three folders at once, while in GUI I need to right-click and create one by one. Getting system info like `whoami`, `hostname`, and `ipconfig` was also faster in CLI than clicking through Settings. However, checking the content of `profile.txt` and organizing files was easier in the GUI because File Explorer and Notepad are visual and I can see the files directly. CLI requires memorizing commands, while GUI is more intuitive for beginners.

2. **G-Q2. What error did you encounter (if any), what caused it, and how did you fix it?**
   I encountered an error "The system cannot find the path specified" when I typed `cd CC101 Lab` with a space. I realized the folder name has no space, the correct name is `CC101-Lab` with a hyphen. I also encountered an error when I used `>` instead of `>>`, my previous text in `profile.txt` was overwritten. I fixed it by retyping the commands correctly and using `>>` to append. I learned that spacing and symbols in CMD must be exact.

3. **G-Q3. Give one real-world job or situation in computing where knowing the command line would be important.**
   Knowing the command line is very important for an IT Support or Network Administrator. For example, when a client's PC has no internet, an IT staff can use `ipconfig`, `ping`, and `systeminfo` to diagnose the problem quickly even if the GUI is lagging. In programming and cybersecurity jobs, many tools only work in CLI. It also helps automate tasks and work faster than clicking through many windows.

---

### Documentation and Submission

Submit one PDF that records what you did, what the computer showed, and what you learned. Someone reading it should be able to repeat your work.

#### Required Contents (in this order)
1. **Cover page:** activity title, your full name, student ID, section, date performed, and instructor's name.
2. **Introduction (3 to 5 sentences):** what the command line is and the purpose of this activity, in your own words.
3. **Procedure and results, Parts A to F:** for each part, a short heading, the commands you typed, the labeled screenshots, and your answers to that part's **[Answer]** questions.
4. **Commands learned table:** every command you used and what it does, in your own words.
5. **Reflection:** your answers to G-Q1 to G-Q3.

#### Formatting Rules

| Item | Requirement |
| --- | --- |
| **File type** | PDF (write in Word or Google Docs, then export as PDF) |
| **File name** | `CC101_CLI-Lab_Lastname_Firstname.pdf` |
| **Font** | Arial or Calibri, 11 pt; commands in Consolas or Courier New |
| **Screenshots** | Crop to the terminal window; text must be readable. Label each one below the image, e.g., "Figure B2. Filtered systeminfo output" |
| **Personal details** | Your own name, section, and student ID must appear in Figures A1, C1, and E3 |
| **Total screenshots** | 16 (A1-A2, B1-B3, C1-C3, D1-D2, E1-E3, F1-F2) |

#### Sample Commands Learned Table

| Command | Shell | What it does |
| --- | --- | --- |
| `mkdir Notes` | Command Prompt | Creates a folder named Notes in the current folder |
| `type profile.txt` | Command Prompt | Displays the contents of profile.txt |

#### Submission
* Upload the PDF to the activity page in the course LMS before the deadline your instructor sets.
* Outputs must be your own work. Identical screenshots or answers will be treated as plagiarism under the class policy.
* Keep your `CC101-Lab` folder; later activities may build on it.

---

### Grading Rubric

The documentation is scored out of 100 points and counts under **Laboratory: Project**.

| Criterion | Points | Full marks | Partial marks | Low marks |
| --- | --- | --- | --- | --- |
| **Completeness of procedure** | 30 | All 16 labeled, readable screenshots; every part A to F documented | 1 to 4 screenshots missing or unreadable | 5 or more screenshots missing |
| **Accuracy of results** | 20 | System-information table complete; commands and conversions correct and personalized | Minor errors or 1 to 2 missing values | Many errors, or results not the student's own |
| **Answers to guide questions (A to F)** | 20 | Correct, clear, in the student's own words | Mostly correct but brief or vague | Missing, incorrect, or copied |
| **Reflection (G-Q1 to G-Q3)** | 15 | Specific, honest, and linked to the activity | General statements with few specifics | Missing or off-topic |
| **Organization and formatting** | 15 | Follows the required order, naming, and formatting rules; commands learned table complete | Some rules not followed | Disorganized; wrong file type or name |
| **Total** | **100** | | | |