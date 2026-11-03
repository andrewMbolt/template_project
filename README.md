Setup steps.

1. VSCode setup
   a. create project folder.
   b. create test.py with print("hello world")
   c. type ctrl + shift + P and type Python: Select Interpreter
   d. select the appropriate python version installed on windows

2. Link github project to VSCode project
   a. ensure that Git is installed for windows
   b. in VSCode project folder open a terminal using ctrl + ~
   c. type
       git init
       git add .
       git commit -m "Initial commit"
   d. log into github and create a new project, copy the URL (ending with .git)
   e. back in VSCode terminal type git remote add origin <paste URL>
   f. type
       git branch -M main
       git push -u origin main
   g. verify that test.py appears in the github repo via the browser
   h. edit a readme file to look similar to this one in github
   i. commit (save) on github with appropriate comment
   j. VSCode terminal type
       git pull origin main
   
   
