# Regex Tutorial

Developers write code, but they also write about code. Take a moment to search the web for tutorials about any of the subjects you’ve learned so far in this course. You’re likely to find thousands of tutorials written by developers of all skill levels, but especially by junior developers—like myself!

## Summary

RegEx is short for regular expression. It is a string of text that allows you to create patterns that help match, locate, and manage text.

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
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors= ^ and $

Matches the starting position within the string. In line-based tools, it matches the starting position of any line. Matches the ending position of the string or the position just before a string-ending newline. In line-based tools, it matches the ending position of any line.

### Quantifiers= \*+?{}

"*" Matches the preceding element zero or more times. For example, ab*c matches "ac", "abc", "abbbc", etc. [xyz]_ matches "", "x", "y", "z", "zx", "zyx", "xyzzy", and so on. (ab)_ matches "", "ab", "abab", "ababab", and so on. "+" Matches the preceding element one or more times. For example, ab+c matches "abc", "abbc", "abbbc", and so on, but not "ac". ?Matches the preceding element zero or one time. For example, ab?c matches only "ac" or "abc".

### OR Operator= | or []

"a(b|c)" Matches a string that has a followed by b or c (and captures b or c), "a[bc]" same as previous, but without capturing b or c.

### Character Classes= \d\w\s .

"\d" Matches a single character that is a digit. "\w" Matches a word character. "\s" Matches a whitespace character. "." Matches any character.

### Flags

A flag would be used after the slash to give more guidelines for matching.
Some examples would be g(global) does not return after the first match, restarting the subsequent searches from the end of the previous match. Also m(multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string. Or i(insensitive) makes the whole expression case-insensitive for instance /aBc/i would match AbC.

### Grouping and Capturing= ()

a(bc) Parentheses create a capturing group with value bc. a(?:bc)\* Using ?: we disable the capturing group. (?<foo>bc) Using ?<foo> we put a name to the group

### Bracket Expressions

[abc] Matches a string that has either an a or a b or a c -> is the same as a|b|c. [a-c] Same as previous. [a-fA-F0-9] A string that represents a single hexadecimal digit, case insensitively. [0-9]% A string that has a character from 0 to 9 before a % sign. [^a-za-z] A string that has not a letter from a to z or from A to Z. In this case the ^ is used as negation of the expression.

### Greedy and Lazy Match

The quantifiers ( \* + {}) are greedy operators, so they expand the match as far as they can through the provided text.

### Boundaries= \b and \B

\babc\b Performs a "whole words only" search. \b represents an anchor like caret (it is similar to $ and ^) matching positions where one side is a word character (like \w) and the other side is not a word character (for instance it may be the beginning of the string or a space character). It comes with its negation, \B. This matches all positions where \b doesn’t match and could be if we want to find a search pattern fully surrounded by word characters.

### Back-references= \1

([abc])\1 Using \1 it matches the same text that was matched by the first capturing group. ([abc])([de])\2\1 We can use \2 (\3, \4, etc.) to identify the same text that was matched by the second (third, fourth, etc.) capturing group. (?<foo>[abc])\k<foo> We put the name foo to the group and we reference it later (\k<foo>). The result is the same of the first regex.

### Look-ahead and Look-behind= (?=)and(?<=)

(?=r) Matches a 'd' only if is followed by r, but r will not be part of the overall regex match. (?<=r)d Matches a 'd' only if is preceded by an r, but r will not be part of the overall regex match

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
