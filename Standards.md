# Standards

The IEEE POSIX standard has three sets of compliance: **BRE** (Basic Regular Expressions), **ERE** (Extended Regular Expressions), and ~~**SRE**~~ (Simple Regular Expressions, but is deprecated).

BRE and ERE **work together**. ERE adds `?`, `+`, and `|`, and it removes the need to escape the metacharacters `( )` and `{ }`, which are required in BRE. 

BRE and ERE provide a "standard" which has since been adopted as the default syntax of many tools, where the choice of BRE or ERE modes is usually a supported option. For example, `GNU grep` has the following options: "grep -E" for **ERE**, and "grep -G" for **BRE** (the default), and "grep -P" for **Perl regexes**. 

Perl regexes have become a ***de facto standard***, having a rich and powerful set of atomic expressions. Perl has no "basic" or "extended" levels. 


## POSIX basic 

In the POSIX standard, Basic Regular Syntax (**BRE**) requires that the ***metacharacters*** `( )` and `{ }` be designated `\(\)` and `\{\}`, whereas Extended Regular Syntax (**ERE**) does not.

| Metacharacter | Description 
| :---:    | --- 
| ^        | Matches the starting position within the string. In line-based tools, it matches the starting position of any line.
| .        | Matches any single character.
| [ ]	     | Matches a single character that is contained within the brackets.
| [^ ]     | Matches a single character that is not contained within the brackets.
| $        | Matches the ending position of the string or the position just before a string-ending newline. In line-based tools, it matches the ending position of any line.
| ( )	     | Defines a marked subexpression. The string matched within the parentheses can be recalled later. **BRE mode: \\( \\)**.
| \n       | Matches what the ***nth*** marked subexpression matched, where n is a digit from 1 to 9.
| *        | Matches the preceding element zero or more times.
| {m, n}   | Matches the preceding element at least ***m*** and not more than ***n*** times. **BRE mode: \\{m,n\\}**.


## POSIX extended

The meaning of metacharacters ***escaped*** with a backslash is **reversed** :star: for some characters in the POSIX Extended Regular Expression (**ERE**) syntax. With this syntax, a backslash causes the metacharacter to be treated as a literal character. So, for example, ~~`\( \)`~~ is now `( )` and ~~`\{ \}`~~ is now `{ }`.

| Metacharacter | Description 
| :---:    | ---
| ?        | Matches the preceding element zero or one time.
| +        | Matches the preceding element one or more times.
| \|        | The choice (also known as alternation or set union) operator matches either the expression before or the expression after the operator. 

POSIX Extended Regular Expressions can often be used with modern Unix utilities by including the command line flag ***-E***.

```bash
$ sed 's/[a-z]+//g' <<<"1234abdf"
1234abdf

$ sed 's/[a-z]\+//g' <<<"1234abdf"
1234

$ sed -E 's/[a-z]+//g' <<<"1234abdf"
1234
```
> The meaning of some metacharacters escaped with a backslash is reversed in different mode.

## Perl and PCRE

Because of its expressive power and (relative) ease of reading, many other utilities and programming languages have adopted syntax similar to Perl's—for example, `Java`, `JavaScript`, `Python`, `Ruby`, `Qt`, Microsoft's `.NET Framework`, and `XML Schema`.
