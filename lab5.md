# Lab Report 5
## 6/05/2023
## Part 1 - Debugging Scenario
### New Question
### Title: Trouble debugging a syntax error in my Bash Script
### Category: Debugging
**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

I am using a Mac, and I am editing my Bash Script with VSCode. I am also using VSCode's terminal to run my Bash Script

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

The symptom is that when I run the bash script, it works as intended except for the fact that it prints unwanted output as well.
What the script is intended to do is iterate through each word in `file1.txt`, which contains several names of fruits. For each fruit that the script looks at in `file1.txt`, it checks if that fruit exists in `file2.txt`, which specifically contains berries. This is meant to check whether the fruit that is being looked at in `file1.txt` is a berry; if it is, it is supposed to print `"$fruit is a berry"`, where `$fruit` is a variable that references the fruit from `file1.txt` that is being looked at in the current for loop iteration. More specifically, the symptom is that for each iteration of the for loop that is included in my Bash Script, on top of the exptected output, the script prints the output of `grep "$fruit" file2.txt`, which prints the full line on which the word was found from `file2.txt`. I want to omit this `grep` output, and only print the intended output of `$fruit is aberry`. How can I do this, considering I cannot get rid of the grep command, as I need it to search for the desired word in `file2.txt`. Below is a screenshot of my bash Script as well as `file1.txt` and `file2.txt`.

![Image](Lab5Buggy.png)
![Image](fruits.png)
![Image](berries.png)

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

The failure inducing input in this case is a command that generates unwanted output to the terminal: `grep "$fruit" file2.txt`. The issue is that this command, which I need to use in order to carry out my desired operation of searching for a specified String in `file2.txt`, has an output itself; it prints the contents of the line(s) of `file2.txt` in which the String was found (only when it is found).






