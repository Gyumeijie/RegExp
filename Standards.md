# Standards

The IEEE POSIX standard has three sets of compliance: **BRE** (Basic Regular Expressions), **ERE** (Extended Regular Expressions), and ~~**SRE**~~ (Simple Regular Expressions, but is deprecated).

BRE and ERE **work together**. ERE adds `?`, `+`, and `|`, and it removes the need to escape the metacharacters `( )` and `{ }`, which are required in BRE. 

BRE and ERE provide a "standard" which has since been adopted as the default syntax of many tools, where the choice of BRE or ERE modes is usually a supported option. For example, `GNU grep` has the following options: "grep -E" for **ERE**, and "grep -G" for **BRE** (the default), and "grep -P" for **Perl regexes**. 

Perl regexes have become a ***de facto standard***, having a rich and powerful set of atomic expressions. Perl has no "basic" or "extended" levels. Because of its expressive power and (relative) ease of reading, many other utilities and programming languages have adopted syntax similar to Perl's—for example, `Java`, `JavaScript`, `Python`, `Ruby`, `Qt`, Microsoft's `.NET Framework`, and `XML Schema`.
