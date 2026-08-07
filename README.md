# PrepTrack — Placement Preparation Performance Analyzer

## Project Title
PrepTrack — Placement Preparation Performance Analyzer

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

| Test ID | Scenario                      | Expected Result                  | Actual Result                        | Status |
| ------- | ------------------------------ | --------------------------------- | ---------------------------------- | ------ |
| TC-01   | All requirements satisfied     | Ready for Mock Interview          | Ready for Mock Interview           | Pass   |
| TC-02   | Critical score present         | Critical Support Required         | Critical Support Required          | Pass   |
| TC-03   | Fewer than six attempts        | Practice Incomplete               | Practice Incomplete                | Pass   |
| TC-04   | Fewer than four passes         | Insufficient Passed Practices     | Insufficient Passed Practices      | Pass   |
| TC-05   | Average below 70               | Practice Improvement Required     | Practice Improvement Required      | Pass   |
| TC-06   | Attendance below 75            | Attendance Improvement Required   | Attendance Improvement Required    | Pass   |
| TC-07   | Graduation year not eligible   | Graduation Criteria Not Met       | Graduation Criteria Not Met        | Pass   |
| TC-08   | Project incomplete             | Application On Hold               | Application On Hold                | Pass   |
| TC-09   | Profile not verified           | Application On Hold               | Application On Hold                | Pass   |
| TC-10   | All days absent                | Practice Not Evaluated            | Practice Not Evaluated             | Pass   |
| TC-11   | Invalid low score              | Input rejected                    | Input rejected                     | Pass   |
| TC-12   | Invalid high score             | Input rejected                    | Input rejected                     | Pass   |
| TC-13   | Boundary scores                | Correct classifications           | Correct classifications            | Pass   |
| TC-14   | Multiple blockers              | First blocker displayed           | First blocker displayed            | Pass   |

## Individual Contribution
This project was completed individually by Lohitha, including:
- Writing and debugging all input validation logic
- Implementing the 7-day scoring loop and score classification
- Building the eligibility and priority-based final status logic
- Testing the program against multiple real and edge-case scenarios
- url: https://github.com/nlohitha97/preptrack-lohitha

## Code Review Completed
- Self-reviewed the code for logical correctness (e.g., verifying priority order in eligibility checks).
- Checked for common bugs like infinite loops, incorrect comparison operators, and division by zero.
- Verified variable names and print statements matched the required output format.

## Feedback Received
- Received guidance on fixing input validation bugs (e.g., incorrect use of `and`/`or` in range checks, `==` vs `=` mistakes).
- Learned to use flags (`first_attempt_found`, `critical_score_found`) for cleanly handling "first occurrence" logic instead of hardcoding assumptions.
- Improved understanding of why `elif` chains are necessary for priority-based decisions instead of separate `if` blocks.

## Author
Lohitha Narasepalli

