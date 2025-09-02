# Practical 1: Git & GitHub Hands-on

This practical will guide you through setting up Git, working with branches, creating pull requests, and resolving merge conflicts in a GitHub repository.

---

## Step 1: Setup Git
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --list
```

## Step 2: Initialize Repository
```bash
mkdir git-practical && cd git-practical
git init
echo "# Git Practical" > README.md
git add README.md
git commit -m "Initial commit"
```

## Step 3: Connect to GitHub
```bash
git remote add origin https://github.com/username/git-practical.git
git branch -M main
git push -u origin main
```

## Step 4: Create Branches
```bash
git checkout -b feature-1
echo "This is Feature 1 branch" >> README.md
git add README.md
git commit -m "Added feature 1 note"
git push origin feature-1
```

## Step 5: Create Another Branch & Conflict
```bash
git checkout main
git checkout -b feature-2
echo "This is Feature 2 branch" >> README.md
git add README.md
git commit -m "Added feature 2 note"
git push origin feature-2
```

## Step 6: Pull Request Workflow
1. Go to GitHub repo → Open a Pull Request for `feature-1` → merge into `main`.
2. Open another Pull Request for `feature-2` (this may cause a conflict).

## Step 7: Resolve Merge Conflict Locally
```bash
git checkout main
git pull origin main
git merge feature-2

# Fix conflict in README.md, then:
git add README.md
git commit -m "Resolved conflict between feature-1 and feature-2"
git push origin main
```

## Step 8: Verify Final Repo State
```bash
git log --oneline --graph --all
git branch -a
```
