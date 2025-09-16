# README – GitHub Workflow Setup and Usage

## 1. Prerequisites

* MacBook / Linux / Windows machine
* Git installed:

```bash
git --version
```

* GitHub account

## 2. Set Up Git on Your System

1. Configure your username and email (linked to your GitHub account):

```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```

2. Verify settings:

```bash
git config --list
```

## 3. Set Up SSH Key for GitHub

1. Generate a new SSH key:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

* Press **Enter** to accept default location.
* Optional: Set a passphrase.

2. Start the SSH agent and add the key:

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

3. Copy the public key to clipboard:

```bash
pbcopy < ~/.ssh/id_ed25519.pub
```

4. Add the public key to GitHub:

* Go to **GitHub → Settings → SSH and GPG keys → New SSH Key**
* Paste the key and save.

5. Test SSH connection:

```bash
ssh -T git@github.com
```

You should see:

```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

## 4. Clone the Repository

1. Navigate to your working directory:

```bash
cd ~/Projects
```

2. Clone the repo using SSH:

```bash
git clone git@github.com:collyge/campusAI.git
```

3. Navigate into the project folder:

```bash
cd campusAI
```

4. Check status:

```bash
git status
```

You should see:

```
On branch main
Your branch is up to date with 'origin/main'.
nothing to commit, working tree clean
```

## 5. Keeping Your Local Repo Updated

1. Pull the latest changes from GitHub:

```bash
git pull origin main
```

* Always do this before starting work to avoid conflicts.

## 6. Making Changes and Pushing to GitHub

1. Stage your changes:

```bash
git add .
```

2. Commit your changes:

```bash
git commit -m "Describe your changes here"
```

3. Push your changes to GitHub:

```bash
git push origin main
```

## 7. Quick Git Tips

* Check which branch you’re on:

```bash
git branch
```

* Switch branches:

```bash
git checkout <branch_name>
```

* See commit history:

```bash
git log --oneline
```

**Workflow Summary**:

1. Set up Git and SSH
2. Clone repo using SSH
3. Pull latest changes before starting work
4. Make changes, stage, commit
5. Push changes to GitHub
