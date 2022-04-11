

## Solution

We are given an executable that asks us to enter three numbers and see if we get the correct answer.


If we examine the program in IDA, we can see that the random number generator is seeded using the current time. So if we know how the numbers are generated, then we can accurately predict what the correct guesses are.


After further investigation, we see that the numbers are generated in a predictable way and we can imitate the process using our own C program.



Next we can run both our program, and the provided executable at the same time so they both have the same time seeds.

./sol && ./revme

This prints out the current time, followed by the three numbers, which we can type in and "guess" correctly.


### Flag

INSEC{t!m3_!5_m0n3y}