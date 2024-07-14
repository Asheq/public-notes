# (neo)vim
- Shouldn't the text that is stored inside a register when recording a macro have the same syntax as the left-hand side of a mapping?
- [neovim only] The value of `shiftwidth` is used where it should not be
    - Setup:
        ```
        - :set tabstop=8
        - :set smarttab
        - :set shiftwidth=3
        - :set expandtab (does not matter actually)
        - :set list
        - :set listchars=tab:>\ ,space:*
        ```
    - Pressing the `<Tab>` key BEFORE the first non-white space character on the line should insert white space up to the next multiple of `'shiftwidth'`
        - Both vim and neovim do this
    - Pressing the `<Tab>` key AFTER the first non-white space character on the line should insert white space up to the next multiple of `'tabstop'`
        - Vim does this. Neovim does not.

- `[` and `]` marks are not always correct
```
    - gUw => check `[ and `] => this is correct
    - yw => check `[ and `] => bug: `] is one character to the right
    - insert text => check `[ and `] => bug: `] is one character to the right
```

- Visual selection includes "empty" space
    - Reproduction steps
        ```
        - insert text: '    thisisaverylongword    anotherverylongword    anotherone     lastonethatislong'
        - set linebreak
        - set breakindent
        - set list
        - set listchars=space:-,eol:$
        - set showbreak=>
        - Decrease window width to make text wrap
        - visually select line entire line `0v$` or `V`
        ```
- [neovim only] Default neovim color scheme
    - Causes `NonText` highlight group (and linked `Whitespace` highlight group ) to "disappear" inside Visual selection.
    - `StatusLineNC` highlight group background is same as `CursorLine`. `StatusLineNC` background is probably better as being same as Visual

- Pasting non-whole lines with `p` or `P` should keep the cursor at the beginning of the pasted text since `gp` and `gP` already puts it on the other side.

- Jumping to opening or closing brackets from inside a bracket pair should work for all types of brackets including:
    - [[
    - ]]
    - [<
    - ]>

# coc.nvim
- Override these commands with LSP
    - ]m
    - ]M
    - [m
    - [M

# preservim/vim-markdown
- `CursorHold` autocommand seems to mess with the default column that a cursor goes to when entering a line
