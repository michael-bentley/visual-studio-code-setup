# Initial configuration of Visual Studio Code

A repo to record information about setting up Visual Studio Code.

## Record setup configuration using git

Create a directory with an empty README.md file in to hold this information in:

```bash
git init visual-studio-code-setup
cd visual-studio-code-setup/
touch README.md
```

Add the README.md file to the staging area and create the first commit:

```bash
git add .
git commit -m "Initialise empty repo with README.md"
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

### Add additional styling using a CSS stylesheet. ###

Create a `style.css` file:

```bash
mkdir documentation
mkdir documentation/css
touch documentation/css/style.css
```

Open the `settings.json` file and add:

```
// Place your settings in this file to overwrite default and user settings.
{
    "markdown.styles": [
        "documentation/css/style.css"
    ]
}
```