# Basic Vim Commands

**Cursor Movement:**

| Command | Description |
|:--------|:------------|
| w | Jump forward to the start of a word. |
| b | Jump backward to the start of a word. |
| e | Jump forwards to the end of a word. |
| ge  | Jump backward to the end of a word. |

**Insert Mode:**

| Command | Description |
|:--------|:------------|
| i | Insert before the cursor. |
| a | Insert (append ) after the cursor. |
| o | Append (open) a new line below the current line. |
| O | Append (open) a new line above the current line. |

**Editing:**

| Command | Description |
|:--------|:------------|
| r | Replace a single character. |
| R | Replace more than one character. |
| cc | Change a line. |
| cw | Change a word. |
| s | Cut a character. |
| S | Cut a line. |
| u | Undo. |
| CTRL + r | Redo. |

**Visual Mode:**

| Command | Description |
|:--------|:------------|
| v | Start visual mode. |
| V | Start line-wise visual mode. |

**Visual Commands:**

| Command | Description |
|:--------|:------------|
| > | Shift selected text right. |
| < | Shift selected text left. |
| y | Copy selected text. |
| d | Cut selected text. |
| ~ | Switch case of selected text. |

**Cut And Paste:**

| Command | Description |
|:--------|:------------|
| yy | Copy a line. |
| yw | Copy a word. |
| p  | Paste copied text after the cursor. |
| P  | Paste copied text before the cursor. |
| gp | Paste the copied text after the cursor and place the cursor after the pasted text. |
| gP | Paste the copied text before the cursor and place the cursor after the pasted text. |
| dd | Cut a line. |
| dw | Cut a word. |
| x  | Cut a character. |

**Indent Text:**

| Command | Description |
|:--------|:------------|
| >> | Indent a line. |
| << | De-indent a line. |

**Exiting:**

| Command | Description |
|:--------|:------------|
| :w | Save. |
| :q | Quit. |
| :x | Save and quit. |

**Search And Replace:**

| Command | Description |
|:--------|:------------|
| /pattern | Search for the pattern. |
| ?pattern | Search backward for the pattern. |
| n | Repeat the search in the same direction. |
| N | Repeat the search in the opposite direction. |
| :/%s/old/new | Replace all of the "old" with the "new". |
| :/%s/old/new/q | Replace all of the "old" with the "new" with confirmations. |

**Folding:**

| Command | Description |
|:--------|:------------|
| zo | Open a fold |
| zO | Open all folds |
| zc | Close a fold |
| zC | Close all folds |
| za | Toggle a fold |

**Scrolling:**

| Command | Description |
|:--------|:------------|
| zt | Scroll to the top |
| zz | Scroll to the middle |
| zb | Scroll to the bottom |

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Vim Notes](../../index.md#vim-notes) / [Basic Vim Commands](#basic-vim-commands)
