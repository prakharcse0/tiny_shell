# Tiny Shell

A minimal Unix-like shell implementation in C++ using POSIX APIs. This shell provides core functionality similar to bash or other Unix shells but with a simpler implementation focused on educational purposes.

## Features

### Basic Features
- Command execution (execute programs with arguments)
- Built-in commands (`cd`, `pwd`, `exit`, `help`, `jobs`)
- Command-line parsing
- Error handling

### Intermediate Features
- Input/output redirection (`>`, `<`, `>>`)
- Pipes to connect multiple commands (`cmd1 | cmd2`)
- Background process execution (`command &`)
- Environment variable handling (expanding `$VAR` or `${VAR}` in commands)
- Command tracking and job management

## Prerequisites

To build and run this shell, you'll need:

- A Unix/Linux environment
- C++ compiler (GCC/G++ recommended)
- Make build system
- Basic knowledge of POSIX APIs (fork, exec, etc.)

## Building the Shell

```bash
# Clone the repository
git clone https://github.com/prakharcse0/tiny_shell.git
cd tiny_shell

# Build the shell
make

# Run the shell
./tiny_shell
```

## Usage

Once the shell is running, you can enter commands just like in a regular shell:

```
# Basic command execution
user@hostname:~/tiny_shell$ ls -l

# I/O redirection
user@hostname:~/tiny_shell$ ls > file_list.txt
user@hostname:~/tiny_shell$ cat < file_list.txt
user@hostname:~/tiny_shell$ ls -la >> file_list.txt

# Pipes
user@hostname:~/tiny_shell$ ls -l | grep ".txt" | wc -l

# Background execution
user@hostname:~/tiny_shell$ sleep 10 &

# Using environment variables
user@hostname:~/tiny_shell$ echo $HOME
user@hostname:~/tiny_shell$ export MY_VAR=hello
user@hostname:~/tiny_shell$ echo $MY_VAR
```

## Built-in Commands

The shell provides several built-in commands:

- `cd [dir]` - Change directory (defaults to home directory)
- `pwd` - Print current working directory
- `env` - Display all environment variables
- `export NAME=VALUE` - Set environment variable
- `unset NAME` - Unset environment variable
- `jobs` - List background processes
- `help` - Display help information
- `exit` - Exit the shell

## Implementation Details

The shell is implemented using standard POSIX APIs:

- `fork()` - Create child processes
- `execvp()` - Execute commands
- `pipe()` - Create pipes for communication between processes
- `dup2()` - Redirect input/output
- `waitpid()` - Wait for child processes to complete

The code is organized to handle parsing commands, executing processes, managing I/O redirection, and implementing built-in commands.
