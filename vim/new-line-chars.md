# Character primitives
## Line Feed
- Abbreviation: LF
- Code: U+000A
- Decimal: 10
- Key: CTRL-J
    - Derivation: 10 + 96 = 106 => j

## Carriage Return
- Abbreviation: CR
- Code: U+000D
- Decimal: 13
- Key: CTRL-M
    - Derivation: 13 + 96 = 109 => m

# Newline character sequence
- Alternative names:
    - Newline
    - Line Ending
    - End of Line (EOL)
    - Line Break
- Representation on operating systems:
    - Unix/Mac: LF
    - Windows: CR+LF

# In Vim
## Mappings
- Represents key-press for inserting a newline:
    - <Return>
    - <Enter>
    - Works, but is technically a misnomer
        - <CR>
    - Does not work:
        - <EOL>
        - <NL>
## Search patterns
    - Search side:
        - \n matches Newline
        - \r matches Carriage Return
    - Substitute side:
        - \r inserts Newline
        - \n inserts Null
