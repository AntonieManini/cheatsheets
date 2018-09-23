# Git commands

**Setup and Config**

|Command|Use case|Description|
|---|---|---|
|git help||lists mostly used git commands|
|git help {command}/{concept}|get info about git command|to get list of concepts type git |
|git help -g|||
|git help -a/--all|get all available git commands||
|git config {key}|get value of config variable|'~/.gitconfig' User-specific configuration file. Also called "global" configuration file. '$GIT_DIR/config' Repository specific configuration file.|
|git config {key} {value}|set, define config variable||
|git config --global {key} {value}|write to global ~/.gitconfig file rather than the repository .git/config||
|git config --remove-section {section-name}|remove the config section and all its values|for example: [credential]	helper = store, where 'credential' is a section name|
|git config --list|lists all the global+local config key-value pairs||
|git config --list [--global/--local]|list all the global/local key-value pairs||
|git config --global core.editor {command to call your editor}|set a default editor|example: git config --global core.editor /usr/bin/vim|
|git config -e/--edit [--global/--local]|edit a config file with a default editor|||

<br><br><br>

**Init and Clone Project**

|Command|Use case|Description|
|---|---|---|
|git init|create an empty git repository||
|git clone {repository url}|clone a repo into a new directory|||

<br><br><br>

**Manage Changes**

|Command|Use case|Description|
|---|---|---|
|git add {path}|add new or modified files from the path to the index|path='.' - everything, '/**.cpp' - only files with cpp extension|
|git add -n/--dry-run [{path}]|don’t actually do anything, just show what would be done||
|git add -i/--interactive [{path}]|interactively add files to the index||
|git add -p/--patch [{path}]|add chunks of code to the index interactively||
|git add -u/--update [{path}]|update previously staged files||
|git add -A/--all [{path}]|add all files from the path or from the whole working tree||
|git commit -am "{message}"|add all changes to index and commit|only modified and deleted files are staged to commit, new files are not affected|
|git commit -p/--patch|commit change hunks interactively||
|git commit --interactive|commit files interactively||
|git commit --amend|fix the commit message of the last commit||
|git commit --status|adds an output of 'git status' command to the commit message template||
|git commit {file}|commit changes of given file|file should be staged, other files in index will stay staged for next commit|
|reset|||
|stash|||
|git clean|remove untracked files|works only if the configuration variable clean.requireForce set to false|
|git clean {file}|remove given untracked file||
|git clean -f|remove untracked files with force|you need this param when clean.requireForce is set to true(default)|
|git clean -d|remove untracked directories in addition to untracked files||
|git clean -i/--interactive|remove untracked files interactively||
|git clean -e {pattern}/--exclude={pattern}|exclude files according to pattern||
|git clean -x|remove also files specified in .gitignore||
|git clean -X|remove only ignored files||
|git rm -f/--force -r -n/--dry-run --cached {files}|remove files from index and working directory|-f -> ignore local modifications, -r -> remove directory recursively, -n -> just show what will be done, --cached -> remove from index but keep file on disk, after you commit changes file will be marked as untracked||

<br><br><br>

**Branching and Merging**

|Command|Use case|Description|
|---|---|---|
|git branch {branch}|create new branch||
|git branch {branch} {remote branch}|create branch and set to track remote branch||
|git branch {branch} -t/--track {remote}/{branch}|create new branch and set it to track remote one||
|git branch -a/--all|show all local and remote branches||
|git branch -m/--move {oldbranch} {newbranch}|rename branch|-M == --move --force|
|git branch -d/--delete {branch}|delete branch|-D == --delete --force|
|git branch -dr origin/{branch}|remove local reference to remote branch||
|git branch -c/--copy {branch}|copy branch and reflog|-C == --copy --force|
|git branch -v/-vv|show sha1 and commit subject line for each head, along with relationship to upstream branch (if any)|-v == --verbose|
|git branch -u {upstream}/--set-upstream-to={upstream}|set remote tracking branch to current branch||
|git branch --unset-upstream|unset upstream tracking branch information||
|git checkout {branch}|switch to branch|updates the index and moves HEAD to top of the branch. if {branch} doesnt exist as a local branch, but exists as a remote, then under the hood it makes (git checkout -b {branch} --track {remote}/{branch})|
|git checkout {path}|checkout path - commit or tag|you will be then in DETACHED HEAD state, you can create commits but no branch will refer to them, which means this commits will be removed by the next garbage collection operation (git gc)|
|git checkout {branch}~N|checkout N-th commit from the last commit of the branch||
|git checkout -b {branch}|create branch and checkout to it||
|git checkout {path}|override files in the working tree with the with the contents of the given commit(path==commit hash) or last commit(path==files path)||
|git checkout -p {path}|checkout interactively deciding which changes to discard||
|git checkout -m/--merge {branch}|follows a merge process when changing to another branch||
|git checkout --orphan {branch}|create branch from init state|git allows you to track multiple independent projects as different branches in a single repository|
|merge|||
|mergetool|||
|git tag|lists all existing tags||
|git tag {tag}|add a tag to the current commit|creates a lightweight tag (default) -> pointer to commit|
|git tag -a -m "{message}" {tag}|create an annotated tag|creates a tag object, which has extra information (author, date, message (release notes/changelog) etc.) and reference to commit. important for public releases.|
|git tag --create-reflog {tag}|creates a tag history entry(reflog entry)||
|git tag -f/--force {tag}|re-tag when you tagged a wrong commit||
|git tag -d/--delete {tag}|delete a given tag||
|git tag -l/--list {regex pattern}|show tags matching pattern||
|git tag -l -n|list all tags including messages, commit message if no tag msg exists||

<br><br><br>

**Sharing and Updating Projects**

|Command|Use case|Description|
|---|---|---|
|pull|||
|push|||
|git push --tags|push all tags to remote repo||
|git push origin {tag}|push specified/given tag to remote repo||
|fetch|||

<br><br><br>

**Inspection and Comparison**

|Command|Use case|Description|
|---|---|---|
|git status|shows changes in the working tree||
|git status -s/--short|output in a short form||
|git status -b/--branch|show local and remote branch info||
|diff|||
|log|||
|grep||||
|show|||
|git show {tag}|shows information about a tag|

<br><br><br>

**Manage commits tree**

|Command|Use case|Description|
|---|---|---|
|revert|||
|rebase|||
|cherry-pick|||
|apply|||
|reflog|||
|git gc|cleanup unnecessary files and optimize the local repository||
|git gc --aggressive|more aggressive optimization, takes more time||

<br><br><br>

**Advanced Use Cases**

|Command|Use case|Description|
|---|---|---|
|git config credential.helper store<br>git pull/push|How to save username and password in git|After you do pull or push and enter your credentials they will be stored in git. To update just do the same again.|
|git clean -df|delete untracked files (-f/--force) and remove untracked directories in addition to untracked files (-d)||
|git clean -df<br>git checkout -- .|discard unstaged changes|untracked files and folders will be also removed|
||delete local and remote branch|||
||push tags to remote||
||change existing tag local and remote||
|git rev-parse {tag}|check to which commit points the tag||
