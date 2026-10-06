# Why You Only Need to Test with 5 Users
Jakob Nielsen (2000). Nielsen Norman Group. https://www.nngroup.com/articles/why-you-only-need-to-test-with-5-users/
Type: research · Read: 2026-10-06

## What it says
- Applies the Nielsen and Landauer (INTERCHI 1993) model: problems found with n users = N(1-(1-L)^n), where L is the share of problems one user reveals. L averaged 31% across "a large number of projects"; the article does not give the count.

## Findings
- **The first user matters most.** Zero users give zero insights; one user reveals almost a third of the problems.
- **Five users find about 85%.** After the fifth user you mostly watch the same problems again.
- **About 15 users find all.** Spend that budget on 3 rounds of 5, fixing between rounds.
- **Why iterate.** Fixes may fail or add new problems. Round 2 finds most of the remaining 15% (2% left for round 3) and reaches deeper issues, such as task flow and information architecture, that surface problems had hidden.
- **Not one user.** One person can mislead; 3 users show the spread of behaviour. The cost-benefit optimum is "around 3 or 5 users", because each study has a fixed start-up cost.
- **Distinct user groups.** Test 3 to 4 per group for two groups, 3 per group for three or more. The formula holds only for comparable users.
- **Exceptions.** Quantitative studies (usability metrics) need 20 users; card sorting needs 15.

## For internal systems
- Test with 5 staff from one role, fix what they hit, then test again with 5 more.
- When several roles use the tool (requesters and approvers), test 3 to 4 from each role.
- Use 5-user rounds to find problems; report success rates or times only from about 20 users.
- Counterpoint: Schmettow (2012), "Sample Size in Usability Studies", CACM 55(4), doi:10.1145/2133806.2133824. Problems differ in how visible they are, so small iterative rounds leave many undiscovered; on one dataset 80% discovery needed about 56 sessions, not 11.
