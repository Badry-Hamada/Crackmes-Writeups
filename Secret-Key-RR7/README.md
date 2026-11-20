# Secret Key - Crackme Write-up

## Overview

This crackme requires two numeric inputs to reach the success message.

I used Ghidra to perform static analysis and inspect the program's main function.

## Analysis

After decompiling the main function, I identified the following operations:

1. The program prompts the user to enter a number.
2. It reads the input using `scanf`.
3. It compares the entered value with `33`.
4. If the first condition is satisfied, the program prompts for a secret key.
5. The second input is compared with `102`.

## Solution

The decompiled code revealed these two conditions:

```c
if (v5 == 33)
{
    printf("Enter The Secret Key : ");
    scanf("%i", &v4);

    if (v4 == 102)
        printf("Congratulations, you have completed the challenge!");
}
```

Therefore, the required inputs are:

- First input: `33`
- Second input: `102`

Both conditions must be satisfied to reach the success message.

## Conclusion

By examining the decompiled main function and following the conditional checks, I was able to identify the two required numeric inputs without modifying the executable.
