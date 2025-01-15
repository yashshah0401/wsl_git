**Author:** Shah, Yash Ketanbhai  
**Student ID:** 8990493  
**Course:** Software Quality Assurance & Test Engineering  
**Date:** January 14, 2025  
**Contact:** yashshah0704@gmail.com
**Professional:** Project Manager and Business Analyst

# Steps to Create a New Repository and Add it to GitHub

## 1. Create a New Repository on GitHub
- Log in to your GitHub account.
- Click the "+" icon in the top-right corner and select "New repository."
- Fill in the repository name (e.g., `firstproject`).
- Add an optional description, and choose visibility (public or private).
- Click "Create repository."

## 2. Navigate to the Desired Directory in WSL
Open the WSL terminal and navigate to the desired drive (e.g., D: drive):
```bash
cd /mnt/d
```

## 3. Create a New Directory for Your Project
```bash
mkdir firstproject
cd firstproject
```

## 4. Initialize the Repository
Initialize a new Git repository in the current directory:
```bash
git init
```

## 5. Create a README File
Use a text editor to create a README.md file:
```bash
nano README.md
```

Add the following content to README.md (as an example):
```markdown
# First Project

This is the README file for the First Project.

## Description
This project is created to demonstrate how to create a new repository on GitHub and connect it with WSL.

## Steps
1. Create a new repository on GitHub.
2. Navigate to the desired directory in WSL.
3. Create a new directory for your project.
4. Initialize the repository.
5. Add a remote repository.
6. Add files and commit.
7. Push to GitHub.

## Author
John Doe
```

Save and exit the editor (Ctrl+X, Ctrl+Y, and Enter for nano).

## 6. Add the README File to the Repository
Add the file to the staging area:
```bash
git add README.md
```

## 7. Commit the Changes
Commit the staged files with a message:
```bash
git commit -m "Add README file"
```

## 8. Add the Remote Repository
Replace `username` and `repository-name` with your GitHub username and repository name:
```bash
git remote add origin git@github.com:username/firstproject.git
```

## 9. Push to GitHub
Push the changes to the GitHub repository:
```bash
git push -u origin master
```

The repository is now successfully created and connected to GitHub.

# License

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
