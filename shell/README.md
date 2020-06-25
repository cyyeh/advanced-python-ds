# The Shell

references:
- https://swcarpentry.github.io/shell-novice/
- https://carpentries-incubator.github.io/shell-extras/

## Introducing the Shell

- Questions
  - What is a command shell and why would I use one?
- Objectives
  - Explain how the shell relates to the keyboard, the screen, the operating system, and users’ programs.
  - Explain when and why command-line interfaces should be used instead of graphical interfaces.
- Key Points
  - A shell is a program whose primary purpose is to read commands and run other programs.
  - The shell’s main advantages are its high action-to-keystroke ratio, its support for automating repetitive tasks, and its capacity to access networked machines.
  - The shell’s main disadvantages are its primarily textual nature and how cryptic its commands and operation can be.

## Navigating Files and Directories

- Questions
  - How can I move around on my computer?
  - How can I see what files and directories I have?
  - How can I specify the location of a file or directory on my computer?
- Objectives
  - Explain the similarities and differences between a file and a directory.
  - Translate an absolute path into a relative path and vice versa.
  - Construct absolute and relative paths that identify specific files and directories.
  - Use options and arguments to change the behaviour of a shell command
  - Demonstrate the use of tab completion, and explain its advantages.
- Key Points
  - The file system is responsible for managing information on the disk.
  - Information is stored in files, which are stored in directories (folders).
  - Directories can also store other directories, which forms a directory tree.
  - `cd path` changes the current working directory.
  - `ls path` prints a listing of a specific file or directory; `ls` on its own lists the current working directory.
  - `pwd` prints the user’s current working directory.
  - `/` on its own is the root directory of the whole file system.
  - A relative path specifies a location starting from the current location.
  - An absolute path specifies a location from the root of the file system.
  - Directory names in a path are separated with `/` on Unix, but `\` on Windows.
  - `..` means ‘the directory above the current one’; . on its own means ‘the current directory’.

## Working With Files and Directories

- Questions
  - How can I create, copy, and delete files and directories?
  - How can I edit files?
- Objectives
  - Create a directory hierarchy that matches a given diagram.
  - Create files in that hierarchy using an editor or by copying and renaming existing files.
  - Delete, copy and move specified files and/or directories.
- Key Points
  - `cp old new` copies a file.
  - `mkdir path` creates a new directory.
  - `mv old new` moves (renames) a file or directory.
  - `rm path` removes (deletes) a file.
  - `*` matches zero or more characters in a filename, so `*.txt` matches all files ending in `.txt`.
  - `?` matches any single character in a filename, so `?.txt` matches `a.txt` but not `any.txt`.
  - Use of the Control key may be described in many ways, including `Ctrl-X`, `Control-X`, and `^X`.
  - The shell does not have a trash bin: once something is deleted, it’s really gone.
  - Most files’ names are `something.extension`. The extension isn’t required, and doesn’t guarantee anything, but is normally used to indicate the type of data in the file.
  - Depending on the type of work you do, you may need a more powerful text editor than Nano.

## Pipes and Filters

- Questions
  - How can I combine existing commands to do new things?
- Objectives
  - Redirect a command’s output to a file.
  - Process a file instead of keyboard input using redirection.
  - Construct command pipelines with two or more stages.
  - Explain what usually happens if a program or pipeline isn’t given any input to process.
  - Explain Unix’s ‘small pieces, loosely joined’ philosophy.
- Key Points
  - `cat` displays the contents of its inputs.
  - `head` displays the first 10 lines of its input.
  - `tail` displays the last 10 lines of its input.
  - `sort` sorts its inputs.
  - `wc` counts lines, words, and characters in its inputs.
  - `command > file` redirects a command’s output to a file (overwriting any existing content).
  - `command >> file` appends a command’s output to a file.
  - `first | second` is a pipeline: the output of the first command is used as the input to the second.
  - The best way to use the shell is to use pipes to combine simple single-purpose programs (filters).

## Loops

- Questions
  - How can I perform the same actions on many different files?
- Objectives
  - Write a loop that applies one or more commands separately to each file in a set of files.
  - Trace the values taken on by a loop variable during execution of the loop.
  - Explain the difference between a variable’s name and its value.
  - Explain why spaces and some punctuation characters shouldn’t be used in file names.
  - Demonstrate how to see what commands have recently been executed.
  - Re-run recently executed commands without retyping them.
- Key Points
  - A `for` loop repeats commands once for every thing in a list.
  - Every `for` loop needs a variable to refer to the thing it is currently operating on.
  - Use `$name` to expand a variable (i.e., get its value). `${name}` can also be used.
  - Do not use spaces, quotes, or wildcard characters such as ‘*’ or ‘?’ in filenames, as it complicates variable expansion.
  - Give files consistent names that are easy to match with wildcard patterns to make it easy to select them for looping.
  - Use the up-arrow key to scroll up through previous commands to edit and repeat them.
  - Use Ctrl+R to search through the previously entered commands.
  - Use `history` to display recent commands, and `!number` to repeat a command by number.

## Shell Scripts

- Questions
  - How can I save and re-use commands?
- Objectives
  - Write a shell script that runs a command or series of commands for a fixed set of files.
  - Run a shell script from the command line.
  - Write a shell script that operates on a set of files defined by the user on the command line.
  - Create pipelines that include shell scripts you, and others, have written.
- Key Points
  - Save commands in files (usually called shell scripts) for re-use.
  - `bash filename` runs the commands saved in a file.
  - `$@` refers to all of a shell script’s command-line arguments.
  - `$1`, `$2`, etc., refer to the first command-line argument, the second command-line argument, etc.
  - Place variables in quotes if the values might have spaces in them.
  - Letting users decide what files to process is more flexible and more consistent with built-in Unix commands.

## Finding Things

- Questions
  - How can I find files?
  - How can I find things in files?
- Objectives
  - Use grep to select lines from text files that match simple patterns.
  - Use find to find files and directories whose names match simple patterns.
  - Use the output of one command as the command-line argument(s) to another command.
  - Explain what is meant by ‘text’ and ‘binary’ files, and why many common tools don’t handle the latter well.
- Key Points
  - `find` finds files with specific properties that match patterns.
  - `grep` selects lines in files that match patterns.
  - `--help` is an option supported by many bash commands, and programs that can be run from within Bash, to display more information on how to use these commands or programs.
  - `man` command displays the manual page for a given command.
  - `$(command)` inserts a command’s output in place.

## Manual Pages

- Questions
  - How to use man pages?
- Objectives
  - Use `man` to display the manual page for a given command.
  - Explain how to read the synopsis of a given command while using `man`.
  - Search for specific options or flags in the manual page for a given command.
- Key Points
  - `man command` displays the manual page for a given command.
  - `[OPTION]...` means the given command can be followed by one or more optional flags.
  - Flags specified after ellipsis are still optional but must come after all other flags.
  - While inside the manual page,use `/` followed by your pattern to do interactive searching.

## Working Remotely

- Questions
  - How do I use ‘`ssh`’ and ‘`scp`’ ?
- Objectives
  - Learn what SSH is
  - Learn what an SSH key is
  - Generate your own SSH key pair
  - Learn how to use your SSH key
  - Learn how to work remotely using `ssh` and `scp`
  - Add your SSH key to an remote server
- Key Points
  - SSH is a secure alternative to username/password authorization
  - SSH keys are generated in public/private pairs. Your public key can be shared with others. The private keys stays on your machine only.
  - The ‘ssh’ and ‘scp’ utilities are secure alternatives to logging into, and copying files to/from remote machine
- References
  - [How Secure Shell Works (SSH) - Computerphile
](https://youtu.be/ORcvSkgdA58)

## Transferring Files

- Questions
  - How to use wget, curl and lftp to transfer file?

## Permissions

- Questions
  - Understanding file/directory permissions
- Objectives
  - What are file/directory permissions?
  - How to view permissions?
  - How to change permissions?
  - File/directory permissions in Windows
- Key Points
  - Correct permissions are critical for the security of a system.
  - File permissions describe who and what can read, write, modify, and access a file.
  - Use `ls -l` to view the permissions for a specific file.
  - Use `chmod` to change permissions on a file or directory.

## Directory structure

- Questions
  - Understanding the concept of Unix directory structure

## Job control

- Questions
  - How do keep track of the process running on my machine?
  - Can I run more than one program/script from within a shell?
- Objectives
  - Learn how to use `ps` to get information about the state of processes
  - Learn how to control, ie., “stop/pause/background/foreground” processes
- Key Points
  - When we talk of ‘job control’, we really mean ‘process control’
  - A running process can be stopped, paused, and/or made to run in the background
  - A process can be started so as to immediately run in the background
  - Paused or backgrounded processes can be brought back into the foreground
  - Process information can be inspected with `ps`

## Aliases and bash customization

- Questions
  - How do I customize my bash environment?
- Objectives
  - Create aliases.
  - Add customizations to the `.bashrc` and `.bash_profile` files.
  - Change the prompt in a bash environment.
- Key Points
  - Aliases are used to create shortcuts or abbreviations
  - The `.bashrc` and `.bash_profile` files allow us to customize our bash environment.
  - The `PS1` system variable can be changed to customize your bash prompt.

## Shell Variables

- Questions
  - How to change shell variables
- Objectives
  - Understanding shell variables