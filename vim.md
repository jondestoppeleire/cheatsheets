# Neovim (nvim) Quick Reference Sheet

## Basic Commands

### Opening, Closing, and Saving Files
```vim
:nvim filename         # Open a file with nvim
:w                     # Save the current file
:wq or :x              # Save and quit
:q                     # Quit (fails if there are unsaved changes)
:q!                    # Quit and ignore unsaved changes
```

### Navigation
```vim
h, j, k, l             # Move left, down, up, right (basic cursor movement)
:w                     # Move to the start of the next word
:b                     # Move to the start of the previous word
G                     # Go to the last line of the document
gg                    # Go to the first line of the document
:%s/old/new/g          # Replace all occurrences of 'old' with 'new' throughout the file
```

### Editing
```vim
i                      # Insert mode at cursor
a                      # Append mode after cursor
o                      # Open a new line below and insert
O                      # Open a new line above and insert
dd                     # Delete the current line
yy                     # Yank (copy) the current line
p                      # Paste below the cursor
P                      # Paste above the cursor
u                      # Undo
Ctrl + r               # Redo
```

## Advanced Usage

### Split Windows
```vim
:split or :sp          # Horizontal split
:vsplit or :vsp        # Vertical split
Ctrl + w then arrow keys # Navigate between splits
Ctrl + w then q        # Close a split
```

### Tabs
```vim
:tabnew [filename]     # Open a new tab
:tabclose              # Close the current tab
:tabnext               # Go to the next tab
:tabprev               # Go to the previous tab
```

### Buffers
```vim
:ls                    # List all buffers
:buffer N              # Switch to buffer number N
:bd                    # Delete a buffer (close a file)
```

## Customization

### vimrc Configuration
```vim
" Set line numbers
:set number

" Enable syntax highlighting
:syntax enable

" Set the indent size for Python files
:autocmd FileType python setlocal shiftwidth=4 tabstop=4
```

### Key Mappings
```vim
" Map Ctrl + N to create a new tab
:nnoremap <C-n> :tabnew<CR>

" Map Ctrl + S for saving the file
:nnoremap <C-s> :w<CR>
```

### Plugins
```vim
" Using vim-plug to install plugins
call plug#begin('~/.vim/plugged')
Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
Plug 'preservim/nerdtree'
call plug#end()

" Using the NERDTree plugin
:NERDTreeToggle          # Toggle NERDTree panel
```

## Scripting with vimscript
```vim
" Function to highlight trailing spaces
function! HighlightTrailingSpaces()
    highlight ExtraWhitespace ctermbg=red guibg=red
    match ExtraWhitespace /\s\+$/
endfunction
autocmd BufWinEnter * call HighlightTrailingSpaces()

" Custom command to delete all trailing whitespace
command! TrimWhitespace :%s/\s\+$//e
```

