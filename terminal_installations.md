
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

Use the Windows key to search for 'Terminal' (Windows 11) or 'PowerShell' (Windows 10). This guide uses **PowerShell** for all Windows commands. Command Prompt uses different commands, so it isn't covered here.

PowerShell has more modern features while Command Prompt is simpler for basic commands and often is easier to debug.

If Windows Terminal isn't installed (common on Windows 10), install it:

```powershell
winget install Microsoft.WindowsTerminal
```

To see which PowerShell version you have:

```powershell
$PSVersionTable.PSVersion
```

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

1. Anaconda is a python package ('distribution') that includes the data science libraries and the Python programming language and interpreter, but does not have a built-in IDE. Instead, it supports IDEs like Jupyter Notebook/JupyterLab, VS Code, and spyder. 
- Python specific.
- Must be run with a 3rd party IDE. i recommend Jupyter Notebook or VS Code.
2. Visual Studio Code is the Microsoft code editor that works with many different languages with extensions and installations. In other words, it is not an IDE, but mimics one with extensions. 
- Works with the most languages and designed for web development. Also does Data Science well and is a lightweight version of Visual Studio.
- Supports Windows, MacOS, and Linux.
- Programming languages: Python, JavaScript, C, C++, C#, Go, Dart, R, Rust, Swift, TypeScript, Java, HTML, and more.
3. Visual Studio (Microsoft compatible only) is the Microsoft IDE which means it has the most robust compiler and diagnostic tools.
- Can handle intense and large apps, including unity game development. 
- Only supported on Windows.


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
## File System Navigation

| Task                        | Mac/Linux                           | Windows (PowerShell)                              |
| --------------------------- | ----------------------------------- | ------------------------------------------------- |
| Show working directory      | `pwd`                               | `pwd`                                             |
| List directory contents     | `ls`                                | `ls`                                              |
| List including hidden files | `ls -a`                             | `ls -Force`                                       |
| List with more info         | `ls -l`                             | `ls` (already shows dates and sizes)              |
| List in reverse order       | `ls -r`                             | `ls \| Sort-Object Name -Descending`              |
| Change to home directory    | `cd`                                | `cd ~`                                            |
| Change to a directory       | `cd [dirname]`                      | `cd [dirname]`                                    |
| Change to home directory    | `cd ~`                              | `cd ~`                                            |
| Change to parent directory  | `cd ..`                             | `cd ..`                                           |
| Change to previous directory| `cd -`                              | `cd -` (PowerShell 7 only)                        |
| Find a file                 | `find [dirtosearch] -name [filename]` | `ls [dirtosearch] -Recurse -Filter [filename]`  |


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
| Task                        | Mac/Linux                    | Windows (PowerShell)                          |
| --------------------------- | ---------------------------- | --------------------------------------------- |
| Make directory              | `mkdir [dirname]`            | `mkdir [dirname]`                             |
| Create file                 | `touch [filename]`           | `New-Item [filename]`                         |
| Remove file                 | `rm [filename]`              | `rm [filename]`                               |
| Remove file, ask first      | `rm -i [filename]`           | `rm [filename] -Confirm`                      |
| Remove directory            | `rm -r [dirname]`            | `rm -Recurse [dirname]`                       |
| Remove non-hidden items in the current folder | `rm ./*`   | `rm .\*`                                      |
| Copy file                   | `cp [filename] [dirname]`    | `cp [filename] [dirname]`                     |
| Copy directory              | `cp -r [dirname] [newname]`  | `cp -Recurse [dirname] [newname]`             |
| Move file                   | `mv [filename] [dirname]`    | `mv [filename] [dirname]`                     |
| Move directory              | `mv [dirname] [dirname]`     | `mv [dirname] [dirname]`                      |
| Rename file or folder       | `mv [filename] [filename]`   | `mv [filename] [filename]`                    |
| Rename, print what happened | `mv -v [old] [new]`          | `mv [old] [new] -Verbose`                     |

<p align="right">(<a href="#readme-top">back to top</a>)</p>
