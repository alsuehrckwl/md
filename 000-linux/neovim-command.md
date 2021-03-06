nvim man page
nvim — edit text

Synopsis
nvim	[options] [file ...]
nvim	[options] -
nvim	[options] -t tag
nvim	[options] -q [errorfile]
Description
nvim is a text editor based on Vim. To enter commands in nvim, type a colon (‘:’) which is also used in this manual to denote commands. For more information, consult the on-line help system with the :help command.

file ...
File(s) to edit. If none are specified, open an empty buffer. If multiple files are specified, open one buffer for each file. To switch between buffers, use the :next and :previous commands.

-
Read text from standard input until EOF, then open a buffer with that text. Commands are read from standard error, which should be a terminal.

-t tag
The file to edit and the initial cursor position depends on a tag, a sort of goto label. tag is looked up in the tags file, the associated file becomes the current file and the associated command is executed. If tag is a function name, the file containing that function is opened with the cursor positioned at the start of the function. See :help tag-commands.

-q [errorfile]
QuickFix mode. Display the first error in errorfile. If errorfile is omitted, the value of the 'errorfile' option is used (defaults to errors.err). Further errors can be jumped to with the :cnext command. See :help quickfix.

There are a number of other options:--
Interpret all further arguments as files. Can be used to edit files starting with a hyphen (‘-’).

--literal
Interpret filenames literally, that is, do not expand wildcards. Has no effect on Unix-like systems, where the shell expands wildcards.

-e
Ex mode. See :help Ex-mode.

-E
Improved Ex mode. See :help gQ.

-s
Silent mode. Only takes effect if -e or -E is specified before it.

-d
Diff mode. Show the difference between two to four files, similar to sdiff(1). See :help diff.

-R
Read-only mode. Sets the option 'readonly'. Implies -n. Buffers can still be edited, but cannot be written to disk if already associated with a file. To overwrite a file, add an exclamation mark to the needed Ex command, such as :w!. See :help 'readonly'.

-Z
Restricted mode. Disable commands that make use of an external shell.

-m
Disable file modifications. Unsets the option 'write'. Writing to a file is disabled, but buffers can still be modified.

-M
Disable file and buffer modifications. Unsets the options 'write' and 'modifiable'. Note that these options can be set to re-enable making modifications.

-b
Binary mode. See :help edit-binary.

-l
Lisp mode. Sets the options 'lisp' and 'showmatch'.

-A
Arabic mode. Sets the option 'arabic'.

-F
Farsi mode. Sets the options 'fkmap' and 'rightleft'.

-H
Hebrew mode. Sets the options 'hkmap' and 'rightleft'.

-V[N][file]
Verbose mode. Print messages about which files are being sourced and for reading and writing a ShaDa file. N is the value for the 'verbose' option; defaults to 10 if omitted. If file is specified, append messages to file instead of printing them.

-D
Debugging mode. Started when executing the first command from a script.

-n
Disable the use of swap files. Sets the option 'updatecount' to 0. Can be useful for editing file(s) on a slow medium.

-r [file]
Recovery mode. If file is omitted then list swap files with recovery information. Otherwise the swap file file is used to recover a crashed session. The swap file has the same name as the file it's associated with, but with ‘.swp’ appended. See :help recovery.

-L [file]
Alias for -r.

-u vimrc
Use vimrc instead of the default of ~/.config/nvim/init.vim. If vimrc is NORC, do not load any initialization files (excluding plugins), and do not attempt to parse environment variables. If vimrc is NONE, loading plugins is also skipped. See :help initialization.

-i shada
Use shada instead of the default of ~/.local/share/nvim/shada/main.shada. If shada is NONE, do not read or write a ShaDa file. See :help shada.

--noplugin
Skip loading plugins. Implied by -u NONE.

-o[N]
Open N windows stacked horizontally. If N is omitted, open one window for each file. If N is less than the number of file arguments, allocate windows for the first N files and hide the rest.

-O[N]
Like -o, but tile windows vertically.

-p[N]
Like -o, but for tab pages.

+[linenum]
For the first file, position the cursor on line linenum. If linenum is omitted, position the cursor on the last line of the file. Note that +5 and -c 5 on the command-line are equivalent to :5 inside nvim.

+/[pattern]
For the first file, position the cursor on the first occurrence of pattern. If pattern is omitted, the most recently used search pattern is used (if there is one). Note that +/foo and -c /foo on the command-line are equivalent to /foo and :/foo inside nvim. See :help search-pattern.

-c command
Execute command after reading the first file. Up to 10 instances of -c or + can be used. Note that “+set si” and -c "set si" are equivalent.

--cmd command
Like -c, but execute command before processing any vimrc. Up to 10 instances of these can be used independently from instances of -c.

-S [session]
Source session after the first file argument has been read. Equivalent to -c "source session". session cannot start with a hyphen (‘-’). If session is omitted, then Session.vim, if found, is used. See :help session-file.

-s scriptin
Read normal mode commands from scriptin. The same can be done with the command :source! scriptin. If the end of the file is reached before nvim exits, further characters are read from the keyboard.

-w scriptout
Append all typed characters to scriptout. Can be used for creating a script to be used with -s or :source!.

-W scriptout
Like -w, but truncate scriptout.

--startuptime file
During startup, append timing messages to file. Can be used to diagnose slow startup times.

--api-info
Dump API metadata serialized to msgpack and exit.

--embed
Use standard input and standard output as a msgpack-rpc channel. Implies --headless.

--headless
Do not start a user interface.

-h, --help
Print usage information and exit.

-v, --version
Print version information and exit.

Environment
VIM
Used to locate various user files, such as the user's init.vim.

VIMRUNTIME
Used to locate run time files, such as on-line documentation and syntax highlighting definitions.

XDG_CONFIG_HOME
Path to use for the user-local configuration directory, see Files. Defaults to ~/.config if not set.

XDG_DATA_HOME
Like XDG_CONFIG_HOME, but used to store data not generally edited by the user, namely swap, backup, and ShaDa files. Defaults to ~/.local/share if not set.

VIMINIT
A string of Ex commands to be executed at startup. For example, the command to quit is :q, so to have nvim quit immediately after starting, set VIMINIT to q. See :help VIMINIT.

SHELL
Used to set the 'shell' option, which determines the shell used by the :terminal command.

Files
~/.config/nvim/init.vim
The user-local nvim configuration file. See XDG_CONFIG_HOME above.

~/.config/nvim
The user-local nvim configuration directory. See XDG_CONFIG_HOME above.

$VIM/sysinit.vim
The system-global nvim configuration file.

/usr/local/share/nvim
The system-global nvim runtime directory.

Authors
nvim was started by Thiago de Arruda, with a lot of help from others.

Most of Vim was written by Bram Moolenaar, with a lot of help from others. See :help credits.

Vim is based on Stevie, worked on by Tim Thompson, Tony Andrews, and G.R. (Fred) Walter.

Info
January 28, 2016