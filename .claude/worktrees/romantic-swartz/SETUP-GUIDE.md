# JBE Elevator Configurator — Setup & Hosting Guide

## Overview

This guide walks you through:
1. Installing Git on your computer
2. Creating a GitHub account and repository
3. Publishing your page live using GitHub Pages (free, permanent hosting)
4. Adding your Netlify URL to DigiPara's allowed origins

---

## PART 1 — Install Git

Git is a tool that tracks changes to your files and lets you publish them online.

### Windows
1. Go to https://git-scm.com/download/win
2. Download and run the installer
3. Accept all default options during installation
4. Once installed, open **Git Bash** (search for it in your Start menu)

### Mac
1. Open **Terminal** (search for it in Spotlight with Cmd+Space)
2. Type: `git --version`
3. If Git is not installed, macOS will prompt you to install it automatically

### Verify installation
Open Git Bash (Windows) or Terminal (Mac) and type:
```
git --version
```
You should see something like: `git version 2.44.0`

---

## PART 2 — Create a GitHub Account

GitHub is a free website that stores your code and can host your webpage.

1. Go to https://github.com
2. Click **Sign up**
3. Choose a username (e.g. `jbe-elevator`), enter your email and a password
4. Complete the verification steps
5. Choose the **Free** plan

---

## PART 3 — Create Your Repository

A repository (or "repo") is a folder on GitHub that holds your project files.

1. Once logged in to GitHub, click the **+** icon in the top-right corner
2. Select **New repository**
3. Fill in the details:
   - **Repository name**: `elevator-configurator`
   - **Description**: JBE Elevator White Label Configurator
   - **Visibility**: Select **Public** (required for free GitHub Pages hosting)
   - Leave everything else as default
4. Click **Create repository**
5. GitHub will show you a page with setup instructions — keep this tab open

---

## PART 4 — Upload Your File Using Git

Now you will connect your computer to GitHub and upload your `index.html` file.

### Step 1 — Configure Git with your identity
Open Git Bash (Windows) or Terminal (Mac) and run these two commands,
replacing the values with your own name and email:

```
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### Step 2 — Navigate to your file location
Your `index.html` file should be in a folder on your computer.
In Git Bash / Terminal, navigate to that folder:

```
cd path/to/your/folder
```

For example, if your file is on your Desktop:
- Windows: `cd ~/Desktop`
- Mac:     `cd ~/Desktop`

### Step 3 — Initialise a Git repository
```
git init
```

### Step 4 — Add your file
```
git add index.html
```

### Step 5 — Save a snapshot (commit)
```
git commit -m "Initial upload: elevator configurator page"
```

### Step 6 — Connect to GitHub
Go back to your GitHub repository page.
Copy the URL that looks like:
`https://github.com/YOUR-USERNAME/elevator-configurator.git`

Then run (replace with your actual URL):
```
git remote add origin https://github.com/YOUR-USERNAME/elevator-configurator.git
git branch -M main
git push -u origin main
```

GitHub may ask for your username and password.
Note: GitHub no longer accepts your account password here.
You need a Personal Access Token instead — see the next step.

### Step 7 — Create a Personal Access Token (if prompted)
1. Go to https://github.com/settings/tokens
2. Click **Generate new token (classic)**
3. Give it a name like "my laptop"
4. Set expiration to **No expiration**
5. Check the box next to **repo**
6. Click **Generate token**
7. Copy the token — use it as your password when Git asks

---

## PART 5 — Enable GitHub Pages (Free Hosting)

GitHub Pages turns your repository into a live website for free.

1. Go to your repository on GitHub:
   `https://github.com/YOUR-USERNAME/elevator-configurator`
2. Click the **Settings** tab
3. In the left sidebar, click **Pages**
4. Under **Source**, select **Deploy from a branch**
5. Under **Branch**, select **main** and folder **/ (root)**
6. Click **Save**
7. Wait about 1–2 minutes, then refresh the page

Your live URL will appear at the top:
```
https://YOUR-USERNAME.github.io/elevator-configurator/
```

This URL is permanent and free. No expiry, no limits.

---

## PART 6 — Add Your URL to DigiPara EAO

Now that you have a permanent URL, register it in the EAO portal.

1. Log in to https://app.elevatorarchitect.com
2. Go to **User menu → Contract Settings**
3. Find your White Label Instance and click **Edit**
4. Scroll to **Allowed Web Site Origins**
5. Click **Add allowed Web Site Origin**
6. Enter your GitHub Pages URL:
   `https://YOUR-USERNAME.github.io`
7. Click **Save**
8. Visit your live page — the configurator should now load!

---

## PART 7 — How to Update Your Page in the Future

Whenever you make changes to `index.html` on your computer,
run these 3 commands in Git Bash / Terminal from your project folder:

```
git add index.html
git commit -m "Describe what you changed"
git push
```

Your live site will update automatically within a minute or two.

---

## Quick Reference

| What                  | Where                                              |
|-----------------------|----------------------------------------------------|
| Your GitHub repo      | https://github.com/YOUR-USERNAME/elevator-configurator |
| Your live site        | https://YOUR-USERNAME.github.io/elevator-configurator/ |
| EAO portal            | https://app.elevatorarchitect.com                  |
| DigiPara support      | sales@digipara.com                                 |

---

## Troubleshooting

**Configurator shows blank / doesn't load**
→ Check that your GitHub Pages URL is added to EAO Allowed Web Site Origins

**Git asks for password and rejects it**
→ Use a Personal Access Token instead (see Part 4, Step 7)

**GitHub Pages URL not appearing after saving**
→ Wait 2 minutes and refresh the Settings → Pages page

**Changes not showing on live site**
→ Run `git add index.html`, `git commit -m "update"`, `git push`
→ Wait 1–2 minutes for GitHub to rebuild
