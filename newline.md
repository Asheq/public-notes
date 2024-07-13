# Alternative names
- Line ending
- End of line (EOL)
- Line break

# Representation
## In a text buffer or file as a character or character sequence
- Unix/Mac: LF
- Windows: CR+LF
- Other: ?
### Character details
#### Line feed
- Abbreviation: LF
- Unicode Code: U+000A
    - Decimal: 10
- Key: CTRL-J
    - Derivation: 10 + 96 = 106 => j
- Escape sequence: \n
#### Carriage return
- Abbreviation: CR
- Unicode Code: U+000D
    - Decimal: 13
- Key: CTRL-M
    - Derivation: 13 + 96 = 109 => m
- Escape sequence: \r
## In Vim
### In search patterns
- Search side:
    - `\n` matches newline
    - `\r` matches carriage return
- Substitute side:
    - `\n` inserts null
    - `\r` inserts newline
### In mappings
- These represent keys that would normally insert a newline character [sequence] in Insert mode
    - `<Enter>`
    - `<Return>`
    - `<CR>`
        - Misnomer because a carriage return character alone is not equivalent to a newline on all systems
    - `<EOL>`
        - Does not work
    - `<NL>`
        - Does not work
