# Week 8 Lab Report
This is something related to debugging? I don't really know anymore, it's week 8 and I'm running on some combination of Shin ramen and cute cat videos. Pray for me.

## Github Repositories
Here is the [link](https://github.com/maotcha/markdown-parse) to my repository, and here's another [link](https://github.com/maotcha/markdownparse2) to the repository I reviewed.

## Snippet 1
According to VScode preview, when `MarkdownParse.java` is run with the first snippet, the `ArrayList` returned from `getLinks()` should look like this: ```[`google.com, google.com, ucsd.edu]```.

![snippet1 own test](https://maotcha.github.io/cse15l-lab-reports/snippet1_JUnit_mine.png)

Above is the test I wrote in `MarkdownParseTest.java` for my own program based on the expected output when using snippet 1. 

![snippet1 other test](https://maotcha.github.io/cse15l-lab-reports/snippet1_JUnit_other.png)

As you can see from the above picture, I had to make some changes to my JUnit test to make it work for the program I'm reviewing.

![running own test](https://maotcha.github.io/cse15l-lab-reports/snippet1_mine_test.png)

Here is the results from me running my test on my own program. As you can see, my program didn't pass the test, and you can see the specific JUnit output saying so below:

![JUnit snippit 1 own test failure](https://maotcha.github.io/cse15l-lab-reports/snippet1_mine_failure.png)

Moving on to the program I'm reviewing, below are the results from running the test:

![running other test](https://maotcha.github.io/cse15l-lab-reports/snippet1_other_test.png)

As you can see, this program didn't pass the test either, and you can see the specific JUnit output saying so below:

![JUnit snippit 1 other test failure](https://maotcha.github.io/cse15l-lab-reports/snippet1_other_failure.png)

For my program, I don't believe a small code change could make it work for snippet 1 and all related cases that use inline code with backticks. In my program, the contents of the file are split into individual lines and stored in an ArrayList. As such, not only would I need to handle any backticks within each String stored in the ArrayList, which would require a lot of variables and conditions to check, but I'd also need to track backticks across indivdual Strings in case, for example, the file started with three backticks, contained a lot of valid links, then ended with another three backticks. I don't know about you, but I don't think I could implement a solution like that in ten lines or less.

## Snippet 2
According to VScode preview, when `MarkdownParse.java` is run with the second snippet, the `ArrayList` returned from `getLinks()` should look like this: `[a.com, a.com(()), example.com]`.

![snippet2 own test](https://maotcha.github.io/cse15l-lab-reports/snippet2_JUnit_mine.png)

Above is the test I wrote in `MarkdownParseTest.java` for my own program based on the expected output when using snippet 2. 

![snippet2 other test](https://maotcha.github.io/cse15l-lab-reports/snippet2_JUnit_other.png)

Above is the test I wrote in `MarkdownParseTest.java` for the program I'm reviewing.

![running own test](https://maotcha.github.io/cse15l-lab-reports/snippet2_mine_test.png)

Here is the results from me running my test on my own program. As you can see, my program didn't pass the test, and you can see the specific JUnit output saying so below:

![JUnit snippit 2 own test failure](https://maotcha.github.io/cse15l-lab-reports/snippet2_mine_fail.png)

Moving on to the program I'm reviewing, below are the results from running the test:

![running other test](https://maotcha.github.io/cse15l-lab-reports/snippet2_other_test.png)

As you can see, this program also didn't pass the test, and you can see the specific JUnit output saying so below:

![JUnit snippit 2 other test failure](https://maotcha.github.io/cse15l-lab-reports/snippet2_other_fail.png)

Once again, I don't believe that there's a small change which will allow my program to correctly handle snippet 2 and all related cases. For something like this, I'd not only need to match up brackets and parantheses, but also check if some combination of the two resulted in a valid link within another link. The matching up could be handled with a stack, and the tracking of a potential nested link could be handled with a few variables tracking various indices, but I think with how many if statements, loops, and variables would be needed, the code would definitely exceed ten lines.

## Snippet 3

According to VScode preview, when `MarkdownParse.java` is run with the third snippet, the `ArrayList` returned from `getLinks()` should look like this: `[https://ucsd-cse15l-w22.github.io/]`.

![snippet3 own test](https://maotcha.github.io/cse15l-lab-reports/snippet3_JUnit_mine.png)

Above is the test I wrote in `MarkdownParseTest.java` for my own program based on the expected output when using snippet 3. 

![snippet3 other test](https://maotcha.github.io/cse15l-lab-reports/snippet3_JUnit_other.png)

Above is the test I wrote in `MarkdownParseTest.java` for the program I'm reviewing.

![running own test](https://maotcha.github.io/cse15l-lab-reports/snippet3_mine_test.png)

Here is the results from me running my test on my own program. As you can see, my program didn't pass the test, and you can see the specific JUnit output saying so below:

![JUnit snippit 3 own test failure](https://maotcha.github.io/cse15l-lab-reports/snippet3_mine_fail.png)

Moving on to the program I'm reviewing, below are the results from running the test:

![running other test](https://maotcha.github.io/cse15l-lab-reports/snippet3_other_test.png)

It seems that the program got stuck in an infinite loop, which is why the results of the JUnit tests never prints. I hit CTRL C and got the result below, which helpfully points out that there was an error when running the tests:

![JUnit snippit 3 other test failure](https://maotcha.github.io/cse15l-lab-reports/snippet3_other_fail.png)

Surprise, surprise, I don't think a small code change through which my program could properly handle snippet 3 and all related cases is possible. This is mainly because my program splits the String containing the contents of a file by `\n` and stores them in an ArrayList. Thus, to handle newlines in brackets and parantheses, not only would I need to add code to check for empty lines within brackets or parantheses, but I'd also need to track brackets and parantheses across Strings in the ArrayList; I'd likely need to rewrite a good chunk of `getLinks()`. As such, between the new code additions and edits to old code, I think a lot more than ten lines would be needed to implement a solution to snippet 3 and all similar cases.

[Return to the home page](https://maotcha.github.io/cse15l-lab-reports/)
