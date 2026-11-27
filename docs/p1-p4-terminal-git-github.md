# Module 1 — Terminal, Git & GitHub

These practicals document the commands and workflow used to build this repository. Run commands from the repository folder unless a step says otherwise.

## P1 — Project folder and terminal navigation

1. Open a terminal.
2. Create and enter the project folder:

```bash
mkdir Web_Dev_Lab
cd Web_Dev_Lab
pwd
ls
```

3. Create the starter structure:

```bash
mkdir -p css docs
touch index.html bio.html newspaper.html
touch css/styles.css
```

Useful navigation commands:

| Command | Purpose |
| --- | --- |
| `pwd` | Print the current directory |
| `ls` / `dir` | List files |
| `cd folder` | Enter a folder |
| `cd ..` | Move up one level |
| `mkdir name` | Create a directory |
| `clear` | Clear the terminal |

## P2 — Portfolio repository with an initial commit

```bash
git init
git add .
git status
git commit -m "chore: create web development lab"
git branch -M main
git remote add origin https://github.com/mauryasameer016-oss/Web_Dev_Lab.git
git push -u origin main
```

If the remote already exists, inspect it with `git remote -v` instead of adding it again.

## P3 — Feature-branch Git workflow

Use a separate branch for each practical or feature:

```bash
git switch -c feature/p5-semantic-bio
# make and test your changes
git status
git add bio.html
git commit -m "feat: add semantic bio page"
git push -u origin feature/p5-semantic-bio
```

Then open a pull request on GitHub, review the changes, and merge it into `main`. Keep commits focused and use descriptive messages.

## P4 — GitHub README and version tags

A useful README explains the project, folder structure, how to run it, and what each practical demonstrates. This repository's README provides that overview.

Create and push a version tag after a milestone:

```bash
git tag -a v1.0.0 -m "Complete P1-P13 web development lab"
git push origin v1.0.0
git tag
```

Semantic versioning uses `MAJOR.MINOR.PATCH`: breaking changes, new features, and fixes respectively.

## Evidence checklist

- [ ] Project folder and subfolders created
- [ ] Git repository initialized and first commit created
- [ ] Feature branch pushed and pull request reviewed
- [ ] README describes the work
- [ ] Version tag created and pushed
