# GIT CHEAT SHEET

#### CREATING LOCAL REPOSITORIES

`git init`
Turn a folder into a Git repository.

`git status`
Check if a folder has already been initialized into a git repository.

#### COMMITTING IN A LOCAL REPOSITORY

`git status`
List all files that have changed and their state.

`git add` <filename>
Add a file to the stage.

`git command -m "[discriptive message]"`
Create a commit including all staged files.

`git log --oneline`
Show the commit history.

#### USING COMMITS AS BACKUPS

`git restore .`
Return to the last committed state of the entire project.

`git restore <filename>`
Restore individual files.

#### CONNECTING TO A REMOTE REPOSITORY

This enables teams to work on the same remote repository and clone it locally. The remote repository also serves as a backup.

#### CONNECTING YOUR LOCAL REPOSITORY TO A NEW REMOTE REPOSITORY

The first thing you need to do is create a new empty remote repository on GitHub. You will then see some hints e.g. "...or push an existing repository from the command line". Copy the commands from GitHub and execute them in your local project folder.

`git remote add origin git@github.com:GitHubUsername/repository-name.git`

`git branch -M main`

`git push -u origin main`

#### CLONING A REMOTE REPOSITORY

You can create a copy of the remote repository on your local machine with the following command:

`git clone <url>`

Retrieve an entire repository from a hosted location via URL. You can find the url of remote repositories on GitHub on the repository page. Please use the SSH url.

#### SYNCHRONIZING LOCAL & REMOTE REPOSITORIES

`git push`

Upload content to the remote repository.

`git pull`

Download content from the remote repository.
..
