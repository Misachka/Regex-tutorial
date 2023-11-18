# Regex tutorial! How to validate an email address

Regex, short for Regular Expressions, is a tool used to manipulate and search for text patterns in strings. It is a language used to describe a specific pattern of characters, which can be used to match, search, replace or validate data.

Regular expressions can be a combination of letters, numbers, special characters, and quantifiers.


## Summary

Regex expressions are character sequences that are used to identify character patterns within a string, They can also be used to replace characters whithin this patten. 

In this tutorial I will cover the components of regulas expressions that we use to validate and email address : `/^w+[+.w-]*@([w-]+.)*w+[w-]*.([a-z]{2,4}|d+)$/i` 


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

In Regex, anchors are special characters used for a specific positioning within a string. There are two types of anchors: the caret ("^") and the dollar sign ("$").

character `^` is used to start and character `$` to finish. 

For example, email Regex:  `/^w+[+.w-]*@([w-]+.)*w+[w-]*.([a-z]{2,4}|d+)$/i`

-The ^ anchor matches the start of a line.
-The $ anchor matches the end of a line.

By using these anchors, we ensure that the entire email address matches the pattern from start to end.

### Quantifiers

Quantifiers are special characters in regex that allow you to match a specific number of instances of a character, group, or character class. Quantifiers are usually placed after the character, group, or character class that you want to match.

They often use maximum and minimum to set the parameters of the regex.

In our example of regex we used  `+` quantifier to match one or more characters in the username part of the email address. `{2,4}`  is also used as a quatifier in this regex which sets the range of characters that match the character set of [a-z.] that precedes it in the regex. They are also called greedy quantifiers. 


### OR Operator

The "OR" operator in regex is denoted by the vertical bar (|) character. It is used to specify alternatives or choices within a regex pattern. When used in a pattern, the "OR" operator matches any of the alternatives listed on either side of the vertical bar.

In our regex pattern, we use the | operator to match either a dot (.) or a hyphen (-) in the domain part of the email address.

### Character Classes

A character class is a way to specify a set of characters that you want to match in a pattern. A character class is enclosed in square brackets [ ], and any character within the brackets is considered a valid match.

In our example, we can point out 3 patterns:

1.  ([a-zA-Z0-9._%+-]+) represents the username part of the email address.

2.  ([a-zA-Z0-9.-]+) represents the domain part of the email address. It allows alphanumeric characters, dots, and hyphens.

3.  ([a-zA-Z]{2,}) represents the TLD part of the email address. It allows alphabetical characters with a minimum length of 2.

In our regex example, the character class `\w` is used. Jacascript classifies this as a use of any word.

### Flags

Flags are modifiers that can be added to a regular expression pattern to change the way the pattern is interpreted or matched. There are several flags available in most regex implementations, each with its own purpose and syntax. This flags are:

1. Case-insensitive flag(i)  - it allows a pattern to match both uppercase and lowercase letters.

2. Global flag(g) - it causes a pattern to match all occurrences in a string.

3. Multiline flag (m) - it changes the behavior of the "^" and "$" anchors, so that they match the beginning and end of each line within a string.

4. Sticky flag (y) - it forces a pattern to match only at the current position in the string.

In our regex example Case-insensitive flag(i) is used. 


### Grouping and Capturing

Grouping in regular expressions allows you to treat multiple characters as a single unit. It enables you to apply quantifiers, capture specific parts of the pattern, or create logical sections within the regex.

There are three groups being captured in out example. 

1. `/^w+[+.w-]*@`. This is the "user name" and it captures everything before the `@`. 

2.  `([w-]+.)*w+[w-]*.`. This is the "domain name" and it captures everything in between the `@` and the `.`. 

3.  `([a-z]{2,4}|d+)$/i` captures the "extension", or everything that comes after the `.`. (i.e .com or .net)


### Bracket Expressions

A bracket expression is a way to specify a set of characters that should match a single character in the input string.

We have four different bracket expressions in out example expression! The information inside of the bracket is held in open/close bracketsm like this `[]`. This identifies which information is matched.

### Greedy and Lazy Match

Greedy and lazy matching refer to how the pattern matching engine behaves when encountering a quantifier, such as *, +, or ?.

Greedy matching is the default behavior, where the engine tries to match as much of the input string as possible while still satisfying the pattern. 

Lazy matching, on the other hand, matches the shortest possible sequence of characters while still satisfying the pattern. This is achieved by adding a question mark after the quantifier, such as "?" or "+?". 

In our example we only have greedy matches,  `+` and `{}`. This means that it will allow the match to expand as long as it needs to. 

### Boundaries

Boundaries are special characters or sequences that define the edges of a word or line in the input string. These boundaries can be used to match specific patterns within the input string, such as words that start or end with a particular sequence of characters.

The boundaries used in our example are `^` and `$`, which representes the start and endpoint of the string. 

### Back-references

Back-references are a feature in regex that allow you to refer to a previously matched group in the same pattern. This can be useful for matching patterns that have repeated characters or sequences, or for extracting specific parts of the input string that match a certain pattern.

To create a back-reference in regex, we use a special syntax that includes a backslash followed by a number, such as "\1" or "\2". The number refers to the capturing group that you want to reference, where the first capturing group is numbered as 1, the second as 2, and so on.

### Look-ahead and Look-behind

Look-ahead and look-behind are advanced features in regex that allow you to match patterns based on what comes before or after a given string without including it in the match. These features are called "look-around" because they let you look around a string without actually matching it.

Look-ahead and look-behind can be combined with other regex features,that we discussed above,  to create complex patterns matching expressions. These features are particularly useful for extracting specific patterns from the input string that are surrounded by certain characters or sequences.

## Author

This tutorial was created by a Full Stack web development bootcamp student.

Github: https://github.com/Misachka 
