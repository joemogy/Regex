# Regex Cheat Sheet

Introductory paragraph (replace this with your text)

## Summary

Regular expressions, or regex, are a powerful tool used in many programming languages to search and manipulate strings. In JavaScript, regex is used to match a pattern in a string, such as checking if an email is valid, replacing text, or extracting information. 
Here's a basic structure of a regular expression in JavaScript:

bash
/pattern/flags

The pattern is the string you want to match, and the flags are optional and specify how the pattern should be matched.

Here are some common regex patterns and what they do:

. (dot): Matches any single character except for a newline character.
*: Matches the preceding expression 0 or more times.
+: Matches the preceding expression 1 or more times.
?: Matches the preceding expression 0 or 1 time.
^: Matches the start of a string.
$: Matches the end of a string.
[...]: Matches any single character within the square brackets.
[^...]: Matches any single character not within the square brackets.
\d: Matches a digit (0-9).
\w: Matches a word character (a-z, A-Z, 0-9, _).
\s: Matches a white-space character (spaces, tabs, newlines).
(...): Captures a group.
(?:...): Non-capturing group.
Here's an example of using regex in JavaScript to check if a string is a valid email address:

javascript
let email = "test@example.com";
let regex = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/;
let result = regex.test(email);
console.log(result); // true

The test() method tests if a string matches the regex pattern and returns a boolean value.

Regex can be a powerful tool for developers, but it can also be complex and difficult to understand. It's important to take the time to learn and practice regex to fully understand its capabilities and limitations.

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
Regular expressions (regex) consist of various components or elements that can be combined to match patterns in a string. Here are some common regex components:

Literal characters: These are regular characters that match themselves exactly. For example, the pattern abc matches the string "abc".
Special characters: These are characters with a special meaning in regex, such as ., *, +, ?, [, ], etc. They are used to match specific types of characters or sets of characters.
Character classes: These are defined inside square brackets [] and match any character within the class. For example, [aeiou] matches any vowels.
Quantifiers: These specify how many times the preceding element should be matched. For example, a* matches zero or more a characters, while a+ matches one or more a characters.
Alternation: The | symbol is used to match either the expression before or after the |. For example, apple|banana matches either "apple" or "banana".
Grouping: Parentheses () are used to group elements together and create sub-expressions. For example, (ab)+ matches one or more occurrences of the string "ab".
Anchors: These are special characters that match a specific position in a string, such as the start ^ or end $ of a string.
By combining these components, you can create complex regex patterns to match a wide range of strings.
### Anchors
Anchors in regex are special characters that match a specific position in a string, rather than a specific character. Here are two common anchors:

^ (caret): Matches the start of a string. For example, /^A/ will match the "A" in "Apple", but not in "banana".
$ (dollar sign): Matches the end of a string. For example, /t$/ will match the "t" in "cat", but not in "cut".
Anchors are often used to ensure that a match occurs at the start or end of a string, or to specify the exact position where a match should occur. They can be combined with other regex elements to form complex patterns.
### Quantifiers
Quantifiers in regex specify how many times the preceding element should be matched. There are several quantifiers in regex:

* (asterisk): Matches the preceding element 0 or more times. For example, a* matches zero or more "a" characters.
+ (plus sign): Matches the preceding element 1 or more times. For example, a+ matches one or more "a" characters.
? (question mark): Matches the preceding element 0 or 1 time. For example, a? matches either 0 or 1 "a" characters.
{n} (curly brackets with a number n): Matches the preceding element exactly n times. For example, a{3} matches exactly 3 "a" characters.
{n,} (curly brackets with a number n and a comma): Matches the preceding element n or more times. For example, a{3,} matches 3 or more "a" characters.
{m,n} (curly brackets with numbers m and n separated by a comma): Matches the preceding element at least m times, but no more than n times. For example, a{3,5} matches between 3 and 5 "a" characters.
Quantifiers are useful for matching patterns that occur a specific number of times in a string. They can be combined with other regex elements to create complex patterns.
### OR Operator
The OR operator, represented by | (vertical bar) in regex, is used to match either the expression before or after the |. For example, the pattern apple|banana matches either "apple" or "banana". The OR operator is used to specify alternatives in a regex pattern, allowing you to match one of several possible options.
### Character Classes
Character classes in regex are used to match any character within a set of characters. They are defined inside square brackets [] and match a single character from the set. For example, the pattern [aeiou] matches any vowels. Character classes can also specify a range of characters using a hyphen -. For example, [a-z] matches any lowercase letter.

Character classes can be negated by including a caret ^ at the start of the class. For example, [^aeiou] matches any character that is not a vowel. This is useful for matching characters that are not part of a specific set.

Character classes are a powerful tool for matching specific characters or ranges of characters in a string, and are a fundamental part of regex.
### Flags
Flags in regex are optional parameters that modify the behavior of a regular expression. They are specified after the regular expression and are separated by a forward slash /.

Here are two common flags in regex:

i (ignore case): Makes the regex match case-insensitive. For example, /abc/i matches "abc", "Abc", "aBc", etc.
g (global): Makes the regex match all occurrences in the string, rather than stopping after the first match. For example, /a/g matches all "a" characters in a string.
There are other flags available in regex, but these two are the most commonly used. By using flags, you can customize the behavior of your regex to better match the needs of your application.
### Grouping and Capturing
Grouping and capturing in regex are used to group elements together and capture the matched text as a separate group. This allows you to perform operations on specific parts of the matched text and apply quantifiers or other regex elements to the grouped elements.

Parentheses () are used to define a group. For example, the pattern (ab)+ matches one or more occurrences of the string "ab". The matched text within each group can be accessed through group references or backreferences in the replacement string.

In addition to grouping, capturing is used to capture the matched text of a group for later use. For example, the pattern (\d\d) captures two digits in a string, and the captured text can be accessed later in a replacement string.

Grouping and capturing are important concepts in regex, as they allow you to perform more advanced operations on matched text and extract specific parts of the matched text for further processing.
### Bracket Expressions
Bracket expressions in regex are similar to character classes, but with a few additional features. They are defined inside square brackets [] and match a single character from the set. For example, the pattern [aeiou] matches any vowels.

Bracket expressions support the same features as character classes, such as specifying a range of characters using a hyphen - and negating the class by including a caret ^ at the start.

In addition, bracket expressions support several additional features, such as:

Predefined character sets: Certain characters can be matched by including specific sequences within the bracket expression. For example, \d matches any digit, and \w matches any word character (letters, digits, or underscores).
POSIX character classes: Certain character sets can be specified using the syntax [:class:]. For example, [:alpha:] matches any alphabetical character.
Bracket expressions are a powerful tool for matching specific characters or ranges of characters in a string, and are an important part of regex.
### Greedy and Lazy Match
In regex, a "greedy" match is one that matches as much of the string as possible, while a "lazy" match matches as little of the string as necessary to make the pattern match.

By default, quantifiers in regex are greedy, which means they match as much of the string as possible. For example, the pattern .* matches as much of the string as possible, including any newline characters.

Lazy matching is used to change the behavior of a greedy quantifier so that it matches as little of the string as necessary. This is done by adding a question mark ? after the quantifier. For example, the pattern .*? matches as little of the string as necessary, excluding newline characters.

The choice between greedy and lazy matching depends on the specific requirements of your pattern, and can make a big difference in the way your pattern matches the input string. Understanding the difference between greedy and lazy matching is important for effectively using regex.
### Boundaries
Boundaries in regex are special characters or constructs that define the start or end of a string, a word, or a line. They allow you to match specific parts of a string and ensure that the pattern matches only where you want it to.

Here are some common boundaries in regex:

^ (start of line): Matches the start of a line. For example, ^A matches "A" at the start of a line.
$ (end of line): Matches the end of a line. For example, A$ matches "A" at the end of a line.
\b (word boundary): Matches the boundary between a word character (letters, digits, or underscores) and a non-word character. For example, \bA\b matches "A" when it is surrounded by non-word characters.
\B (non-word boundary): Matches any position that is not a word boundary.
By using boundaries, you can define where a pattern must start and end, and ensure that it matches only the desired parts of a string. Understanding the use of boundaries is essential for writing effective regex patterns.
### Back-references
Back-references in regex allow you to refer back to a previously captured group within a pattern. This allows you to match repeating patterns, perform substitution, and more.

Back-references are created by including a backslash \ followed by the group number in the pattern. For example, if you have captured a group using parentheses ( ), you can refer to it later in the pattern using \1.

For example, the pattern (.*)\1 matches any string that is repeated, such as "the the" or "hello hello".

Back-references are a powerful tool in regex and can be used in a variety of ways to match complex patterns, perform substitution, and more. Understanding how to use back-references is essential for writing effective regex patterns.
### Look-ahead and Look-behind
Look-ahead and Look-behind in regex are constructs that allow you to specify conditions that must be met, but do not consume any characters in the input string. They allow you to match patterns based on what follows or precedes the current position in the string.

There are two types of look-ahead and look-behind: positive and negative.

Positive Look-ahead: Matches the pattern only if it is followed by the specified pattern. For example, the pattern A(?=B) matches "A" only if it is followed by "B".
Negative Look-ahead: Matches the pattern only if it is not followed by the specified pattern. For example, the pattern A(?!B) matches "A" only if it is not followed by "B".
Positive Look-behind: Matches the pattern only if it is preceded by the specified pattern. For example, the pattern (?<=A)B matches "B" only if it is preceded by "A".
Negative Look-behind: Matches the pattern only if it is not preceded by the specified pattern. For example, the pattern (?<!A)B matches "B" only if it is not preceded by "A".
Look-ahead and look-behind constructs are useful for matching patterns that are conditional on the surrounding context. They allow you to specify conditions that must be met without consuming any characters in the input string. Understanding the use of look-ahead and look-behind is important for writing effective regex patterns.
## Author
Joseph Mogavero is a web developer who specializes in the MERN stack. The MERN stack is a combination of technologies used to build web applications, including MongoDB (a NoSQL database), Express (a web framework), React (a JavaScript library for building user interfaces), and Node.js (a JavaScript runtime). 
## author's GitHub profile
github.com/Joemogy
