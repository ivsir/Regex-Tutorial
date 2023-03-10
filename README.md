# Regular Expression Tutorial: Matching an Email

Regular Expressions are a JavaScript tool which simplifies the validation process of common frameworks for specific strings. Such common frameworks including but not limited to - usernames, emails, passwords and URLs. Regular expressions often contains a set series of special characters that follow specific frameworks to ensure that the framework is being properly verified.


## Summary

In this tutorial we will be exploring how Regular Expressions or Regex for short with an email regex as our example. Refer to the line of code below as this is the universal line of code for email regex's.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

In summary, the regex is a template literal of a typical email which includes three different bracket expressions to make up an email.

* The first bracket expression is limited to lowercase letters,numbers, underscores, periods and hyphens and followed by an @
* The second bracket expression is a domain limited to any lowercase letter, any number, a hyphen, a period and is followed by a period '.'
* The third and final bracket expression is limited to lowercase letters and can only contain a string with a size from 2-6 characters in length and ends afterwards

We will go in further detail throughout the tutorial.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Escapes](#character-escapes)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components
The regex pattern must be wrapped in forward slashes (/), because they are considered literals. Take a look at the "Matching an email" regex's first and last character:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Anchors
The '^' and '$' are generally considered to be the anchors.

The ^ anchors signify the beginning of a string. The strings that typically follow the ^ are one of the two formats

* One format is an exact string match. Exact string matches are typically stricter with its validation process. For example, given a regex ^What, the strings "What" and "What the" match, but "what" and "what the" do not since a regex is case sensitive
* The other format offers a range of possible characters to verify rather than an exact match for verification. These are typically enclosed within bracket expressions.

The $ signifies the end of the string.

So for example, in our "Matching an Email" regex, the first string must start and end with a character that is include in the pattern [a-z0-9_\.-], with the (\.) being included so that we can include a period in the pattern.

### Quantifiers
Quantifiers are located within the curly brackets ({}). They set the limits of the string that the regex matches.

Some common quantifiers include: 

* *???Matches the pattern zero or more times
* +???Matches the pattern one or more times
* ????Matches the pattern zero or one time
* {}???Curly brackets can provide three different ways to set limits for a match:
    * { n }???Matches the pattern exactly n number of times
    * { n, }???Matches the pattern at least n number of times
    * { n, x }???Matches the pattern from a minimum of n number of times to a maximum of x number of times

In our email regex, the {2,6} is a quantifier located before the $ anchor. If we refer to the { n, x } structure, then the third bracket expression is limited to a range between 2 characters and 6 characters.

### Character Escapes
The backslash (\) in a regex escapes specific characters that are usually used literally. For example, the character ([) is often used to begin a bracket expression, but if we put the backslash before it (\[), then the ([) is defined as a left bracket and escapes its use as the beginning of a bracket expression.

In our "Matching an email regex", the (\) is used before the (.) and (-), which are typically used to represent a character class and a range respectively. This was include before the

### Character Classes
A character class defines a set of characters in which the string is to match.

Common character classes include:

* . - Matches any character except newline character (\n)

* \d - Matches any numerical digit. This is equivalent to [0-9]. This is used in our second string in the email regex.

* \w - Matches any alphanumber letter from the basic Latin alphabet. This is equivalent to [A-Za-z0-9_]

* \s - Matches a single whitespace character including tabs and white spaces.

If we capitalize the letter for a character class, then the inverse of the criteria need to be met. For example, (\D) matches a characters that are not numerical digits from [0-9].

In our email regex, our second string uses a \d to represent any numerical digit. If we interpret our second string, again

### Grouping and Capturing
Grouping constructs break up sections of a regex using parantheses (()). Each section within the parentheses is referred to as a subexpression.

If we refer to our email regex, it is split into three different subexpressions

* The first being ([a-z0-9_\.-]+)
* The second being ([\da-z\.-]+)
* and the third being ([a-z\.]{2,6})

### Bracket Expressions
The character patterns within the square brackets ([]) offer a range of characters that we are expected to match. While they are commonly known as bracket expressions, they are also known as a positive character group as they outline the characters we want the user to include. These expressions are typically written so that they contain all the characters we want to match. 

Take [bcde] or [b-e] for example. Strings such as "bed" "bcccde" or "decbee" match the criteria of the positive character group.

The hyphen (-) that we see from the previous example is often used between alphanumeric characters (letters and numbers). The two bracket expressions in the example above are essentially calling for the same criteria.

### Greedy and Lazy Match
Quantifiers are commonly referred to as "greedy" expression. It is commonly referred to as greedy, because they want to match a certain amount of occurences of particular patterns as ppossible. 

They can be made Lazy by adding a ? symbol after it as it will match as few occurences as possible. 


## Author
Risvi Tareq
GitHub: https://github.com/ivsir
