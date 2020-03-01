# Vim course

## Modal editor

Vim is a modal editor : TODO

## Surviving vim 

Before starting this guide you shall know the basic commands to move around and 
quit vim.

These are the basic motion command :

`h`, `j`, `k`, `l` you could instead use arrows LEFT, DOWN, UP, RIGHT but vim philosophy
is designed around `hjkl` try to not use the arrows to move around.

To quit press `:q!` in normal mode.

## [C][O][M]

The most important thing you shall remember when learing vim are those three words :

**Count** - **Operator** - **Motion**

A count is an arbitrary number representing how many times you want vim to perform an action.

An operator is an action that changes the current buffer (ex: `d` for delete)

A motion is an action moving the cursor without doing any modification to the current buffer (ex: `w` move forward a word)

`[count][operator][motion]` is how you automate action and reduce repetition in vim. All almost all command can be combined in this way. For instance if you want to delete three words you could type `3daw` in normal mode. Most command can be translated to english `daw` stands for "delete a word". Try it! 

*One two three !

## Using the help :

- Press `K`, in a vim  file to get help on the current word.
- Type `:help {topic}` to get help from anywhere.

## `:` Commands

`q:`  command history

`:w`  write current buffer to the current file

`:q`  quit current window 

`:x` `:wq` write current buffer and quit window

`:qa` quit vim unless some buffer have been changed 

`:find {filename}` find a file in path and `:edit` it

`:edit {filename}` edit a file in path 

`:r filename` copy the content of a file to current cursor position

`:r !external_command` copy the result off an external command to cursor position

## Motions : 

All the above command are used in normal mode.

#### Words 

`w` one word

`W` one word with special chars (ex: a/path/is/a/W/word)

`b` back a word

`B` back a word with special characters

`e` end of a word 

`E` end of a word with special character

#### Line 

`0` begining of the current line

`$` end of the current line

#### Search motions

`f` forward to character

`F` backward to character

`t` forward until character

`T` backward until character

`%` matching '()', '[]', '{}' ... 

### Screen control

`G` go to last line

`gg` go to first line

`Ctrl-f` forward a screen

`Ctrl-b` backward a screen

`Ctrl-d` scroll down half a screen

`Ctrl-u` scroll up half a screen

`zz`     move the screen so the current line is in the middle 

`zt`     move the screen so the current line is at the top

`zb`     move the screen so the current line is at the bottom

#### Jumps

see `[:help jumps]`

`Ctrl-o`  backward a jump

`Ctrl-i`  forward a jump

`gf`      edit the file whose name is under or after the cursor

## Insert mode

`a` enter insert mode after cursor position

`A` enter insert mode at the end of current line

`i` enter insert mode on current cursor position

`I` enter insert mode at the start of current line

`s` delete character a enter insert mode

`S` delete line and enter insert mode

`c` change delete motion and enter insert mode 

`C` delete from cursor positon to end of the line and enter insert mode

`r` replace the character under cursor

`R` enter replace mode

## The . command

Pressing `.` in normal mode will repeat the last change you made. 

**Example :** 

1. position your cursor under a word a type`caw` 
2. your are now in insert mode type : "hello world"
3. exit insert mode with `esc`
4. position your cursor under another word and press `.`

## Yank

`y` yank + motion

`Y` yank a line 

`p` paste

**Example :**

1. press `2Y` on the line below starting with --> 
2. go to to the next line and press `p`

--> Rose are red
--> Violet are blue

## Search 

`/foo`  search "foo" 
`?bar`  search bar backward
`*`     search the word under cursor position
    - press `n` to go to next occurence
    - press `N` to go to previous occurence


### Substitute

`:s/old/new`         substitute first occurence of "old" with "new" on the current line

`:s/old/new/g`       substitute all occurence of "old" with "new" on the current line

`:%s/old/new/g`      substitute all occurence of "old" with "new" on the current buffer

`:%s/old/new/gc`     substitute all occurence of "old" with "new" on the current buffer and ask for confirmation

`:%s/old//gn`        count all occurence of "old"  

`:12,15/old/new/g`   substitute all occurrences of "old" with "new" from line 12 to 15

`:.,+3/old/new/g`    substitute all occurrences of "old" with "new" from current line to current line plus 3
 
## Objects commands : 

`diw/W`   delete inner word

`daw/W`   delete a word

`dd`      delete a line

`das`     delete a sentence

`dis`     delete inner sentence

`dap`     delete a paragraph

`dib`     delete inner '()' block

`dab`     delete a '()' block

`diB`     delete a '{}' inner block

## Plugins

TODO
