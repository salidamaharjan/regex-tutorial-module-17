# Match an Email - Regex-Tutorial

A Regular Expression or Regex is a pattern that describes a set of strings that matches the pattern.
It is particularly useful for defining filters containing a series of characters that define a pattern of text to be matched—to make a filter more specialized, or general.

## Summary

This tutorial is going to explain to use a regex called 'Matching an Email'. The tutorial will be using the expression as follow:

<span style="color: green; font-size: 1.5em">/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/</span>

It is clear by it name that this expression is used to validate the email. This tutorial will help understand the components of the expression and walk through how it matches email.

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

Anchors belong to the family of regex tokens that don't match any characters, but that assert something about the string or the matching process. For instance;

- `^` indicates the beginning of String or line.
- `$` indicates the end of String or line.

### Quantifiers

Quantifiers are meta-characters that specify how many times the previous character or group should be matched.

- `+` indicates that the previous character must occur at least one or more times. In the given expression, it matches a to z, 0-9, special characters '.','\_','-' and must have at least one time.
- `{n,m}` indicates occurrences of the preceding element between n and m. The regex has `{2,6}` which allows a match from 2 to 6 characters for set `[a-z\.]`.

### OR Operator

`|`OR operator matches a string that is matched by either. For example, the ERE `a((bc)|d)` matches the string `abc` and the string `ad`. We don't have this operator in the given expression.

### Character Classes

Character class matches any one of the enclosed characters. `\d` in this expression matches a single digit characters from 0-9. In the given expression the username must have at least one number.

### Flags

A flag is an optional parameter to a regex that modifies its behavior of searching. For example 'g' flag
stands for global. 'm' flag refers to multiple.

### Grouping and Capturing

In the given expression, groups are `([a-z0-9_\.-]+)`, `([\da-z\.-]+)` and `([a-z\.]{2,6})` where the first group captures the username for the email which must contain at least one characters from a to z, number from 0 to 9, special characters like'-', '.' , '\_'.

The second and third group captures the domain name that comes after @, that should match character from a - z, number from 0-9, and characters like '\_', '.', '-'. The third group captures the top level domain name. In this expression it captures '.com'.

### Bracket Expressions

`[]` Brackets indicates, the characters inside the bracket to match. In the given expression, we have `[a-z0-9_\.-]`, this matches characters between a-z, 0-9, '-', '.', '\_'. Next one is `[\da-z\.-]` which matches number from 0-9, characters from a-z, character like '.', '-'. And the last one is `[a-z\.]` which matches characters between a-z and character '.'.

### Greedy and Lazy Match

This will try to match longest possible string. We have '+' and '{}' in the given expression, which attempts to match the largest group within given parameters.

### Boundaries

`\b` matches positions where one side word character and other side is not.
For example, The regex `\bcat\b` would therefore match cat in a black cat, but it wouldn't match it in catatonic, tomcat or certificate. Removing one of the boundaries, `\bcat` would match cat in catfish, and `cat\b` would match cat in tomcat, but not vice-versa. Both, of course, would match cat on its own.

### Back-references
Back-references, matches the text matched by an earlier pattern in the expression. For example, (abc)\1 matches abcabc .

### Look-ahead and Look-behind
This looks ahead in the string to check for intended patterns in the string. 
Look ahead `(?=foo)`, asserts that what immediately follows the current position in the string is foo. Look behind `(?<=foo)`, asserts that what immediately precedes the current position in the string is foo.

## Author

You can view my profile and projects at https://github.com/salidamaharjan
