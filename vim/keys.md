# Mappings

Below is a list of every key (and single-modifier key chord) on a standard QWERTY keyboard, grouped into categories, and represented the same way they would in a Vim key mapping. If pressing a key conventionally inserts a character with a visible glyph into a text buffer, then that character is used to represent the key in a mapping. If pressing a key does not conventionally insert a character with a visible glyph into the buffer, then an angle bracket syntax is used. This includes when:
    - A character with an invisible glyph is inserted: `<Space>`
    - A character with no glyph is inserted: `<C-a>`, `<Tab>`, `<Enter>`, 
    - No character is inserted: `<Left>`, `<BS>`

## Alphabet Keys:
- Alone
    - `a` `b` `c` `d` `e` `f` `g` `h` `i` `j` `k` `l` `m` `n` `o` `p` `q` `r` `s` `t` `u` `v` `w` `x` `y` `z`
- Shift
    - `A` `B` `C` `D` `E` `F` `G` `H` `I` `J` `K` `L` `M` `N` `O` `P` `Q` `R` `S` `T` `U` `V` `W` `X` `Y` `Z`
- Ctrl
    - `<C-a>` ...
- Alt
    - `<A-a>` ...
- Cmd
    - `<D-a>` ...

## Number Keys:
- Alone
    - `1` `2` `3` `4` `5` `6` `7` `8` `9` `0`
- Shift
    - `!` `@` `#` `$` `%` `^` `&` `*` `(` `)`
- Ctrl: 
    - `<C-1>` ...
- Alt:
    - `<A-1>` ...
- Cmd:
    - `<D-1>` ...

## Punctuation and Symbols:
- Alone
    - `` ` `` `-` `=` `[` `]` `\` `;` `'` `,` `.` `/`
- Shift
    - `` ~ `` `_` `+` `{` `}` `|` `:` `"` `<` `>` `?`
- Ctrl
    - `<C-=>` ...
- Alt
    - `<A-=>` ...
- Cmd
    - `<D-=>` ...

## Whitespace Keys:
- Alone
    - `<Space>` `<Tab>` `<Enter>` or `<Return>`
    - NOTE: `<Space>` normally inserts a character with an invisible glyph. `<Tab>` normally inserts a character with no glyph. `<Enter>` normally inserts a character (or two) with no glyphs.
- Shift
    - `<S-Space>` ...
- Ctrl
    - `<C-Space>` ...
- Alt
    - `<A-Space>` ...
- Cmd
    - `<D-Space>` ...

## Other Keys:
- Alone
    - `<BS>` `<Esc>` `<Insert>` `<Delete>`
- Shift
    - `<S-BS>` ...
- Ctrl
    - `<C-BS>` ...
- Alt
    - `<A-BS>` ...
- Cmd
    - `<D-BS>` ...

## Navigation Keys:
- Alone
    - `<Up>` `<Down>` `<Left>` `<Right>` `<Home>` `<End>` `<PageUp>` `<PageDown>`
- Shift
    - `<S-Up>` ...
- Ctrl
    - `<C-Up>` ...
- Alt
    - `<A-Up>` ...
- Cmd
    - `<D-Up>` ...

## Function Keys:
- Alone
    - `<F1>` `<F2>` `<F3>` `<F4>` `<F5>` `<F6>` `<F7>` `<F8>` `<F9>` `<F10>` `<F11>` `<F12>`

## Numeric Keypad:
- Alone
    - `<kPlus>` `<kMinus>` `<kMultipy>` `<kDivide>` `<kPoint>` `<kComma>` `<kEqual>` `<kEnter>` `<kUp>` `<kDown>` `<kLeft>` `<kRight>` `<kHome>` `<kEnd>` `<kOrigin>` `<kPageUp>` `<kPageDown>` `<kDel>` `<k0>` `<k1>` `<k2>` `<k3>` `<k4>` `<k5>` `<k6>` `<k7>` `<k8>` `<k8>`
    - NOTE: Some of these keys insert a character with a visible glyph, but since that character is already used to represent another key, Vim needs to use the angle bracket notation to represent these keys.
## Non Mappable Keys:
- (Caps Lock) (Print Screen) (Scroll Lock) (Pause/Break) (Num Lock)
- NOTE: These keys are never sent to Vim because they are consumed by the OS

# Macros

When saving keys that have been pressed (saving them into a register) while recording a macro, Vim does not represent the keys in the same syntax as Vim key mappings. Below is the same list as in the "# Mappings" section above but in this other syntax.

## Alphabet Keys:
- Alone
    - `a` `b` `c` `d` `e` `f` `g` `h` `i` `j` `k` `l` `m` `n` `o` `p` `q` `r` `s` `t` `u` `v` `w` `x` `y` `z`
- Shift
    - `A` `B` `C` `D` `E` `F` `G` `H` `I` `J` `K` `L` `M` `N` `O` `P` `Q` `R` `S` `T` `U` `V` `W` `X` `Y` `Z`
- Ctrl
    - `€üA` ...
    - `` ...
- Alt
    - `€üa` ...
    - `a` ...
- Cmd
    - `€ü€a` ...

## Number Keys:
- Alone
    - `1` `2` `3` `4` `5` `6` `7` `8` `9` `0`
- Shift
    - `!` `@` `#` `$` `%` `^` `&` `*` `(` `)`
- Ctrl: 
    - `€ü3` ...
- Alt:
    - `€ü3` ...
    - `3` ...
- Cmd:
    - `???`

## Punctuation and Symbols:
- Alone
    - `` ` `` `-` `=` `[` `]` `\` `;` `'` `,` `.` `/`
- Shift
    - `` ~ `` `_` `+` `{` `}` `|` `:` `"` `<` `>` `?`
- Ctrl
    - `€ü.` ...
- Alt
    - `€ü.` ...
    - `.` ...
- Cmd
    - `€ü€.` ...

## Whitespace Keys:
### Space
    - Alone
        - ` `
    - Shift
        - ` `
    - Ctrl
        - `€ü `
    - Alt
        - `€ü `
        - ` `
    - Cmd
        - `€ü€ `

### Tab
    - Alone
        - `	`
    - Shift
        - `€kB`
    - Ctrl
        - `€ü	`
    - Alt
        - `€ü	`
        - `	`
    - Cmd
        - `???`
### Enter
    - Alone
        - ``
    - Shift
        - `€ü`
    - Ctrl
        - `€ü`
    - Alt
        - ``
        - `€ü`
    - Cmd
        - `€ü€`

## Other Keys:
- Alone
    - `€kb` `` `€kI` `€kD`

## Navigation Keys:
- Alone
    - `€ku` `€kd` `€kl` `€kr` `€kh` `€@7` `€kP` `€kN`

## Function Keys:
- Alone
    - `€k1` `€k2` `€k3` `€k4` `€k5` `€k6` `€k7` `€k8` `€k9` `€k;` `???` `€F2`

## Numeric Keypad:
- Alone
    - `???` ...
