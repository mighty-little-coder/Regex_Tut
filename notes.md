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

Qualifiers:

    - "*" = this is a quantifier meaning 0 or more characters
    - "+" = this is a quantifier meaning 1 or more characters
    - "?" = this is a quantifier meaning 0 or 1 characters
    - "{min, max}" = this is a quantifier meaning predefined minimum or or maximum characters
    - "{n}" = this is a quantifier meaning predefined number of characters

