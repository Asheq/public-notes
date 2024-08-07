# List of Text Objects
- word
- WORD
+ quotes:
    - "
    - '
    - `` ` ``
- sentence
- paragraph
- section
+ brackets:
    - `{`
    - `(`
    - `[`
    - `<`
- tag (example: `<div>...</div>`)

# List of Text Object Motions
+ word
    - `w`
    - `e`
    - `b`
    - `ge`
+ WORD
    - `W`
    - `E`
    - `B`
    - `gE`
+ quotes
+ sentence
    - `)`
    - `(`
+ paragraph
    - `}`
    - `{`
+ section
    - `[[`
    - `]]`
+ brackets
    + `{`
        - `[{`
        - `]}`
    + `(`
        - `[(`
        - `])`
    + `[`
    + `<`
+ tag

# List of Text Object Selections
+ word
    - `iw`
    - `aw`
+ WORD
    - `iW`
    - `aW`
+ quotes
    + "
        - `i"`
        - `a"`
    + '
        - `i'`
        - `a'`
    + `` ` ``
        - `` i` ``
        - `` a` ``
+ sentence
    - `is`
    - `as`
+ paragraph
    - `ip`
    - `ap`
+ section
+ brackets
    + `{`
        - `i{` or `iB`
        - `a{` or `aB`
    + `(`
        - `i(` or `ib`
        - `a(` or `ab`
    + `[`
        - `i[`
        - `a[`
    + `<`
        - `i<`
        - `a<`
+ tag
    - `it`
    - `at`

# Peculiarities of Text Object Selections
+ word
+ WORD
+ quotes
    - Opening and closing quotes need to be on the same line for vim to consider the text object
+ sentence
+ paragraph
+ section
+ brackets
    + For "inner" bracket text objects
        - If the opening bracket is followed immediately by a newline, the newline is not included
        - If the closing bracket is preceded immediately by whitespace preceded immediately by a newline, the whitespace is not included (but the newline is)
+ tag
