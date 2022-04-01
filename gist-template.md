# Breaking Down Regex

It is my goal through the form on this Readme file; it will be my goal to make Regex a little less confusing for those who are new to the topic.

## Summary

Regex, described in one sentence is code that can be used to find patterns within a string (or a body of text).
The expression that I will be breaking down will be the Regex that will be matching a URL string.

- Matching a URL string
- `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]_)_\/?$/`
- when writing a regular expression the beginning and the end of will always be /
- The information / characters that are passed inside of the slashes will indicate how the regular expression is to function.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Recap](#recap)

## Regex Components

---

### Anchors

In our example the first section of code that we will be looking at is ^(https?:\/\/)

- Anchors belong to the family of regex tokens that don't match any characters but are able to define where the searched information is located at.
- In our example that we are breaking down, we can see that at the beginning of the expression we can see the anchor of `^`.
- The `^` Anchor defined that the following information / group should be located at the start of the string.
- The code will be looking at the beginning of the string, or in our case a URL and is stated that the Https should be at the beginning of said string for the information to match.

### Quantifiers

- Quantifiers specify how many instances of a character, group, or character class must be present in the input or a batch to be found.
- Some common quantifiers include
  - `+` : One or more
  - `{3}` : Exactly three times, the three can be replaced with any specified number
  - `{2,4}` : Two to four times , The two and the four can be replaced with any specified number
  - `{3,}` : Three or more times.
  - `*` : Zero or more times.
  - `?` : Once or none

In our example expression you are able to see that several Quantifiers have been passed.

- The `https:?` will be looking for the section of the string that is defined that it should only appear once, or zero times.
- The `+` is looked for one or more of the information that is defined in the [\da-z\.-] section.
- The `{2,6}` is looking for the information defined in the [a-z\.] section to appear between 2 - 6 times in the string

### Grouping Constructs

Part of the pattern can be defined inside of a group, when creating a group in regex, you will pass th information for the group in a set of ()

Below is the list of groups that our example expression contains.

- `(https?:\/\/)`
- `([\da-z\.-]+)`
- `([a-z\.]{2,6})`
- `([\/\w \.-]\_)`

### Character Classes

- `[]` : One if the characters in the brackets.
- `[a-z]` : One of the characters in the range from a-z.
- `[^x]` : One character that is not an X.
- `[^e-g]` : One character that is not in the range of E to G.
- `[\d\D]` : One character that is a digit or a non-Digit.
- `[\x33]` : matches a character at the hexadecimal position 33

In our example expression, many character classes are defined, including :

- `[\da-z\.-]+` : Which is stating that it is looking for one or more characters that are a digit that lie somewhere within the range of a-z
- `[a-z\.]` : This is looking for a letter that lies within the range of a-z that is followed by a period.

### Flags

Flags can be included in order to affect certain aspects of the search.

- `i` : the search is not case sensitive (no difference between Apple and apple).
- `g` with this flag the search looks for all matches, without it only one match is returned.
- `m` multiline mode
- `s` Enables the dotall mode, this allows the dot to match newline characters.
- `u` Enables full unicode support.
- `y` sticky modem searching at the exact position in the text.

### Character Escapes

Character escapes are used in order to pass certain characters as strings so that they can be included in the search rather than be passed with the original functionality that they contain.

- `.` : Any char except line breaks
- `\` : Escapes a special character

In our example expression we can see that `\` escape is being used, this allows us the utilize the / as a part of the string to avoid the early closing of our regular expression since the character that we are looking as is the '/' which is the same as what we use to begin and end the expression.

Later on in the expression we can see that the `\.` is being passed. This allows for the regex to search for the string of a period, since the normal . is used for other functionality in regex.

### Recap

The expression that we are breaking down is : `/^(https?:\/\/)?([\da-z\.]+)\.([a-z\.]{2,6})([\/\w \.-]_)_\/?$/`

- `^(https?:\/\/)?` : At the beginning of the URL we are looking for a match of https:// that can appear once or not appear at all. In a url this is what comes before the domain name.
- `([\da-z\.])\.` : We are looking for multiple numbers between 0-9 and multiple characters that are between a-z followed by an escaped period. This is where the domain
- `([a-z\.]{2,6})` : We are looking for two to six characters that are following the \., This signifies the '.com', '.io' etc.. endpoint for the.
- `({\/w \.-]_)` : We are looking at the part of the url that would be following after the '.com' wether this be just the / wor a word defining which page that we are on.
- `_\/?$/` : This section is looking for optional endpoints that may exist following the prior section. When working with websites or an api this is where queries may be passed into it.

## Author

This MD file was written by Adam Cleland [Github](https://github.com/aclelandx)

About Me :
I currently am a full stack developer in training, this project was an assignment in the Ohio State Coding Boot Camp for full stack development.

I love what i do and enjoy working on a wide array of projects, if you would ever like to collaborate or have any questions feel free to reach out.
