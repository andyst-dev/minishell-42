# minishell

A small Unix shell developed as part of the 42 curriculum.
`minishell` is an interactive shell written in C that handles command parsing, pipes, redirections, builtins and environment variables.

It was a good way to build solid foundations in processes, file descriptors, parsing, memory management and shell behavior.

## Features
- Interactive prompt with command history
- Execution of builtins and external commands
- Support for pipes and redirections
- Environment variable expansion and exit status handling
- Signal handling for interactive shell behavior

## Project structure
- `minishell.h` — main header file, structures, globals and function prototypes
- `Main/` — program entry point and signal setup
- `Parsing/` — input preprocessing and variable expansion
- `Tokenization/` — command splitting and shell token handling
- `Builtins/` — builtin command implementation
- `Execution/` — builtin and external command execution flow
- `Pipes/` — pipeline parsing and execution
- `Redirects/` — input, output, append and heredoc redirections
- `Environment/` — environment list management and conversion helpers
- `Utilities/` — shared helper functions
- `Makefile` — builds the `minishell` executable

## Mandatory part
The mandatory part focuses on the parsing and execution flow required to run a small interactive shell.

### Program
- `minishell` — launches an interactive shell prompt and executes supported commands

### Core behavior
- displays a prompt and keeps a command history
- parses quoted input and expands environment variables
- supports `<`, `>`, `<<` and `>>` redirections
- supports pipelines with `|`
- executes builtins directly in the shell when needed
- searches executables through `PATH` or direct paths
- handles `ctrl-C`, `ctrl-D` and `ctrl-\\` with bash-like behavior

### What happens at runtime
- the program initializes the shell state and signal handling
- it waits for a command through `readline`
- the input is parsed, tokenized and expanded when needed
- commands are dispatched either to builtins or external executables
- redirections and pipes are applied before execution
- the shell returns to the prompt until the user exits or sends EOF

### Subject requirements to respect
- the shell must display a prompt and support history
- it must correctly handle single and double quotes
- it must implement the required redirections and pipes
- it must expand environment variables and `$?`
- builtins must follow the subject scope only
- signal behavior must match the mandatory interactive rules
- the implementation must avoid crashes and memory leaks in user code

## Notes
This repository comes from a collaborative 42 project built with [tmoel1](https://github.com/tmoel1).
His part mainly focused on execution-related logic and builtin behavior.

## My part in this project
My part in this project mainly covers the shell entry flow, signal handling, parsing, tokenization and environment management.

### What I worked on
- preparing and processing the raw input line before execution
- handling quote-aware parsing and environment variable expansion
- splitting the command line into meaningful shell tokens
- managing the shell environment
- setting up the main interactive loop and signal behavior

The parsing side is a central part of `minishell`.
It turns the raw command entered by the user into structured data that the shell can actually execute.

That includes:
- recognizing quoted sections correctly
- preserving the meaning of special characters
- expanding variables at the right moment
- preparing commands so pipes, redirections, builtins and external executables can be handled correctly afterward

## Build
Build the project:

```bash
make
```

Clean object files:

```bash
make clean
```

Remove object files and executable:

```bash
make fclean
```

Rebuild everything:

```bash
make re
```

## Usage
Run the shell:

```bash
./minishell
```

Example interactions:

```bash
echo hello
ls -l | grep minishell
export TEST=value && echo $TEST
```

## Learning outcomes
This project was my first real introduction to shell implementation in C.
It helped build solid foundations in:
- process creation and synchronization
- file descriptor manipulation
- pipes and redirections
- command parsing
- environment management
- interactive signal handling
