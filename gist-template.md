# Regex
I will be talking about regex and some of the components that are available while using regex

## Summary
Regular expressions are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These patterns are used with the exec() and test() methods of RegExp , and with the match() , matchAll() , replace() , replaceAll() , search() , and split() methods of String .

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
What are anchors in a regex?
Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or the matching process. Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.
### Quantifiers
quantifier matches the preceding element one or more times, but as few times as possible. It is the lazy counterpart of the greedy quantifier + . For example, the regular expression \b\w+?\ b matches one or more characters separated by word boundaries.
### Grouping Constructs
Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. You can use grouping constructs to do the following -  Include a subexpression in the string that is returned by the Regex. Replace and Match.
### Bracket Expressions
A bracket expression is either a matching list expression or a non-matching list expression. It consists of one or more expressions: ordinary characters, collating elements, collating symbols, equivalence classes, character classes, or range expressions.
### Character Classes
The character class is the most basic regex concept after a literal match. It makes one small sequence of characters match a larger set of characters. For example, [A-Z] could stand for any uppercase letter in the English alphabet, and \d could mean any digit. Character classes apply to both POSIX levels.
### The OR Operator
You can use the | operator (logical OR) to match characters or expression of either the left or right of the | operator. For example the (t|T) will match either t or T from the input string.
### Flags
The flag s means dot all. That is, it makes the . dot character (technically refered to as the wildcard character) match everything, even newlines. In other words, with the s flag, the dot matches all possible characters. By default, the dot character in a regular expression matches everything, but newline characters.
### Character Escapes

## Author
https://github.com/Tayyibm21/regex
