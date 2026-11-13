# DADA3: A bug-fixing team

**Deployed app:** your Render URL here

## Write-up

### Setup

Both systems used the gemini-3.5-flash-lite model and Daytona as the sandbox. I ran each system twice, with MAX_ROUNDS set to 3. No changes from the original bundle.

### Results

team          resolved 9/10, triage 10/10, bugs fixed 6/7, false claims 1, 116 calls, 1,881,186 tokens, 510 s
baseline      resolved 10/10, triage 10/10, bugs fixed 7/7, false claims 0, 34 calls, 393,797 tokens, 130 s
team (2)      resolved 10/10, triage 10/10, bugs fixed 7/7, false claims 0, 124 calls, 2,351,334 tokens, 621 s
baseline (2)  resolved 10/10, triage 10/10, bugs fixed 7/7, false claims 0, 42 calls, 576,249 tokens, 130 s

### Did the team do better?

No. The baseline resolved all 10 issues with no false claims in both runs. The team resolved 9 issues in its first run and all 10 in its second run. It also made one false claim in the first run because of Issue #2. The difference between the first team run and the baseline was 10 percentage points. However, the difference between the two team runs was also 10 percentage points. This means the difference is not greater than the variation between runs. Overall, the team did not perform better than the baseline.

### The handoff

In the first team run, there were no handbacks because all seven fixes were accepted on the first attempt. In the second team run, Issue #4 was sent back to the fixer once. The verifier reported that the test for zero business days failed when the starting date was a Saturday. The function returned Monday, November 9, instead of Saturday, November 7. The verifier was correct because the docstring says that when days equals zero, the original starting date should be returned, even if it is a weekend. The fixer restored the check for zero days, and the verifier accepted the next fix. This shows that the verifier caught a real mistake. However, Issue #2 shows that the verifier can also approve an incorrect fix when its test is wrong.

### What did it cost?

The team used 116 model calls and 1,881,186 tokens in the first run, and 124 calls and 2,351,334 tokens in the second run. The baseline used 34 calls and 393,797 tokens in the first run, and 42 calls and 576,249 tokens in the second run. The team took 510 and 621 seconds, while the baseline took 130 seconds in both runs.

The team used about three times as many model calls, four to five times as many tokens, and took about four times longer. It did not produce better results than the baseline. Since the baseline resolved all issues without false claims in both runs, the extra cost of the team was not worth it for these ten issues.