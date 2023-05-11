# Lab Report 3
## 5/10/2023

## Command Chosen: `grep`
- `grep` is a command that searches for a certain String (pattern) in a group of files. There are several variations of this command which I will expand on in this lab. 

### Variation 1: `grep -i`
**Example 1**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "right" rr74.txt
          Right ventricular pressure measurements
          flushed with cold PBS. The right lung was frozen for
        Mice deficient in iNOS do have a slight increase in right
        = right ventricular systolic pressure.
In this code block from the command line, I used `grep -i` which retured all the lines from rr74.txt that contained the word "right". However, what the `-i` moderator did to the grep command was searched for all instances of the word "right" in rr74.txt REGARDLESS of case. That is why "Right" was included as well as "right".

**Example 2**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "conclusion" gb-2003-4-9-r60.txt
        Conclusions
        In conclusion, the development of any complete, 
In this code block from the command line, I used `grep -i` again, which similarly returned all the lines from gb-2003-4-9-r60.txt that contained the word "conclusion". Due to the `-i` moderator, it returned both "Conclusions" and "conclusion" because it recognized the pattern: conclusion, regardless of case. This example also shows another feature of grep, which is that it also returns lines in which the pattern was found within other words. "Conclusions" is not the same String as "conclusion" however, after disregarding case, the pattern "conclusion" was recognized within the word "Conclusions", and therefore it was recognized.

### Variation 1: `grep -v`

### Variation 1: `grep -n`

### Variation 1: `grep -w`
