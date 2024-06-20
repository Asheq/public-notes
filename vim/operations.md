# OPERATIONS with MOTIONS
- An OPERATION using a LINEWISE MOTION affects all the characters on the start line and end line (and on all the lines between them), including the newlines. An OPERATION using a CHARWISE MOTION affects just the start character and end character (and all the characters between them).
	- Example LINEWISE MOTIONS
		- j
		- k
		- gg
		- G
	- Example CHARWISE MOTIONS
		- e, E
		- w, W
		- b, B
		- (
		- )
        - gj
        - gk

- Each CHARWISE MOTION is either INCLUSIVE or EXCLUSIVE. An OPERATION using an EXCLUSIVE MOTION does not include the last character (towards the end of the buffer) that was moved over.
	- Example INCLUSIVE MOTIONS
		- e, E
	- Example EXCLUSIVE MOTIONS
		- w, W
		- b, B
        - (
        - )
        - gj
        - gk

- All LINEWISE MOTIONS are INCLUSIVE. In other words, an OPERATION using a LINEWISE MOTION includes the last line (towards the end of the buffer) that was moved over.

# OPERATIONS with TEXT OBJECTS
- An OPERATION using a LINEWISE TEXT OBJECT affects all the characters on the start line and end line (and on all the lines between them), including the newlines. An OPERATION using a CHARWISE TEXT OBJECT affects just the start character and end character (and all the characters between them).
	- Example LINEWISE TEXT OBJECTS:
		- ip
		- ap
	- Example CHARWISE TEXT OBJECTS:
		- iw
		- aw
		- is
		- as

- All TEXT OBJECTS are INCLUSIVE. An OPERATION using a TEXT OBJECT includes the last character or line (towards the end of the buffer) that was part of the TEXT OBJECT.

- When a TEXT OBJECT is used in Visual mode, you are changed to or left in either Visual LINEWISE mode or Visual CHARWISE mode to match the TEXT OBJECT.

# Force change behavior of OPERATION
You can force change the behavior of an OPERATION by entering v or V just after the OPERATOR
    - v
        - if MOTION is LINEWISE, make it CHARWISE (EXCLUSIVE)
        - if MOTION is CHARWISE, toggle INCLUSIVE/EXCLUSIVE
        - if TEXT OBJECT is LINEWISE, make it LINEWISE EXCLUSIVE
        - if TEXT OBJECT is CHARWISE, make it CHARWISE EXCLUSIVE
    - V
        - if MOTION is CHARWISE, make it LINEWISE
        - if TEXT OBJECT is CHARWISE, make it LINEWISE
    - CTRL-V
        - if MOTION is CHARWISE or LINEWISE, make it BLOCKWISE (with the corners of the block defined by the cursor positions before and after)

*Examples*:
- `dj` - Deletes two lines.
- `dvj` - Deletes from the cursor position until the character below the cursor.
- `d<C-v>j` - Deletes the character under the cursor and the character below the cursor.

# Additional Notes
- Doubling an OPERATOR means perform an OPERATION on the current line, i.e. use the current line (including the new line at the end) as the TEXT OBJECT

- `cw` and `cW` are special OPERATIONS: the `w` is treated like an `e`

- There are two general exceptions to how MOTIONS work: http://vimdoc.sourceforge.net/htmldoc/motion.html#exclusive

- Confusing NOTE: When text that is operated on is placed in a register (e.g., via a yank or delete), sometimes it includes a newline but this is not always related to anything else, e.g., whether the MOTION or TEXT OBJECT is LINEWISE/CHARWISE or INCLUSIVE/EXCLUSIVE. This is confusing. Example: `yas` when there is only one sentence on the line vs when there are multiple sentences on the line.
