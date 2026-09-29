<!-- for github instructions - creating a repo, cloning, forking, terminal commands -->
<a id="readme-top"></a>

# GitHub for Data Science Projects

GitHub hosts your Git repositories online so you can back up your work, collaborate, and show projects to others. This guide covers creating an account, connecting your computer, and the workflow you'll use every day, with tips for data science projects and building a portfolio.

This guide assumes you have completed `terminal_installations.md` and the VS Code or Anaconda guide. You must have done the git configuration step. 

There are **Mac** and **Windows** sections for OS specific instructions and shared sections.

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#what-github-adds-to-git">What GitHub adds to Git</a></li>
    <li><a href="#create-and-secure-your-account">Create and secure your account</a></li>
    <li><a href="#authenticate-with-github">Authenticate with GitHub</a>
      <ul>
        <li><a href="#mac-authentication">Mac</a></li>
        <li><a href="#windows-authentication">Windows</a></li>
      </ul>
    </li>
    <li><a href="#create-a-repository-and-clone-it">Create a repository and clone it</a></li>
    <li><a href="#everyday-workflow">Everyday workflow</a></li>
    <li><a href="#branches-and-pull-requests">Branches and pull requests</a></li>
    <li><a href="#forks-and-contributing">Forks and contributing</a></li>
    <li><a href="#data-science-repository-tips">Data science repository tips</a></li>
    <li><a href="#build-your-portfolio">Build your portfolio</a></li>
    <li><a href="#undo-mistakes">Undo mistakes</a></li>
    <li><a href="#merge-conflicts">Merge conflicts</a></li>
    <li><a href="#common-commands">Common commands</a></li>
    <li><a href="#troubleshooting">Troubleshooting</a></li>
  </ol>
</details>

## What GitHub adds to Git

Git tracks your project's history on your own computer (the **local repository**). GitHub stores a copy online (the **remote repository**, usually named `origin`). On top of that it adds:

- **Backup and sharing:** your project lives in the cloud. You can collaborate with other people and share code easily.
- **Pull requests:** a way to propose, review, and discuss changes before merging them.
- **Issues:** to-do lists and bug reports for a project.
- **GitHub Pages:** free hosting for simple websites.
- **A public profile:** your portfolio for employers and collaborators.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Create and secure your account

You may have done step 1 in `vs_code_installations.md` but this will be where you should finish setting up your account. 

1. Sign up at [github.com](https://github.com/). Use a professional username, preferably as close to your real name as possible since it appears in your profile URL and your repository links.
2. Turn on two-factor authentication (2FA). In GitHub, open **Settings**, find the **Password and authentication** page, and set up 2FA with an authenticator app or passkey. GitHub requires 2FA for people who contribute code.
3. [Optional] Protect your email address. Under **Settings → Emails**, check **Keep my email addresses private** and **Block command line pushes that expose my email**. Then use the no-reply address shown on that page as your Git `user.email`.


<p align="right">(<a href="#readme-top">back to top</a>)</p>


## Authenticate with GitHub

GitHub no longer accepts your account password for Git commands. Your computer needs to prove who you are another way. The simplest approach on both systems is the GitHub CLI (`gh`), which signs you in through your browser. Follow the Mac or Windows section, then continue.

### Mac authentication

1. Install the GitHub CLI:

```sh
   brew install gh
```

2. Log in:

```sh
   gh auth login
```

3. Answer the prompts:
   - **Account:** GitHub.com
   - **Protocol:** HTTPS
   - **Authenticate Git with your GitHub credentials?** Yes
   - **How would you like to authenticate?** Login with a web browser

4. Copy the one-time code shown in the terminal, press Enter, paste the code into the browser page that opens, and approve the login.

5. Verify:

```sh
   gh auth status
```

The first time you use Git on a Mac, macOS may ask you to install the Command Line Tools. Click **Install** and wait for it to finish.

<!-- insert image here -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>



### Windows authentication

1. Install the GitHub CLI, then **close and reopen PowerShell** so it can find `gh`:

```powershell
   winget install GitHub.cli
```

2. Log in:

```powershell
   gh auth login
```

3. Answer the prompts:
   - **Account:** GitHub.com
   - **Protocol:** HTTPS
   - **Authenticate Git with your GitHub credentials?** Yes
   - **How would you like to authenticate?** Login with a web browser

4. Copy the one-time code shown in the terminal, press Enter, paste the code into the browser page that opens, and approve the login.

5. Verify:

```powershell
   gh auth status
```

Git for Windows also includes **Git Credential Manager**. If you skip `gh`, your first `git push` opens a browser window to sign in, and Git Credential Manager remembers you afterward.

<!-- insert image here -->

<p align="right">(<a href="#readme-top">back to top</a>)</p>



## Everyday workflow commands

All of these commands are done in the terminal.

```sh
git init                              # initializes the repository to Git
git pull origin main                  # get the latest changes first (can also be done after commiting before pushing)
git switch branch-name                # switch to branch that you are editing
git status                            # see what changed
git add .                             # stage all your changes
git add filename                      # stage specific files to commit
git commit -m "Add data cleaning script" # commit your changes to be ready to push to the remote reposity
git push origin branch-name           # upload to GitHub
```

Tips for good commits:
- Commit small, related changes often rather than one giant commit.
- Write a good pull request inside GitHub with detail and visuals. 
- Run `git status` before `git add` so you know what you're staging.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Branches and pull requests

A **branch** is a separate line of work, so you can experiment without touching the working version on `main`. A **pull request** (PR) asks to merge your branch into `main`.

1. Start from an up-to-date `main` and create a branch:

```sh
   git switch main
   git pull
   git switch -c branch-name
```

2. Make changes, then commit and push the branch:

```sh
   git add .
   git commit -m "Message that becomes the Pull Request Title"
   git push -u origin branch-name
```

3. Open a pull request, either with the CLI or by clicking **Compare & pull request** on the repository page:

```sh
   gh pr create --fill
```

Make sure that your pull request is detailed, clear, and with organization. 


4. Review the changes on the **Files changed** tab. You can also perform a **Code Review** where you go over their native code and Copilot suggestions. When you're happy, click **Merge pull request**.

5. Update your local copy and merge branches

```sh
   git switch main
   git pull origin main
   git switch branch-name
   git merge main branch-name
```

On solo projects you can commit directly to `main`, but branches and PRs are good practice for teams and show good habits in a portfolio. By also using branches and commits, you are less likely to make mistakes. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Forks and contributing

A **fork** is your own copy of someone else's repository. You use one to contribute to a project you don't have write access to.

```sh
gh repo fork OWNER/REPOSITORY --clone
cd REPOSITORY
git remote -v
```

`origin` points to your fork. The original is usually added as `upstream`. Make a branch, commit, push it to your fork, and open a pull request from your fork to the original repository. To bring in the original project's newer changes:

```sh
git pull upstream main
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Data science repository tips

**Start with a good `.gitignore`.** For a data science project:

```
.venv/
__pycache__/
.ipynb_checkpoints/
.env
.DS_Store
Thumbs.db
```

Anything listed in the `.gitignore` file is ignored by GitHub, which is great for protecting data like API keys, foreign keys, and sensitive passwords. In fact, you can't even make commits if a foreign key is not properly ignored. But it is a pain to fix if you accidentally attempt to push a foreign key. 


## Build your portfolio

**Write a strong README.** It's the first thing people see. Include:
- The project title and a one-sentence summary
- The question you answered and the main findings (add a chart or screenshot)
- The data source
- How to run it (the environment setup steps)
- The tools and libraries you used

**Pin your best repositories.** On your profile, click **Customize your pins** and choose up to six.

**Host a site with GitHub Pages.** In a repository, go to **Settings → Pages**, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, and save. After a minute or two, your site appears at `https://YOUR-USERNAME.github.io/REPOSITORY/`. This works for static pages such as an exported HTML report.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Undo mistakes

```sh
git log --oneline                        # see recent commits
git restore file.py                      # discard unsaved changes to a file
git restore --staged file.py             # unstage a file (keeps your changes)
git commit --amend -m "Better message"   # fix your last commit (before pushing)
git revert COMMIT-ID                     # undo a pushed commit safely
```

`git reset --hard` discards **all** uncommitted changes permanently, and `git push --force` can overwrite other people's work. Avoid both unless you're sure what they do. Very useful if you accidentally commit a foreign key or something else that is now stuck in your commit history. 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Merge conflicts

A conflict happens when two changes touch the same lines. Git stops and marks the file like this:

```
<<<<<<< HEAD
your version of the line
=======
the other version of the line
>>>>>>> branch-name
```

To resolve it:

1. Open the file in VS Code. Use the **Accept Current Change**, **Accept Incoming Change**, or **Accept Both Changes** buttons above the conflict, or edit the text by hand. Make sure all the `<<<<<<<`, `=======`, and `>>>>>>>` lines are gone.
2. Save the file, then stage and commit:

```sh
   git add file.py
   git commit
```

To avoid most conflicts, run `git pull` before you start working and commit often.

You may also at some point need to commit changes before switching to a main branch and pulling. When you then merge the main into the branch, the terminal may switch to a Vim text editor. It wants you to create a merge commit message. The merge message is already filled in, so you can accept it:

Press Esc (to make sure you're in command mode).
Type :wq and press Enter (write the file and quit).

If you want to edit the message first, press i to start typing, then Esc, then :wq.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Common commands

| Task | Command |
| --- | --- |
| Copy a repository to your computer | `git clone URL` |
| See what changed | `git status` |
| See line-by-line changes | `git diff` |
| Stage all changes | `git add .` |
| Save a commit | `git commit -m "message"` |
| Upload commits | `git push` |
| Download and merge changes | `git pull` |
| Create and switch to a branch | `git switch -c branch-name` |
| Switch branches | `git switch branch-name` |
| List branches | `git branch` |
| See your remotes | `git remote -v` |
| Open a pull request | `gh pr create --fill` |
| Check your GitHub login | `gh auth status` |

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Troubleshooting

- **"Authentication failed" or "password authentication was removed":** GitHub doesn't accept account passwords for Git. Run `gh auth login` (see [Authenticate with GitHub](#authenticate-with-github)).
- **`rejected ... non-fast-forward` or `failed to push some refs`:** GitHub has changes you don't have. Run `git pull`, resolve any conflicts, then `git push` again.
- **`fatal: not a git repository`:** You're not inside a repository folder. Use `cd` to move into it, or run `git init` to create one.
- **Push rejected because of a large file:** The file is over 100 MiB. If it's only in your most recent commit, run `git rm --cached path/to/file`, add it to `.gitignore`, and run `git commit --amend`. If it's further back in your history, ask for help or look up "removing files from a repository's history" in GitHub's docs.
- **`gh: command not found` (Windows):** Close and reopen PowerShell after installing.

<p align="right">(<a href="#readme-top">back to top</a>)</p>