# Lab Report 3
## 5/10/2023

## Command Chosen: `grep`
- `grep` is a command that searches for a certain String (pattern) in a group of files. There are several variations of this command which I will expand on in this lab. 

### Variation 1: `grep -i`
#### This variation of `grep` searches for a pattern regardless of case (uppercase or lowercase). 

**Example 1:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "right" rr74.txt
          Right ventricular pressure measurements
          flushed with cold PBS. The right lung was frozen for
        Mice deficient in iNOS do have a slight increase in right
        = right ventricular systolic pressure.
In this code block from the command line, I used `grep -i` which retured all the lines from rr74.txt that contained the word "right". However, what the `-i` moderator did to the grep command was searched for all instances of the word "right" in rr74.txt REGARDLESS of case. That is why "Right" was included as well as "right".

**Example 2:**

    dhruv.patravali@Dhruvs-MacBook-Air biomed % grep -i "conclusion" gb-2003-4-9-r60.txt
        Conclusions
        In conclusion, the development of any complete, 
In this code block from the command line, I used `grep -i` again, which similarly returned all the lines from gb-2003-4-9-r60.txt that contained the word "conclusion". Due to the `-i` moderator, it returned both "Conclusions" and "conclusion" because it recognized the pattern: conclusion, regardless of case. This example also shows another feature of grep, which is that it also returns lines in which the pattern was found within other words. "Conclusions" is not the same String as "conclusion" however, after disregarding case, the pattern "conclusion" was recognized within the word "Conclusions", and therefore it was recognized.

Source: https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use.

### Variation 2: `grep -v`
This variation of `grep` searches for all lines that DON'T contain the specified pattern. 

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

Here is another example of `grep -v` being used. In this case, once again the `-v` modifier ensured that all the lines from rr196.txt that DID NOT contain the pattern "e" were returned. What is interesting about this example, however, is that I demonstrated how modifiers can be used in conjunction with one another. By using `grep -iv`, I was able to return all the lines from rr196.txt that didn't contain the pattern "e" regardless of case. This means it ommitted lines with "E" (capitalized) as well.

Source: https://www.freecodecamp.org/news/grep-command-in-linux-usage-options-and-syntax-examples/#:~:text=Grep%20is%20a%20useful%20command,a%20powerful%20command%20to%20use.

### Variation 3: `grep -n`

### Variation 4: `grep -w`
