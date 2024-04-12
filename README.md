### git_workshop

```
SHELL := $(shell which bash)
default:
	 git branch --set-upstream-to=origin/master master
	 git remote add upstream git@github.com:RandyMcMillan/git_workshop.git 2>/dev/null || \
		 git remote add upstream https://github.com/RandyMcMillan/git_workshop.git 2>/dev/null || \
		 true
tag:
	## remove shell from commands to use in the terminal
	git tag -f $(shell git rev-parse --short HEAD~1)-$(shell date +%s)
tags-delete:
	for t in $(shell git tag);do git tag -d $$t;done
test-commit:
	git commit -m "test commit" --allow-empty
empty-commit:
	GIT_AUTHOR_DATE="Thu, 01 Jan 1970 00:00:00 +0000" GIT_COMMITTER_DATE="Thu, 01 Jan 1970 00:00:00 +0000" git commit --allow-empty -m 'empty commit'
install:
	apt-get install make || brew install make || winget install ezwinports.make
submodules:
	git submodule update --init --recursive
branch:
	git checkout -b topic-branch-$(shell date +%s) || git checkout -b topic-branch-$^
	#git branch -a
branch-sort: branch
	 git branch -a | sort || true
push:push--all-f
push--all-f:
	git push --all -f
readme:empty-commit
	echo >> README.md
	echo $(shell git rev-parse --short HEAD~1) >> README.md
	echo $@  >> README.md
	echo >> README.md
	git add README.md
	$(MAKE) test-commit
	$(MAKE) branch tag
index:readme
	pandoc README.md --from markdown --to html >> index.html
serve:server
server:
	 source .functions && server
```

8a26022
readme


9cdd33e
readme


296a578
readme


bef6bf1
readme


72ae7b9
readme


58899ee
readme


3bfe339
readme


c84d2bf
readme

