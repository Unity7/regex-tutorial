# Regex - A complete tutorial

This complete tutorial outlines how to use regular expressions in Javascript.

## Summary

A regular expression is a sequence of characters that forms a search pattern in texts.

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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

### Anchors

Anchors match a position before, after, or between characters.
The caret ^ matches the position before the first character in the string.
The $ matches right after the last character in the string.

For example: applying "^a" to abc matches a. ^b does not match abc because the b cannot be matched right after the start of the string; c$ matches c in abc.

### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.

- - Match zero or more times.

* - Match one or more times.
    ? - Match zero or one time.
    { n } - Match exactly n times.
    { n ,} - Match at least n times.
    { n , m } - Match from n to m times.

### OR Operator

With [ ], you have the OR operator at a character level. With alternation, you have the OR operator at the pattern level.

(pattern1|pattern2|pattern3) will match either pattern1 OR pattern2 OR pattern3

### Character Classes

can tell the regex engine to match only one out of several characters. Place the characters you want to match between square brackets. If you want to match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey.

### Flags

Regular expressions may have flags that affect the search
i - With this flag the search is case-insensitive: no difference between A and a (see the example below).
g - With this flag the search looks for all matches, without it – only the first match is returned.
m - Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m").
s - Enables “dotall” mode, that allows a dot . to match newline character \n (covered in the chapter Character classes).
u - Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter Unicode: flag "u" and class \p{...}.
y -“Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position)

### Grouping and Capturing

A part of a pattern can be enclosed in parentheses (...). This is called a “capturing group”. It allows to get a part of the match as a separate item in the result array. If we put a quantifier after the parentheses, it applies to the parentheses as a whole.

Example: file_record_transcript.pdf - To capture only the file name without the extension you would use something like ^(file.+)\.pdf$

### Bracket Expressions

Bracket expressions match one character out of a set of characters, just like regular character classes. Bracket expressions adapt to the user’s or application’s locale.

Regular expression [\d] matches a \ or a d. To match a ], put it as the first character after the opening [ or the negating ^. To match a -, put it right before the closing ]. To match a ^, put it before the final literal - or the closing ]. Put together, []\d^-] matches ], \, d, ^ or -.

### Greedy and Lazy Match

Greedy means match longest possible string.

Lazy means match shortest possible string.

For example, the greedy h.+l matches 'hell' in 'hello' but the lazy h.+?l matches 'hel'.

### Boundaries

The metacharacter \b is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

\b allows you to perform a “whole words only” search using a regular expression in the form of \bword\b. A “word character” is a character that can be used to form words. All characters that are not “word characters” are “non-word characters”.

### Back-references

Backreferences match the same text as previously matched by a capturing group.

### Look-ahead and Look-behind

Lookahead and lookbehind, collectively called “lookaround”, are zero-length assertions just like the start and end of line, and start and end of word anchors

## Author

https://github.com/unity7
