# Regex Tutorial Starter Code

Module 17 - Regular Expression (REGEX) - Matching a Hex Value
Regular Expression, otherwise known as "regex", is commonly used to search through a string of text in an advanced way allowing us to perform things like validation or get certain pieces of text using advanced find & replace. I plan to explain the regular expression used to match the HEX value in this document. The below takes you through each component and how that component works.

Summary
This regular expression is used to match HEX values: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

This code enables developers to find any hex code based on a set of rules such as

Allows detection with or without the presence of an optional # symbol.
Allows the use of 6 or 3 characters in length, excluding the optional # symbol.
Uses the [0-9a-f] character set.
Table of Content
Anchors
Quantifiers
Grouping Constructs
Bracket Expressions
OR Operator
Character Classes
About the Author
Regex Components
There are two ways to create a regular expression in JavaScript.

A literal notation: A regex is considered a literal. Literal notation parameters consist of patterns enclosed between 2 slash characters /, the first indicating the start of a regular expression and the second indicating the end of a regular expression and the start of expression flags meaning optional flags can follow this after the second slash.
RegExp Constructor: The RegExp constructor function's parameters are enclosed using quotation marks "" and takes either a string or RegExp object as the first parameter and a string of optional flags as its second parameter.
Regular expression literals provide a compilation of the regular expression when the script is loaded. If the regular expression stays constant, using this can improve performance.

Using a constructor function often provides runtime compilation of the Regular Expression. You will generally use the constructor function when you know the regular expression pattern will change or if you are unsure of the pattern due to receiving it from another source, for example, a user input.

Anchors
Anchors do not match any character; instead, they match a position before, after or between characters. They often anchor the regex match at a specific position.

This particular instance begins with the ^ anchor indicating the start of the string. This can also mean the start of a line when using a multi-line pattern.

Code Snippet: /^ with the start anchor being the ^ symbol.

The end of a regular expression finishes with the $ anchor representing the string's ending; however, it can also mean the end of a line.

Code Snippet: $/ with the end anchor being the $ symbol.

Quantifiers
Quantifiers are used to set a limit of the string that the regex matches (Or an individual section of a string). It is a way to indicate the minimum and the maximum number of characters or expressions your Regex wants to match.

By default, Quantifiers are greedy, meaning they generally will match as many occurrences of particular patterns as possible. So adding a ? symbol immediately after a quantifier will then, in turn, make the Quantifiers lazy by matching the minimum number of times.

In our instance, the ? The quantifier is greedy and tells it to match as many occurrences with or without the # as possible. This is used in this location as the # is optional. The ? apended at this point matches its preceding characters 0 - 1 times.

Another Quantifier used is the curly brackets {}. This is used to limit the number of alphanumeric characters the string contains. Code Snippet: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/. Individual examples: {6} and {3}.

Quantifiers include:

* = This is matching a pattern 0 or more times
+ = This is matching a pattern 1 or more times
? = This is matching a pattern 0 or 1 time or can be added directly after each of these Quantifiers, making them lazy
{} = These curly brackets provide 3 different ways to set limits for a match within a string:
{n} = This is matching the pattern exactly n number of times
{n, } = This is matching the pattern at least n number of times
{n, x} = This is matching the pattern from a minimum of n number of times to a maximum of x number of times
Our first Quantifier is the ? symbol in this particular instance. As this has been appended directly after the first Quantifier of #, it matches the proceeding item 0 - 1 times, meaning this Expression will match with a string that starts with # or without the #, making the # optional in this case.
Code Snippet: /^#?

Grouping Constructs
The grouping construct is used to determine a section of the string using parentheses (...), helping clarify different sections that fulfil different requirements and control the precedence of evaluation within an expression. Each section captured in parentheses is known as a subexpression.

In our Regex, it is grouping the entire Expression.
Code Snippet: ([a-f0-9]{6}|[a-f0-9]{3})

Bracket Expressions
A Bracket Expression (also known as a positive character group) is anything that sits inside square brackets [] and can represent a range of characters you want to match. For example, if you were to place abcd inside of []: [abcd], it will look for a string that includes the letters a, b, c or d regardless of the length of the string. To set a range, you could also write Bracket Expressions using the hyphen - between a character or number (only works using letters and numbers). If I were to use the above example of abc, you would write it as [a-d], and it will look for the same thing, i.e. a,b, c and d. Using numerics, you would write it as [1-9], and it would look for strings that contain numbers from 1 through to 9.

In our Regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ it is going to search for any strings that contains exactly 6 or 3 (limits set using curly bracket quantifiers {6} {3}) letters and numbers between "a" to "f" and between "0" to "9". Code Snippet: [a-f0-9] these are divided and matched either before or after by the OR Operator.
Code Snippet: ([a-f0-9]{6}|[a-f0-9]{3})

OR Operator
The OR Operator is used outside group bracket expressions within a grouping construct or between two different grouping constructs. OR Operators are used in our Regex to act like a Boolean OR. This matches the Expression before or after the |. Code Snippet: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

Character Classes
Character Classes are a regex that defines a set of characters such as letters and digits that can occur in an input string to fulfil a match. As explained in the bracket expressions section, you can specify a range of character classes utilising the Hyphen (-). A Bracket Expression is also considered a character class that includes both positive and negative character groups. If the Hyphen appears as the first or last character enclosed in the square brackets, it is considered literal and included in the character class as a regular character.

Other common Character Classes include:

. = This matches any character except a newline character (/n).
\ d = This matches any Arabic numeral digit. This class is equivalent to the bracket expression [0-9]/.
\w = This matches any alphanumeric character from the basic Latin alphabet, including the underscore (_). This class is equivalent to the bracket expression [A-Za-z0-0_].
\s = This matches a single whitespace character, including tabs and line breaks.
Each of the last three character classes can be changed to perform an inverse match by capitalising the letter character. An example would be \D matching a non-digit character.

In our Regex, our Character Classes of lower case a-f finds matches containing characters between a and f and numeric values 0-9 finds matches containing numbers between 0 and 9 are repeated twice. This repetition is because the Regex uses |, the OR Character, which dictates the possibility of HEX code containing either 6 or 3 alphanumeric characters.

About the Author
My name is Chris, and I am an aspiring full-stack developer with a background in Graphic Design and User Experience. To see my work, please click here to view my GitHub Repositories