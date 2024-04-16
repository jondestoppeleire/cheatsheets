# Zsh (Z Shell) Quick Reference Sheet

## Basic Commands

### Command Execution
```zsh
echo "Hello, World!"   # Prints string to the terminal
ls -l                  # Lists files in long format
```

### File and Directory Management
```zsh
cd /path/to/directory  # Changes the current directory
mkdir newfolder        # Creates a new directory
rm file.txt            # Removes a file
```

### Job Control
```zsh
fg                      # Brings the most recent job to foreground
bg                      # Sends the most recent job to background
jobs                    # Displays all current jobs
```

## Advanced Features

### Extended Globbing
```zsh
setopt EXTENDED_GLOB
^name*                 # Matches everything except files starting with 'name'
*.^txt                 # Matches all files except those ending with '.txt'
```

### Command Line Editing
```zsh
bindkey -v              # Enables vim mode for command line editing
<esc> v                 # Opens the current command line in a Vim editor window
```

### Array Operations
```zsh
array=(one two three four)
echo $array[2]          # Prints 'two'
array[5]="five"         # Adds 'five' at the 5th index
```

### History Management
```zsh
history                 # Shows command history
setopt APPEND_HISTORY   # Appends history list to the history file
setopt INC_APPEND_HISTORY  # Writes history as each command is executed
```

## Customization

### Alias Definition
```zsh
alias ll='ls -lh'       # Creates an alias 'll' for 'ls -lh'
alias rm='rm -i'        # Makes 'rm' command interactive
```

### Prompt Customization
```zsh
PROMPT='%n@%m %1~ %# '  # Customizes the Zsh prompt
RPROMPT='%t'            # Sets right-hand prompt to show time
```

### Functions
```zsh
function mkcd() {
    mkdir -p "$1"
    cd "$1"
}
```

### Theme and Appearance
Using Oh My Zsh and themes:
```zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"  # Installs Oh My Zsh
ZSH_THEME="agnoster"   # Set the theme to agnoster in ~/.zshrc
```

## Plugin Management with Oh My Zsh
```zsh
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
source $ZSH/oh-my-zsh.sh
```

## Scripting with Zsh
```zsh
#!/bin/zsh
# Example of a Zsh script
for i in {1..5}
do
   echo "Looping ... number $i"
done
```

