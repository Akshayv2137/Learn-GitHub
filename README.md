<img
  src="/img/git.png"
  width="70"
  align="right"
/>



# Learn GitHub Git Commands


## About it
> New to Git? Master the fundamentals with this quick guide. We'll cover the most important commands for managing your code. Let's make version control easy; feel free to suggest improvements."

## Table of contents

* [What is Git?](#what-is-git?)
* [Install git](#how-do-i-get-git-on-computer?)
* [Setting up git Your Identity](#setting-up-git-your-identity)
* [Applying colour to git ](#applying-colour-to-git)
* [Initializing a repository in an existing directory](#initializing-a-repository-in-an-existing-directory)
* [Checking the status of your files](#checking-the-status-of-your-files)
* [Staging files](#staging-files)
* [Stashing files](#stashing-files)
* [Committing files](#committing-files)
* [Branching and Merging](#branching-and-merging)
* [Fetching and Checking Out Remote Branches](#fetching-and-checking-out-remote-branches)
* [Merging branch to trunk/master](#merging-branch-to-trunk/master)
* [Updating a local repository with changes from a Github repository](#updating-a-local-repository-with-changes-from-a-github-repository)
* [Git Resetting](#git-resetting)
* [Git Remote Management](#git-remote-management)
* [Git grep](#git-grep)
* [Git blame](#git-blame)
* [Git Log Exploration](#git-log-exploration)
* [Checking what you are committing](#checking-what-you-are-committing)
* [Useful Commands](#useful-commands)
* [Useful Alias](#useful-alias)
* [Contributing Git repository](#contributing-git-repository)
* [Resolving Conflicts in Git](#resolving-conflicts-in-git)

#### What is Git?


Git is a version control system. It acts like a powerful "undo" button for your project files, especially code.  Key features include:

Change tracking: Tracks every modification to your files over time.
Snapshots: Records the entire state of your project at different points.
Reverts: Lets you jump back to previous versions if needed.
Collaboration: Enables multiple developers to work on the same project smoothly.

#### Install Git

Absolutely! Here's a longer version of the answer, providing more context without being repetitive:

####How do I get Git on computer?

1. **Download the installer:**
   * Visit the official Git website ([https://git-scm.com/download](https://git-scm.com/download)).
   * Select the installer appropriate for your version of Windows (32-bit or 64-bit). If you're unsure, check your system properties.

2. **Run the installation:**
   * Double-click the downloaded installer file and follow the on-screen instructions. 
   * You can usually accept the default settings during installation.

3. **Verify installation:**
   * Open a Command Prompt (search for "cmd" in the Windows search bar).
   * Type `git --version` and press Enter. If Git is installed correctly, you'll see the installed version number displayed.

**Additional Notes:**
* If you prefer, Git Bash (included with the installer) provides a similar interface to Linux-style command lines.
* For more advanced installation options or troubleshooting, refer to the Git documentation.To view other ways of installing it visit the [Git official site](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
 
### Setting up git Your Identity

- Upon installing Git, it's crucial to set up your user name and email address promptly.
- This information is integral as it's associated with every Git commit, becoming a permanent part of your commit history.

To configure your identity globally, use the following commands:

```sh
$ git config --global user.name "User Name"

$ git config --global user.email "email"
```

##### Applying colour to git

```sh
$ git config --global color.ui true
```

##### Initializing a repository in an existing directory

To initialize a repository in an existing directory:
- Navigate to the project's directory.
- Execute the following command:
```sh
$ git init
```
This command creates a new subdirectory named .git, housing all necessary repository files, essentially establishing a Git repository skeleton. However, it's important to note that, at this stage, none of your project files are yet tracked.

To commence version control for existing files, you must track them and perform an initial commit. Achieve this by:
1. Specifying the files you wish to track using `$ git add`.
   Example:
   ```sh
   $ git add <file>
   $ git add README
   ```
2. Committing the changes with a descriptive message.
   Example:
   ```sh
   $ git commit -m 'Initial project version'
   ```
#### Checking the status of your files

How do I check what's happening with my files in Git?

The `git status` command is your best friend for understanding your project's state. Here's how to use it:

**1. Use the command** 
   ```bash
   git status 
   ```
   
**2. Interpret the output**
   * **Clean working directory:** If you see "nothing to commit (working directory clean)", there are no changes since your last commit.
   * **Untracked files:** New files that Git isn't managing yet will show up as "untracked". Use `git add <file>` to start tracking.
   * **Other statuses:** Git might tell you about modified files or staged changes – giving you a clear picture of what's ready to be committed.

**Example:** 
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


#### Staging files

Question: How do you stage files for commit in a Git repository, and what are the different methods available?

In the process of staging files for commit in a Git repository, several methods are available to effectively manage changes. Here's a breakdown of these methods:

- To stage a specific file, use:
  ```sh
  $ git add filename
  ```

- To stage all files, including new, modified, and deleted ones, utilize:
  ```sh
  $ git add -A
  ```

- Alternatively, to stage changes within a specific directory, apply:
  ```sh
  $ git add .
  ```

- For more granular control over which changes to stage, the interactive staging mode can be employed:
  ```sh
  $ git add -p
  ```

By employing these commands, you can efficiently prepare your changes for the next commit in your Git repository.

Important Notes:

New Files Matter: Remember, git add also introduces completely new files to Git's tracking system.
Think Before You Commit: Staging lets you carefully review and refine what will be permanently saved. Until you git commit, nothing is set in stone.

#### Stashing files
Question: How can I use Git stash effectively to manage changes in a dirty directory, and what are some common commands associated with it?

Git stash is a handy command that allows you to temporarily "hide" changes in a dirty directory, preserving them for later use. This command is particularly useful when you need to switch branches or perform other operations without committing your changes. 
Here's a breakdown of some common Git stash commands:

```sh
# Stash local changes
$ git stash

# Stash local changes with a custom message
$ git stash save "this is your custom message"

# Re-apply the changes you saved in your latest stash
$ git stash apply

# Re-apply the changes you saved in a given stash number
$ git stash apply stash@{stash_number}

# Drops any stash by its number
$ git stash drop stash@{0}

# Apply the stash and then immediately drop it from your stack
$ git stash pop

# 'Release' a particular stash from your list of stashes
$ git stash pop stash@{stash_number}

# List all stashes
$ git stash list

# Show the latest stash changes
$ git stash show

# See diff details of a given stash number
$ git diff stash@{0}
```

These commands provide flexibility in managing stashed changes, allowing you to apply, drop, or list stashes as needed.


When to use the stash:

Switching branches: Quickly jump to a different task without finishing what you're currently working on.
Cleaning up: You want to commit some of your work but not everything. Stash the rest for later.
Avoiding conflicts: You need to pull in changes from a teammate, but your own work isn't ready to merge.
Experimenting: Try out an idea but preserve the option to easily revert back to your previous state.
Remember: The stash is flexible and powerful. Don't be afraid to use it to keep your workflow organized and avoid losing work!

#### Committing files
Question: How can I effectively manage file commits in Git, and what are the different techniques involved in committing files?

After staging files, the next step is to commit them using the following commands:

**Formatted Information:**

#### Committing files

Once files are added or staged, the subsequent step involves committing them.

```sh
# Commit staged file(s)
$ git commit -m 'commit message'

# Add file and commit
$ git commit filename -m 'commit message'

# Add file and commit staged file
$ git commit -am 'insert commit message'

# Amending a commit
$ git commit --amend 'new commit message' or no message to maintain previous message

# Squashing commits together
$ git rebase -i
This will present an interface in your default editor:
# Commands:
#  p, pick = use commit
#  r, reword = use commit, but edit the commit message
#  e, edit = use commit, but pause for amending
#  s, squash = use commit, but merge into the previous commit
#  f, fixup = like "squash", but discard this commit's log message
#  x, exec = execute command (the rest of the line) using shell

# Squashing commits together using reset --soft
$ git reset --soft HEAD~number_of_commits
$ git commit
** WARNING: This action necessitates force pushing commits, which is acceptable if it's on a branch before pushing to master or generating a Pull Request.
```

**Additional Information:**
- Squashing commits using `git reset --soft` may require force pushing commits, which is acceptable if it's on a branch before pushing to master or creating a Pull Request.
- The provided commands illustrate various ways to commit files in Git.
- Techniques such as amending commits and squashing commits together are also explained.


#### Branching and Merging

Question: How can you delete a local branch in Git, ensuring it is removed even if it hasn't been merged yet?

Below are essential Git commands for managing branches and merging changes:

- **Creating a Local Branch:**
  ```
  $ git checkout -b branchname
  ```
  This command creates a new branch named `branchname` and switches to it.

- **Switching Between Branches:**
  ```
  $ git checkout -
  ```
  This command allows you to switch between the current and the previous branch.

- **Pushing a Local Branch to Remote:**
  ```
  $ git push -u origin branchname
  ```
  Use this command to push a local branch `branchname` to the remote repository.

- **Deleting a Local Branch:**
  ```
  $ git branch -d branchname
  ```
  Deletes a local branch named `branchname` after it has been merged.

- **Forced Deletion of a Local Branch:**
  ```
  $ git branch -D branchname
  ```
  Deletes a local branch named `branchname`, even if it hasn't been merged yet.

- **Removing Stale Remote References:**
  ```
  $ git remote prune origin
  ```
  Removes any remote references that are no longer present on the remote repository.

- **Viewing All Branches:**
  ```
  $ git branch -a
  ```
  Displays all branches, including local and remote ones.

- **Viewing Merged Branches:**
  ```
  $ git branch -a --merged
  ```
  Shows branches merged into the current branch, both local and remote.

- **Viewing Unmerged Branches:**
  ```
  $ git branch -a --no-merged
  ```
  Lists branches not yet merged into the current branch, both local and remote.

- **Viewing Local Branches:**
  ```
  $ git branch
  ```
  Lists all local branches.

- **Viewing Remote Branches:**
  ```
  $ git branch -r
  ```
  Lists all remote branches.

- **Rebasing the Master Branch:**
  ```
  $ git rebase origin/master
  ```
  Rebases the current branch onto the `origin/master` branch.

- **Pushing After Rebase:**
  ```
  $ git push origin +branchname
  ```
  Pushes the local branch `branchname` to the remote repository after rebasing.
  
Tips:

Name branches descriptively: (e.g., "new-login-feature", "bugfix-123")
Switch branches often: Keeps your changes focused within each branch.
Merge strategically: Decide when and how to bring changes from a branch into your main "master" branch.

#### Fetching and Checking Out Remote Branches
Question: How can I fetch and check out remote branches in Git, and what commands are involved?

To fetch and check out remote branches in Git, follow these steps:

1. **Fetching Remote Branches:**
   ```sh
   # Fetch all remote branches
   $ git fetch origin
   ```

2. **Checking Out Remote Branches:**
   ```sh
   # Create a local working copy of a remote branch
   $ git checkout -b <local-branch-name> origin/<remote-branch-name>
   ```

3. **Deleting a Remote Branch:**
   ```sh
   # Remove a remote branch reference locally
   $ git branch -rd origin/<branch-name>
   
   # Delete the remote branch from the repository
   $ git push origin --delete <branch-name>
   ```
   Replace `<branchname>` with the name of the branch you wish to delete. 
   
These commands will help you effectively manage remote branches in your Git repository.

#### Merging branch to trunk/master

Question: How can I merge a branch into the trunk/master using Git, specifically on a command-line interface?

To merge a branch into the trunk/master, follow these steps:

1. **Checkout trunk/master**: Use the following command to switch to the trunk/master branch:
   ```sh
   $ git checkout trunk/master
   ```

2. **Merge branch into trunk/master**: After checking out the trunk/master branch, merge the desired branch (replace `branchname` with the actual name of the branch) using the command:
   ```sh
   $ git merge branchname
   ```

3. **Cancel a merge (if needed)**: If you encounter issues during the merge process and wish to cancel it, utilize the following command:
   ```sh
   $ git merge --abort
   ```

This sequence of commands allows for the seamless integration of changes from a specific branch into the trunk/master branch while providing an option to cancel the merge operation if necessary.t merge --abort
```

#### Updating a local repository with changes from a Github repository
Question: How can I update my local repository with changes from a GitHub repository and track an existing branch? 

Instructions and Explanation:

1. **Updating a local repository with changes from a GitHub repository**:
   To update your local repository with changes from a GitHub repository, you can use the following Git command:
   ```sh
   $ git pull origin master
   ```
   This command pulls changes from the `master` branch of the remote repository named `origin` into your current local branch.

2. **Tracking an existing branch**:
   If you want to track an existing branch in your local repository to its counterpart on GitHub, use the following command:
   ```sh
   $ git branch --set-upstream-to=origin/foo foo
   ```
   Replace `foo` with the name of your local branch. This command sets up tracking so that when you push or pull changes, Git knows which branch on the remote repository to synchronize with.
   
#### Git Resetting

Question: How can I "undo" things in Git?

Git provides several options for resetting changes in your repository. 
Below are some common scenarios and their corresponding commands:

1. **Mixing Head with a Given SHA:**
   - To mix your HEAD with a specific commit, enabling actions like splitting a commit:
     ```sh
     $ git reset --mixed [sha]
     ```

2. **Resetting to Upstream Master:**
   - Resetting a specific file to match the version in the upstream master branch:
     ```sh
     $ git reset HEAD origin/master -- filename
     ```

3. **Resetting to Most Recent Commit Version:**
   - Resetting a file to the version from the most recent commit:
     ```sh
     $ git reset HEAD -- filename
     ```

4. **Resetting to Version Before Most Recent Commit:**
   - Reverting a file to the version before the most recent commit:
     ```sh
     $ git reset HEAD^ -- filename
     ```

5. **Moving HEAD to a Specific Commit:**
   - Moving the HEAD pointer to a specific commit:
     ```sh
     $ git reset --hard sha
     ```

6. **Hard Reset:**
   - Resetting the staging area and working directory to match the most recent commit. This overwrites all changes in the working directory:
     ```sh
     $ git reset --hard
     ```
Things to Remember

Find the commit code: Use git log to find the commit code (like 'abc123') that you want to rewind to.
Make Backups: If unsure, create a new branch before resetting to protect your work.

#### Git Remote Management

Question: How can I manage Git remotes and track branches, particularly when working with repositories on GitHub?

To manage Git remotes efficiently, consider the following commands:

1. To show where 'origin' is pointing to and view tracked branches:
   ```sh
   $ git remote show origin
   ```

2. To display where 'origin' is pointing to:
   ```sh
   $ git remote -v
   ```

3. To change the URL of the 'origin' remote:
   ```sh
   $ git remote set-url origin https://github.com/user/repo.git
   ```

4. To add a new remote, typically utilized for rebasing from forks:
   ```sh
   $ git remote add [NAME] https://github.com/user/fork-repo.git
   ```

**Additional Information:**

- Use `git remote show origin` to get detailed information about the 'origin' remote, including its URL and tracked branches.
- `git remote -v` provides a concise view of the remotes and their associated URLs.
- When changing the URL of the 'origin' remote, ensure to replace `https://github.com/user/repo.git` with the desired repository URL.
- Adding a new remote using `git remote add [NAME] https://github.com/user/fork-repo.git` allows for easy collaboration and synchronization, particularly beneficial when rebasing from forks. Replace `[NAME]` with a suitable name for the new remote.

#### Git Grep

Question: How can I efficiently search for specific strings within a directory using Git grep?

Git grep is a powerful tool for searching within a Git repository for specific strings or patterns. Here's how you can utilize it effectively:

- **Basic search**: To search for a string 'something' within a directory, you can use the following command:
  ```sh
  $ git grep 'something'
  ```

- **Printing line numbers**: If you want to know the line numbers where matches are found, you can use the `-n` option:
  ```sh
  $ git grep -n 'something'
  ```

- **Contextual search**: To see some lines before and after the grepped term for better context, you can use the `-C<number of lines>` option:
  ```sh
  $ git grep -C<number of lines> 'something'
  ```

- **Displaying lines before**: If you're interested in seeing lines before the grepped term, you can use the `-B<number of lines>` option:
  ```sh
  $ git grep -B<number of lines> 'something'
  ```

- **Displaying lines after**: Similarly, to display lines after the grepped term, you can use the `-A<number of lines>` option:
  ```sh
  $ git grep -A<number of lines> 'something'
  ```

#### Git Blame

Question: How can I utilize Git Blame to track the alteration history of a file, displaying both the author's name and the corresponding SHA?

```sh
# To display the alteration history of a file with the author's name
$ git blame [filename]

# To display the alteration history of a file with the author's name and SHA
$ git blame [filename] -l
```

Explanation:
Git Blame is a command used to investigate the alteration history of a file within a Git repository. By running `git blame [filename]`, you can view the history of changes made to the specified file along with the name of the author for each change. Adding the `-l` option to the command additionally displays the SHA (Secure Hash Algorithm) associated with each change, providing a more detailed view of the file's revision history.

Bonus Tip: Many Git code platforms (like GitHub or GitLab) have built-in blame views for easy visualization!

#### Git Log Exploration

Question: How can I effectively navigate and explore the commit history of a Git repository on my local machine, especially when searching for specific information or changes?



To navigate and explore the commit history within a Git repository, you can utilize various `git log` commands. Here are some options along with their functionalities:

1. **Basic Commit List:**
```sh
$ git log
```
This command displays a comprehensive list of all commits in the repository, providing details such as commit ID, author, date, and commit message.

2. **Commit Details with Changes:**
```sh
$ git log -p
```
By adding `-p` flag, you can view not only commit messages but also the changes made in each commit.

3. **Search for Specific Expression:**
```sh
$ git log -S 'something'
```
This command helps to filter commits based on a particular expression or text, aiding in tracking down specific changes.

4. **Filter Commits by Author:**
```sh
$ git log --author 'Author Name'
```
By specifying an author's name, you can narrow down the commit history to only show commits made by that specific author.

5. **Summarized Commit List:**
```sh
$ git log --oneline
```
This option provides a more concise view of the commit history, showing abbreviated commit IDs along with their messages.

6. **Commits Since Yesterday:**
```sh
$ git log --since=yesterday
```
To view commits made since the previous day, this command helps in tracking recent changes.

7. **Combining Author and Message Search:**
```sh
$ git log --grep "term" --author "name"
```
This command allows you to search for commits with a specific term in their messages, attributed to a particular author.

By leveraging these `git log` commands, you can efficiently navigate through the commit history, track changes, and locate relevant information within your Git repository.

#### Checking what you are committing

Question: How can I check for changes made to files in my local repository before committing them?
```sh
# To view all changes made to files in your local repository (not staged for commit)
$ git diff

# To view changes staged for commit
$ git diff --cached

# To compare changes between your committed files and the remote repository's master branch
$ git diff --stat origin/master
```
#### Useful commands

Question: How can I efficiently manage and analyze Git repositories using various commands?

- **Check if a sha is in production:**
  ```sh
  $ git tag --contains [sha]
  ```
  This command helps determine if a specific commit is present in the production environment by listing tags containing the commit.

- **Number of commits by author:**
  ```sh
  $ git shortlog -s --author 'Author Name'
  ```
  This command provides the count of commits made by a specific author within the repository.

- **List of authors and commits sorted alphabetically:**
  ```sh
  $ git shortlog -s -n
  ```
  This command lists authors along with their commit counts in alphabetical order.

- **List of commit comments by author:**
  ```sh
  $ git shortlog -n --author 'Author Name'
  ```
  This command displays the commit comments and the total number of commits made by a particular author.

- **Number of commits by contributors:**
  ```sh
  $ git shortlog -s -n
  ```
  This command lists the contributors along with their commit counts.

- **Undo local changes to a File:**
  ```sh
  $ git checkout -- filename
  ```
  This command discards local changes made to a specific file and reverts it to the last committed state.

- **Show more detailed info about a commit:**
  ```sh
  $ git cat-file sha -p
  ```
  This command provides comprehensive information about a specific commit identified by its SHA hash.

- **Show number of lines added and removed from a repository by an author since some time in the past:**
  ```sh
  $ git log --author="Author name" --pretty=tformat: --numstat --since=month | awk '{ add += $1; subs += $2; loc += $1 - $2 } END { printf "added lines: %s, removed lines: %s, total lines: %s\n", add, subs, loc }'
  ```
  
#Additional Information:

These commands offer various functionalities for managing Git repositories efficiently.
Users can customize commands according to their requirements by replacing placeholders such as [sha] and 'Author Name' with actual values.
Understanding and utilizing these commands can enhance productivity and streamline repository management.

#### Useful alias

Question: How can I create a useful alias for Git commands, specifically to enhance the display of logs with branch and merge information?

To set up a useful alias for Git commands, follow these steps:

1. Open your `.gitconfig` file located in your home directory.
2. Add the following alias code snippet to the file:

```sh
# Shows the log in a more consistent way with the graph for branching and merging
lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit
```

This alias, named `lg`, enhances the log display by incorporating a graph for branching and merging, making it easier to visualize the project's history.

Why Aliases Matter:

Speed: Eliminate repetitive typing and focus on the task at hand.
Clarity: Well-constructed aliases bring greater visual order to often complex Git outputs.
Customization: Adapt Git to your preferences and the specific needs of your project.
Discoverability: Aliases can even make less-known Git features more accessible by wrapping them in familiar commands.

#### Contributing Git repository
Question: How can I contribute to a Git repository? Could you provide a step-by-step guide, especially for beginners?

**Steps and Explanation:**
1. **Fork it!**
   - **Explanation:** Forking refers to creating a personal copy of a repository.
   
2. **Create your feature branch:**
   - **Command:** `git checkout -b my-new-feature`
   - **Explanation:** This command creates a new branch named "my-new-feature" where you'll work on your changes.
   
3. **Commit your changes:**
   - **Command:** `git commit -m 'Add some feature'`
   - **Explanation:** This command records your changes to the repository along with a descriptive message explaining the changes made.
   
4. **Push to the branch:**
   - **Command:** `git push -u origin my-new-feature`
   - **Explanation:** Pushes your changes to the remote repository, specifically to the branch "my-new-feature" on the remote repository named "origin."
   
5. **Submit a pull request - cheers!**
   - **Explanation:** After pushing your changes to your forked repository, you can submit a pull request to the original repository, proposing your changes for inclusion. It's like saying, "Hey, I've made some changes, please review and consider merging them into the main project!"
   
####Resolving Conflicts in Git

**Steps to Resolve Conflicts:**

1. **Identify Conflicts:** Conflicts occur when Git detects changes in the same part of a file that cannot be automatically merged. Use `git status` to identify conflicted files.

2. **Open Conflicted Files:** Open the conflicted files in a text editor. Git marks the conflicting sections with `<<<<<<<`, `=======`, and `>>>>>>>`.

3. **Resolve Conflicts:** Manually edit the conflicted sections to incorporate the desired changes. Remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) and keep the desired content.

4. **Save Changes:** Save the modified files after resolving conflicts.

5. **Add Changes:** Use `git add <file>` to stage the resolved files for the next commit.

6. **Commit Changes:** Commit the resolved files using `git commit -m "Resolved conflicts"`.

7. **Push Changes:** Push the changes to the remote repository with `git push`.

**Notes:**

- **Understanding Conflict Markers:** Git uses conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`) to highlight conflicting sections. The content between `<<<<<<<` and `=======` represents changes from the current branch, while the content between `=======` and `>>>>>>>` represents changes from the incoming branch.

- **Manual Conflict Resolution:** Conflict resolution often requires manual intervention to decide which changes to keep. Carefully review the conflicting sections and make adjustments to ensure the desired outcome.

- **Testing After Resolution:** After resolving conflicts, it's essential to test the changes to ensure they function as expected. Run tests or perform manual checks to verify the integrity of the resolved code.

- **Communication:** When working in a team, communicate with other developers to ensure everyone is aware of conflicts and their resolution. Collaboration and coordination can prevent future conflicts and ensure smoother development workflows.
