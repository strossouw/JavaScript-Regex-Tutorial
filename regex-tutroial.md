Regular Expression (REGEX) - Matching an Email Address
Regular Expression (REGEX) - Matching an Email Address

Summary
Regular Expression, more commonly referred to as REGEX is a a set of characters, numbers, and symbols that define a search criteria. In this tutorial I will explain how to use the regex to match email address from a string of text.

Table of Contents
Components
Anchors
Quantifiers
Character Escapes
Flags
Grouping and Capturing
Bracket Expressions
Regex Components
The regex components of this search are: /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

Anchors
The characters ^ and $ are both considered to be anchors.

When using this regex to search for an email address there are two anchors. The first anchor is ^ . The ^ signals the start of the search expression. The end anchor is $ signaling the end of the search expression.

Quantifiers
Quantifiers appear before the $ anchor as:

*—Matches the pattern zero or more times
+—Matches the pattern one or more times
?—Matches the pattern zero or one time
{}—Curly brackets can provide three different ways to set limits for a match:
{ n, }—Matches the pattern at least n number of times
{ n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times in { } .
The quantifiers for this regex /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/

are + + {2,6}

The + character is used to connect one part of the email string to the next. username + (google, aol, yahoo) + .com. The 2-6 allows for a range of 2 to 6 characters to be used for matching the set of characters.

Character Escapes
The . is used to exclude characters from being interpreted literally. In this regex it is used to exclude ]+)@([ from being a literal interpretation.

Flags
There are three flags encountered in this regex.

g—Global search: the regex should be tested against all possible matches in a string.
i—Case-insensitive search: case should be ignored while attempting a match in a string
m—Multi-line search: a multi-line input string should be treated as multiple lines
Grouping and Capturing
There are three groupings in this search.

The first grouping construct in the expression used when matching email is [a-z0-9_.-]+, this is used to matches the username/email name or the first part of the email before that @.

The next matching group is defined by \da-z.-+. This is used to group for matching the email service (google, aol, yahoo).

Finally the third capture group is [a-z.]{2,6}. This is used to group the last part of the email (.com, .net) for matching.

Bracket Expressions
There are three different bracket expressions that are used for validating an email address.

The first set being [a-z0-9_.-]. This set is used for matching an alpha and numeric characters from a-z and 0-9. This set is specifically case sensitive. It can also match the _,-, and the period character.

The next bracket expression is [\da-z.-], which matches only a single digit from 0-9, as well as any letter from a-z.

Finally there is [a-z.], which will match any letter a-z, as well as the period character.

Author
Stephanie Rossouw

https://github.com/strossouw