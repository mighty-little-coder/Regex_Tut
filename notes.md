# Regular Expression (Regex) Construction Tutorial

Regular Expression (or 'Regex') is sequence of chatacters that defines a search or manipulation pattern within a text string. This is especially powerful when used within a text processor like Microsoft Word, VS Code, PowerShell, etc. This can be utilized to edit large amount of text strings without having to search indiviually for test manually or edit indivually. It is also especiall handy for manipulating text to useful or even hidden when utulized in various other programs, for example, names showing up in last-name, first order, or phone numbers being captured and displayed as hidden character rather than divulging personal information.
</br>
</br>
</br>
## Summary

In this tutorial, we will breakdown the regex for matching an email address. The below code was provided by the EdEx Instructional team, that c ode snippet looks like this:

```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```

This code snippet would be useful in an application that required a registration to access some or all of it's content, among other things. Upon registration there will need to be a check to verify the information that has been input will fit the registration criteria as well as allow the user to know what change must be made to create a functional account. We can use this Regex to verify that information as well as manipulate it for use elsewhere within our code.

There are a few different segments within this regex. We will breakthem down here and then define their purposes in the following sections.

```/``` ```/```<br>
The forward slashes present at either end of a snippet of code are simply how the regex is wrapped to define it as a template literal (or a text string not to be treated as code).

```^``` ```$```<br>
These are known as the anchors. They define the beginning and end of a text string respectively.

```([a-z0-9_\.-]+)``` <br>
This snippet represents the search criteria for the email username.
  
```@```<br>
This represents the search for the '@' icon criteria for an email address.

```([\da-z\.-]+)```<br>
This snippet represents the serarch criteria for the mail server portion of an email address. (Gmail, Yahoo, AOL, etc)
 
```\.```<br>
This represents the literal '.' character.

```([a-z\.]{2,6})```<br>
This snippet represents the top-level domain portion of an email address. (com, net, edu, etc)
</br>
</br>
</br>
## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look---ahead-and-look---behind)
</br>
</br>
</br>
## Regex Components

A typical regex consists of a few major components which will be broken down more in the categories below. Mainly, there are what is known as a literal character and a metacharacter though. 

A literal character can be thought of as a one-to-one relationship meaning a search criteria can be defined literally by the letters ```trg``` for example will filter a search for any instance of the letters ```t```, ```r```, and ```g```. 

A metacharacter can be thought of as a formula or a standin value. It can be used as a much wider search criteria such as ```\d``` searching for any digit of any value (0-9) with no limitions. 
</br>
</br>
</br>
### Anchors

The 'anchors' in this regex are the ```^``` and ```$``` characters. These signify the begining and the end of the expression. This denotes in our file that the search critera MUST begin with what directly follows this character which, in our case, is what falls between the following parenthasis:<br>
```([a-z0-9_\.-]+)```

This also means that it MUST end with what directly preceeds the $ which, in our case, is what falls between the preceeding set of parenthesis:<br>
```([a-z\.]{2,6})```

These are ways to further refine the search criteria to ensure accuracy.
</br>
</br>
</br>
### Quantifiers

Quantifiers denote the number of characters that the specific current regex segment is scoped to. Below are some examples of quantifiers:
- ```*``` = this is a quantifier meaning 0 or more characters
- ```+``` = this is a quantifier meaning 1 or more characters
- ```?``` = this is a quantifier meaning 0 or 1 characters
- ```{min, max}``` = this is a quantifier meaning predefined minimum or or maximum characters
- ```{n}``` = this is a quantifier meaning predefined number of characters

So when used in our code snippet here: ```([a-z0-9_\.-]+)@...``` the ```+``` at the very end signifies that we are searching for one or more characters defined by the process within the square brackets before and to stop the search once the ```@``` symbol is reached.
</br>
</br>
</br>
### OR Operator

The 'Or Operator' define what are known as 'Alterations'. These are when we specify specific cases that the Regex is able to search for. This is represented by the ```|``` character. This bar will be accompanied by the alterations on either side of the character and can be strung together as many times as necessary.

Our code does not utulize this tool, but an example of that would be:
```[\w+\.+w\+]+@\w+.(com|net|edu)```

In this instance, the or operators have limited the search to an email string ending only in ```.com```, ```.net```, OR ```.edu```.
</br>
</br>
</br>
### Character Classes

Character classes define an array of characters to be searched for within the confines of a fixed location in the string. This is defined by the ```[]``` characters. These characters create a bracket expression which will be defined later. This is what it looks like within our code:

```[a-z0-9_\.-]```<br>
This snippet is looking for any array of characters that are alphabetical as defined by the ```a-z``` snippet (this criteria defults to lowercase or uppercase letters). It also searches for any numerical value as defined by ```0-9```. It allows for the underscore, period, and dash characters to be included in the search as well as defined by the ```_```, ```\.```, and ```-``` values respectively.

```[\da-z\.-]```<br>
This snippet contains ```\d``` which is another way of allowing any digit 0-9. There is effectively no differece, but some languages may not accept this syntax. As it is considered a 'metacharacter'.

```[a-z\.]```<br>
This snippet is similar to those above in that is allows for any character ```a-z``` and includes the literal period using ```.```. But this does not allow for any numbers to be included in the search.
</br>
</br>
</br>
### Flags

Flags are used to further refine the results of a regex. They are assigned at the end of a regex string following the last ```/``` character as they modify the search parameters of the entire string. They can be used in any order and can be combined or used seperately. Our code doesn't use any, but some common examples of theres are:

- ```g``` = This applies the search globally in any given body of text.
- ```i``` = This ignores case-sensativity so upper and lowercase lettering does not effect search results.
- ```y``` = This applies a 'sticky' search that starts the search from your current position within the text body.
- ```m``` = This creates a multi-line search condition so that multiple searches appear as seperate lines of code.

An exmaple application of this component would look like this: ```/\d+.\d+/g```
</br>
</br>
</br>
### Grouping and Capturing

<strong>Grouping</strong> allows you to deconstruct a search into one or more 'subexpressions' or 'capture groups'. These are helpful when looking to run a search with in a search and possibly maniuplate these subexpressions differently. An example of this can be seen in our code here: ```([a-z0-9_\.-]+)```. This happens to fall prior to the ```@``` symbol and can now be used seperately to manipulate and re-assign later on to something like a username.

<strong>Capturing</strong> allows you to collect these groupd for potential re-use later on. This can be thought of as storing these groups into a cache or a short term memory.
</br>
</br>
</br>
### Bracket Expressions

The bracket expression search criteria or the ```[]``` syntax, is how an array of literal charaters, meta charaters, special characters or character classes are defined. Here are the examples of bracket expressions in our code (notice they are similar to the character class examples earlier):

```[a-z0-9_\.-]```<br>
This snippet, as one whole bracket expression, defines the entirety of the search criteria for email's username.

```[\da-z\.-]```<br>
This snippet, as a bracket expression, serves as the search criteria for the mail service.

```[a-z\.]```<br>
This snippet, as a bracket expression, serves as the search criteria for the domain of the email address.
</br>
</br>
</br>
### Greedy and Lazy Match

Any character class or, by extension, bracket extension are known as 'greedy' by default. This is due to the nature of their search results. They search for as many of the matching criteria as possible. Once those search results are further refined, they become what is known as 'lazy' matches. Meaning they will be limited in the results they return in one way or another. This can be defined in our code as a ```?```. With this we can limit a search like this:</br>
</br>
```/h.+l/``` from the the string ```hello``` which returns ```hell```. (Greedy)</br>
</br>
to this:</br>
</br>
```/h.+?l/``` from the the string ```hello``` to return ```hel```. (Lazy)</br>
</br>
</br>
### Boundaries

Setting boundries around our search parameters using the ```/b.../b``` syntax will define our search to only whole words. This refinement amends our criteria to check and verify that the next both the previous postion and the postion is a word character or not a word character. This is how it is able to define what is a word. For example, we can use this to refines a search like this:</br>
</br>
Searching this string ```note notepad notebook``` with this regex ```\/bnote/b\``` will return only the string ```note``` since the other terms have more characters within the same word and therefor do not fit our confined search.
</br>
</br>
</br>
### Back-references

Earlier we reviewed that grouping and capturing object meant we had ther ability to recall and manipulate parts of a regex elsewhere. We use back-references to do just that. Depending on the language we plan on using this with, there different way to call those references. In JavaScript, we can give them a name and call them by their array position. In our code we have a total of 4 groups. The first group being the whole string. Our code would break down like this:</br>
</br>
- ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/``` = group[0]
- ```([a-z0-9_\.-]+)``` = group[1]
- ```([\da-z\.-]+)``` = group[2]
- ```([a-z\.]{2,6})``` = group[3]
</br>
</br>
</br>

### Look-ahead and Look-behind

Look-ahead is a search paramter that we can use to check the text 'ahead' or 'right' of our current position while maintaining our current position. This is so that we can select and modify text ahead of our current position while still referencing our current position. For this we use the ```?=pattern``` and ```?!pattern``` syntax. Within this syntax, ```pattern``` will be any regex statement, ```?=``` means the look ahead pattern matches the pattern criteria, and the ```?!``` means the text ahead does NOT match our pattern criteria.</br>
</br>
Look-behind is a similar criteria but, as the name suggests, looks 'behind' or 'left' of our current position. All other functionality is identical to that of look-ahead. The look-behind search criteria syntax is: ```?<=pattern``` or ```?<!pattern```. Similar to the of look-ahead, ```?<=``` means the look behind patternmatches the npattern criteria, and the ```?<!``` means the text ahead does NOT match our pattern criteria.
</br>
</br>
</br>
## Author

<a href="https://github.com/mighty-little-coder">Jeremy Doran</a> authored this gist. Click to view his GitHub profile! 🚀
</br>
</br>
</br>
# REF

- <a href="https://bootcampspot.instructure.com/">Bootcamp Spot</a>
- <a href="https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial">Full-Stack Training Materials</a>
- <a href="https://developer.mozilla.org/en-US/">MDN</a>
- <a href="https://www.youtube.com/@TheCodingTrain">The Coding Train</a>
- <a href="https://www.yourdictionary.com/articles/email-message-parts">Your Dictionary</a>