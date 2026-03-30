

In this markdown, you can find the Git Cheat Sheet:



| Functionality             | Git Command                                  | Description                       |
|------------------------------|------------------------------------------|-----------------------------------------|
| **Getting Started**          | `git init`                                | Start a new repository.                                                                 |
|                              | `git ingit clone <url>`                             | Clone an existing repository.                                                          |
| **Prepare to Commit**        | `git add <file>`                          | Add an untracked file or unstaged changes.                                            |
|                              | `git add .`                                   | Add all untracked files and changes.                                                   |
|                              | `git add -p`                                  | Choose which parts of a file to stage interactively.                                    |
|                              | `git mv <old> <new>`                          | Move or rename a file.                                                                 |
|                              | `git rm <file>`                               | Delete a file and stage the change.                                                    |
|                              | `git rm --cached <file>`                      | Stop tracking a file without deleting it locally.                                       |
|                              | `git reset <file>`                            | Unstage a file.                                                                         |
|                              | `git reset`                                   | Unstage all files.                                                                      |
|                              | `git status`                                  | Check the status of the working and staging areas.                                      |
| **Make Commits**             | `git commit`                              | Create a commit and open a text editor for the message.                                 |
|                              | `git commit -m 'message'`                     | Commit with a message directly.                                                        |
|                              | `git commit -am 'message'`                    | Add and commit unstaged changes.                                                       |
| **Move Between Branches**    | `git switch <name>`                        | Switch branches.                                                                        |
|                              | `git checkout <name>`                         | Alternate way to switch branches.                                                      |
|                              | `git switch -c <name>`                        | Create and switch to a new branch.                                                     |
|                              | `git checkout -b <name>`                      | Alternate way to create and switch to a new branch.                                     |
|                              | `git branch`                                  | List all branches.                                                                      |
|                              | `git branch --sort=-committerdate`            | List branches by most recently committed to.                                           |
|                              | `git branch -d <name>`                        | Delete a branch.                                                                        |
|                              | `git branch -D <name>`                        | Force delete a branch.                                                                  |
| **Diff Staged/Unstaged Changes** | `git diff HEAD`                           | Show all staged and unstaged changes.                                                  |
|                              | `git diff --staged`                           | Show just staged changes.                                                              |
|                              | `git diff`                                    | Show just unstaged changes.                                                            |
| **Diff Commits**                 | `git show <commit>`                       | Show the diff between a commit and its parent.                                         |
|                              | `git diff <commit> <commit>`                  | Show the diff between two commits.                                                     |
|                              | `git diff <commit> <file>`                    | Show the changes to one file since a commit.                                           |
|                              | `git diff <commit> --stat`                    | Show a summary of a diff.                                                              |
|                              | `git show <commit> --stat`                    | Alternate way to show a summary of a diff.                                             |
| **Discard Changes**              | `git restore <file>`                          | Delete unstaged changes to one file.                                                   |
|                              | `git checkout <file>`                         | Alternate way to delete unstaged changes to one file.                                   |
|                              | `git restore --staged --worktree <file>`      | Delete all staged and unstaged changes to one file.                                     |
|                              | `git checkout HEAD <file>`                    | Alternate way to delete all staged and unstaged changes to one file.                   |
|                              | `git reset --hard`                            | Reset all staged and unstaged changes.                                                 |
|                              | `git clean`                                   | Delete untracked files.                                                                |
|                              | `git stash`                                   | Stash all staged and unstaged changes.                                                 |
| **Edit History**             | `git reset HEAD^`                             | Undo the most recent commit (keep the working directory the same).                     |
|                              | `git rebase -i HEAD~6`                        | Squash the last 5 commits into one.                                                    |
|                              | `git reflog BRANCHNAME`                       | Undo a failed rebase using the reflog.                                                 |
|                              | `git reset --hard <commit>`                   | Reset to a specific commit, discarding changes.                                        |
|                              | `git commit --amend`                          | Change a commit message or add files to the last commit.                               |
| **Code Archaeology**             | `git log main`                                | Show the commit log of the main branch.                                           |
|                              | `git log --graph main`                        | Show a graphical representation of commit history.                                    |
|                              | `git log --oneline`                           | Show a one-line summary of commits.                                                   |
|                              | `git log <file>`                              | Show all commits that modified a file.                                                |
|                              | `git log --follow <file>`                     | Show commits that modified a file, including before it was renamed.                   |
|                              | `git log -G <text>`                           | Find commits that added or removed specific text.                                     |
|                              | `git blame <file>`                            | Show who last changed each line of a file.                                            |
| **Combine Diverged Branches**    | `git rebase main`                             | Rebase one branch onto another.                                                   |
|                              | `git merge <branch>`                          | Merge another branch into the current branch.                                         |
|                              | `git cherry-pick <commit>`                    | Copy one commit to the current branch.                                                |
| **Restore an Old File**      | `git checkout <commit> <file>`                | Get the version of a file from another commit.                                        |
|                              | `git restore <file> --source <commit>`        | Alternate way to restore a file from another commit.                                  |
| **Add a Remote**             | `git remote add <name> <url>`                 | Add a remote repository.                                                              |
| **Push Your Changes**        | `git push origin main`                        | Push the main branch to the remote origin.                                            |
|                              | `git push`                                    | Push the current branch to its tracking branch.                                       |
|                              | `git push -u origin <name>`                   | Push a branch and set it to track a remote branch.                                    |
|                              | `git push --force-with-lease`                 | Force push with additional safety checks.                                             |
|                              | `git push --tags`                             | Push tags to the remote repository.                                                   |
| **Pull Changes**             | `git fetch origin main`                       | Fetch changes without applying them.                                                  |
|                              | `git pull --rebase`                           | Fetch changes and reapply your commits on top.                                        |
|                              | `git pull origin main`                        | Fetch and merge changes into the current branch.                                      |
|                              | `git pull`                                    | Alternate way to fetch and merge changes.                                             |
| **Configure Git**            | `git config user.name 'Your Name'`            | Set your Git username.                                                                |
|                              | `git config --global ...`                     | Set configuration options globally.                                                   |
