# (neo)vim
- `<C-b>` from very bottom of buffer does not "overlap" lines correctly

- Moving cusor into wrapped lines that are partially visible behaves strangely and inconsistently, coming into it from bottom side and top side

- `zt` `zb` `zz` do not work as expected from inside a wrapped line, even with `smoothscroll` on

- `H` `M` `L` do not work as expected when wrapped lines are in view, especially when a wrapped line is only partially in view at the bottom or top

- [vim only] Returning to a buffer (from another buffer) where your cursor was on a line between the first line and middle line of the second page, vim attempts to scroll that line to the bottom of the window rather than to the center as usual.

- [neovim only] Default neovim colorscheme
    - Causes NonText highlight group (and linked Whitespace highlight group ) to "disappear" inside Visual selection.
    - StatusLineNC highlight group background is same as CursorLine. StatusLineNC background is probably better as being same as Visual

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

- Pasting non-whole lines with `p` or `P` should keep the cursor at the beginning of the pasted text since `gp` already puts it on the other side.

- Jumping to opening or closing brackets from inside a bracket pair should work for all types of brackets including:
    - [[
    - ]]
    - [<
    - ]>

- Make jumplist updates consistent with `'` mark updates
    - The jumplist is only updated if the command is a "jump" command AND the cursor moves into a new line
    - The `'` mark is updated if the command is a "jump" command, regardless of whether the cursor moves into a new line or not

# coc.nvim
- Override these commands with LSP
    - ]m
    - ]M
    - [m
    - [M
