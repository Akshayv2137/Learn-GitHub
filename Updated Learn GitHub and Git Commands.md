<img
  src="/img/git.png"
  width="70"
  align="right"
/>


# 🚀 Learn GitHub and Git Commands

## 📌 About it

> New to Git? Master the fundamentals with this quick guide. We'll cover the most important commands for managing your code. Let's make version control easy; feel free to suggest improvements."

---

## 🧭 Table of Contents

- [📘 What is Git?](#-what-is-git)
- [🔧 Install Git](#-install-git)
- [🙋 Setting Up Your Git Identity](#-setting-up-your-git-identity)
- [🌈 Applying Colour to Git](#-applying-colour-to-git)
- [📁 Initializing a Repository](#-initializing-a-repository-in-an-existing-directory)
- [🔍 Checking File Status](#-checking-the-status-of-your-files)
- [📥 Staging Files](#-staging-files)
- [🧳 Stashing Changes](#-stashing-changes)
- [✅ Committing Files](#-committing-files)
- [🌿 Branching and Merging](#-branching-and-merging)
- [🌍 Working with Remote Branches](#-fetching-and-checking-out-remote-branches)
- [📤 Merging Branch to Main](#-merging-branch-to-trunkmaster)
- [🔗 Updating Local Repo with GitHub](#-updating-local-repo-with-gitHub)
- [🗑️ Git Resetting](#-git-resetting)
- [🌐 Git Remote Management](#-git-remote-management)
- [🔎 Git Grep](#-git-grep)
- [🕵️ Git Blame](#-git-blame)
- [🧭 Git Log Exploration](#-git-log-exploration)
#- [📝Checking What Youre Committing](#-checking-what-youre-committing)
- [📚 Useful Git Commands](#-useful-git-commands)
- [📌 Useful Alias](#-useful-alias)
- [⚔️ Resolving Conflicts in Git](#-resolvingc-onflicts-in-git)
- [🤝 Contributing to a Git Repository](#-contributing-to-a-git-repository)



---

## 📘 What is Git?

Git is a **version control system** — like a powerful "undo" button for your project files, especially code.

### 🔑 Key Features:
1. **Change tracking:** Tracks every modification to your files over time.
2. **Snapshots:** Records the entire state of your project at different points.
3. **Reverts:** Lets you jump back to previous versions if needed.
4. **Collaboration:** Enables multiple developers to work on the same project smoothly.

---

## 🔧 Install Git

**❓ Question:** How do I get Git on my computer?

1. **Download the installer:**
   - Visit: [https://git-scm.com/download](https://git-scm.com/download)
   - Select the installer for your OS (32-bit or 64-bit). If unsure, check system properties.

2. **Run the installation:**
   - Double-click the downloaded file and follow the prompts.
   - Default settings usually work fine.

3. **Verify installation:**
   - Open a Command Prompt (search for "cmd" in the Windows search bar).
   - Run:

     ```sh
     git --version
     ```

   - You should see the version number.

> 💡 **Tip:** Use Git Bash (included with installer) for a Linux-like terminal experience.

🔗 For advanced options: [Installing Git - Official Guide](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

---

## 🙋 Setting Up Your Git Identity

After installing Git, configure your **name** and **email**. This info is attached to every commit.

### 📋 Commands to set globally:

```sh
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```
---
## 🎨 Applying Colour to Git

```sh
git config --global color.ui true
```

This command ensures Git output is colorized for better readability.

---

## 📁 Initializing a Repository in an Existing Directory

To initialize a Git repository:

1. Navigate to your project directory.
2. Run:

```sh
git init
```

This creates a `.git` subdirectory, initializing Git version control.  
⚠️ At this point, none of your project files are tracked.

To start tracking:

### ➕ Add Files

```sh
git add <file>
git add README
```

### ✅ Commit the Files

```sh
git commit -m "Initial project version"
```

---

## 📊 Checking the Status of Your Files

**❓ Question:** How do I check what's happening with my files in Git?

The `git status` command is your best friend for understanding your project's state. Here's how to use it:

**1. Use the command** 
   ```bash
   git status 
   ```
**2. Interpret the output**
### 🔍 What You'll See:

- **Clean working directory:**  
   If you see "nothing to commit (working directory clean)", there are no changes since your last commit.
  
- **Untracked files:**  
New files that Git isn't managing yet will show up as "untracked". Use `git add <file>` to start tracking.

- **Modified files:**  
Git might tell you about modified files or staged changes – giving you a clear picture of what's ready to be committed.

### 🧪 Example:

```bash
$ git status
# On branch master
# Changes not staged for commit:
#   (use "git add <file>..." to update what will be committed)
#
#       modified:   README.md
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
#
#       new_script.py 
```

---

## 📥 Staging Files

**❓ Question:** How do I stage files for commit, and what options are available?
In the process of staging files for commit in a Git repository, several methods are available to effectively manage changes. 
Here's a breakdown of these methods:

### ➕ Stage Specific File 

```sh
git add filename
```

### ➕ Stage All Changes (new, modified, deleted)

```sh
git add -A
```

### ➕ Stage Changes in Current Directory

```sh
git add .
```

### 🔍 Interactive Staging Mode

```sh
git add -p
```
By employing these commands, you can efficiently prepare your changes for the next commit in your Git repository.

> 💡 **Important:**  
> - New files must be added to Git before being tracked.  
> - Use staging to selectively prepare changes before committing.

---

## 🧳 Stashing Changes

**❓ Question:** How do I use Git stash to manage changes temporarily?
Git stash is a handy command that allows you to temporarily "hide" changes in a dirty directory, preserving them for later use. This command is particularly useful when you need to switch branches or perform other operations without committing your changes. 
Here's a breakdown of some common Git stash commands:

### 🗃️ Basic Usage / Stash local changes

```sh
git stash
```

### 📝 Stash local changes with a custom message

```sh
git stash save "this is your custom message"
```

### ♻️ Re-apply the changes you saved in your latest stash

```sh
git stash apply           # latest
```
### ♻️ Re-apply the changes you saved in a given stash number
```sh
git stash apply stash@{1} # specific stash
```

### ❌ Drop a Stash (Drops any stash by its number)

```sh
git stash drop stash@{0}
```

### 🚀 Apply and Remove from Stash (Apply the stash and then immediately drop it from your stack)

```sh
git stash pop
```
### 🚀 'Release' a particular stash from your list of stashes
```sh
git stash pop stash@{stash_number}
```

### 📋 View Stashes (List all stashes)

```sh
git stash list
```

### 🔍 Show Changes

```sh
git stash show
```
### 🔍 See diff details of a given stash number
```sh
git diff stash@{0}
```

> ✅ **When to Use Stash:**  
 - Switching branches:** Quickly jump to a different task without finishing what you're currently working on.
 - Cleaning up: You want to commit some of your work but not everything. Stash the rest for later.
 - Avoiding conflicts:** You need to pull in changes from a teammate, but your own work isn't ready to merge.
 - Experimenting:** Try out an idea but preserve the option to easily revert back to your previous state.

**Remember:** The stash is flexible and powerful. Don't be afraid to use it to keep your workflow organized and avoid losing work!

---

## 📝 Committing Files

**❓ Question:** What are the different ways to commit files in Git?
After staging files, the next step is to commit them using the following commands:

### ✅ Commit Staged Files

```sh
git commit -m "commit message"
```

### ➕ Add & Commit in One Step

```sh
git commit filename -m "commit message"
```

### 🚀 Commit All Tracked Changes

```sh
git commit -am "insert commit message"
```

### ✏️ Amend a Commit

```sh
git commit --amend  # (optionally with a new message)
```

## 🧬 Squashing Commits Together

### 🧠 Interactive Rebase

```sh
git rebase -i
```

Edit commits in your default editor using commands like:

- pick: use commit
-  p, pick = use commit
-  r, reword = use commit, but edit the commit message
-  e, edit = use commit, but pause for amending
-  s, squash = use commit, but merge into the previous commit
-  f, fixup = like "squash", but discard this commit's log message
-  x, exec = execute command (the rest of the line) using shell

### 🧹 Using Reset + Soft Commit

```sh
git reset --soft HEAD~2
git commit
```

> ⚠️ **Warning:** This will rewrite commit history. Force push may be required. Use with caution, especially on shared branches.

---

🧠 Happy Coding! Keep committing with confidence!  
✨ Want to contribute or improve this guide? Feel free to open a PR!

---
Great! Here's how you can integrate your “Additional Information” section cleanly at the end of the 📝 Committing Files section in your GitHub-friendly Markdown guide:

👇 This will keep the flow smooth, professional, and still easy for beginners to understand.

---

### 📌 Additional Information

  - 🧼 Squashing commits using git reset --soft may require force-pushing commits. This is generally acceptable:
  - If you're working on a feature branch
  - Before merging to master/main
  - Before creating a Pull Request
  - 💡 The commands listed above show multiple ways to commit files in Git.
  - 🔧 Techniques such as amending commits and squashing commits help you maintain a clean and understandable commit history.

---

# 🚀 Git Branching, Merging & Remote Management Guide
---
## 🌿 **Branching and Merging**

**❓ Question:** How can you delete a local branch in Git, ensuring it is removed even if it hasn't been merged yet?

Below are essential Git commands for managing branches and merging changes:

### ✅ Creating a Local Branch
```bash
$ git checkout -b branchname
```
Creates and switches to a new branch named `branchname`.

### 🔄 Switching Between Branches
```bash
$ git checkout -
```
Switches between the current and previous branch.

### 📤 Pushing a Local Branch to Remote
```bash
$ git push -u origin branchname
```
Pushes local branch `branchname` to the remote repository.

### 🗑️ Deleting a Local Branch (After Merge)
```bash
$ git branch -d branchname
```
 Deletes a local branch named `branchname` after it has been merged.

### 💣 Force Delete Local Branch (Unmerged)
```bash
$ git branch -D branchname
```
 Deletes a local branch named `branchname`, even if it hasn't been merged yet.

### 🧹 Remove Stale Remote References
```bash
$ git remote prune origin
```
Removes any remote references that are no longer present on the remote repository.

### 📚 Viewing Branches

- All branches (local + remote):
  ```bash
  $ git branch -a
  ```
  Displays all branches, including local and remote ones.

- Merged branches:
  ```bash
  $ git branch -a --merged
  ```
 Shows branches merged into the current branch, both local and remote.

- Unmerged branches:
  ```bash
  $ git branch -a --no-merged
  ```
 Lists branches not yet merged into the current branch, both local and remote.

- Local branches:
  ```bash
  $ git branch
  ```

- Remote branches:
  ```bash
  $ git branch -r
  ```

### 🧬 Rebasing
- Rebase onto master:
  ```bash
  $ git rebase origin/master
  ```

- Push after rebase:
  ```bash
  $ git push origin +branchname
  ```
 Pushes the local branch `branchname` to the remote repository after rebasing.

### 💡 Tips
- Name branches descriptively: `feature-login`, `bugfix-404`
- Switch branches often: Keeps your changes focused within each branch.
- Merge strategically: Decide when and how to bring changes from a branch into your main "master" branch.

---

## 🌐 **Fetching and Checking Out Remote Branches**

**❓ Question:** How can I fetch and check out remote branches in Git?
To fetch and check out remote branches in Git, follow these steps:

### 1️⃣ Fetch Remote Branches
    Fetch all remote branches
```bash
$ git fetch origin
```

### 2️⃣ Checkout Remote Branch
    Create a local working copy of a remote branch
```bash
$ git checkout -b <local-branch-name> origin/<remote-branch-name>
```

### 3️⃣ Delete Remote Branch
    Remove a remote branch reference locally
  ```bash
  $ git branch -rd origin/<branch-name>
  ```

    Delete the remote branch from the repository
  ```bash
  $ git push origin --delete <branch-name>
  ```
  Replace `<branchname>` with the name of the branch you wish to delete. 
  These commands will help you effectively manage remote branches in your Git repository.
---

## 🔁 **Merging Branch to Trunk/Master**

**❓ Question:** How can I merge a branch into the trunk/master using Git?

### 🧭 Step-by-Step

1. Checkout trunk/master: Use the following command to switch to the trunk/master branch:
   ```bash
   $ git checkout trunk/master
   ```

2. Merge your branch: After checking out the trunk/master branch, merge the desired branch (replace `branchname` with the actual name of the branch) using the command:

   ```bash
   $ git merge branchname
   ```

3. Cancel a merge (if needed): If you encounter issues during the merge process and wish to cancel it, utilize the following command:
   ```bash
   $ git merge --abort
   ```
This sequence of commands allows for the seamless integration of changes from a specific branch into the trunk/master branch while providing an option to cancel the merge operation if necessary.t merge --abort

---

## 🔄 **Updating Local Repo with GitHub**

**❓ Question:** How can I update my local repo with changes from GitHub and track branches?

### 🔃 Update Local with GitHub Changes
   To update your local repository with changes from a GitHub repository, you can use the following Git command:
```bash
$ git pull origin master
```
   This command pulls changes from the `master` branch of the remote repository named `origin` into your current local branch.

### 📍 Track an Existing Branch
   If you want to track an existing branch in your local repository to its counterpart on GitHub, use the following command:
```bash
$ git branch --set-upstream-to=origin/foo foo
```
   Replace `foo` with the name of your local branch. This command sets up tracking so that when you push or pull changes, Git knows which branch on the remote repository to synchronize with.

---

## 🔙 **Git Resetting**

**❓ Question:** How can I "undo" things in Git?

### ✨ Common Git Reset Scenarios

1. **Mixed reset with SHA**:
      - To mix your HEAD with a specific commit, enabling actions like splitting a commit:
   ```bash
   $ git reset --mixed [sha]
   ```

2. **Reset file to upstream master**:
   - Resetting a specific file to match the version in the upstream master branch:
   ```bash
   $ git reset HEAD origin/master -- filename
   ```

3. **Reset file to last commit**:
      - Resetting a file to the version from the most recent commit:
   ```bash
   $ git reset HEAD -- filename
   ```

4. **Reset file to commit before last**:
      - Reverting a file to the version before the most recent commit:
   ```bash
   $ git reset HEAD^ -- filename
   ```

5. **Move HEAD to specific commit**:
     - Moving the HEAD pointer to a specific commit:

   ```bash
   $ git reset --hard sha
   ```

6. **Hard reset to latest commit**:
      - Resetting the staging area and working directory to match the most recent commit. This overwrites all changes in the working directory:
   ```bash
   $ git reset --hard
   ```

### ⚠️ Things to Remember
- Use `git log` to find the commit hash.
- Find the commit code: Use git log to find the commit code (like 'abc123') that you want to rewind to.
- Make Backups: If unsure, create a new branch before resetting to protect your work.

---

## 🌍 **Git Remote Management**

**❓ Question:** How can I manage Git remotes, especially on GitHub?

### 🔍 Show Remote Details
To show where 'origin' is pointing to and view tracked branches
```bash
$ git remote show origin
```

### 🔗 View Remote URLs
To display where 'origin' is pointing to
```bash
$ git remote -v
```

### 🔧 Change Remote URL
To change the URL of the 'origin' remote
```bash
$ git remote set-url origin https://github.com/user/repo.git
```

### ➕ Add New Remote (e.g., for forks)
To add a new remote, typically utilized for rebasing from forks
```bash
$ git remote add [NAME] https://github.com/user/fork-repo.git
```

### 📝 Additional Information
- Use `git remote show origin` to get detailed information about the 'origin' remote, including its URL and tracked branches.
- `git remote -v` provides a concise view of the remotes and their associated URLs.
- When changing the URL of the 'origin' remote, ensure to replace `https://github.com/user/repo.git` with the desired repository URL.
- Replace placeholders like `[NAME]` or `repo.git` as needed.
- Great for collaborating and rebasing from forks.

---
## 🔍 Git Grep

**❓ Question:** How can I efficiently search for specific strings within a directory using Git grep?

Git grep is a powerful tool for searching within a Git repository for specific strings or patterns. Here's how you can utilize it effectively:

- **🔹 Basic search:** To search for a string 'something' within a directory, you can use the following command:
  ```sh
  git grep 'something'
  ```

- **🔹 Printing line numbers:** If you want to know the line numbers where matches are found, you can use the `-n` option:
  ```sh
  git grep -n 'something'
  ```

- **🔹 Contextual search (lines before & after):** To see some lines before and after the grepped term for better context, you can use the `-C<number of lines>` option:
  ```sh
  git grep -C<number of lines> 'something'
  ```

- **🔹 Lines before only:** If you're interested in seeing lines before the grepped term, you can use the `-B<number of lines>` option:
  ```sh
  git grep -B<number of lines> 'something'
  ```

- **🔹 Lines after only:** Similarly, to display lines after the grepped term, you can use the `-A<number of lines>` option:
  ```sh
  git grep -A<number of lines> 'something'
  ```

---

## 👤 Git Blame

**❓ Question:** How can I utilize Git Blame to track the alteration history of a file, displaying both the author's name and the corresponding SHA?

- **🔸 Basic Blame:** To display the alteration history of a file with the author's name
  ```sh
  git blame [filename]
  ```

- **🔸 Blame with SHA:** To display the alteration history of a file with the author's name and SHA
  ```sh
  git blame [filename] -l
  ```

**🧠 Explanation:**
Git Blame is a command used to investigate the alteration history of a file within a Git repository. By running `git blame [filename]`
Git Blame shows who last modified each line of a file. The `-l` flag adds the SHA for more context.

**💡 Bonus Tip:** GitHub/GitLab have built-in blame views for easy browsing!

---

## 📜 Git Log Exploration

**❓ Question:** How can I effectively navigate and explore the commit history of a Git repository?
To navigate and explore the commit history within a Git repository, you can utilize various `git log` commands. Here are some options along with their functionalities:

### Common git log usages:

- **📘 Basic commit list:**
- This command displays a comprehensive list of all commits in the repository, providing details such as commit ID, author, date, and commit message.

  ```sh
  git log
  ```

- **📘 Show changes with commits:**
- By adding `-p` flag, you can view not only commit messages but also the changes made in each commit.

  ```sh
  git log -p
  ```

- **📘 Search for expression in history:**
- This command helps to filter commits based on a particular expression or text, aiding in tracking down specific changes.

  ```sh
  git log -S 'something'
  ```

- **📘 Filter by author:**
- By specifying an author's name, you can narrow down the commit history to only show commits made by that specific author.

  ```sh
  git log --author 'Author Name'
  ```

- **📘 Summarized list:**
- This option provides a more concise view of the commit history, showing abbreviated commit IDs along with their messages.

  ```sh
  git log --oneline
  ```

- **📘 Commits since yesterday:**
- To view commits made since the previous day, this command helps in tracking recent changes.

  ```sh
  git log --since=yesterday
  ```

- **📘 Combine author and message filters:**
- This command allows you to search for commits with a specific term in their messages, attributed to a particular author.

  ```sh
  git log --grep "term" --author "name"
  ```
By leveraging these `git log` commands, you can efficiently navigate through the commit history, track changes, and locate relevant information within your Git repository.

---

## ✅ Checking What Youre Committing

**❓ Question:** How can I check for changes made before committing?

- **🔸 Unstaged changes:**
- To view all changes made to files in your local repository (not staged for commit)

  ```sh
  git diff
  ```

- **🔸 Staged changes:**
- To view changes staged for commit
  ```sh
  git diff --cached
  ```

- **🔸 Compare with remote master:**
- To compare changes between your committed files and the remote repository's master branch
  ```sh
  git diff --stat origin/master
  ```

---

## 🛠️ Useful Git Commands

**❓ Question:** How can I efficiently manage and analyze Git repositories using various commands?

- **🔹 Check if a SHA is in production:**
-   This command helps determine if a specific commit is present in the production environment by listing tags containing the commit.

  ```sh
  git tag --contains [sha]
  ```

- **🔹 Number of commits by author:**
-   This command provides the count of commits made by a specific author within the repository.

  ```sh
  git shortlog -s --author 'Author Name'
  ```

- **🔹 List of authors sorted alphabetically:**
-   This command lists authors along with their commit counts in alphabetical order.

  ```sh
  git shortlog -s -n
  ```

- **🔹 Commit comments by a specific author:**
-   This command displays the commit comments and the total number of commits made by a particular author.

  ```sh
  git shortlog -n --author 'Author Name'
  ```

- **🔹 Contributors and commit counts:**
-   This command lists the contributors along with their commit counts.

  ```sh
  git shortlog -s -n
  ```

- **🔹 Undo local changes to a file:**
-   This command discards local changes made to a specific file and reverts it to the last committed state.

  ```sh
  git checkout -- filename
  ```

- **🔹 Show detailed commit info by SHA:**
-   This command provides comprehensive information about a specific commit identified by its SHA hash.

  ```sh
  git cat-file sha -p
  ```

- **🔹 Count added/removed lines by author since a point in time:**
- Show number of lines added and removed from a repository by an author since some time in the past
  ```sh
  git log --author="Author name" --pretty=tformat: --numstat --since=month \
  | awk '{ add += $1; subs += $2; loc += $1 - $2 } \
  END { printf "added lines: %s, removed lines: %s, total lines: %s\n", add, subs, loc }'
  ```

---

## 📎 Additional Information

- 🧩 Replace placeholders like `[sha]`, `filename`, or `'Author Name'` with your actual values.
- 🧠 Understanding and using these commands will greatly enhance your Git productivity.
- ⚙️ All commands work in the terminal—perfect for automation, analysis, and investigation!

---

## ✨ Useful Alias

💬 **Question:** How can I create a useful alias for Git commands, specifically to enhance the display of logs with branch and merge information?

To set up a helpful alias for Git logs, follow these steps:

1. 📝 Open your `.gitconfig` file (located in your home directory).
2. ➕ Add the following alias code snippet under the [alias] section:

```ini
# Shows the log in a more consistent way with the graph for branching and merging
lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

✅ This alias (called lg) enhances the git log by including a visual graph for branches and merges — super handy for understanding history!

### 🎯 Why Aliases Matter:

- ⚡️ **Speed:** Skip repetitive typing.
- 👀 **Clarity:** Better formatting improves visibility.
- 🛠 **Customization:** Tailor Git to your workflow.
- 🔍 **Discoverability:** Wrap complex Git commands in simpler aliases.

---

## 🔧 Resolving Conflicts in Git

### 🛠️ Steps to Resolve Conflicts:

1. 🚨 **Identify Conflicts:**
   Conflicts occur when Git detects changes in the same part of a file that cannot be automatically merged. Use `git status` to identify conflicted files.
   - Use the command:
     ```sh
     git status
     ```
   - This shows files with merge conflicts.

2. 🧠 **Open Conflicted Files:**
   Open the conflicted files in a text editor. Git marks the conflicting sections with `<<<<<<<`, `=======`, and `>>>>>>>`.
   - Conflicted sections will look like this:
     ```
     <<<<<<< HEAD
     your changes
     =======
     incoming changes
     >>>>>>> branch-name
     ```

3. ✏️ **Resolve Conflicts:**
   - Manually edit the file.
   - Choose the correct version or merge both.
   - Remove conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).

4. 💾 **Save Changes** in your editor.
   Save the modified files after resolving conflicts.

5. ✅ **Add Resolved Files:**
   Use to stage the resolved files for the next commit.
   ```sh
   git add <filename>
   ```

6. 📌 **Commit the Resolution:**
   Commit the resolved files using
   ```sh
   git commit -m "Resolved conflicts"
   ```

7. 🚀 **Push the Changes:**
   Push the changes to the remote repository
   ```sh
   git push
   ```

### 📝 Notes:

- ⚠️ **Conflict Markers Explained:**
    Git uses conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) to highlight conflicting sections. The content between `<<<<<<<` and `=======` represents changes from the current branch, while the content between `=======` and `>>>>>>>` represents changes from the incoming branch.

- 🤝 **Manual Conflict Resolution:**  
    Conflict resolution often requires manual intervention to decide which changes to keep. Carefully review the conflicting sections and make adjustments to ensure the desired outcome.

- 🧪 **Test After Resolution:**
    After resolving conflicts, it's essential to test the changes to ensure they function as expected. Run tests or perform manual checks to verify the integrity of the resolved code.

- 💬 **Communicate with Your Team:**  
   When working in a team, communicate with other developers to ensure everyone is aware of conflicts and their resolution. Collaboration and coordination can prevent future conflicts and ensure smoother development workflows.

---

## 🤝 Contributing to a Git Repository

💬 **Question:** How can I contribute to a Git repository? Could you provide a step-by-step guide, especially for beginners?

### 🪜 Steps & Explanation:

1. 🍴 **Fork it!**
   - This creates your personal copy of the repository.

2. 🌿 **Create Your Feature Branch:**
   ```sh
   git checkout -b my-new-feature
   ```
   - Work on your changes in this new branch.

3. 💾 **Commit Your Changes:**
   ```sh
   git commit -m "Add some feature"
   ```
   - Add a message describing what you've done.

4. 📤 **Push to the Branch:**
   ```sh
   git push -u origin my-new-feature
   ```
  - Pushes your changes to the remote repository, specifically to the branch "my-new-feature" on the remote repository named "origin."

5. 📬 **Submit a Pull Request – Cheers!**
   - Visit the repo on GitHub.
   - Click “Compare & pull request” to propose your changes.
   - It's like saying, "Hey, I've made some changes, please review and consider merging them into the main project!"
   

---
