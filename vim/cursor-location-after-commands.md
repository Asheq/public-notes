# Exiting INSERT MODE
- Cursor "grows" to left

# Using TEXT OBJECT in VISUAL MODE
- Visual Mode
    - If you start in LINEWISE VISUAL MODE but use a CHARWISE TEXT OBJECT (or vice versa), neovim will switch the VISUAL MODE to match the TEXT OBJECT before updating the selection
        - Special case: If you start in CHARWISE VISUAL MODE with the selection spanning multiple lines and you use a LINEWISE TEXT OBJECT, neovim will switch back to CHARWISE VISUAL MODE after updating the selection.
- Selection Expansion
    - If you start with the VISUAL selection width equal to one (either one character or one line, depending on the VISUAL MODE), neovim will expand the selection on both sides to select the entire TEXT OBJECT
    - If you start with the VISUAL selection width equal to more than one, neovim will expand the selection on one side only - the side on which the cursor is
        - Special case: If you use a BLOCK TEXT OBJECT, neovim will always expand the selection on both sides to select the entire TEXT OBJECT
- Cursor Location
    - When expanding on both sides, neovim leaves the cursor at the "ENDMOST" edge of the TEXT OBJECT
        - If CHARWISE, cursor is left on the RIGHTMOST character
        - If LINEWISE, cursor is left on the BOTTOMMOST line
    - When expanding only on one side, neovim leaves the cursor on whichever edge was expanded to
        - If CHARWISE, put cursor on either LEFTMOST or RIGHTMOST character
        - If LINEWISE, put cursor on either TOPMOST or BOTTOMMOST line
    - When expanding in VISUAL LINEWISE MODE, put cursor on first character of whichever line the cursor is left on

# Performing an OPERATION
- After an OPERATION, the cursor moves to the start character or start line (sometimes preserving the column) of operated text
    - Exceptions: Some commands do something else. Examples:
        - `gw`: Keeps the cursor in place
        - `gq`: Moves the cursor to the first non-blank of the last formatted line

# PASTING
- p and P
    - When PASTING less than one line
        - The cursor is left at the last character of the pasted text (STRANGE)
    - When PASTING more than one line
        - And the pasted text is not whole lines (i.e., there is no newline character at the end of the register contents)
            - The cursor is left at the first character of the pasted text
        - And the pasted text is whole lines (i.e., there is a newline character at the end of the register contents)
            - The cursor is left at the first non-whitespace character of the first line of the pasted text

- gp an gP
    - When PASTING less than one line
        - The cursor is left one character after the last character of the pasted text
    - When PASTING more than one line
        - And the pasted text is not whole lines (i.e., there is no newline character at the end of the register contents)
            - The cursor is left one character after the last character of the pasted text
        - And the pasted text is whole lines (i.e., there is a newline character at the end of the register contents)
            - The cursor is left at the first character of the line after the last line of the pasted text
