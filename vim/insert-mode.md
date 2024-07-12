# Interesting commands
- CTRL-A          Insert previously inserted text.
- CTRL-]          Trigger abbreviation, without inserting a character.
- CTRL-G j        cursor one line down, insert start column
- CTRL-G CTRL-J   cursor one line down, insert start column
- CTRL-G k        cursor one line up, insert start column
- CTRL-G CTRL-K   cursor one line up, insert start column
- <S-Left>        cursor one word back (like "b" command)
- <S-Right>       cursor one word forward (like "w" command)
- <Home>          cursor to first char in the line
- <End>           cursor to after last char in the line
- <C-Home>        cursor to first char in the file
- <C-End>         cursor to after last char in the file
- <PageUp>        move window one page up
- <PageDown>      move window one page down
- <Insert>        Toggle between Insert and Replace mode.

# Notes
- Many keys in Insert mode create a new undo point, including `<Left>` and `<Right>`. For more, see `:h ins-special-special`. Pressing undo once will only undo changes made since the last undo point. This also affects what change is repeated with `.` in Normal mode and the text inserted with `<C-a>` in Insert mode.
- `CTRL-]` (not to be confused with `CTRL-[`) triggers an abbreviation without requiring inserting another character (like a space or newline)
- `CTRL-C` does not trigger abbreviations, whereas `<Esc>` and `CTRL-[` do
- Use `CTRL-V {char}` to enter a `{char}` without triggering an abbreviation after text that would normally trigger an abbreviation
- Use `CTRL-V <Tab>` to avoid expanding to spaces when `expandtab` is set or to avoid executing a mapping (e.g., to navigate through a coc.nvim PUM when it is visible)
- Use `CTRL-J` (instead of `<Enter`) to enter a newline without having the `<Enter>` eaten in order to close the PUM when it is visible
- After pressing `CTRL-V`, you can type numbers to enter the code point of the character to insert
    **first char**       **mode**             **max nr of chars**     **max value**
    (none)           decimal          3                   255
    o or O           octal            3                   377      (255)
    x or X           hexadecimal      2                   ff       (255)
    u                hexadecimal      4                   ffff     (65535)
    U                hexadecimal      8                   7fffffff (2147483647)

    - You can "short-circuit" out of entering the code point by entering an invalid character (including a space)
- `textwidth` and `wrapmargin` cause automatic hard-wrapping (a.k.a. line breaking a.k.a. insertion of newline characters) when typing in Insert mode
    - Lines are only broken automatically while typing in Insert mode, not in Replace mode, or pasting in Normal mode.
    - The option formatoptions has some flags that change how line breaking works
- The (screen) column width of a Tab character is variable -- the end column of the character is the column of the next tab stop. Tab stops are located on columns that are multiples of the `'tabstop'` option value.
- The `<Tab>` key normally inserts a Tab character. However, with `'expandtab' `set, the `<Tab>` key will insert the number of Space characters required to move the cursor to just past the next tab stop (at the time the key is pressed).
- It is rare for `'shiftwidth'` to be set to non-zero and differ from `'tabstop',` but it is possible.
- `>>` always adds `'shiftwidth'` columns of white space at the beginning of the line (regardless of what white space is already there). The resulting characters at the beginning of the line will be a combination of Tabs and Spaces, depending on the value of `'expandtab'`:
        - With `'expandtab'` set, only Spaces will be used
        - With `'expandtab'` not set, as many Tabs as possible will be used and then Spaces will be used to fill the remainder if necessary. Note that there can only be a remainder if `'tabstop'` and `'shiftwidth'` differ or if there were already some extra Spaces at the begging of the line.
    White space at the beginning of the line will be COMPLETELY replaced if needed.
- `'smarttab'` causes a `<Tab>` key at the beginning of the line to take `'shiftwidth'` into consideration instead of `'tabstop'`. It will insert whatever white space characters are required to move the cursor to the next column that is a multiple of 'shiftwidth'. Whether just Spaces are used or Tabs are also used depends on the value of `'expandtab'`. `<BS>` normally only deletes one character, but `'smarttab'` makes it so it deletes up to the previous tab stop at the beginning of the line.
