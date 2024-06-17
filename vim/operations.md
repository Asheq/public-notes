# Operations with MOTIONS
- An OPERATION using a MOTION either affects the entire start and end lines OR just the characters based on whether the MOTION that is used is linewise or charwise (with some exceptions)
	- example linewise MOTIONS
		- j
		- k
		- gg
		- G
	- example charwise MOTIONS
		- e, E
		- w, W
		- b, B
		- (
		- )
        - gj
        - gk
		- { with exception when ???
		- } with exception when starting on first non-blank of line and ???

- Each charwise MOTION is either inclusive or exclusive. An OPERATION using an exclusive MOTION does not include the last character (towards the end of the buffer) that was moved over. There are two general exceptions: http://vimdoc.sourceforge.net/htmldoc/motion.html#exclusive
	- example inclusive MOTIONS
		- e, E
	- example exclusive MOTIONS
		- w, W
		- b, B
        - (
        - )
        - gj
        - gk
        - { with exception when ???
        - } with exception when ???

- All linewise MOTIONS are inclusive. In other words, an OPERATION using a linewise MOTION includes the last line (towards the end of the buffer) that was moved over.

# Operations with TEXT OBJECT
- An OPERATION using a TEXT OBJECT either affects whole lines or characters based on whether the TEXT OBJECT that is used is linewise or charwise. When a TEXT OBJECT is used in Visual mode, you are changed to or left in either Visual linewise mode or Visual charwise mode depending on whether the TEXT OBJECT is linewise or charwise.
	- example linewise TEXT OBJECTS:
		- ip
		- ap
	- example charwise TEXT OBJECTS:
		- iw
		- aw
		- is
		- as
- All TEXT OBJECTS are inclusive. An OPERATION using a TEXT OBJECT includes the last character or line (towards the end of the buffer) that was part of the TEXT OBJECT.

# Force change behavior or OPERATION
You can force change the behavior of an OPERATION by entering v or V just after the operator
    - v
        - if MOTION is linewise, make it charwise (exclusive)
        - if MOTION is charwise, toggle inclusive/exclusive
        - if TEXT OBJECT is charwise, make it charwise exclusive
        - if TEXT OBJECT is linewise, make it linewise exclusive
    - V
        - if MOTION is charwise, make it linewise
        - if TEXT OBJECT is charwise, make it linewise
    - CTRL-V

*Examples*:
- `dj` - deletes two lines.
- `dvj` - deletes from the cursor position until the character below the cursor.
- `d<C-v>j` - deletes the character under the cursor and the character below the cursor.

# Additional Notes
- Doubling an OPERATOR means perform an OPERATION on the current line, i.e. use the current line (including the new line at the end) as the TEXT OBJECT

- `cw` and `cW` are special OPERATIONS: the `w` acts like an `e`

- Confusing NOTE: When text that is operated on is placed in a register (e.g., via a yank or delete), sometimes it includes a newline but this is not always related to anything else, e.g., whether the MOTION or TEXT OBJECT is linewise/charwise or inclusive/exclusive. This is confusing. Example: `yas` when there is only one sentence on the line vs when there are multiple sentences on the line.
