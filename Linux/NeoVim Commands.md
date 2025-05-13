#linux #NeoVim #commands #text-editor 

Open NeoVim with the `nvim` command.
## Basic Operations

### Movement
- `h` or `Left Arrow Key` - Move cursor left
- `j` or `Down Arrow Key` - Move cursor down
- `k` or `Up Arrow Key`- Move cursor up
- `l` or `Right Arrow Key`- Move cursor right
- `w` - Jump to start of next word
- `b` - Jump to start of previous word
- `e` - Jump to end of word
- `0` - Jump to start of line
- `$` - Jump to end of line
- `gg` - Go to first line of document
- `G` - Go to last line of document
- `{number}G` - Go to line number
- `Ctrl+u` - Page up
- `Ctrl+d` - Page down

### Insertion
- `i` - Insert before cursor
- `I` - Insert at beginning of line
- `a` - Insert after cursor
- `A` - Insert at end of line
- `o` - Insert new line below
- `O` - Insert new line above
- `ea` - Insert at end of word
- `esc` - Exit Insert mode

### Editing
- `x` - Delete character under cursor
- `dw` - Delete word
- `dd` - Delete line
- `D` - Delete from cursor to end of line
- `c` - Change command
- `cc` - Change entire line
- `cw` - Change word
- `C` - Change from cursor to end of line
- `r` - Replace single character
- `R` - Replace mode
- `u` - Undo
- `Ctrl+r` - Redo
- `yy` - Copy line
- `yw` - Copy word
- `p` - Paste after cursor
- `P` - Paste before cursor

## Visual Mode
- `v` - Enter visual mode
- `V` - Enter visual line mode
- `Ctrl+v` - Enter visual block mode
- `gv` - Reselect last visual selection

### Visual Mode Commands
- `d` - Delete selected text
- `y` - Copy selected text
- `>` - Indent right
- `<` - Indent left
- `~` - Switch case
- `:sort ui` - Sort highlighted lines alphabetically

## Line Numbers
- `:set number` - add line numbers
- `:set nonumber` - remove line numbers

## Search and Replace
- `/pattern` - Search forward for pattern
- `?pattern` - Search backward for pattern
- `n` - Repeat search forward
- `N` - Repeat search backward
- `:%s/old/new/g` - Replace all occurrences in file
- `:%s/old/new/gc` - Replace all occurrences with confirmation
- `:sort ui `

## Files and Buffers
- `:w` - Save file
- `:w filename` - Save as filename
- `:q` - Quit
- `:q!` - Quit without saving
- `:wq` - Save and quit
- `:e filename` - Open file
- `:r filename` - Add content of another file into current file
- `:bn` - Next buffer
- `:bp` - Previous buffer
- `:ls` - List buffers
- `:b number` - Go to buffer number
- `:bd` - Close buffer but stay in NeoVim

## Windows and Tabs
- `:sp filename` - Open file in horizontal split
- `:vsp filename` - Open file in vertical split
- `Ctrl+w s` - Horizontal split
- `Ctrl+w v` - Vertical split
- `Ctrl+w w` - Switch windows
- `Ctrl+w h` - Move to left window
- `Ctrl+w j` - Move to window below
- `Ctrl+w k` - Move to window above
- `Ctrl+w l` - Move to right window
- `Ctrl+w c` - Close window
- `:tabnew` - Open new tab
- `gt` - Next tab
- `gT` - Previous tab

## Text Objects
- `iw` - Inner word
- `aw` - A word
- `is` - Inner sentence
- `as` - A sentence
- `ip` - Inner paragraph
- `ap` - A paragraph
- `i"` - Inner quotes
- `a"` - A quotes
- `i(` - Inner parentheses
- `a(` - A parentheses

## Marks
- `ma` - Set mark 'a'
- `'a` - Jump to line of mark 'a'
- `` `a `` - Jump to position of mark 'a'
- `:marks` - List all marks

## Macros
- `qa` - Record macro 'a'
- `q` - Stop recording macro
- `@a` - Run macro 'a'
- `@@` - Repeat last macro

## Advanced Commands
### Folding
- `zf` - Create fold
- `zo` - Open fold
- `zc` - Close fold
- `zR` - Open all folds
- `zM` - Close all folds

### Text Formatting
- `gq` - Format text
- `==` - Auto-indent line
- `gg=G` - Auto-indent entire file
- `>>`/`<<` - Indent/outdent line

### Registers
- `"ay` - Yank into register 'a'
- `"ap` - Paste from register 'a'
- `:reg` - Show registers

## Tips and Tricks
1. Use `.` to repeat last change
2. Combine numbers with commands: `5dd` deletes 5 lines
3. Use `ci(` to change text inside parentheses
4. `%` jumps between matching brackets
5. Use `*` to search for word under cursor
6. `gf` jumps to file under cursor
7. `Ctrl+a`/`Ctrl+x` increment/decrement numbers

## Configuration
- `:set number` - Show line numbers
- `:set relativenumber` - Show relative line numbers
- `:set wrap` - Enable line wrapping
- `:set ignorecase` - Case-insensitive search
- `:set smartcase` - Smart case search
- `:syntax on` - Enable syntax highlighting

## Plugin Commands
*Note: These commands depend on installed plugins*

### Common Plugin Commands
- `:NERDTree` - Open file explorer (NERDTree)
- `:PlugInstall` - Install plugins (vim-plug)
- `:CocConfig` - Configure CoC
- `:Telescope` - Open fuzzy finder (Telescope)
- `:GitGutter` - Toggle git changes
- `:!` - Run Linux commands from within NeoVim