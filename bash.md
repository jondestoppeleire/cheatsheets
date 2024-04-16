# Bash Language Cheatsheet

## Basics

### Variables
```bash
# Defining variables
name="John"
age=25

# Using variables
echo "Name: $name, Age: $age"
```

### Command Substitution
```bash
# Capturing the output of a command
result=$(ls -l)
echo "Listing: $result"
```

### Exporting Variables
```bash
# Making a variable available to child processes
export PATH="/usr/local/bin:$PATH"
```

## File Operations

### Creating Files and Directories
```bash
touch myfile.txt            # Creates an empty file
mkdir mydirectory           # Creates a directory
```

### Reading and Writing Files
```bash
echo "Hello, world!" > file.txt   # Writes to a file (overwrites)
echo "Hello again!" >> file.txt   # Appends to a file
cat file.txt                      # Displays the content of a file
```

### File Permissions
```bash
chmod +x script.sh           # Makes the script executable
chmod 755 script.sh          # Sets read and execute permissions for everyone, write for owner
```

## Text Processing

### Echo and Printing
```bash
echo "Hello world"
printf "Name: %s, Age: %d\n" "$name" "$age"
```

### Grep, Sed, Awk
```bash
grep 'pattern' filename           # Searches for a pattern in a file
sed 's/old/new/g' filename        # Replaces all occurrences of 'old' with 'new' in file
awk '{print $1}' filename         # Prints the first column in a file
```

### Sorting, Uniq
```bash
sort file.txt                     # Sorts lines in a file
uniq file.txt                     # Removes duplicate lines (input must be sorted)
```

## Control Structures

### If Statement
```bash
if [ $age -gt 18 ]; then
    echo "Adult"
elif [ $age -eq 18 ]; then
    echo "Just turned 18"
else
    echo "Not an adult"
fi
```

### For Loop
```bash
for i in {1..5}; do
    echo "Number $i"
done
```

### While Loop
```bash
while [ $count -lt 10 ]; do
    echo "Count: $count"
    count=$((count+1))
done
```

## System Information

### Disk Space, Memory, Processes
```bash
df -h                               # Disk space
free -m                             # Memory usage
top                                 # Running processes
```

## Networking

### Curl, Wget
```bash
curl https://www.example.com       # Fetches the content of a webpage
wget https://www.example.com/file.zip # Downloads a file from the internet
```

### SSH, SCP
```bash
ssh user@host                      # Connects to a host as user
scp file.txt user@host:/path       # Copies file.txt to a remote host
```

## Advanced Scripting

### Functions
```bash
function greet {
    echo "Hello, $1"
}
greet "World"
```

### Arrays
```bash
arr=(apple banana cherry)
echo ${arr[1]}                     # Outputs 'banana'
```

## File Handling
```bash
# Redirecting stdout and stderr
command >stdout.txt 2>stderr.txt   # Redirects stdout to stdout.txt, stderr to stderr.txt
command &>output.txt               # Redirects both stdout and stderr to output.txt
```

## Debugging
```bash
set -x                             # Activates debugging from here
set +x                             # Deactivates debugging from here
```

