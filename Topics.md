## Basic topics

### Anchors — ^ and $

### Quantifiers — * + ? and {}

### OR operator — | or []

```
a(b|c)     matches a string that has a followed by b or c
a[bc]      same as previous
```

### Character classes — \d \s \w \D \S \W . [[:xxx:]]
> Note: The `[:xxx:]` forms is the POSIX standard, and `\d \s \w \D \S \W` is Perl syntax. :star: 

```
\d  matches a single character that is a digit
\w  matches a word character (alphanumeric character plus underscore)
\s  matches a whitespace character
.   matches any character
```
> They are all match ***a single character***. :star: :star:

## Intermediate topics

### Grouping and capturing — ()

```
// Grouping with capturing
a(bc)           parentheses create a capturing group with value bc
a(?<foo>bc)     using ?<foo> we put a name to the group

// Grouping without capturing
a(?:bc)*        using ?: we disable the capturing group
```

### Greedy and Lazy match

The quantifiers ( `* + {}`) are **greedy** operators, so they expand the match as far as they can through the provided text.

The aforementioned quantifiers may, however, be made **lazy** or minimal or reluctant, `matching as few characters as possible`, by appending a question mark(`?`).

