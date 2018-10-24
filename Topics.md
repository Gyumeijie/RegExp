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
