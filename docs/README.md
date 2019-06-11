# Initial configuration of Visual Studio Code

A repo to record information about setting up Visual Studio Code.

## Record setup configuration using git

Create a directory with an empty README.md file in to hold this information in:

```bash
git init visual-studio-code-setup
cd visual-studio-code-setup/
mkdir docs
touch docs/README.md
```

Add the README.md file to the staging area and create the first commit:

```bash
git add .
git commit -m "Initialise empty repo with docs/README.md"
```

Create a repo on [GitHub]() with the same name and give it a description: 'A repo to record information about setting up Visual Studio Code.'

Add the local directory to [GitHub]():

```bash
git remote add origin https://github.com/michael-bentley/visual-studio-code-setup.git
git push -u origin master
```

## Configure markdown

To view the markdown file, press `Ctrl+Shift+V`.

To add linting, quick open using `Ctrl+P`, and install the `markdownlint` package:

```
ext install DavidAnson.vscode-markdownlint
```

To open markdown side-by-side press `Ctrl+K V`.

To add [GitHub]() markdown styling, quick open using `Ctrl+P`, and install the `markdown-preview-github-styles` package:

```
ext install bierner.markdown-preview-github-styles
```

### Add additional styling using a CSS stylesheet

Create a `style.css` file:

```bash
mkdir docs
mkdir docs/css
touch docs/css/style.css
```

Open the `settings.json` file and add:

```
// Place your settings in this file to overwrite default and user settings.
{
    "markdown.styles": [
        "docs/css/style.css"
    ]
}
```

### Compiling markdown into HTML

It can be useful to convert markdown into HTML. To do this in VS Code, install a [Node.js]() module called [mardown-it](). To install this, we type:

```bash
npm install -g markdown-it
```

To use the HTML converter, we can a `task` to the task configuration file `task.json`. To this, we go to **Terminal** > **Configure Tasks** > **Create tasks.json file from templates**. We can then choose one of the template tasks. Here, we want to create an external task, so we select **Others**. We then specify the content of the `tasks.json` as:

```json
{
    // See https://go.microsoft.com/fwlink/?LinkId=733558
    // for the docs about the tasks.json format
    "version": "2.0.0",
    "tasks": [
        {
            "label": "Compile Markdown",
            "type": "shell",
            "command": "markdown-it README.md -o README.html",
            "group": "build"
        }
    ]
}
```

To create the HTML, we then simply press `Ctrl+Shift+B` to **Run Build Task**. 

## Using Python environments in VS Code

Use a specified Python environment with a particular interpreter and installed packages.

To select a specific environment, use the **Python: Select Interpreter** command from the **Command Palette** using `Ctrl+Shift+P`.

The status bar at the bottom indicates which Python interpreter is selected. 

### Using virtual environments

The default VS Code Python environment is a global environment. It is tpyically better to create a new virtual environment for each project. A virtual environment is a subfolder in a project that contains a copy of a specific interpreter and any local packages. To create a new virtual environment:

```bash
python3 -m venv .venv
```

To use the newly created virtual environment in the terminal (to install new packages, for instance), we activate and deactive it using the commands:

```bash
source .venv/bin/activate
deactive
```
respectively. When activating a project, the terminal should show (.venv) on the terminal line.

To use the newly created virtual environment in VS Code, reselect the new interpreter using **Python: Select Interpreter** from the **Command Palette** using `Ctrl+Shift+P`. 