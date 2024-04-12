default:
	 git branch --set-upstream-to=origin/master master
	 git remote add upstream git@github.com:RandyMcMillan/git_workshop.git || \
		 git remote add upstream https://github.com/RandyMcMillan/git_workshop.git || \
		 true
tag:
	## remove shell from commands to use in the terminal
	git tag -f $(shell git rev-parse --short HEAD~1) && git tag
