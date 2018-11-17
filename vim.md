# Vim commands

**Exiting**

:w - save file, but don't exit

:wq or :x or ZZ - save and quit

:q - quit (fails if there are unsaved changes)

:q! - quit and throw away unsaved changes

**Search and replace**

/pattern - search for pattern

?pattern - search backward for pattern

**Navigating**

H - move to top of screen

L - move to bottom of screen

w - jump forwards to the start of a word (can be a punctuation sign)

W - jump forwards to the start of a word (ignoring punctuation)

e - jump towards the end of a word (ignoring punctuation sign straight after)

E - jump towards the end of a word (can be a punctuation sign)

b - jump backwards to the start of a word (can be a punctuation sign)

B - jump backwards to the start of a word (ignoring punctuation)

0 - jump to the start of the line

$ - jump to the end of the line

**Insert mode**

Insert - enter insert mode

i - insert before the cursor

I - insert at the beginning of the line

a - insert after the cursor

A - insert at the end of the line

o - insert a new line after the current line

O - insert a new line before the current line

Esc - exit insert mode

**Cut and paste**

yy - copy a line

Nyy - copy N lines

p - paste after cursor

P - paste before cursor

dd - delete (cut) a line

Ndd - delete (cut) N lines

D - delete (cut) to the end of the line

d$ - delete (cut) to the end of the line

**Visual commands**

\> - shift text right

< - shift text left
