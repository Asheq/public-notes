# (neo)vim
- `[` and `]` marks are not always correct
```
    - gUw => check `[ and `] => this is correct
    - yw => check `[ and `] => bug: `] is one character to the right
    - insert text => check `[ and `] => bug: `] is one character to the right
```

- Visual selection includes "empty" space
    - Repro steps
        - insert text: '    thisisaverylongword    anotherverylongword    anotherone     lastonethatislong'
        - set linebreak
        - set breakindent
        - set list
        - set listchars=space:-,eol:$
        - set showbreak=>
        - Decrease window width to make text wrap
        - visually select line entire line `0v$` or `V`

- [neovim only] Default neovim colorscheme
    - Causes NonText highlight group (and linked Whitespace highlight group ) to "disappear" inside Visual selection.
    - StatusLineNC highlight group background is same as CursorLine. StatusLineNC background is probably better as being same as Visual

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
