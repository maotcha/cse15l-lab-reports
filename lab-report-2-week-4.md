# Week 4 Lab Report
This week's lab report is all about my debugging process for a buggy piece of code (no offense to the original author). How fun! Sort of! Well anyway, let's get started.

## Code Change 1
![change1part2](https://maotcha.github.io/cse15l-lab-reports/change1part1.png)
![change1part2](https://maotcha.github.io/cse15l-lab-reports/change1part2.png)

Above are the changes I made to the code in response to a failure-inducing input from this [test file](https://github.com/maotcha/markdown-parse/blob/main/test-file.md). The symptom of said input is shown below.

![symptom1](https://maotcha.github.io/cse15l-lab-reports/symptom1.png)

The bug in my code was that when the program tried extracting a link from the string containing the contents of the entire file, it'd extract a substring starting from the index of the first open parantheses and ending at the index of the last parantheses in the string. Since my input for the program contained two links, instead of extracting two seperate links, the program instead extracted one string starting from the start of the first link and ending at the end of the second link. Thus, when the program printed out the ArrayList containing all the links, not only was the output not a link, but the ArrayList only contained one (fake) link, not two. 