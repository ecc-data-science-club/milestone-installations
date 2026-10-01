<a id="readme-top"></a>
# Visual Studio Code and Git

This guide assumes that you have done the installations from `terminal_installations.md` and have chosen to code using the VS Code editor. 

There are **Mac** and **Windows** sections for OS specific instructions and shared sections.

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#install-vs-code">Install VS Code</a>
      <ul>
        <li><a href="#mac">Mac</a></li>
        <li><a href="#windows">Windows</a></li>
      </ul>
    </li>
    <li><a href="#git-and-github">Git and GitHub</a>
      <ul>
        <li><a href="#what-is-version-control">What is version control?</a></li>
        <li><a href="#what-is-github">What is GitHub?</a></li>
        <li><a href="#install-git">Install Git</a></li>
        <li><a href="#configure-git">Configure Git</a></li>
        <li><a href="#connect-to-github">Connect to GitHub</a></li>
        <li><a href="#create-and-push-your-first-repository">Create and push your first repository</a></li>
        <li><a href="#everyday-git-commands">Everyday Git commands</a></li>
      </ul>
    </li>
  </ol>
</details>

## Install VS Code

### Mac Installation

1. Install with homebrew:

```sh
brew install --cask visual-studio-code
```

or download it manually from here: [VS Code](https://code.visualstudio.com/)
<!-- insert image here -->

2. Open VS Code from your Applications folder


3. Install the 'code' CLI command so you can launch VS Code from the terminal:
- Open the Command Palette with 'Cmd+Shift+P'
- Type 'Shell Command: Install 'code' command in PATH' and press 'enter'

4. Restart your terminal and verify the installation:

```sh
   code --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Windows Installation

1. install with winget

Type in your terminal: 

```sh
winget install Microsoft.VisualStudioCode
```

Or download it manually from here: [VS Code](https://code.visualstudio.com/download)

<!-- insert image here -->

2. Open a new terminal and verify the installation:

```sh
   code --version
```

This installer adds 'code' by default.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Git Version Control and GitHub 


### What is version control and why is it important?
**Version control** is a system that records changes to a file or set of files over time so that you can recall specific versions later. It can be used to track changes, revert to a version before a bug developed and see who last edited a block of code. 

Git is a version control system that works with [Visual Studio Code](https://code.visualstudio.com/) and [Anaconda](https://www.anaconda.com/download) and uses the terminal to run those commands. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### What is GitHub and why is it important?
**GitHub** is a cloud-based hosting service for Git repositories. While Git is the local tool that tracks your code history on your machine, GitHub lets you store that history remotely, collaborate with others, share projects, and back up your work.

For the moment, unless you want to create your own website, GitHub is the best way to host your portfolio projects. It also makes it very easy for people to be able to clone and test your code themselves. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Install Git

First, create a free account at [github.com](https://github.com/). Use a professional username, preferably as close to your real name as possible since it appears in your profile URL and your repository links.

### Mac Installation

For any application you open and edit on your computer, that is a local file. Any application that is stored on your GitHub account is your remote copy. 

To push your local repository to your remote repository or make changes to the remote copy, you need to have a connection from your terminal to your GitHub account. 

On the bottom left corner of VS Code is your Account that can manage extensions. Let's connect your VS Code to GitHub and add version control. 

1. Install Git with brew

Type into the terminal:

```sh
brew install git
```

Or download it here: [git](https://git-scm.com/install/mac)

<p align="right">(<a href="#readme-top">back to top</a>)</p>


### Windows Git Installation

For any application you open and edit on your computer, that is a local file. Any application that is stored on your GitHub account is your remote copy. 

To push your local repository to your remote repository or make changes to the remote copy, you need to have a connection from your terminal to your GitHub account. 

On the bottom left corner of VS Code is a profile that can manage extensions. Let's connect your VS Code to GitHub and add version control. 

1. Install git with winget

Type into the terminal:

```sh
winget install Git.Git
```

Or download it here: [git](https://git-scm.com/install/windows)

Restart your terminal.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


### configure Git

1. Set your configuration to identify the user in commits:

```sh
git config --global user.name "John Doe"
git config --global user.email johndoe@example.com
```

<!-- insert auth-prompt image -->

<!-- Insert vscode-extension image here  -->



### Connect to GitHub

To push your local work to GitHub, your computer needs to be authenticated with your account.

1. **In VS Code:** click the **Accounts** icon in the bottom left corner and choose **Sign in with GitHub**. This lets VS Code's Source Control panel work with your repositories.

   <!-- insert auth-prompt image -->

2. **In the terminal:** signing in through VS Code may not cover `git push` from the terminal. Use one of these:
   - **Windows:** Git Credential Manager is included with Git for Windows. The first time you push, a browser window opens for you to sign in.
   - **Mac (or any system):** install the GitHub CLI and log in:

```sh
     brew install gh
     gh auth login
```

Follow the prompts and choose HTTPS when asked for a protocol.


For **Next Steps** on creating, pushing, and pull GitHub repositories, go to github_guide.

<p align="right">(<a href="#readme-top">back to top</a>)</p>