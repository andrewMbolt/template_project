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

3. Setup git ignore
   a. create a file called .gitignore in the project root folder 
        (a git icon should automatically be associated with the file if VSCode and Git are properly setup)
   b. add common patterns to ignore. Examples below
    # Python virtual environments
    .venv/
    venv/
    env/

    # Local configuration & environment variables
    .env
    .env.local
    .python-version

    # VS Code settings
    .vscode/


4. Link Gemini (similar for other AI agents) to VSCode
   a. in VSS click extensions
   b. search "Google Antigravity" and install
   c. sign in with google account (click gemini icon in left hand side tray)

5. Setup UV. UV will act as a package manager and environment for each project. 
    This avoids package and versioning projects between projects.
   a. install UV on your computer
   b. through VSCode powershell (ctrl + ~) type
        powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1" | iex"
   c. restart the terminal so that UV commands are recognised. Confirm that uv is added to path following
      the install prompts or $env:Path = "C:\Users\<username>>\.local\bin;$env:Path" as an example
   d. naavigate to the project root folder. in bash type
        uv init --app
      to setup a uv environment for the project
   e. add packages using
        uv add <package name>
   f. to explicitly connect uv's virtual environment to VS code point to it by using ctrl + shift + p
      select python interpreter, and select the environment connected to the project root
   g. to view installed packages use the command 
        uv pip list
        OR
        uv tree
   h. development tools (not used in final work) can be installed via
        uv add --dev <package>
        eg.
        uv add --dev jupyter
      in the example this will allow for jupyter like execution within .py files using the magic command # %% for each code block

6. set up ruff for linting
   a. uv add --dev ruff
   b. set VSCode ruff extension (published by Astral)
   c. add the following item to the root .vscode/settings.json file (or a similar formatting)
        {
            "python.defaultInterpreterPath": ".venv\\Scripts\\python.exe", # existing item
            "[python]": {                                                  # add this [python] item
                "editor.formatOnSave": true,
                "editor.defaultFormatter": "charliermarsh.ruff",
                "editor.codeActionsOnSave": {
                "source.fixAll": "explicit",
                "source.organizeImports": "explicit"
                }
            }
        }

7. setup pytest
   

   
