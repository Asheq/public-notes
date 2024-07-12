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
