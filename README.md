# New git repository

```shell
$ git clone git@github.com:leitiannet/git-new.git
$ cd git-new
$ export PATH=$PATH:`pwd`
$ cd ..
$ git new -h
usage: git new [<options>] [<directory>]
   options:
        -m <msg> Use the given <msg> as the commit message
        -h       Show this help
$ git new -m "new example" example
Initialized empty Git repository in /home/example/.git/
[master (root-commit) b697dba] new example
 4 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 .gitattributes
 create mode 100644 .gitignore
 create mode 100644 LICENSE
 create mode 100644 README.md
Use 'git gi Go > .gitignore' to set gitignore file.
Use 'git ga go,vim > .gitattributes' to set gitattributes file.
```
