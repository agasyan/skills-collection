# User Interface Evaluation in the Real World: A Comparison of Four Techniques
Robin Jeffries, James R. Miller, Cathleen Wharton, Kathy M. Uyeda (1991). Proceedings of CHI '91, ACM. https://www.miramontes.com/writing/uievaluation/
Type: research · Read: 2026-10-06

## What it says
- Four groups each evaluated a beta of HP-VUE (a graphical UNIX desktop) with one technique: heuristic evaluation (4 UI specialists), usability testing (1 human factors professional, 6 users, 10 tasks), guidelines (3 software engineers, 62 HP guidelines), cognitive walkthrough (3 software engineers, 7 tasks).
- 206 unique core problems; 7 raters scored severity from 1 to 9; benefit/cost = summed severity per person-hour.

## Findings
- **Heuristic evaluation found the most.** 105 core problems (over half of all), including 28 of the most severe third, in 20 hours of analysis. Benefit/cost 12 against 1 to 3 for the others; about 2:1 when time spent learning the system is excluded.
- **It needs several experts.** No single evaluator found more than 42 core problems, and 52 of its problems fell in the least-severe third.
- **Usability testing found serious, recurring problems.** Highest mean severity (4.15) and only 2 problems in the least-severe third, but it cost 199 person-hours, missed many serious problems, and only 6% of its problems concerned consistency (25% overall).
- **Some problems only real use reveals.** Deleting your home directory blocked later logins; a test user found it by accident.
- **Cognitive walkthrough was tedious.** It performed about as well as guidelines, covered only 7 tasks in the longest session, and found less general, less recurring problems than the other techniques. It did help define user goals and assumptions.
- **Developers can use guidelines and walkthroughs** to find some important problems when no UI specialist is available.

## For internal systems
- Run a heuristic pass yourself and get 1 to 2 colleagues to run their own; one evaluator misses most problems.
- Walk through only the 3 to 5 core tasks; a full walkthrough is too slow for a whole tool.
- Still watch real staff use it: some severe problems appear only in actual use.
