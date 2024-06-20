# Bugs to report to neovim
- [ and ] marks are not always correct
    ```
    - gUw => check `[ and `] => this is correct
    - yw => check `[ and `] => bug: `] is one character to the right
    - insert text => check `[ and `] => bug: `] is one character to the right
    ```

- Default neovim colorscheme causes NonText highlight group (and linked Whitespace highlight group ) to "disappear" inside visual selection.


# Requests to make to neovim
- Jumping to opening or closing brackets from inside a bracket pair should work for all types of brackets including:
    - [[
    - ]]
    - [<
    - ]>

- Make jumplist updates consistent with `'` mark updates
    - The jumplist is only updated if the command is a "jump" command AND the cursor moves into a new line
    - The `'` mark is updated if the command is a "jump" command, regardless of whether the cursor moves into a new line or not

# Requests to make to coc.nvim
- Override these commands with LSP
    - ]m
    - ]M
    - [m
    - [M
