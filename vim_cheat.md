# Modes

`i`: Go to Insert Mode
`Esc` or `Ctrl-C`: Go to Normal Mode

# Navigation

`gg`: Move to top of file
`G`: Move to end of file
`{line}gg`: Move to specific line

`w`: Move to beginning of next word
`b`: Jump to beginning of last word
`e`: Jump to end of word
`ge`: Jump backwards to end of last word

**A count is a number at the beginning of a command that will multiply the effect of that command.**

**In vim, a WORD is a string of characters that contains non-alphabetic characters. We
navigate through these using the uppercase versions of the above commands.**

`f{character}`: Jump to specific character
`t{character}`: Jump to just before specific character
`;` or `,`: Jump to next or previous occurrence of character search

`0`: Moves to the first character of a line
`^`: Moves to the first non-blank character of a line
`$`: Moves to the end of a line
`g_`: Moves to the non-blank character at the end of a line

`}`: jumps entire paragraphs downwards
`{`: similarly but upwards
`CTRL-D`: lets you move down half a page by scrolling the page
`CTRL-U`: lets you move up half a page also by scrolling


