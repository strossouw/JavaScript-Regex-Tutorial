

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
Regex uses two anchors when matching an email. The anchors are ^ as well as $. The ^ is entered by the developer to show the start of the search string. The $ is used to show the end of the search string.

### Quantifiers
The quantifiers used in the regex with regard to matching email are {2,6} as well as +. The + character or operator is used to connect one part of the email string to the nex. username + email (google, aol, yahoo) + .com. The 2-6 allows for a range of 2 to 6 characters to be used for matching the set of characters.

### Grouping Constructs
The first grouping construct in the expression used when matching email is [a-z0-9_\.-]+, this is used to matches the username/email name or the first part of the email before that @. The next matching group is defined by \da-z\.-+. This is used to group for matching the email service (google, aol, yahoo). Finally the third capture group is [a-z\.]{2,6}. This is used to group the last part of the email (.com, .net) for matching.

### Bracket Expressions
There are also three different bracket expressions that are used for validating an email address. 
The first set being [a-z0-9_\.-]. This set is used for matching an alpha and numeric characters from a-z and 0-9. This set is specifically case sensative. It can also match the _,-, and the period character. The next bracket expression is [\da-z\.-], which matches only a single digit from 0-9, as well as any letter from a-z. Finally there is [a-z\.], which will match any letter a-z, as well as the period character.

### Character Classes
The character class that is used in the email matching regex is \d. This will match only a single character that can be a digit in the range from 0 to 9. For example it will match, 2, but it will not match the input 33 as it contains multiple digits. 

### The OR Operator
The Or operator is deliniated by |. It allows grouping between two grouping constructs outside of bracket expression.

### Flags
There are three different types of flags that are used in this regex. The are as follows:
g- which means it is a glboal search, that will look for every single possible match within a string.
i- this deliniates a case in-sensitive search. Meaning that case should not be considered when searching for letters.
finally- m- which is a multiple line search, and says that the string should be interperted as multiple lines.

### Character Escapes
To escape characters that you do not want to be literally interpreted, you use the backslash \. This would allow the regex to search for things like " or { within the string without interpreting them as the start of a quantifier.
