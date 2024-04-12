default:
	 git branch --set-upstream-to=origin/master master
	 git remote add upstream git@github.com:RandyMcMillan/git_workshop.git || \
		 git remote add upstream https://github.com/RandyMcMillan/git_workshop.git || \
		 true
tag:
	## remove shell from commands to use in the terminal
	git tag -f $(shell git rev-parse --short HEAD~1) && git tag
test-commit:
	git commit -m "test commit" --allow-empty
empty-commit:
	GIT_AUTHOR_DATE="Thu, 01 Jan 1970 00:00:00 +0000" GIT_COMMITTER_DATE="Thu, 01 Jan 1970 00:00:00 +0000" git commit --allow-empty -m 'empty commit'
install:
	apt-get install make || brew install make || winget install ezwinports.make
submodules:
	git submodule update --init --recursive
