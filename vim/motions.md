# List of Motions
Motion            | Linewise (L) or Charwise (C)          | Inclusive (I) or Exclusive (E)
:---:             | :---:                                 | :---:
`j`               | L                                     | N/A
`k`               | L                                     | N/A
`-`               | L                                     | N/A
`+`               | L                                     | N/A
`_`               | L                                     | N/A
`G`               | L                                     | N/A
`gg`              | L                                     | N/A
`H`               | L                                     | N/A
`M`               | L                                     | N/A
`L`               | L                                     | N/A
`'{mark}`         | L                                     | N/A
`:[range]`        | L                                     | N/A
`$`               | C                                     | I
`g_`              | C                                     | I
`g$`              | C                                     | I
`f{char}`         | C                                     | I
`t{char}`         | C                                     | I
`{count}%`        | C                                     | I
`e`               | C                                     | I
`E`               | C                                     | I
`ge`              | C                                     | I
`gE`              | C                                     | I
`h`               | C                                     | E
`l`               | C                                     | E
`0`               | C                                     | E
`^`               | C                                     | E
`g0`              | C                                     | E
`g^`              | C                                     | E
`gm`              | C                                     | E
`|`              | C                                     | E
`F{char}`         | C                                     | E
`T{char}`         | C                                     | E
`gk`              | C                                     | E
`gj`              | C                                     | E
`[count]go`       | C                                     | E
`w`               | C                                     | E
`W`               | C                                     | E
`b`               | C                                     | E
`B`               | C                                     | E
`)`               | C                                     | E
`(`               | C                                     | E
`{`               | C                                     | E
`}`               | C                                     | E
`]}`              | C                                     | E
`[{`              | C                                     | E
`])`              | C                                     | E
`[(`              | C                                     | E
`]m`              | C                                     | E
`[m`              | C                                     | E
`]M`              | C                                     | E
`[M`              | C                                     | E
`]*` or `]/`      | C                                     | E
`[*` or `[/`      | C                                     | E
`` `{mark}``      | C                                     | E
`]]`              | C                                     | E
`[[`              | C                                     | E
`][`              | C                                     | E
`[]`              | C                                     | E
`:call FindEnd()` | C                                     | E

# Other remarks
- Jump list updates vs `'` mark updates
    - The jump list is only updated if the command is a "jump" command AND the cursor moves into a new line
    - The `'` mark is updated if the command is a "jump" command, regardless of whether the cursor moves into a new line or not
