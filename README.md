# proj3-anagrams
Vocabularly anagrams game for primary school English language learners (ELL)


## Overview

A simple anagram game designed for English-language learning students in 
elementary and middle school.  
Students are presented with a list of vocabulary words (taken from a text file) 
and an anagram.  The anagram is a jumble of some number of vocabulary words, randomly chosen.  Students attempt to type vocabularly words that can be created from the  
jumble.  When a matching word is typed, it is added to a list of solved words. 

The vocabulary word list is fixed for one invocation of the server, so multiple
students connected to the same server will see the same vocabulary list but may 
have different anagrams.

## Authors 

Initial version by M Young; 
Final version by P Hunter
Contact: phunter@uoregon.edu

## Known bugs

The start/stop scheme is not working.  Flask (or perhaps the virtual
environment) is creating two Unix processes running the application,
and I am capturing the process ID for only one of them.  Therefore
stop.sh manages to kill only one, leaving the other running.  At this
time I do not know a workaround.  It is necessary to kill the second
process manually.  Use 'ps | grep python' to discover it, then 'kill'
to kill it.  Or, on Linux systems, use the 'killall' command. 

## Status

updated version runs a real-time checker
Everytime a key is pressed it checks the word (or partial word) against the word list, jumble, and
solved words. If the key is a valid key it gives a prompt to keep going. If the key is not a valid 
key the program will display an equivalent error message and clear the text box. The user can then
start over with a new word.

## Minijax? 

flask_minijax.py and templates/minijax.html are a tiny example of using JQuery 
with flask for an Ajax application.  They should not be included in the
version of the project you turn in. 


## To run automated tests 
* `nosetests`

There are currently nose tests for vocab.py, letterbag.py, and jumble.py. 

'make test' should work.  To run 'nosetests' explicitly, you must be
in the 'vocab' subdirectory. 

