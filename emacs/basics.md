## Open File

`C-x C-f` <path to file><CR>

## Creating a Directory

`M-x` make-directory<CR>
then
<directory-name><CR>

## Save File (buffer)

`C-x C-s`

## Quit

`save-buffers-kill-emacs`

`C-x C-c`

## See open buffers

`C-x C-b`

## Show line numbers

`M-x linum-mode`

## Jump to prev/next function

Top-level definitions like functions are called 'defuns'.

`C-M-a` jumps to prev defun

`C-M-e` jumps to next defun

`C-M-h` selects the whole defun

## Go to beginning/end of a file

`ESC-<` jumps to beginning of file
`ESC->` jumps to end of file

## Move forward over a word with underscores

Similar: `forward-sexp`: "move forward over a balanced expression
`C-M-f`
backward: `C-M-b`

## Cut, copy, paste

cut: `C-w`
copy: `M-w`
paste (yank): `C-y`

That last one is confusing because in Vim yank is copy not paste. How is 'yank' the same as paste???

## Select text

Set a mark: `C-@`

When you set a second mark, all the text between is selected

