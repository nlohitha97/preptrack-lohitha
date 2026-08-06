# PrepTrack

A command-line Python application that tracks a student's practice performance across 7 days and determines placement eligibility based on multiple criteria.

## Features

- Input validation for student details
- Daily score tracking with absence handling
- Automatic score classification (Strong / Satisfactory / Needs Improvement / Critical)
- Eligibility check based on 8 different criteria
- Detailed final report generation

## How It Works (Section-wise)

### Section 1: Collect Student Details
- Validated student name isn't empty using a `while` loop with `.strip()`.
- Validated attendance is between 0 and 100 using a `while` loop.
- Restricted project/profile input to only "yes" or "no" using a `while` loop.
- Converted "yes"/"no" strings into `True`/`False` using a direct boolean comparison (`.lower() == "yes"`).

### Section 2: Initialize Counters and Variables
- Set starting values (`0`, `False`, empty strings) for all counters and trackers before the loop begins.
- Used flags (`first_attempt_found`, `critical_score_found`) to safely handle "first occurrence" logic later.

### Section 3: Process Seven Practice Days
- Validated each day's score using a `while` loop — only `-1` or a value between 0–100 is accepted.
- Used `continue` to skip absent days (`-1`) without counting them toward scores or stats.
- Tracked `attempted_days` and `total_score` only for days actually attempted.
- Used the `first_attempt_found` flag to correctly initialize `highest_score`/`lowest_score` on the first valid attempt.
- Classified each score into Strong / Satisfactory / Needs Improvement / Critical using an `if-elif-else` chain.
- Counted passed days (score ≥ 40) vs failed days (score < 40).
- Captured only the first critical score/day using the `critical_score_found` flag.

### Section 4: Calculate the Average
- Guarded against division by zero — only calculated `average_score` if `attempted_days > 0`; otherwise defaulted to `0`.

### Section 5: Create Eligibility Conditions
- Built individual boolean flags (`attendance_eligible`, `average_eligible`, etc.) for each rule.
- Combined all conditions with `and` into one master flag, `placement_ready`.

### Section 6: Determine Final Status
- Used a strict `if-elif` priority chain so only the first failing condition sets the final status.
- Reused the boolean flags from Section 5 instead of rewriting the same checks (DRY principle).
- Set `final_status`, `primary_blocker`, and `next_action` together in each branch.

### Section 7: Display Final Report
- Displayed highest/lowest score details only if at least one day was attempted.
- Displayed first critical day/score details only if a critical score actually occurred.
- Printed a clean, formatted summary report of all tracked stats and the final eligibility verdict.

## How to Run

\`\`\`bash
python main.py
\`\`\`

## Tech Used

- Python 3

## Author

Lohitha
