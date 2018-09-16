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
|add
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
|status
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
