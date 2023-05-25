# Lab Report 3
## 5/10/2023

## Command Chosen: `grep`
- `grep` is a command that searches for a certain String (pattern) in a group of files. There are several variations of this command which I will expand on in this lab. 

### Variation 1: `grep -i`
#### This variation of `grep` searches for a pattern regardless of case (uppercase or lowercase). 
This variation is useful because oftentimes, when searching for a pattern — such as a key word or key phrase — the case of the pattern is irrelevant for the purposes of the search. When all the user is trying to do is find every instance of the pattern, being able to use `grep -i` to ignore case allows the user to find all occurances of the pattern without missing instances due to case, or needing to run multiple `grep` commands of the same pattern with different case combinations. 

**Example 1:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "right" rr74.txt
          Right ventricular pressure measurements
          flushed with cold PBS. The right lung was frozen for
        Mice deficient in iNOS do have a slight increase in right
        = right ventricular systolic pressure.  


In this code block from the command line, I used `grep -i` which retured all the lines from `rr74.txt` that contained the word "right". However, what the `-i` moderator did to the grep command was searched for all instances of the word "right" in `rr74.txt` REGARDLESS of case. That is why "Right" was included as well as "right".

**Example 2:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "conclusion" gb-2003-4-9-r60.txt
        Conclusions
        In conclusion, the development of any complete,     


In this code block from the command line, I used `grep -i` again, which similarly returned all the lines from `gb-2003-4-9-r60.txt` that contained the word "conclusion". Due to the `-i` moderator, it returned both "Conclusions" and "conclusion" because it recognized the pattern: conclusion, regardless of case. This example also shows another feature of grep, which is that it also returns lines in which the pattern was found within other words. "Conclusions" is not the same String as "conclusion" however, after disregarding case, the pattern "conclusion" was recognized within the word "Conclusions", and therefore it was recognized.

Source: [Grep Command in Linux - Usage, Options, and Syntax Examples](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use).

### Variation 2: `grep -v`
#### This variation of `grep` searches for all lines that DON'T contain the specified pattern.
This variation is particularly useful when you want to omit a certain pattern from a search. For instance, if there is a particular term/phrase that is irrelevant to the content that you are searching for, it might be useful to narrow your search results by excluding all the lines that contain that particular term/phrase.

**Example 1:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -v "a" rr166.txt

  
        Introduction
        the fibrotic process [ 2 ] .
        properties 
        (TX)A 
      
      
        
          to 8.
        
        
          2 , 6-keto-PGF 
          2 , PGF 
          2α , TXB 
          vol/vol) for 6-keto-PGF 
          2 . Then PGF 
          2 , PGE 
          ions m/z 569/573 for PGF 
          2α , m/z 614/618 for TXB 
        
        
          1% Tween 20, 10 mM phenylmethylsulphonyl fluoride,
        
        
          overnight.
        
        
        
      
      
        Results
        
          ng/10 6cells/30 min, respectively; 
          
          2 ), PGF 
          except TXB 
          0.61 [0.21-1.64] ng/10 6cells/30 min with IL-1β
          (results not shown).
          HF-NL (0.61 [0.21-1.64] ng/10 6cells/30 min; 
          different between the two cell groups (1.73 [0.77-2.53]
          versus 0.75 [0.15-2.58] ng/10 6cells/30 min, in HF-IPF
          1α :TXB 
          P = 0.09 [Fig. 2]).
        
        
          4).
        
      
      
        Discussion
        2 , TXB 
        2 to TXA 
        2 :TXA 
        [ 13 14 15 16 17 26 ] . TXA 
        smooth muscle cells TXA 
        c-fos , 
        14 ] .
        of PGI 
        fibrogenesis.
        2 to TXA 
        in vivo .
        
        5 6 7 8 ] .
        PGE 
        2 production, but they further showed
        2 production in response to TGFβ
        Wilborn 
        lungs of subjects with IPF.
      
      
        Conclusion
        2 :TXA 
        of IPF.     


In this example, you can see the use of `grep -v`. What this command did in this example is return all the lines for which the pattern, "a", was NOT found. As you can see, none of the lines contain the lowercase letter "a". This is useful if you want to omit a certain pattern while conducting a search. 

**Example 2:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -iv "e" rr196.txt

  
    
      
        Introduction
        strips 
      
      
        
        
        
          Diaphragm strip physiology in vitro
          L 
          L 
          o was 2.68 ± 0.09 cm in control
          P = 0.001).
          L 
          P = 0.51).
        
        
        
        
          MHC RT-PCR
          PCR.
          PCR amplification.
          of 25 mM MgCl 
          (Fig. 1).
          runs.
        
        
          with a rabbit anti-rat laminin primary antibody (Sigma,
          antibody dilution of 1:50, an 18 hour incubation, and a
        
        
        
        
          Statistical analysis
        
      
      
        
          lung capacity (25 cmH 
          n = 9; 
          n = 9) and 25.3 ± 0.3 ml in
          controls animals ( 
          n = 10) ( 
          P < 0.0001). Thus, H 
          controls.
        
        
          RT-PCR
        
        
        
        
          P = 0.99).
        
        
          In vitrostrip physiology
          with a 
        
      
      
        Discussion
        humans.
        rats, Kanbara 
        in situ hybridization that 1.0% of
        29 ] .
        difficult to draw any firm conclusions from comparisons
        diaphragmatic function 
        diaphragm strips.
      
      
        Conclusion
        isoforms.       



Here is another example of `grep -v` being used. In this case, once again the `-v` modifier ensured that all the lines from `rr196.txt` that DID NOT contain the pattern "e" were returned. What is interesting about this example, however, is that I demonstrated how modifiers can be used in conjunction with one another. By using `grep -iv`, I was able to return all the lines from `rr196.txt` that didn't contain the pattern "e" regardless of case. This means it ommitted lines with "E" (capitalized) as well.

Source: [Grep Command in Linux - Usage, Options, and Syntax Examples](https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use).

### Variation 3: `grep -n`
#### This variation of `grep` returns not only the contents of each line that contains the search pattern, but also returns the line number of each returned line of text. 
This variation is useful for when you want to not only find the contents of each occurence of a particular search pattern, but want to find the location of each instance of that search pattern. This is useful in several scenarios, one of the most prominent being when you need to edit lines of text that contain the given search pattern. `grep -n` makes it much easier to find the exact location of where these edits need to occur in the text file, and allows you to make these edits much more efficiently. 

**Example 1:**

    [cs15lsp23ex@ieng6-202]:biomed:238$ grep -n "method" 1471-2202-3-5.txt
    47:        18 ] . This method has proved especially valuable in
    86:        a method to eliminate nonlinear trends in the data, a
    367:          bivariate method as shown in Figures 9, 10, both the
    412:          method for monitoring 
    654:        methods to ask whether the two 
    728:        real-time methods (potentially including images of tissues)
    867:        periodic by correlogram. This method is presented in detail
    900:        method does not specify whether the difference is due to

Above is an example of `grep -n` being used. In this case, the `grep -n` command was used to find the exact line numbers in which the word "method" occured in the file `1471-2202-3-5.txt`. The numbers on the left side of the command line output correspond to each line of texts that sits directly to its right, which makes it much easier to locate the occurances of the search pattern in the text file. 

**Example 2**

    [cs15lsp23ex@ieng6-202]:Alcohol_Problems:248$ grep -nw "14" Session2-PDF.txt
    49:drinking as consumption of more than 14 drinks/week or more than 4
    147:their clinical impressions.14-16 Stereotypic profiling may be the
    469:14. Becker B, Woolard RH, Nirenberg TD, Minugh A, Longabaugh R,
    
Above is another example of `grep -n` being used but this time in conjunction with `grep -w`, which is why the command shown is `grep -nw`. This combination is particularly useful as it allows you to isolate specific, exact instances of the search pattern with their corresponding line number, all without the results being convoluted by lines that contain some variation of the search parameter (for example maybe 1495 instead of 14). This can be useful especially when writing or editting code, when you are trying to find very specific patterns in your code in order to make changes. Excluding patterns that aren't exactly the pattern that you are searching is more efficient, but more importantly, seeing the line number of each occurance of your specified pattern ensures that you not only know what edits need to be made, but you know exactly WHERE to make them. 

### Variation 4: `grep -w`
#### Did not have time to do this variation, Planning on doing the same thing with the same format as I did for Variation 1 and 2. Would just like feedback on the work that I have completed so that I can submit a better project into the resubmission next week. 
