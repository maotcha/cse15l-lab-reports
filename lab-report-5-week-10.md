# Week 6 Lab Report
More bugs! Yay! It's week 10! Yay! I have finals on Saturday! Not yay!

## How I Found the Different Results
To find tests that produced different results, I ran my own implementation of `MarkdownParse.java` and the version provided during Week 9's lab, saving the output from each in a file called `results.txt`. I then ran the command `diff markdown-parse/results.txt markdown-parse-1/results.txt`, which showed me which lines in both `results.txt` differed. From there, I picked two lines with different results and opened up the `results.txt` files to find the responsible test files.

## Test File 12
For test file 12, my `MarkdownParse.java` implementation produced `[\]`, while the provided implementation produced `[]`. Sadly, my implementation is wrong. 

![change for test file 12](https://maotcha.github.io/cse15l-lab-reports/test-file-12-change.png)

My code is shown above. The bug in this code is that the program never checks if the parantheses for a potential link come after the square brackets; text with this `()[]` format aren't valid links. To fix my code, I should change the highlighted area to find the index of the first open parantheses after the closed square bracket and the index of the first closed parantheses after the open parentheses. If I don't get -1 for either indexes, then I'd add the substring from between those indexes to my ArrayList of links.

## Test File 14
For test file 14, my `MarkdownParse.java` implementation produced `[]`, while the provided implementation produced `[/foo]`. This time, the provided implementation is wrong.

![change 1 for test file 14](https://maotcha.github.io/cse15l-lab-reports/test-file-14-change-1.png)

![change 2 for test file 14](https://maotcha.github.io/cse15l-lab-reports/test-file-14-change-2.png)

The relevant code from the provided implementation is shown above. The bug in this code is that the program never checks if there's a backslash at the start of a new line; in Markdown, `\` is used as an escape character. To fix the code, I would add an additional condition in both of the highlighted if statements that checks if there's a backslash before the open square bracket. 

[Return to the home page](https://maotcha.github.io/cse15l-lab-reports/)
