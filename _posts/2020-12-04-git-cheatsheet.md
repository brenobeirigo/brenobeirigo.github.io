# GIT Cheatsheet

## Create a new repository on the command line
	
	echo "# aviz" >> README.md
	git init
	git add README.md
	git commit -m "first commit"
	git branch -M main
	git remote add origin https://github.com/brenobeirigo/aviz.git
	git push -u origin main
                
## Push an existing repository from the command line

	git remote add origin https://github.com/brenobeirigo/aviz.git
	git branch -M main
	git push -u origin main

## Start with branch "main"

	git init -b main
	
## Rename default branch master -> main


	git branch -m master main
	git push -u origin main
