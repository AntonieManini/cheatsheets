# Git commands

**Setup and Config**

|Command|Use case|Description|
|---|---|---|---|
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



**Init and Clone Project**

|Command|Use case|Description|
|---|---|---|---|
|git init|create an empty git repository||
|git clone {repository url}|clone a repo into a new directory|

**Manage Changes**

|Command|Use case|Description|
|---|---|---|---|
|git add {path}|add new or modified files from the path to the index|path='.' - everything, '/**.cpp' - only files with cpp extension|
|git add -n/--dry-run [{path}]|don’t actually do anything, just show what would be done||
|git add -i/--interactive [{path}]|interactively add files to the index||
|git add -p/--patch [{path}]|add chunks of code to the index interactively||
|git add -u/--update [{path}]|update previously staged files||
|git add -A/--all [{path}]|add all files from the path or from the whole working tree||
|commit
|reset
|stash
|clean
|rm

**Branching and Merging**

|Command|Use case|Description|
|---|---|---|---|
|branch
|checkout
|merge
|mergetool
|tag

**Sharing and Updating Projects**

|Command|Use case|Description|
|---|---|---|---|
|pull
|push
|fetch

**Inspection and Comparison**

|Command|Use case|Description|
|---|---|---|---|
|git status|shows changes in the working tree||
|git status -s/--short|output in a short form||
|git status -b/--branch|show local and remote branch info||

|diff
|log
|grep

**Manage commits tree**

|Command|Use case|Description|
|---|---|---|---|
|revert
|rebase
|cherry-pick
|apply
|reflog
|gc

**Advanced Use Cases**

|Command|Use case|Description|
|---|---|---|---|
|git config credential.helper store<br>git pull/push|How to save username and password in git|After you do pull or push and enter your credentials they will be stored in git. To update just do the same again.|
|git clean -df|delete untracked files (-f/--force) and remove untracked directories in addition to untracked files (-d)||
|git clean -df<br>git checkout -- .|discard unstaged changes|untracked files and folders will be also removed|
