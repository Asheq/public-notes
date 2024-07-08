# Interesting commands
- CTRL-A		Insert previously inserted text.
- CTRL-]		Trigger abbreviation, without inserting a character.
- CTRL-G j	cursor one line down, insert start column    *i_CTRL-G_j*
- CTRL-G CTRL-J	cursor one line down, insert start column    *i_CTRL-G_CTRL-J*
- CTRL-G k	cursor one line up, insert start column	     *i_CTRL-G_k*
- CTRL-G CTRL-K	cursor one line up, insert start column	     *i_CTRL-G_CTRL-K*
- <S-Left>	cursor one word back (like "b" command)	     *i_<S-Left>*
- <S-Right>	cursor one word forward (like "w" command)   *i_<S-Right>*
- <Home>		cursor to first char in the line	     *i_<Home>*
- <End>		cursor to after last char in the line	     *i_<End>*
- <C-Home>	cursor to first char in the file	     *i_<C-Home>*
- <C-End>		cursor to after last char in the file	     *i_<C-End>*
- <PageUp>	move window one page up			     *i_<PageUp>*
- <PageDown>	move window one page down		     *i_<PageDown>*
- <Insert>	Toggle between Insert and Replace mode.

# Notes
- Many keys in Insert mode create a new undo point, including `<Left>` and `<Right>`. For more, see `:h ins-special-special`. Pressing undo once will only undo changes made since the last undo point. This also affects what change is repeated with `.` in Normal mode and the text inserted with `<C-a>` in Insert mode.
