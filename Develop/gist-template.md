# Title Regex tutorial: email match. 

The Regex tutorial for beginners.

## Summary

This:

/^([a-z0-9\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

...and the explantion of what this mysterious line of code actually means.

In simple terms this regex searches and matches with valid email addresses.

1. The first part component of the regex: /^([a-z0-9\.-]+) is a search for any username associated with the first part of the email address. It matches with letters, numbers, dots, or hyphens. If we were to use my email address this would return:

agentalliancela33

2. The second component of this regex is:
@([\da-z\.-]+) which represents a match the Domain. 

This matches with @ and any letters, dots, or hyphens.  Using my personal email again as an example this would match with: 

@gmail.

3. The third component of this regex: )\.([a-z\.]{2,6})$/ matches with the extension. 

This regex will match with a dot, any letter, and match with any reoccurrence 2-6 times.

using my personal email as an exapmle would return


This regex would match with my personal address:

agentalliancela33  @  gmail  .  com




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

Anchors don't match with any character at all, they only match positions. A position can be before, in between, or after characters.

The example above shows the anchor "^" caret matching the beginning of the string and the "$" matching the end of the string.

Applying ^a to a-z matches a. ^- does not match a-z at all, because the - cannot be matched right after the start of the string.

### Quantifiers

A Quantifier specifies how many instances of a group, character class, or a single character must be included to find a match. In the example the "+" symbol matches the minimum and the maximum of the first and second segments of my example.

### OR Operator

The “OR” operator is represented with two vertical line symbols: || .

result = a || b translates to: result equals a or b.

In classical programming, the logical OR is meant to manipulate boolean values only. If any of its arguments are true, it returns true, otherwise it returns false.

Logical “or” is difficult to achieve using tools external to the regular expression engine itself, but it is achievable by combining results of multiple regular expressions using the "or" operator.

Grouping and alternation are core features of every modern regular expression library. You can provide as many terms as desired, as long as they are separated with the pipe character: |.

 This character separates terms contained within each (...) group. Take the following example, for instance:

^I like (cats|tigers), but not (dogs|wolves).$

you might verbally express this as " I like cats or tigers, but not dogs or wolves. 

This expression will match any of the following strings:

I like cats, but not dogs.
I like cats, but not dogs.
I like tigers, but not wolves .
I like tigers, but not wolves.

### Character Classes

A character class, also known as a character set, can match with any symbol from a chosen character set.

If you want to match a character set just place the characters you want to match between square brackets []. If you wanted to match "da-z" then you can do that by using [\da-z]. In this example the "\d" would match any digit and "a-z" would specify a and z with the hypen searching for all characters in between. 

Character classes are one of the most commohly used features of regular expressions.

### Flags

Flags are optional parameters that are used to search in a diffent way. Without flags and special symbols, a search is the same as a substring search.

There are only 6 flags in JavaScript:

1. The "i" flag: With this flag the search is case-insensitive: no difference between A and a.
2. The "g" flag: With this flag the search looks for all matches, without it – only the first match is returned.
3. The "m" flag: Multiline mode ( Multiline mode of anchors ^ $, flag "m").
4. The "s" flag: Enables “dotall” mode, that allows a dot . to match newline character \n.
5. The "u" flag: Enables full Unicode support. The flag enables correct processing of surrogate pairs.
6. The "y" flag: “Sticky” mode: searching at the exact position in the text.

### Grouping and Capturing

Parentheses are used to group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.

Capturing groups make it easy to extract part of the regex match. You can reuse the text inside the regular expression via a backreference. Backreferences can also be used in replacement strings.

### Bracket Expressions

A Bracket expression are characters that match with a character out of a set of characters. They match an character inside of brackets ([]).

The example matches lowercase a-z and 0-9. Applies to the brackets in all 3 components:
/^([a-z0-9\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


### Greedy and Lazy Match

Greedy quantifiers attempt to repeat sub-patterns before looking for prior shorter matches. Lazy quantifiers are the opposite, they repeate sub-patterns as little as possible and then looking for other matches using expansion. The + symbol in the example code matches the previous token between one and infinity as many times as it can only giving back as needed which is an example of a greedy quantifier.

### Boundaries

Boundaries are like anchors, but match at the start of a word and/or the end of a word.

In other words: Anchors assert that the current position in the string matches a certain position: the beginning, the end, or in the case of \G the position immediately following the last match. In contrast, boundaries make assertions about what can be matched to the left and right of the current position

Also a boundry will match with a position between a word character and a non-word character or position or the start or the end of a string.

### Back-references

Backreferences match the same text as previously matched by a capturing group.

If we want to match a pair of opening HTML tags along with text in between the tags then you'd need to put opening & closing tags into the back-reference by using "< >".

### Look-ahead and Look-behind

Look-ahead and Look-behind can collectively be referred to as Look-arounds and they can be conusing. 

One confusing thing about Look-arounds is that a look-around is zero-length.

A zero-length assertion is like a beginning and ending of a line and the start and finish of a word. An example of a look behind is: ?<>=123. An example of a look ahead is: ?=123.

The reason its referred to as an "assertion" is because they don't consume characters in the string, but only assert whether a match is possible or not. A Lookaround can allow you to create regular expressions that are very difficult to create without their use.

## Author

Toby Moore

github.com/Tobydawg

https://gist.github.com/Tobydawg/18200fd771cce4ceb0ebe8d555b92f19

https://github.com/Tobydawg/regex
