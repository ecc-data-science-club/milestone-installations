
<!-- for git, Github, and terminal information for VS Code -->
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#**Git-version-control-Github-and-other-terminal-installations-for-VS-Code**
">Git version control, Github, and other terminal installations for VS Code</a>
      <ul>
         <li><a href="#What-is-version-control-and-why-is-it-important?">What is version control and why is it important?</a></li>
         <li><a href="#What-is-GitHub-and-why-is-it-important?">What is GitHub and why is it important?</a></li>
        <li><a href="#Mac-Terminal-Installation">Mac Terminal Installation</a></li>
        <li><a href="#Windows-Terminal-Installation">Windows Terminal Installation</a></li>
        <li><a href="#Useful-General-Computer-Commands">Useful General Computer commands</a></li>
        <li><a href="#Common-Terminal-Commands">Common Terminal Commands</a></li>
      </ul>
    </li>
  </ol>
</details>



# **Git version control, Github, and other terminal installations for VS Code**

Mac uses a Unix-based shell environment, bash and zsh, and Windows uses a native environment called Command Prompt or PowerShell.

## What is version control and why is it important?
Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. It can be used to track changes, revert to a version before a bug developed and see who last edited a block of code. 

Git is a version control system that works with Visual Studio Code and uses the terminal to run those commands. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## What is GitHub and why is it important?
GitHub is a cloud-based hosting service for Git repositories. While Git is the local tool that tracks your code history on your machine, GitHub lets you store that history remotely, collaborate with others, share projects, and back up your work.

For the moment, unless you want to create your own website, GitHub is the best way to host your portfolio projects. It also makes it very easy for people to be able to clone and test your code themselves. 


<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Mac Terminal Installation
Preferred web browser for web development is Google Chrome for its debugging tools, but using any web browser is fine. 


<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Locate Terminal

Use Spotlight (magnifying glass icon) in the upper right hand corner and search for 'Terminal', or search for 'Terminal' in Apps. 


<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Homebrew 

Homebrew is a package manager for macOS and installs command-line tools and mac Apps. It's necessary to download the rest of the Mac applications.

Install it from [brew.sh](https://brew.sh/)
<!-- insert image here  -->

Verify your installation with this command: 
```sh
brew --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Visual Studio Code installation

[VS Code](https://code.visualstudio.com/)

1. Install with homebrew:
```sh
brew install --cask visual-studio-code
```

<!-- insert image here -->

2. Open VS Code:
```sh
code
```

3. Shell command for code CLI command

If running 'code' in the terminal gives an error, verify that the code CLI was properly installed. 

- On the command palette by pressing Cmd + Shift + P (Mac) or Ctrl + Shift + P (Windows), or typing '>' in the text input on the top.
- Type Shell Command: Install 'code' command in PATH and press Enter.
- Verify the installation with this command:
```sh
code --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Install Git

For any application you open and edit on your computer, that is a local file. Any application that is stored on your GitHub account is your remote copy. 

To push your local version to your remote copy or make changes to the remote copy, you need to have a connection from your terminal to your GitHub account. 

On the bottom left corner of VS Code is a profile that can manage extensions. Let's connect your VS Code to GitHub and add version control. 

1. Create a GitHub account

2. Download git to your computer. 

Install here: [git](https://git-scm.com/install/mac)

3. Open VS Code and sign in to your GitHub account in 'Source Control' on the left vertical navigation bar.

4. Set your configuration to identify the user in commits:
```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

<!-- insert auth-prompt image -->



<!-- Insert vscode-extension image here  -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Useful Javascript Installations

Important! Skip these installations if you are not running Javascript.


#### Node.js/npm or node manager/nvm

Node.js is a free, open-source, cross-platform JavaScript runtime environment that lets developers create servers, web apps, command line tools and scripts. It runs JavaScript outside a web browser and is what allows you to make installations with the 'npm' command. 'npm' is included with Node.js and installs JavaScript packages.

Install here: [Node.js](https://nodejs.org/en/download)

<!-- insert iamge here -->

Verify your installation with these two commands: 
```sh
node -v
npm -v
```

#### Yarn (optional)

Yarn is an alternative package manager for Javascript packages.

Install here: [yarn](https://classic.yarnpkg.com/lang/en/docs/install/#mac-stable)

Use brew to download yarn classic: 
```sh
brew install yarn
```

<!-- insert image here -->

check your installation with command:
```sh
yarn --version
```

#### Node version manager and nvm (optional) 

nvm lets you install and switch between Node.js versions. It can be useful when different projects require different versions and is often preferred for it's greater stability. 

- Install here: [nvm](https://github.com/nvm-sh/nvm#installing-and-updating)
- Run the installation and then restart your terminal.
- Install the latest version:
```sh
nvm install --lts
```
<!-- insert image here -->

- Verify your installation by checking if the file is there: 
```sh
nvm ls
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Windows Terminal Installation


### Windows Terminal


<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Install Visual Studio Code

[VS Code](https://code.visualstudio.com/Download?_exp_download=fb315fc982)


<!-- insert image here -->

2. Open VS Code:
```sh
code
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Install Git

For any application you open and edit on your computer, that is a local file. Any application that is stored on your GitHub account is your remote copy. 

To push your local version to your remote copy or make changes to the remote copy, you need to have a connection from your terminal to your GitHub account. 

On the bottom left corner of VS Code is a profile that can manage extensions. Let's connect your VS Code to GitHub and add version control. 

1. Create a GitHub account

2. Download git to your computer. 

Install here: [git](https://git-scm.com/install/windows)

3. Open VS Code and sign in to your GitHub account in 'Source Control' on the left vertical navigation bar.

4. Set your configuration to identify the user in commits:
```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

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