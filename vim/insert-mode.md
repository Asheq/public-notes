# Interesting keys in Insert mode
- `<S-Left>`        cursor one word back (like "b" command)
- `<S-Right>`       cursor one word forward (like "w" command)

- `CTRL-]`          trigger abbreviation, without inserting a character

- `CTRL-A`          insert previously inserted text

- `CTRL-G j`        cursor one line down, insert start column
- `CTRL-G CTRL-J`   cursor one line down, insert start column
- `CTRL-G k`        cursor one line up, insert start column
- `CTRL-G CTRL-K`   cursor one line up, insert start column

# Notes
- Many keys in Insert mode close the current undo sequence, including `<Left>` and `<Right>`. In this way, they act like `CTRL-G u`. For all such keys, see `:h ins-special-special`. The text inserted since the last time a key from this set was pressed is placed in the `.` register (and is thus used by `CTRL-A` in Insert mode) and becomes the change that is repeated with `.` repeat command in Normal mode. Specifically, the change is saved as a text insertion with the `i` command.
    - Note that these are separate concepts:
        - Undo sequences and associated `u` / `CTRL-R` commands
        - The `.` register and associated `CTRL-A` Insert mode command
        - The Normal mode `.` repeat command

- Abbreviations
    - An abbreviation is triggered when:
        - A character that is not part of `'iskeyword'` is inserted
            - This usually includes characters like:
                - ` ` (Space character)
                - `/`
                - `.`
                - Newline character (whatever character is inserted by the `<Enter>` key)
        - Insert mode is exited with `<Esc>` or `CTRL-[`
        - `CTRL-]` is pressed
    - An abbreviation is not triggered when:
        - Insert mode is exited with `CTRL-C`
        - `CTRL-V {char}` is pressed even if `{char}` is not a part of `'iskeyword'`

- Press `CTRL-J` (instead of `<Enter>`) to insert a newline without having the `<Enter>` key get "eaten" by the coc.nvim PUM when it is visible

- CTRL-V
    - After pressing `CTRL-V`, you can type numbers to enter the code point of the character to insert
        **first char**       **mode**             **max nr of chars**     **max value**
        (none)           decimal          3                   255
        o or O           octal            3                   377      (255)
        x or X           hexadecimal      2                   ff       (255)
        u                hexadecimal      4                   ffff     (65535)
        U                hexadecimal      8                   7fffffff (2147483647)

        - You can "short-circuit" out of entering the code point by entering an invalid key, including a <Space>

- Hard-wrapping
    - '`'textwidth` and `'wrapmargin'` cause automatic hard-wrapping (a.k.a. line breaking a.k.a. insertion of newline characters) when typing in Insert mode
        - Lines are only broken automatically while typing in Insert mode, not in Replace mode, or pasting in Normal mode
        - The option `'formatoptions'` has some flags that change how line breaking works

- Tabs and shifting
    - The (screen) column width of a Tab character is variable -- the end column of the character is the column of the next tab stop. Tab stops are located on columns that are multiples of the `'tabstop'` option value.
    - The `<Tab>` key normally inserts a Tab character. However, with `'expandtab' `set, the `<Tab>` key will insert the number of Space characters required to move the cursor to just past the next tab stop (at the time the key is pressed).
    - It is rare for `'shiftwidth'` to be set to non-zero and differ from `'tabstop',` but it is possible.
    - `>>` always adds `'shiftwidth'` columns of white space at the beginning of the line (regardless of what white space is already there). The resulting characters at the beginning of the line will be a combination of Tabs and Spaces, depending on the value of `'expandtab'`:
            - With `'expandtab'` set, only Spaces will be used
            - With `'expandtab'` not set, as many Tabs as possible will be used and then Spaces will be used to fill the remainder if necessary. Note that there can only be a remainder if `'tabstop'` and `'shiftwidth'` differ or if there were already some extra Spaces at the begging of the line.
        White space at the beginning of the line will be COMPLETELY replaced if needed.
    - `'smarttab'` causes a `<Tab>` key at the beginning of the line to take `'shiftwidth'` into consideration instead of `'tabstop'`. It will insert whatever white space characters are required to move the cursor to the next column that is a multiple of 'shiftwidth'. Whether just Spaces are used or Tabs are also used depends on the value of `'expandtab'`. `<BS>` normally only deletes one character, but `'smarttab'` makes it so it deletes up to the previous tab stop at the beginning of the line.

# Interesting keys to enter Insert mode
`gI`
`gi`

# Automatic indenting for new lines
When creating a new line (either by hitting `<Enter>` in Insert mode or by entering Insert mode with `o` or `O`), indenting can be automatically calculated and inserted if certain options are set. These options include 'autoindent', 'smartindent', 'cindent', etc. Learn more from `:h indent.txt`
