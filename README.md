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
git add README.md
git commit -m "Initialise empty repo with README.md"
```

Create a repo on [GitHub]() with the same name and give it a description: 'A repo to record information about setting up Visual Studio Code.'

Add the local directory to [GitHub]():

```bash
git remote add origin https://github.com/michael-bentley/visual-studio-code-setup.git
git push -u origin master
```

