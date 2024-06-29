# Bugs to report to neovim
- [ and ] marks are not always correct
    ```
    - gUw => check `[ and `] => this is correct
    - yw => check `[ and `] => bug: `] is one character to the right
    - insert text => check `[ and `] => bug: `] is one character to the right
    ```

- Default neovim colorscheme
    - Causes NonText highlight group (and linked Whitespace highlight group ) to "disappear" inside Visual selection.
    - StatusLineNC highlight group background is same as CursorLine. StatusLineNC background is probably better as being same as Visual

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

# Requests to make to vim
- Pasting non-whole lines with `p` or `P` should keep the cursor at the beginning of the pasted text since `gp` already puts it on the other side.
- Jumping to opening or closing brackets from inside a bracket pair should work for all types of brackets including:
    - [[
    - ]]
    - [<
    - ]>

- Make jumplist updates consistent with `'` mark updates
    - The jumplist is only updated if the command is a "jump" command AND the cursor moves into a new line
    - The `'` mark is updated if the command is a "jump" command, regardless of whether the cursor moves into a new line or not

- When 'linebreak' and 'wrap' are set, visually selecting a wrapped line highlights empty space (no text at all there, not even white space, not even a newline character) at the end of a screen line.

# Requests to make to coc.nvim
- Override these commands with LSP
    - ]m
    - ]M
    - [m
    - [M
