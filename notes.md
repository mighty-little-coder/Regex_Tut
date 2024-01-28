# Notes for project

## Stand seperate from JS, Python, C++, etc. Simple tool for text based resources.

## Sequence of characters that defines a search pattern with in text.

## Derived from a mathmatical concept of regular sets.

## Search patterns can consist of "literal characters" or "meta characters".

### Literal Characters:
These are characters that are equal to the value that is exactly as they are defined. 

    - "R" = capitol 'r'
    - "b" = lowercase 'b'
    - "2" = the numeral '2'
    - "6" = the numeral '6'
    - "\." = the literal '.' character

### Meta Characters:
These are characters that do not indicate a singular, specific character but a general idea of a character. (These characters can vary based on general 'flavors' based on languages.)

There ae a few main meta character categories:

Single characters:

    - "\d" = any digit equal to the value of '0' through '9'
    - "\w" = any character that is capital 'A' through capital 'Z', lowercase 'a' through lowercase 'z', and an number '0' through '9'
    - "\s" = any white space. like a 'space' or a 'tab'. potentionally even cover a line-break 
    - "\W" = anything that is NOT a word character
    - "\S" = anything that is NOT a white space
    - "." = any character

Quantifiers:

    - "*" = this is a quantifier meaning 0 or more characters
    - "+" = this is a quantifier meaning 1 or more characters
    - "?" = this is a quantifier meaning 0 or 1 characters
    - "{min, max}" = this is a quantifier meaning predefined minimum or or maximum characters
    - "{n}" = this is a quantifier meaning predefined number of characters

Position:

    - "^" = refers to position at the begining of a line
    - "$" = refers to position at the end of a line
    - "\b" = refers to word boundry

Character classes:

    - "[]" = the bountry to define search charateristics based on input values
    - "[abc]" = match any character equal to an 'a', 'b', or 'c'
    - "[-.]" = match any character equal to a '-' or '.'
    - "[-]" = match any character equal to a '-' unless it is not the first search criteria, then it means 'through' (as in a-z)
    - "[^]" = match any character NOT equal to the following criteria unless it is not the first search criteria itself, in which case it means a literal '^' character

Alternation:

    - "(|)" = structure for writing an 'or' statement
    - "(me|you)" = search for any literal string of letters either 'm,e' or 'y,o,u'


The following RegEx has been designed to pick out phone numbers written in any common or popularly used format:

    ```\(?\d{3}[-.\s)]\s?\d{3}[-.\s]\d{4}```

The following text block is used to display the regex functionality:

    This is my official phone number: (860) 555-8654. My old phone number was 860-de867-5309 but that has been gone for quite some time. If I am unreachable, you can find me via my wife @ 949.102.0304 or if I am at work, the reachable number will be 203 911 2346.

The following RegEx has been designed to pick out emails written with common or popularly used addresses:

    ```[\w+\.+w\+]+@\w+.(com|net|edu)```

The following text block is used to display the regex functionality:

    If you cannot reach me by phone, feel free tot reach out via email. You'll find my personal email to be jeremy.thecoder@gmail.com. To reach my professional email, contact me @ mr.whosetheboss@yahoo.net. If this is spam, I will respond promptly via email at not.a.real.email+spam@aol.edu.``