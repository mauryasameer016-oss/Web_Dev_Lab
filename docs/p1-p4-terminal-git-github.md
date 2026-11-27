# Module 1 — Terminal, Git & GitHub (P1–P4)

This guide explains the commands and workflow behind the Web Dev Lab. Run the commands in a terminal. Commands are shown for macOS/Linux and are also compatible with Git Bash on Windows unless noted.

## P1 — Project folder and terminal navigation

### Goal
Create a project directory and understand how to move around the file system.

### Commands

\`\`\`bash
mkdir Web_Dev_Lab
cd Web_Dev_Lab
pwd
ls
mkdir css docs
touch index.html bio.html newspaper.html
touch css/styles.css
\`\`\`

On Windows Command Prompt, use \`mkdir\` and \`type nul > filename\` to create empty files. In PowerShell, \`New-Item index.html -ItemType File\` works.

| Command | What it does |
| --- | --- |
| \`pwd\` | Shows the current directory |
| \`ls\` | Lists files and folders |
| \`cd folder\` | Enters a folder |
| \`cd ..\` | Moves up one directory |
| \`mkdir name\` | Creates a directory |
| \`clear\` | Clears the terminal |
| \`touch file\` | Creates an empty file (Unix/Git Bash) |

### Checkpoint
Run \`pwd\` and \`ls\`. Confirm that the project folder contains the HTML files and the \`css\` and \`docs\` folders.

## P2 — Initialize Git and make the first commit

### Goal
Track project changes with Git and connect the local project to GitHub.

\`\`\`bash
git init
git status
git add .
git status
git commit -m "chore: initialize Web Dev Lab"
git branch -M main
git remote add origin https://github.com/mauryasameer016-oss/Web_Dev_Lab.git
git push -u origin main
\`\`\`

If \`origin\` already exists, do not add it again. Check it with \`git remote -v\`; if necessary update it with \`git remote set-url origin https://github.com/mauryasameer016-oss/Web_Dev_Lab.git\`.

### Checkpoint

- \`git status\` shows a clean working tree after committing.
- \`git log --oneline\` shows your initial commit.
- The files are visible in the GitHub repository.

## P3 — Feature-branch workflow

### Goal
Make changes in an isolated branch and keep commits focused.

\`\`\`bash
git switch -c feature/update-bio
# Edit bio.html and save your work
git status
git add bio.html
git commit -m "feat: personalize biography page"
git push -u origin feature/update-bio
\`\`\`

On GitHub, open a pull request from \`feature/update-bio\` into \`main\`. Review the changed files and merge when they are ready. Then update your local main branch:

\`\`\`bash
git switch main
git pull origin main
\`\`\`

Useful inspection commands:

\`\`\`bash
git branch
git log --oneline --graph --all
git diff
git status
\`\`\`

### Checkpoint
Show the feature branch, its commit, and the pull request. Do not commit directly to main when practising this workflow.

## P4 — README and version tags

### Goal
Document the project so another person can understand and run it. The root \`README.md\` is the project overview.

After completing the practicals, create a milestone tag:

\`\`\`bash
git tag -a v1.0.0 -m "Complete P1-P13 Web Dev Lab"
git push origin v1.0.0
git tag --list
\`\`\`

Semantic versioning convention:

- MAJOR: incompatible or breaking changes.
- MINOR: new backwards-compatible functionality.
- PATCH: backwards-compatible fixes.

### Final evidence checklist

- [ ] Project directory and files created.
- [ ] Git repository initialized.
- [ ] Initial commit visible in Git history.
- [ ] Feature branch pushed.
- [ ] Pull request opened and reviewed.
- [ ] README explains the project and how to run it.
- [ ] Version tag created and pushed.

**Important:** Documentation is not a substitute for the actual Git history. Run the commands yourself in your local clone so your practical evidence is genuine.
