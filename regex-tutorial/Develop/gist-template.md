# Regex Turtorial

Regular expressions, also known as regexes, are a sequence of characters that define a search pattern. These search patterns are used to find and manipulate text, so they are often used in text editing and processing. In programming, regular expressions are often used to validate user input, search for patterns in data, and perform operations on strings.

## Summary

Regular expressions (regex) are a powerful tool for matching patterns in strings. They can be used to search, edit, and manipulate text, and are often used in programming languages, text editors, and other tools.

Regex patterns are composed of simple characters, such as a or 9, and special characters, such as \* and \d, which represent sets of characters or perform special functions.

Regex patterns can be modified using quantifiers, which specify how many times a character or group of characters should be repeated, and flags, which modify the behavior of the search pattern.

Regex patterns can also include capturing groups, which allow you to extract a portion of the matched string for later use, and alternation, which allows you to specify multiple possible patterns.

Boundaries, such as ^ and $, allow you to match the position of a character or sequence of characters, rather than the character itself, and look-ahead and look-behind allow you to match a pattern based on what comes before or after it, without including the preceding or following text in the matched text.

Here are a few examples of regular expressions and what they would match:

1. `cat`: This regex would match the string "cat" in the input "The cat in the hat."

2. `ca[rt]`: This regex would match the strings "cat" and "rat" in the input "The cat in the hat."

3. `c.t`: This regex would match any three-letter string that starts with "c" and ends with "t", such as "cat", "cbt", or "cxt".

4. `\d{3}-\d{3}-\d{4}`: This regex would match any phone number in the format "123-456-7890".

5. `\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}\b`: This regex would match any email address.

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

In regular expressions, there are several different components that can be used to build a search pattern. Here are some examples of common regex components:

1. Characters: Any individual character, such as a letter or number, can be used as a regex component. For example, the regex a would match the character "a" in the string "cat".

2. Character sets: A character set is a group of characters that can be matched by a single regex component. Character sets are defined using square brackets and can include individual characters, ranges of characters, and special characters such as \d (any digit) and \w (any alphanumeric character). For example, the regex [aeiou] would match any vowel in the string "cat", and the regex [a-zA-Z] would match any letter in the string "123abc".

3. Quantifiers: Quantifiers are used to specify how many times a regex component should be repeated. For example, the quantifier _ means "zero or more times", so the regex a_ would match any string containing zero or more "a" characters. Other common quantifiers include + (one or more times), ? (zero or one time), and {n} (exactly n times).

4. Grouping: Parentheses can be used to group multiple regex components together. This can be useful for applying quantifiers to multiple components or for capturing a portion of a match for later use. For example, the regex (cat)+ would match any string containing one or more occurrences of the word "cat".

5. Alternation: The vertical bar symbol (|) is used to specify an "or" condition in a regex. For example, the regex cat|dog would match the string "cat" or the string "dog".

### Anchors

In regular expressions, anchors are used to match the position of a character or sequence of characters, rather than the character itself. Here are some examples of common anchors:

1. `^`: The caret symbol is used to match the start of a line or string. For example, the regex ^A would match the string "Apple" but not the string "banana".

2. `$`: The dollar symbol is used to match the end of a line or string. For example, the regex a$ would match the string "banana" but not the string "Apple".

3. `\b`: The word boundary anchor is used to match the position between a word character (as defined by the \w regex) and a non-word character. For example, the regex \bthe\b would match the word "the" in the string "The cat in the hat." but not the word "the" in the string "There's a cat in the hat."

4. `\B`: The non-word boundary anchor is used to match any position that is not a word boundary (as defined by the \b regex). For example, the regex \Bthe\B would match the word "the" in the string "There's a cat in the hat." but not the word "the" in the string "The cat in the hat."

### Quantifiers

In regular expressions, quantifiers are used to specify how many times a regex component should be repeated. Here are some examples of common quantifiers:

1. `*`: The asterisk symbol means "zero or more times". For example, the regex a\* would match any string containing zero or more "a" characters, such as "", "a", "aaa", or "hello".

2. `+`: The plus symbol means "one or more times". For example, the regex a+ would match any string containing one or more "a" characters, such as "a", "aaa", but not the string "".

3. `?`: The question mark means "zero or one time". For example, the regex a? would match the strings "a" or "", but not the string "aa".

4. {n}: The curly braces are used to specify an exact number of repetitions. For example, the regex a{3} would match the string "aaa" but not the string "aa" or "aaaa".

5. {n,}: The curly braces with a comma are used to specify a minimum number of repetitions. For example, the regex a{3,} would match any string containing at least three "a" characters, such as "aaaa" or "aaaaaa".

6. {n,m}: The curly braces with a comma are used to specify a minimum and maximum number of repetitions. For example, the regex a{3,5} would match any string containing at least three and at most five "a" characters, such as "aaa" or "aaaaa".

### OR Operator

In regular expressions, the vertical bar symbol (|) is used as an "or" operator to specify an alternation between two or more regex components. For example, the regex cat|dog would match the string "cat" or the string "dog".

### Character Classes

In regular expressions, character classes are used to match any character that belongs to a specific set of characters. Character classes are defined using square brackets and can include individual characters, ranges of characters, and special characters such as \d (any digit) and \w (any alphanumeric character).

Here are some examples of character classes:

1. [abc]: This character class would match any character that is either "a", "b", or "c".

2. [a-z]: This character class would match any lowercase letter (a-z).

3. [A-Z]: This character class would match any uppercase letter (A-Z).

4. [0-9]: This character class would match any digit (0-9).

5. [^a-z]: This character class would match any character that is not a lowercase letter (a-z).

### Flags

In regular expressions, flags are used to modify the behavior of the search pattern. Flags are appended to the end of a regex and are usually preceded by a backslash (\).

Here are some examples of common regex flags:

1. `g`: The "global" flag indicates that the regex should search for all matches, rather than stopping after the first match.

2. `i`: The "case-insensitive" flag indicates that the regex should ignore the case of the characters being matched.

3. `m`: The "multi-line" flag indicates that the regex should treat the input string as multiple lines, rather than a single line. This allows the caret (^) and dollar ($) symbols to match the start and end of a line, rather than the start and end of the entire string.

4. `s`: The "dotall" flag indicates that the regex should treat the dot (.) character as matching any character, including newline characters.

5. `u`: The "unicode" flag indicates that the regex should treat the input string as a sequence of Unicode characters, rather than as a sequence of bytes.

It's important to note that the syntax for regex flags may vary depending on the programming language or regex implementation you are using.

### Grouping and Capturing

In regular expressions, grouping is used to group multiple regex components together, so that you can apply quantifiers or alternation to the group as a whole. Grouping is performed using parentheses (( and )).

For example, the regex (cat)+ would match any string containing one or more occurrences of the word "cat".

Capturing is a related concept that refers to the ability to extract a portion of the matched string for later use. Capturing is performed using parentheses, and the captured text can be accessed using capture groups.

For example, the regex (cat) would capture the word "cat" and store it in capture group 1. In many programming languages, you can access the captured text using a special syntax, such as $1 in Perl or \1 in Python.

Here's an example of how you might use grouping and capturing in a regular expression:

`/(cat)s?/`

This regex uses grouping to apply the optional quantifier (?) to the word "cat", and also uses capturing to store the word "cat" in capture group 1. If the regex matches the string "cats", the captured text would be "cat".

### Bracket Expressions

A bracket expression is a special syntax used in regular expressions to match any character that belongs to a set of characters. Bracket expressions are defined using square brackets ([ and ]) and can include individual characters, ranges of characters, and special characters such as \d (any digit) and \w (any alphanumeric character).

Here are some examples of bracket expressions:

1. [abc]: This bracket expression would match any character that is either "a", "b", or "c".

2. `[a-z]`: This bracket expression would match any lowercase letter (a-z).

3. `[A-Z]`: This bracket expression would match any uppercase letter (A-Z).

4. `[0-9]`: This bracket expression would match any digit (0-9).

5. `[^a-z]`: This bracket expression would match any character that is not a lowercase letter (a-z).

### Greedy and Lazy Match

In regular expressions, "greedy" and "lazy" refer to the way in which the regex engine handles repetitions. By default, most regex engines are "greedy", which means that they will try to match as many repetitions as possible.

For example, consider the following regex and string:

`Regex: <.+>
String: <em>hello</em>`

f the regex engine is greedy, it will match the entire string, from the opening < to the closing >, because that is the longest possible match for the .+ pattern.

On the other hand, if the regex engine is "lazy", it will try to match as few repetitions as possible. In the example above, the lazy regex engine would match only the first <em> portion of the string.

To make a regex pattern lazy, you can add a ? after the quantifier. For example, the regex <.+?> would match the first <em> portion of the string, rather than the entire string.

It's important to note that the behavior of greedy and lazy matching can vary depending on the programming language or regex implementation you are using.

### Boundaries

In regular expressions, boundaries are used to match the position of a character or sequence of characters, rather than the character itself. Here are some examples of common boundaries:

1. `^`: The caret symbol is used to match the start of a line or string. For example, the regex ^A would match the string "Apple" but not the string "banana".

2. `$`: The dollar symbol is used to match the end of a line or string. For example, the regex a$ would match the string "banana" but not the string "Apple".

3. `\b`: The word boundary anchor is used to match the position between a word character (as defined by the \w regex) and a non-word character. For example, the regex \bthe\b would match the word "the" in the string "The cat in the hat." but not the word "the" in the string "There's a cat in the hat."

4. `\B`: The non-word boundary anchor is used to match any position that is not a word boundary (as defined by the \b regex). For example, the regex \Bthe\B would match the word "the" in the string "There's a cat in the hat." but not the word "the" in the string "The cat in the hat."

### Back-references

In regular expressions, back-references are used to match a previously captured group. Back-references are defined using the backslash (\) followed by the number of the capture group that you want to match.

For example, consider the following regex and string:

`Regex: (cat)\1
String: catcat`

In this example, the regex uses a back-reference (\1) to match the second "cat" portion of the string. The first "cat" portion is captured in capture group 1, and the back-reference \1 matches the same text as capture group 1.

Here's an example of how you might use a back-reference in a more complex regex:

`/(\d+)-\1/`

This regex uses a back-reference (\1) to match a repetition of a captured group. In this case, the regex will match any string that contains a sequence of digits followed by a dash and the same sequence of digits. For example, the regex would match the string "123-123" but not the string "123-456".

### Look-ahead and Look-behind

In regular expressions, look-ahead and look-behind are special syntaxes that allow you to match a pattern based on what comes before or after it, without including the preceding or following text in the matched text.

Look-ahead is defined using the syntax (?=...), where the ... represents the pattern that you want to look for. For example, the regex cat(?=fish) would match the string "cat" only if it is followed by "fish", but the matched text would not include the "fish" portion.

Look-behind is defined using the syntax (?<=...), where the ... represents the pattern that you want to look for. For example, the regex (?<=cat)fish would match the string "fish" only if it is preceded by "cat", but the matched text would not include the "cat" portion.

It's important to note that look-ahead and look-behind are "zero-width" assertions, which means that they do not consume any characters in the input string. They simply look for a pattern before or after the current position in the string.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
