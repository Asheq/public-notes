Below, `N` is a number and `range` is a line range (see `:help :range`)

# In Normal mode
	[N]>>
		Indent N lines once

# In Visual mode
	[N]>
		Indent selected lines N times

# In Command line mode
	:[range]>
		Indent lines in range once
	:[range]>>
		Indent lines in range twice
	:> N
		Indent N lines once
	:>> N
		Indent N lines twice
