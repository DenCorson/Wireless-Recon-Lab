# Generating password list guide

This guide outlines the process of generating a list of passwords with a set of specified characters in a
string.

##This guide is for educational purposes only. Unauthorized access to networks is illegal and unethical. Use only on networks you own or have explicit permission to test.

## Tools
- Kali Linux
- Crunch


## Open Command Terminal in Linux
  sudo crunch (min) (max) (charset) -o (file name)   (-t (pattern))

  ## PARAMETERS
  (min): Minimum length of the passwords
 
  (max): Maximum lenth of the passwords
  
  (charset): Characters to use (e.g abcd)
 
  -o: Output file to save the wordlist
 
  -t (Optional) Pattern template for more words  
          follow pattern with
              (@) Lowercase letters (a-z)
              (,) Uppercase letters (A-Z)
              (%) Numbers (0-9)
              (^) Special characters
        <!-- the min is the minumum amount of characters which will be generated/cycled through in the string AND max will be maximum chars generated from string-->

## After List is generated open up file
  sudo cat (file.txt)

## List of populated potentail passwords should be generated from here.

        
  

  
