# Basic Vim commands
- https://missing.csail.mit.edu/2020/editors/
- https://superuser.com/questions/246487/how-to-use-vimtutor
- https://thevaluable.dev/vim-adept/

##### Switching Modes
```
vim filename-to-open-in-vim-editor # opens file_name with vim editor

i    # start insert mode so you can change the contents
esc  # go back to command mode where you can do things like :w or :wq
	   shift+V (capital V) # go into visual mode
:    # to enter into extended mode
```

##### Command Mode 
```
esc # back to command mode from insert mode
:q # quits vim
:q! # quits without saving
:wq # saves and quits vim
:w # saves and stay in vim
:su nu # shows line numbers

press / to search then `n` to go to next search
press j to go down or 10j to move 10 lines down
press k to go up or 10k to move 10 lines up
press l to go to right
press h to go to left
press d to delete
press dd (double d) to delete a line and copy to clipboard
press . (period) to do your last command again
press u to undo a change
press ctlr+r to redo change
press G (capital G) to go to bottom of page
press gg (double g) to go to top of page
press } to move to next block
press { to move to prev block
press yy (double y) to copy line you're at to clipboard
press 4yy to copy 4 lines
press p to paste below the line you're at (if you have something in your clipboard)
press P (capital P) to paste above the line you're at (if you have something in your clipboard)
press o to change to insert mode and adds a new line
```
##### Visual Mode
```
pressing j,k,l,h and moving in editor will select the contents
```