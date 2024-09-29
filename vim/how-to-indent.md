# In Normal mode
    `>{motion}`
        Indent `{motion}` LINES once
    `[count]>>`
        Indent `[count]` LINES once

# In Visual mode
    `{Visual}[count]>`
        Indent selected lines `[count]` TIMES

# In Command-line mode
    `:> {count}`
        Indent `{count}` LINES once
    `:>>> {count}`
        Indent `{count}` LINES thrice
    `:[range]>`
        Indent lines in RANGE once
    `:[range]>>>`
        Indent lines in RANGE thrice
