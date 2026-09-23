# Visual Studio Code and Git

This guide assumes that you have done the installations from terminal_installations.md and have chosen to code using the VS Code editor. 


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#Visual-Studio-Code-And-Git">Visual Studio Code</a>
      <ul>
        <li><a href="#Mac-Installation">Mac Installation</a></li>
        <li><a href="#Windows-Installation">Windows Installation</a></li>
        <li><a href="#Git-Version-Control-and-GitHub">Git Version Control and GitHub </a></li>
        <ul>
         <li><a href="#Mac-Git-Installation">Mac Git Installation </a></li>
         <li><a href="#Windows-Git-Installation">Windows Git Installation </a></li>
         </ul>
      </ul>
    </li>
  </ol>
</details>

## Mac Installation

1. Install with homebrew:

```sh
brew install --cask visual-studio-code
```

or install manually from here: [VS Code](https://code.visualstudio.com/)
<!-- insert image here -->
2. Open VS Code:

```sh
code
```

3. Shell command for code CLI command

If running 'code' in the terminal gives an error, verify that the code CLI was properly installed. 

- Open the Command Palette by pressing Cmd + Shift + P (Mac) or Ctrl + Shift + P (Windows), or typing '>' in the text input on the top.
- Type Shell Command: Install 'code' command in PATH and press Enter.
- Verify the installation with this command:

```sh
code --version
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Windows Installation

1. install with winget:
```sh
winget install Microsoft.VisualStudioCode
```

Or install manually from here: [VS Code](https://code.visualstudio.com/download)

<!-- insert image here -->

2. Open VS Code:

```sh
code
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Git Version Control and GitHub 

### About Git and GitHub 

#### What is version control and why is it important?
Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later. It can be used to track changes, revert to a version before a bug developed and see who last edited a block of code. 

Git is a version control system that works with [Visual Studio Code](https://code.visualstudio.com/) and [Anaconda](https://www.anaconda.com/download) and uses the terminal to run those commands. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

#### What is GitHub and why is it important?
GitHub is a cloud-based hosting service for Git repositories. While Git is the local tool that tracks your code history on your machine, GitHub lets you store that history remotely, collaborate with others, share projects, and back up your work.

For the moment, unless you want to create your own website, GitHub is the best way to host your portfolio projects. It also makes it very easy for people to be able to clone and test your code themselves. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Mac Git Installation

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


### Windows Git Installation

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


<!-- how to install extensions for different languages -->

<!-- using javascript -->

<!-- using python -->