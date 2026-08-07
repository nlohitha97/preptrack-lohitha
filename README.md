# PrepTrack — Placement Preparation Performance Analyzer

## Project Overview
PrepTrack is a command-line Python application that tracks a student's practice performance across 7 days and determines their placement/mock-interview eligibility based on multiple criteria such as attendance, average score, project completion, and profile verification.

## Features Implemented
- Input validation for student details (name, attendance, graduation year, yes/no answers)
- Daily score tracking with absence handling (`-1` marks a day as absent)
- Automatic score classification into Strong / Satisfactory / Needs Improvement / Critical
- Tracking of highest and lowest scores along with the day they occurred
- Tracking of the first critical score (if any) separately
- Eligibility check based on 8 different criteria
- Priority-based final status decision (reports the most important blocker first)
- Detailed, formatted final report generation

## Python Concepts Used
- Input validation using `while` loops
- Loop control using `continue`
- `for` loops for iterating over 7 practice days
- `if-elif-else` conditional chains for classification and priority checks
- Boolean logic (`and`, `or`, `not`) for eligibility rules
- Flag variables (`first_attempt_found`, `critical_score_found`) to track "first occurrence" logic
- Division-by-zero prevention when calculating averages
- f-strings for formatted output
- Type casting (`int()`, `float()`)

## How to Run the Program
1. Make sure Python 3 is installed on your system.
2. Open a terminal in the project folder.
3. Run the following command:
```bash
   python main.py
```
4. Follow the on-screen prompts to enter student details and daily scores.

## Test Result Summary
The program was manually tested with multiple scenarios, including:
- A student with all 7 days attempted and passing scores → Status: Ready
- A student with one or more absent days → Absences correctly excluded from score calculations
- A student with a critical score (below 40) → Correctly flagged as "Not Ready" with the first critical day/score shown
- A student with fewer than 6 attempts → Correctly flagged as "Not Ready" due to insufficient attempts
- Edge cases like attendance exactly at 75% and scores exactly at classification boundaries (40, 60, 75) → Verified correct classification

## Individual Contribution
This project was completed individually by Lohitha, including:
- Writing and debugging all input validation logic
- Implementing the 7-day scoring loop and score classification
- Building the eligibility and priority-based final status logic
- Testing the program against multiple real and edge-case scenarios

## Code Review Completed
- Self-reviewed the code for logical correctness (e.g., verifying priority order in eligibility checks).
- Checked for common bugs like infinite loops, incorrect comparison operators, and division by zero.
- Verified variable names and print statements matched the required output format.

## Feedback Received
- Received guidance on fixing input validation bugs (e.g., incorrect use of `and`/`or` in range checks, `==` vs `=` mistakes).
- Learned to use flags (`first_attempt_found`, `critical_score_found`) for cleanly handling "first occurrence" logic instead of hardcoding assumptions.
- Improved understanding of why `elif` chains are necessary for priority-based decisions instead of separate `if` blocks.

## Author
Lohitha
