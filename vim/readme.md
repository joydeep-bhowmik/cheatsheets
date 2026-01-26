

# VIM CHEAT SHEET

## Modes (this matters or you’re dead in the water)

Vim is **modal**. If you don’t understand this, everything else fails.

* `NORMAL` → move, delete, copy (default)
* `INSERT` → type text
* `VISUAL` → select text
* `COMMAND` → `:` commands

### Switching modes

```vim
i        # NORMAL → INSERT (before cursor)
a        # NORMAL → INSERT (after cursor)
Esc      # go back to NORMAL (hit it like you mean it)
v        # VISUAL (character)
V        # VISUAL (line)
Ctrl+v   # VISUAL (block)
:        # COMMAND mode
```

---

## Moving Around (stop using arrow keys)

### Basic movement

```vim
h j k l      # left down up right
w            # next word
b            # previous word
0            # start of line
^            # first non-blank char
$            # end of line
```

### Scrolling

```vim
Ctrl+d       # half page down
Ctrl+u       # half page up
gg           # top of file
G            # bottom of file
```

---

## Editing Like You Mean It

### Insert shortcuts

```vim
i    # insert before cursor
a    # insert after cursor
o    # new line below
O    # new line above
```

### Delete (this is power)

```vim
x            # delete character
dw           # delete word
dd           # delete line
D            # delete to end of line
```

### Undo / redo

```vim
u            # undo
Ctrl+r       # redo
```

---

## Copy / Paste (Yank / Put)

```vim
yy           # yank (copy) line
yw           # yank word
p            # paste after cursor
P            # paste before cursor
```

## Select 
```vim
gg           # go to first line
G            # go to last line
V            # start line-wise visual mode
v            # start character-wise visual mode
ggVG         # select all (line-wise)
ggvG         # select all (character-wise)
ggVGy        # select all and copy (yank)
ggVGd        # select all and delete
ggVG=        # select all and auto-indent
``
Visual mode:

```vim
v → select → y
v → select → d
```

---

## Search & Replace (this is non-negotiable)

### Search

```vim
/word        # search forward
?word        # search backward
n            # next match
N            # previous match
```

### Replace

```vim
:%s/old/new/g        # replace all
:%s/old/new/gc       # replace all with confirmation
```

---

## Files (don’t panic)

```vim
:w          # save
:q          # quit
:wq         # save and quit
:q!         # quit without saving (rage exit)
:e file     # open file
```

---

## Visual Mode Power

```vim
V            # select lines
Ctrl+v       # block select
>            # indent
<            # unindent
```

---

## Buffers & Windows (basic)

```vim
:ls          # list buffers
:b 2         # go to buffer 2
:bd          # close buffer

:split       # horizontal split
:vsplit      # vertical split
Ctrl+w w     # switch windows
```

---

## Absolute Minimum You Must Memorize

If you learn **nothing else**, learn this:

```
Esc → :wq → Enter
```

And:

```
h j k l
dd
u
/word
```



