# VSCode Setup

## Extensions
:warning: for the most important extensions

### Languages
- :warning: [Python](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwjS-Ov0gIyCAxWYQ0EAHcXrA2IQFnoECB4QAQ&url=https%3A%2F%2Fmarketplace.visualstudio.com%2Fitems%3FitemName%3Dms-python.python&usg=AOvVaw3TP4iKzvx17hibUyj1XWsH&opi=89978449)

### git
- :warning: [Git Graph](https://marketplace.visualstudio.com/items?itemName=mhutchie.git-graph)
    - Viewing a git graph and performing GUI git operations
- :warning: [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    - Additional feature for git, more hover information, blame, file history, interactive rebase, file annotations, etc. 

### Tests
- [Python Test Explorer](https://marketplace.visualstudio.com/items?itemName=LittleFoxTeam.vscode-python-test-adapter)
    - Python extension has one now, but this claims it still has a richer feature set

### Linting
- :warning: [Flake8](https://marketplace.visualstudio.com/items?itemName=ms-python.flake8)
    - Flake8 linter for style guide enforcement
- :warning: [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens)
    - Improved highlighting of errors, warnings, and other language diagnostics
- :warning: [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
    - Simple source code spell checker

### Formatting
- :warning: [Black](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)
    - Black code formatter

### ToDos
- :warning: [ToDo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)
    - Searches repo for TODO, FIXME, etc. and displays an overview tab
- [todo+](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus)
    - ToDo list maintainer, lots of nice features

### Project/time management
- [Project Manager](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)
    - Organise projects

### Code completion
- [Tabnine](https://marketplace.visualstudio.com/items?itemName=TabNine.tabnine-vscode)
    - AI completion that supports offline mode

### Documentation
- [autoDocstring](https://marketplace.visualstudio.com/items?itemName=njpwerner.autodocstring)
    - Generates template docstrings for Python through tabbing
- :warning: [GiHub Markdown Preview](https://marketplace.visualstudio.com/items?itemName=bierner.github-markdown-preview) and [Markdown Preview GitHub Styling](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-preview-github-styles)
    - Changes default md preview to match GitHub's styling

### SSH and tunnelling
- [Remote SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)
    - Use any server as your development environment through ssh
-  [Remote Tunnels](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-server)
    - Connect to a remote machine through a secure tunnel
    - Requires [VSCode Server](https://code.visualstudio.com/docs/remote/vscode-server) to be installed on the remote machine
- [Remote Explorer](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-explorer)
    - Complements the Remote SSH and Remote Tunnels with the Remote Explorer view 



## Settings.json
- Global settings
    - **enable** `Files: Trim Final Newlines`
    - **enable** `Files: Trim Trailing Whitespace`
    - **disable** `Diff Editor: Ignore Trim Whitespace`
    - **set** `Python -> Formatting: Provider -> black` (if you don't use the `Black` extension)
    - **consider enabling** `Editor: Format On Save Mode -> 'modifications'`
- `Settings.json`
    - Cmd palette: `Preferences: Open User Settings (JSON)`
    - Paste in:
        ```json
        {
            "workbench.colorTheme": "Default Light+",
            "workbench.editorAssociations": {
                "*.ipynb": "jupyter-notebook"
            },
            "notebook.cellToolbarLocation": {
                "default": "right",
                "jupyter-notebook": "left"
            },
            "files.autoSave": "onFocusChange",
            "workbench.editor.closeOnFileDelete": true,
            "files.exclude": {
                "**/.git": true,
                "**/.svn": true,
                "**/.hg": true,
                "**/CVS": true,
                "**/.DS_Store": true,
                "**/__pycache__": true,
                "**/.pyc": true,
                "**/results/**": true,
                "**/summary/**": true,
                "**/log/**": true,
                "**/tmp/**": true
            },
            "files.watcherExclude": {
                "**/.git/objects/**": true,
                "**/.git/subtree-cache/**": true,
                "**/.pytest_cache": true,
                "**/results/**": true,
                "**/models/**": true,
                "**/summary/**": true,
                "**/log/**": true,
                "**/tmp/**": true
            },
            "python.testing.unittestEnabled": true,
            "editor.rulers": [
                88
            ],
            "isort.args": ["--profile", "black"],
            "[python]": {
                "editor.formatOnSave": true
            },
            "[json]": {
                "editor.formatOnSave": false
            },
            "autoDocstring.docstringFormat": "numpy",
            "editor.bracketPairColorization.enabled": true,
            // Make sure these keys are in Todo-tree > General: Tag Groups
            "todo-tree.highlights.customHighlight": {
                "TODO": {
                    "icon": "check",
                    "type": "text-and-comment",
                    "foreground": "#000000",
                    "iconColour": "#00FFFF",
                    "background": "#00FFFF"
                },
                "FIXME": {
                    "icon": "alert",
                    "type": "text-and-comment",
                    "foreground": "#000000",
                    "iconColour": "#FF0000",
                    "background": "#FF0000"
                },
                "REMOVEME": {
                    "icon": "trashcan",
                    "type": "text-and-comment",
                    "foreground": "#000000",
                    "iconColour": "#FFA500",
                    "background": "#FFA500"
                },
                "HACK": {
                    "icon": "flame",
                    "type": "text-and-comment",
                    "foreground": "#FF0000",
                    "iconColour": "#FFFF00",
                    "background": "#FFFF00"
                },
                "DEBUG": {
                    "icon": "bug",
                    "type": "text-and-comment",
                    "foreground": "#000000",
                    "iconColour": "#FFFF00",
                    "background": "#FFFF00"
                },
                "BROKEN CODE": {
                    "icon": "alert",
                    "type": "whole-line",
                    "foreground": "#FFFF00",
                    "iconColour": "#FF0000",
                    "background": "#FF0000"
                }
            }
        }
        ```
