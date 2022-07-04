# Title

Regular Expressions- Regex

## Summary

Regular Expressions are a tool for describing search patterns. The search pattern can be used for text search and text replacement operations. These patterns can be various kinds: a mix of letters with digits, special characters and different language characters.

In this tutorial I will cover the basics of RegEx(shorthand) to ensure that only validated email addresses can be used that follows the correct regex format.

Matching an Email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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

### Anchors

Anchors do not match any character in the regex, instead they match a position before or after characters:

- ^ The caret anchor matches the beginning of the text.
- $ The dollar anchor matches the end of the text.

In our case the matching email code:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

The anchor ^ illustrates that the code must start ^([a-z0-9_\...here and ends with ...]{2,6})$ to be able to validate or it won't work.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.

Common quantifiers used:

- - Match zero or more times.
- - Match one or more times.
- ? Match zero or one time.

More than one quantifier is use in our case, quantifier + means that it has to contain at least one of this in order to have a match.

### OR Operator

In a regular expression it is denoted with a vertical line character | and logically(OR), where it can be used to match the character on the left or right side.

Not used in our email example we are using.

### Character Classes

Character classes differentiates between kinds of characters, for example letters and digits.

| Character Classes | Meaning                                                                |
| :---------------- | :--------------------------------------------------------------------- |
| .                 | Matches any single character except line terminators                   |
| \d                | Matches any digit                                                      |
| \D                | Matches any character that is not a digit                              |
| \w                | Matches any alphanumeric character from the basic Latin alphabet       |
| \W                | Matches any character that is not a word character from Latin alphabet |
| \s                | Matches single white space character                                   |
| \S                | Matches a single character other than white space.                     |

We have used \d for the search pattern in the email.

### Flags

Flags are optional in regex.

There are 6 types of flags in JavaScript:

- "i" With this flag the search is case-insensitive so no difference between a and A.
- "g" The search looks for all matches, without it – only the first match is returned.
- "m" Multiline mode. It only affects the behavior of ^ and $.
- "s" Allows a dot . to match newline character.
- "u" The flag enables correct processing of surrogate pairs.
- "y" Searches at the exact position in the text.

No flags used in our email example.

### Grouping and Capturing

Capturing groups are a way to treat multiple characters as a single unit. By enclosing part of a regular expression in parentheses, we can group that part of the regular expression as a new "index" of the string. This allows to apply a quantifier to the entire group or to restrict alternation to part of the regex.

There would be three different groups in our example:

- ([a-z0-9_\.-]+) is the first group that appears in our regex that matches the user email name
- ([\da-z\.-]+) is the second group that appears in our regex which will match the email service.
- ([a-z\.]{2,6}) is the third group that appears in our regex that capture the domain's .com.

### Bracket Expressions

A bracket expression indicates characters that should match a specific set of single characters, and may match a specific set of multi-character collating elements, based on the non-empty set of list expressions contained in the bracket expression.

In our email validation example /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/:

- [a-z0-9_.-] which is matching any letter a-z and is case-senstive. It also matches a character 0-9 and matches the characters "\_" , "-" , and "."

- The [\da-z.-] means 0 through 9, a through z, "." dot, and "-" hyphen.

- The [a-z] means a through z, and "."

### Greedy and Lazy Match

Regex has two ways of matching greedy and lazy.

Greedy: will try to match the longest possible string.

Lazy Search — will try to match the smallest possible string.

In our case /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/ it includes the + quantifier, it will match as many times as possible giving back as needed.

### Boundaries

The (\b) is an anchor like the caret (^) and the dollar sign ($). It matches a position that is called a “word boundary”. The word boundary match is zero-length.

The following three positions are qualified as word boundaries:

- Before the first character in a string if the first character is a word character.
- After the last character in a string if the last character is a word character.
- Between two characters in a string if one is a word character and the other is not.

### Back-references

Back references are used to match the same text previously matched by a capturing group. This both helps in reusing previous parts of your pattern and in ensuring two pieces of a string match.

### Look-ahead and Look-behind

Lookahead and lookbehind, are zero-length assertions just like the start and end of line, and start and end of word anchors explained earlier in this tutorial. The difference is that lookaround actually matches characters, but then gives up the match, returning only the result: match or no match. They do not consume characters in the string, but only assert whether a match is possible or not.

## Author

Researched and authored by Senthol Kumar.

Reach out for any questions or collaborations.
