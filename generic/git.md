# Basic Setup

```
$ git config --global user.name "John Doe"
$ git config --global user.email "jdoe@mail.com"
$ git config --global color.ui true
$ git config --global rebase.autosquash true
$ git config --global commit.gpgsign true
$ git config --global user.signingkey 123456789ABCDEF
```

**NOTE:** Get GPG KeyID by `$ gpg --list-secret-keys --keyid-format long`

## Initializing

Create a new repository.

```
$ git init
```
   
The above is typically preceded by `$ mkdir myproject && cd myproject` which creates a directory called *myproject* and then changes into that directory.

## Misc

```
git status
```
Checks the status of `git` repository

```
git add some_file.txt
```

Adds some_file.txt to be tracked.

```
git diff some_file.py
```

Displays the differences between the working directory *some_file.py* and the staging directory. Adding `--staged` compares the staging area to the repository.

```
git diff HEAD some_file.py
```

Compares the file *some_file.py* in your working directory to the most recent commit version of the same file.

## Logging / History

Show a Tk GUI showing commit history

```
gitk
```
    
Show a history of commits on the current repository.

```
git log
```

Adding the following flags changes the output of `git log`

`--stats` show's the history with some statistics of what was changed.

`--oneline` shows single line version of commits history.

`--graph` shows branch diagrams (may be combined with `--oneline`)

`--pretty="%h, %cn, %cr"` shows commit history in a formatted version (example uses abbreviated hash, commiter name, and relative commiter date seperated via commas)

### --pretty Formatter Values

| | | | |
|:--------:|:-------------------------|:----------|:-------------------------|
| ```%H``` | Commit Hash              | ```%ad``` | Author Date              |
| ```%h``` | Abbreviated Hash         | ```%ar``` | Author Date, Relative    |
| ```%T``` | Tree Hash                | ```%cn``` | Committer Name           |
| ```%t``` | Abbreviated Tree Hash    | ```%ce``` | Committer E-mail         |
| ```%P``` | Parent Hashes            | ```%cd``` | Committer Date           |
| ```%p``` | Abbreviated Parent Hashes| ```%cr``` | Committer Date, Relative |
| ```%an```| Author Name              | ```%s```  | Subject (Commit Message) |
| ```%ae```| Author E-mail            |

## Commiting

```
git commit
```

Commits all files by showing a status and asking for a commit message.

### Flags

```
git commit -a
```
Commits all currently tracked files with all current changes. Asks for a commit message by showing a status screen.

## Ignoring

```
cat .gitignore
     .DS_Store
     tmp/*.txt
     !tmp/important.txt
```

A file that tells `git` what to ignore. One file/folder per line. Wildcards (`*`) are allowed. A line starting with `!` tels `git` to *include* such files and folders regardless of what other rules are listed in this file.
