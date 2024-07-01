# Bugs to report to (neo)vim
- Returning to a buffer (from another buffer) where your cursor was on a line between the first line and middle line of the second page, vim attempts to scroll that line to the bottom of the window rather than to the center as usual.

- [ and ] marks are not always correct
    ```
    - gUw => check `[ and `] => this is correct
    - yw => check `[ and `] => bug: `] is one character to the right
    - insert text => check `[ and `] => bug: `] is one character to the right
    ```
- Default neovim colorscheme
    - Causes NonText highlight group (and linked Whitespace highlight group ) to "disappear" inside Visual selection.
    - StatusLineNC highlight group background is same as CursorLine. StatusLineNC background is probably better as being same as Visual

- `<<<` characters for wrapped line are not customizable
    - listchars extends/precedes and fillchars lastline are confused
        - top left side behaves differently than bottom right in terms of which character option is used and how many times it is displayed

- zt zb zz does not work in wrapped line, even with smoothscroll on

- H M L does not work with wrapped lines, especially when a wrapped line is only partially in view

- Moving cusor into wrapped lines that are partially visible behaves strangely and inconsistently, coming into it from bottom side and top side

- C-b from very bottom of buffer does not overlap lines correctly

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

# Requests to make to (neo)vim
- Pasting non-whole lines with `p` or `P` should keep the cursor at the beginning of the pasted text since `gp` already puts it on the other side.
- Jumping to opening or closing brackets from inside a bracket pair should work for all types of brackets including:
    - [[
    - ]]
    - [<
    - ]>

- Make jumplist updates consistent with `'` mark updates
    - The jumplist is only updated if the command is a "jump" command AND the cursor moves into a new line
    - The `'` mark is updated if the command is a "jump" command, regardless of whether the cursor moves into a new line or not

- When 'linebreak' and 'wrap' are set, visually selecting a wrapped line highlights empty space (no text at all there, not even whitespace, not even a newline character) at the end of a screen line.

# Requests to make to coc.nvim
- Override these commands with LSP
    - ]m
    - ]M
    - [m
    - [M
