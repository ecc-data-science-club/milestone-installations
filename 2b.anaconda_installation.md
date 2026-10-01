<!-- for writing git and terminal instructions for anaconda -->
<!-- does this have a git /github setup -->
<a id="readme-top"></a>

# Anaconda for Data Science

Anaconda is a python package ('distribution') that includes the data science libraries and the Python programming language and interpreter, but does not have a built-in IDE. Instead, it supports IDEs like Jupyter Notebook/JupyterLab, VS Code, and spyder.

It installs Python along with `conda`, a tool for installing packages and keeping each project's packages in separate environments.

This guide assumes you have completed `terminal_installations.md`. There are **Mac** and **Windows** sections for OS specific instructions and shared sections.


<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#anaconda-or-venv">Anaconda or venv?</a></li>
    <li><a href="#licensing-note">Licensing note</a></li>
    <li><a href="#mac-installation">Mac installation</a></li>
    <li><a href="#windows-installation">Windows installation</a></li>
    <li><a href="#create-and-use-an-environment">Create and use an environment</a></li>
    <li><a href="#use-anaconda-in-vs-code">Use Anaconda in VS Code</a></li>
    <li><a href="#jupyter-and-anaconda-navigator">Jupyter and Anaconda Navigator</a></li>
    <li><a href="#share-your-environment">Share your environment</a></li>
    <li><a href="#use-git-with-your-anaconda-project">Use Git with your Anaconda Project</a></li>
    <li><a href="#common-conda-commands">Common conda commands</a></li>
    <li><a href="#troubleshooting">Troubleshooting</a></li>
  </ol>
</details>



## Anaconda or venv?

Both tools create isolated Python environments, so pick one per project.

| | Anaconda (`conda`) | `venv` + `pip` |
| --- | --- | --- |
| Comes with | Python, conda, and hundreds of data science packages | Nothing extra (you install Python and packages yourself) |
| Download size | Large (several GB) | Small |
| Best for | Data science, especially packages with hard-to-install dependencies | Lightweight projects, web development |
| Guide | This guide | Python in VS Code guide |

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Mac Installation

### 1. Check your chip

Anaconda has separate installers for Apple Silicon and Intel Macs. Run this in the terminal:

```sh
uname -m
```

- `arm64` means Apple Silicon (M1 or newer). Download the **Apple Silicon (ARM64)** installer.
- `x86_64` means Intel. Download the **Intel (x86_64)** installer.

### 2. Download and run the installer

1. Go to [anaconda.com/download](https://www.anaconda.com/download) and download the macOS installer for your chip.
2. Double-click the downloaded `.pkg` file and click through the prompts.
3. When asked where to install, choose **Install for me only** if it's offered. This installs into your home folder and doesn't need admin rights. If the installer uses `/opt/anaconda3` instead, that works too.

<!-- insert image here -->

**Alternative: Homebrew**

```sh
brew install --cask anaconda
```

Read the "Caveats" text that Homebrew prints when it finishes. It shows the command to activate conda for the first time.

### 3. Restart your terminal and initialize conda

Close and reopen Terminal so it can find `conda`. Then verify:

```sh
conda --version
which conda
python --version
```

`which conda` should print a path inside your Anaconda folder. If you see `conda: command not found`, see [Troubleshooting](#troubleshooting).

Once conda is initialized, you'll see `(base)` at the start of your terminal prompt. That is the default environment. Don't install your project packages into it. Create a separate environment for each project instead.

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Windows Installation

### 1. Download and run the installer

1. Go to [anaconda.com/download](https://www.anaconda.com/download) and download the Windows 64-bit installer.
2. Double-click the `.exe` file and click **Next** through the license agreement.
3. For **Install for**, choose **Just Me (recommended)**.
4. Keep the default destination folder (`C:\Users\your-name\anaconda3`). Avoid paths with spaces or non-English characters, which cause problems with some packages.
5. On the advanced options screen, use these settings. Names may vary slightly by installer version.
   - **Add Anaconda3 to my PATH environment variable:** leave **unchecked**. Anaconda recommends against it, and it can conflict with other Python installations.
   - **Register Anaconda3 as my default Python:** leave **checked**. This lets VS Code find it.
6. Click **Install**, then **Finish**.

<!-- insert image here -->

### 2. Open a conda-enabled terminal

Because PATH was left unchanged, `conda` doesn't work in a regular terminal yet. You have two options:

**Option A: Anaconda Prompt.** Search for **Anaconda Prompt** in the Start menu. Conda works there right away. It is a Command Prompt window, so use it only for `conda` commands. The file and folder commands in your terminal guide are written for PowerShell.

**Option B (recommended): PowerShell.** Run this once in Anaconda Prompt to enable conda in PowerShell and the VS Code terminal:

```sh
conda init powershell
```

Close all terminal windows and open a new PowerShell window. If PowerShell shows a red error about scripts being disabled, run this once, then reopen PowerShell:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### 3. Verify the installation

```powershell
conda --version
where.exe conda
python --version
```

`where.exe conda` should print a path inside your Anaconda folder. Once conda is initialized, you'll see `(base)` at the start of your prompt. That is the default environment. Don't install your project packages into it. Create a separate environment for each project instead.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Create and use an environment

These commands are the same on Mac and Windows. Run them in your conda-enabled terminal.

1. Create an environment with the packages you need:

```sh
   conda create -n data-science pandas numpy matplotlib seaborn scikit-learn jupyterlab ipykernel
```

   Type `y` when asked to proceed. If conda asks you to accept Terms of Service for a package channel, follow the command it prints.

2. Activate it:

```sh
   conda activate data-science
```

   The start of your prompt changes from `(base)` to `(data-science)`.

3. Test it:

```sh
   python -c "import pandas as pd; print(pd.__version__)"
```

4. When you're done:

```sh
   conda deactivate
```

To add a package later, activate the environment and run `conda install package-name`. If a package isn't available through conda, use `python -m pip install package-name` inside the activated environment. Try conda first, since mixing the two tools carelessly can cause conflicts.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Use Anaconda in VS Code

1. Install the **Python** and **Jupyter** extensions (Microsoft). Open the Extensions view with `Ctrl+Shift+X` (Windows) or `Cmd+Shift+X` (Mac).
2. Open your project folder with `code .`.
3. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`), run **Python: Select Interpreter**, and choose the entry labeled `data-science` (conda). If it isn't listed, choose **Enter interpreter path** and browse to your Anaconda folder's `envs` directory, then `data-science`.
4. For notebooks (`.ipynb`), click **Select Kernel** in the top right and choose the same environment. The environment needs `ipykernel`, which the create command above includes.
5. Open the built-in terminal with `` Ctrl+` ``. VS Code activates the selected environment for you, and `(data-science)` appears in the prompt.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Jupyter and Anaconda Navigator

**JupyterLab.** From your activated environment, in your project folder:

```sh
jupyter lab
```

It opens in your browser. Press `Ctrl+C` in the terminal to stop it.

**Anaconda Navigator.** Open it from Launchpad (Mac) or the Start menu (Windows), or run:

```sh
anaconda-navigator
```

Navigator lets you launch JupyterLab and Spyder and manage environments with buttons instead of commands.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Share your environment

Export the packages you installed so others (or you, on another computer) can recreate the environment:

```sh
conda env export --from-history > environment.yml
```

To recreate it:

```sh
conda env create -f environment.yml
```

Commit `environment.yml` to Git. Don't commit the environment folder itself.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Use Git with your Anaconda project

**Git** tracks the history of your project on your computer so you can go back to earlier versions. Git is not included with Anaconda, so this section covers setting it up. You don't need `conda install git`. Use one copy of Git installed on your computer.

### Install Git

**Mac**

Check whether Git is already installed:

```sh
git --version
```

Install it with Homebrew:

```sh
brew install git
```

**Windows**

Install it with winget: 

```powershell
winget install Git.Git
```

Or download it from [git-scm.com](https://git-scm.com/). Close and reopen PowerShell, then verify:

```powershell
git --version
```


### Configure Git

Tell Git who you are. This information is attached to every commit:

```sh
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
git config --global init.defaultBranch main
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Common conda commands

| Task | Command |
| --- | --- |
| Check the conda version | `conda --version` |
| Update conda | `conda update conda` |
| List environments | `conda env list` |
| Create an environment | `conda create -n name package1 package2` |
| Activate / deactivate | `conda activate name` / `conda deactivate` |
| Install a package | `conda install package-name` |
| Remove a package | `conda remove package-name` |
| List installed packages | `conda list` |
| Delete an environment | `conda env remove -n name` |
| Stop `(base)` from activating automatically | `conda config --set auto_activate false` (named `auto_activate_base` in older conda versions) |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Troubleshooting

**Mac**

- **`conda: command not found`:** Open a new terminal window first. If it still fails, initialize conda with the full path to your install, then open a new terminal:

```sh
  ~/anaconda3/bin/conda init zsh
```

  Use `/opt/anaconda3/bin/conda init zsh` if you installed system-wide.
- **Slow performance or Rosetta prompts on an M-series Mac:** You may have installed the Intel version. Check with `python -c "import platform; print(platform.machine())"`. It should print `arm64`. If not, reinstall using the Apple Silicon installer.

**Windows**

- **`conda` is not recognized in PowerShell:** Run `conda init powershell` from Anaconda Prompt, then open a new PowerShell window.
- **Script execution is disabled:** Run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`, then reopen PowerShell.
- **Install fails or packages break:** Check that your install path has no spaces or non-English characters.

**Both**

- **`ModuleNotFoundError` in VS Code:** The wrong interpreter or kernel is selected. Reselect your conda environment.
- **Environment not listed in VS Code:** Reload the window (Command Palette → **Developer: Reload Window**) and check again.
- **Package conflicts:** Create a fresh environment instead of repairing a broken one. It's faster.

<p align="right">(<a href="#readme-top">back to top</a>)</p>