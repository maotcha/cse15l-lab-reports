# Week 2 Lab Report
This week's lab report is all about answering the question: How do I log into a course-specific account on ieng6? I am probably not the best person to ask, but I'll give it a shot anyways! 

As a small heads-up, I have a Mac, so I will not be including any Windows-specific instructions because I didn't need them. If you're a Windows owner, you should therefore either find someone else's blog to read or go buy a Mac before proceeding.

## Installing VSCode
First things first, we need to install VSCode. Clink the [link](https://code.visualstudio.com/) here and follow the instructions for download and installation. If you've succeeded, you should get a window that looks something like this when you open VSCode.

![VSCode](https://maotcha.github.io/cse15l-lab-reports/part1.png)

## Remotely Connecting
Now we can get to the fun (and headache-inducing) part! You'll need to first look up your course-specific account for CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php). Make sure to set a password for that account! Next, open up a terminal using VSCode and type the following command: `ssh cs15lwi22???@ieng6.ucsd.edu`. Replace the three question marks with the letters in your account. After entering the password you set for your account your terminal should look similar to this.

![SSH](https://maotcha.github.io/cse15l-lab-reports/part2.png)

## Trying Some Commands
We can now try running some commands in our terminal. I ran the following commands on both my own computer and the remote one:
* cd -> change directory
* ls -a -> list all files in current directory
* ls -lat -> lists all files in current directory and provides more information

This is how the commands ran on my computer.
![commands1](https://maotcha.github.io/cse15l-lab-reports/part3_1.png)

Here's how the commands ran on the remote computer.
![commands1](https://maotcha.github.io/cse15l-lab-reports/part3_2.png)

