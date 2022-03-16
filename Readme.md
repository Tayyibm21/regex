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
Implementation of RegExs differ to suit the need for the expression. Although, sometimes a character has a relatively universal use. Below are some regular expression components. Consider a search operation for digits on a multi-line text. The pattern [0–9] finds every digit in the text, no matter where it is located.
### Anchors
Anchors are characters that specify the location within a particular string to search.

For example: The pattern ^[0–9] finds every digit that is the first character on a line.

12 3 4

The same idea applies to line endings with [0–9]$.

1 2 34

Some more examples of anchors that do not consume characters:

^- Beginning of string (or line, depending on the mode)
$- End of string (or line, depending on the mode)
\A- Beginning of string
\z- End of string
\Z- Varies a lot depending on the engine, so be careful with it
\b- Word boundary
\B- Not a word boundary


## Quantifiers
Quantifiers allow a user to specify how many times they would like a particular regex string to match.

By default, regex matching is eager and will match as much as possible, which is not always the desired behavior.

Lazy quantifiers allow you to limit how much is matched, and you can further specify how many times matches are found with other limiting characters, such as:

* - - Match 0 or more times.
+ - - Match 1 or more times.
{ n } - Match exactly n times.

### Grouping Constructs

We can match groups of characters by surrounding them with parentheses. This allows a user to combine a sequence of literals and pattern characters with a quantifier to find repeating or optional matches.

Going back to the vehicle registration plates RegEx above:

(^[A-Z]{2}[0-9]{2} [A-Z]{3}$)
Is a combination of a sequence of literals and pattern characters with a quantifier. Breaking this grouped constructor down, reads as:

^[A-Z]{2} - ^ anchor asserts that this is the beginning of the string. [A-Z]{2} Matches any character from A-Z but the length range must between 2.

### Bracket Expressions
[ ] Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set. for example:

[A-Za-z] - captures any character between A-Z upper or lower case, as these character sets are case sensitive.

[A-Z]/i - captures any character between A-Z upper or lower case but is offset with the i flag.

{ } Curly braces are used to specify an exact amount of things to match. They are used after an expression: \na{2}\ will only match ‘na’ exactly twice.

### Character Classes
Character Sets: You can tell the regex engine to match only one out of several characters. This can be done by placing the characters you want to match between square brackets. If you want to match an a or an e, use [ae].
You can use a hyphen inside a character class to specify a range of characters. [0-9] matches a single digit between 0 and 9.

Negated Character Classes: If a caret is inserted after the opening square bracket, negates the character class. Therefore the character class matches any character that is not in the character class.
If you don’t want a negated character class to match line breaks, you need to include the line break characters in the class. [^0-9\r\n] matches any character that is not a digit or a line break.

Metacharacters Inside Character Sets: Special characters or metacharacters inside a character class are the closing bracket ], the backslash \, the caret ^, and the hyphen -. The usual metacharacters are normal characters inside a character class, and do not need to be escaped by a backslash.


### The OR Operator
You can provide as many terms as desired, as long as they are separated with the pipe character |. This term separates terms within each parenthesis group. So the (logical OR) matches characters or expression of either the left or right of the operator For example:

(^[A-Z]{2}[0-9]{2} [A-Z]{3}$)|(^[A-Z][0-9]{1,3} [A-Z]{3}$)

The above code offers a regex for a Valid Current style registration plate, OR a Valid Prefix style registration plate. Therefore the sting that would be passed through that would look for a match for either one.

### Flags
Flags in the world of regular expressions are used to modify the searching behaviour of given patterns.

Flags are optional parameters, that can be added to an expression to make it search in a different way. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression's searching behaviour. For example:

i - which stands for ignore casing, does the job of carrying out a case-insensitive search.

g - which stands for global, serves to extend the searching to find all matches for a given expression inside a string, instead of stopping on the first match.

The General way of implementing these flags is using the following syntax:

/pattern/flags
### Character Escapes
When learning how to correctly escape characters in a regular expression, we can divide the escaping rules into two different lists of characters that need to be escaped:

for characters inside a character class

There are 5 characters that need to be escaped inside a character class (anywhere inside [...]):

[ Purpose: Start of character class.
] Purpose: End of character class.
\ Purpose: Escaping.
- Purpose: Character ranges.
^ Purpose: Class Negation.

for characters outside a character class

We can use the same characters from above to be escaped outside of a character class, however they have a few differences:

[ Purpose: Needed to define a character class.
] Purpose: Needed to close a character class, some regular expression will allow you to not escape a ']' as long as it's outside a character class.
\ Purpose: Used to escape both inside and outside character classes but it must always be escaped when specifying a literal '' character.
- Purpose: Does not need to be escaped outside a character class.
^ Purpose: Used to find every digit/character that is the first on a line.

There are at least 14 characters to escape outside a character class.
## Author
https://github.com/Tayyibm21/regex
