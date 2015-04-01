# parsed

Parsed (pronounced par-séd) is a suite of shell scripts to simplify parsing from the Unix shell.
It improves the classic sed program by incorporating ideas from Haskell's popular [parsec](https://hackage.haskell.org/package/parsec) library.
In particular, the Unix pipe operator `|` corresponds exactly to Haskell's Applicative bind `*>`.
The resulting syntax is both intuitive and powerful.
The original syntax used by sed can match only regular languages;
but our improved syntax can match any context sensitive language.

For example, the following one liner creates a parser for matching balanced parenthesis.
```
$ parens() { choice "$1" "match '(' | parens \"$1\" | match ')'"; }
```
For more examples and a detailed tutorial, please see our [SIGBOVIK2015 paper](https://github.com/mikeizbicki/parsed/raw/master/sigbovik2015/paper.pdf).
