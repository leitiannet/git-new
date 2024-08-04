#!/usr/bin/env bash
#
# New git repository
# refer to https://github.com/tj/git-extras/blob/main/bin/git-setup

# see https://git-scm.com/docs/git-sh-setup
USAGE="\
[<options>] [<directory>]
   options:
	-m <msg> Use the given <msg> as the commit message
	-h       Show this help"
#SUBDIRECTORY_OK=
NONGIT_OK=Yes
. "$(git --exec-path)/git-sh-setup"

# global variable
COMMIT_MESSAGE='Initial commit'

if [ "$1" == "-m" ]; then
    COMMIT_MESSAGE=$2
    shift; shift
elif [ "$1" == "-h" ]; then
	usage && exit 0
fi

gitdirexists() {
    if [ -d ".git" ]; then
        echo ".git directory already exists, aborting"
        exit 1
    fi
}

gitinit() {
	git init
}

gittouch() {
	for filename in "$@"; do
		if [ ! -f "$filename" ]; then
			touch "$filename" && git add "$filename"
		fi
	done
}

gitadd() {
	git add .
}

gitcommit() {
	git commit --allow-empty -m "$COMMIT_MESSAGE"
}

gitconfig() {
	git config --global alias.gi '!f() { curl -sL https://www.toptal.com/developers/gitignore/api/$@ ;}; f'
	git config --global alias.ga '!f() { curl -sL https://gitattributes.com/api/$@ ;}; f'
	echo "Use 'git gi Go > .gitignore' to set gitignore file."
	echo "Use 'git ga go,vim > .gitattributes' to set gitattributes file."
}

dir=$(test -z "$*" && echo "." || echo "$*")
mkdir -p "$dir" \
  && cd "$dir" \
  && gitdirexists \
  && gitinit \
  && gittouch .gitignore .gitattributes LICENSE README.md \
  && gitadd \
  && gitcommit \
  && gitconfig
