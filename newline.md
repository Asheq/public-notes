# Alternative names
- Line ending
- End of line (EOL)
- Line break

# Representation
## Using a character a character sequence
- Unix/Mac: LF
- Windows: CR+LF
- Other: ?
## Character details
### Line Feed
- Abbreviation: LF
- Code: U+000A
- Decimal: 10
- Key: CTRL-J
    - Derivation: 10 + 96 = 106 => j
- Escape sequence: \n
### Carriage Return
- Abbreviation: CR
- Code: U+000D
- Decimal: 13
- Key: CTRL-M
    - Derivation: 13 + 96 = 109 => m
- Escape sequence: \r
## In Vim
### In Mappings
- Works:
    - `<Return>`
    - `<Enter>`
    - `<CR>`
        - Misnomer because a carriage return is not a newline on all systems
- Does not work:
    - `<EOL>`
    - `<NL>`
### In Search patterns
- Search side:
    - `\n` matches newline
    - `\r` matches carriage return
- Substitute side:
    - `\n` inserts null
    - `\r` inserts newline
