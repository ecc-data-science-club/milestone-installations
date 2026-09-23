
<!-- terminal information -->

# **About the Terminal**

Mac uses a Unix-based shell environment, bash and zsh, and Windows uses a native environment called Command Prompt or PowerShell.

These environments are called terminals and they allow us to run and install programs. This guide will tell you where to find the terminals, how to install the package managers, and the general shortcut keys for using the terminal.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#**About-the-Terminal**
">About the Terminal</a>
      <ul>
        <li><a href="#Mac-Terminal-Installation">Mac Terminal Installation</a></li>
        <li><a href="#Windows-Terminal-Installation">Windows Terminal Installation</a></li>
        <li><a href="#Next-Steps">Next Steps</a></li>
        <li><a href="#Useful-General-Computer-Commands">Useful General Computer commands</a></li>
        <li><a href="#Common-Terminal-Commands">Common Terminal Commands</a></li>
        
      </ul>
    </li>
  </ol>
</details>

## Mac Terminal Installation

### Locate Terminal

Use Spotlight (magnifying glass icon) in the upper right hand corner and search for 'Terminal', or search for 'Terminal' in Apps. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Package Manager

Homebrew is a package manager for macOS and installs command-line tools and mac Apps. It's necessary to download the rest of the Mac applications.

Install it from [brew.sh](https://brew.sh/)
<!-- insert image here  -->

Verify your installation with this command: 

```sh
brew --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Windows Terminal Installation

### Windows Terminal

Use the Windows key to search for either the built-in 'Command Prompt' or 'PowerShell.' PowerShell has more modern features while Command Prompt is simpler for basic commands and often is easier to debug.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Package Manager

Windows uses the built in winget package manager command-line tool for installing, upgrading and removing applications in Windows 10 and 11.

We will use it to install Visual Studio code. 

Verify it is installed:
```sh
winget --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Next Steps

From here, go to the next installation guide depending on what type of coding you want to do.

1. Anaconda is a python package ('distribution') that includes the data science libraries and the Python programming language and interpreter, but does not include an IDE. Instead, it supports IDEs like Jupyter Notebook/JupyterLab, VS Code, and spyder. 
- Python specific.
- Must be run with a 3rd party IDE. i recommend Jupyter Notebook or VS Code.
2. Visual Studio Code is the Microsoft code editor that works with many different languages with extensions and installations. In other words, it is not an IDE, but mimics one with extensions. 
- Works with the most languages and designed for web development. Also does Data Science well and is a lightweight version of Visual Studio.
- Supports Microsoft, MacOS, and Linux.
- Programming languages: Python, JavaScript, C, C++, C#, Go, Dart, R, Rust, Swift, TypeScript, Java, HTML, and more.
3. Visual Studio (Microsoft compatible only) is the Microsoft IDE which means it has the most robust compiler and diagnostic tools.
- Can handle intense and large apps, including unity game development. 
- Only supported on Microsoft.


## Useful General Computer commands

| Command                      | Windows                |    Mac                |
| ---------------------------- | ---------------------- | --------------------- |
| copy                         | Ctrl+C                 | command+C             |
| cut                          | Ctrl+X                 | command+X             |
| paste                        | Ctrl+V                 | command+V             |
| undo                         | Ctrl+Z                 | command+Z             |
| save                         | Ctrl+S                 | command+S             |
| open                         | Ctrl+O                 | command+O             |             
| lock pc                      | windows key + L        | command+Control+Q     |
| search                       | windows key + S        | command+space         |
| close a document/tab         | Ctrl+W                 | command+W             |
| switch apps                  | alt+tab                | command+tab           |
| minimize all windows         | windows key + M        | command+option+M      |
| select all                   | Ctr+A                  | command+A             |

Tip: Be careful not to use ctrl+C inside a terminal because it will cancel the running command.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Common Terminal Commands

### Key Commands & Navigation

Before we look at some common commands, I just want to note a few keyboard commands that are very helpful:

- `Up Arrow`: Will show your last command
- `Down Arrow`: Will show your next command
- `Tab`: Will auto-complete your command
- `Ctrl + L`: Will clear the screen
- `Ctrl + C`: Will cancel a command
- `Ctrl + R`: Will search for a command
- `Ctrl + D`: Will exit the terminal

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### File System Navigation

Commands to navigate your file system are very important. You will be using them all the time. You won't remember every single command that you use, but these are the ones that you should remember.

| Command                             | Description                                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------- |
| pwd                                 | Lists the path to the working directory                                           |
| ls                                  | List directory contents                                                           |
| ls -a                               | List contents including hidden files (Files that begin with a dot)                |
| ls -l                               | List contents with more info including permissions (long listing)                 |
| ls -r                               | List contents reverse order                                                       |
| cd                                  | Change directory to home                                                          |
| cd [dirname]                        | Change directory to specific directory                                            |
| cd ~                                | Change to home directory                                                          |
| cd ..                               | Change to parent directory                                                        |
| cd -                                | Change to previous directory (which could be different than the parent of course) |
| find [dirtosearch] -name [filename] | Find location of a file                                                           |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Shortcuts for editing in files
| Command                     | Windows                      | Mac
| --------------------------- | ---------------------------- | -------------------- |
| insert comment              | Ctrl+/                       | command+/            |
| indent/tab                  | tab                          | tab                  |
| back indent/back tab        | shift+tab                    | shift+tab            |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Opening a Folder or File

If you want to open a file or a folder in the GUI from your terminal, the command is different depending on the OS.

Mac - `open [dirname]`
Windows - `start [dirname]`
Linux - `xdg-open [dirname]`

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Modifying Files & Directories

| Mac Command                 | Description                                         |
| --------------------------- | --------------------------------------------------- |
| mkdir [dirname]             | Make directory                                      |
| touch [filename]            | Create file                                         |
| rm [filename]               | Remove file                                         |
| rm -i [filename]            | Remove a file, but ask before                       |
| rm -r [dirname]             | Remove directory                                    |
| rm ./\*                     | Remove non-hidden items in the current folder       |
| cp [filename] [dirname]     | Copy file                                           |
| mv [filename] [dirname]     | Move file                                           |
| mv [dirname] [dirname]      | Move directory                                      |
| mv [filename] [filename]    | Rename file or folder                               |
| mv [filename] [filename] -v | Rename Verbose - print source/destination directory |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### The `echo` Command

The `echo` command is used to display messages, or to create and write to files. It is similar to the `cat` command, but it is used to display a single line of text.

```bash
  echo "Hello World"
```

You can also use it to create a file:

```bash
  echo "Hello World" > [filename]
```

You can also append to a file:

```bash
  echo "Hello World" >> [filename]
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### The `head` and `tail` Commands

The `head` command is used to output the first part of files. By default, it outputs the first 10 lines of each file. You can also specify the number of lines to output.

```bash
  head [filename]
```

You can also specify the number of lines to output:

```bash
  head -n 5 [filename]
```

The `tail` command is used to output the last part of files. By default, it outputs the last 10 lines of each file. You can also specify the number of lines to output.

```bash
  tail [filename]
```

You can also specify the number of lines to output:

```bash
  tail -n 5 [filename]
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### The `find` command

The `find` command is extremely powerful and is used to find the location of files and directories based on conditions that you specify.

```bash
  find [dirname] -name [filename]
```

Let's find the file called `file-001.txt`:

```bash
  find . -name "file-001.txt"
```
This will look in the current directory, which is represented with a dot.

<p align="right">(<a href="#readme-top">back to top</a>)</p>