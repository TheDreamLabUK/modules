# GitHub for Artists – 4‑Hour Hands‑On Workshop

Welcome! This guide is the single source of truth for today’s workshop. Follow it in **VS Code’s Markdown preview** while running commands in your own terminal. Everything here can be copied verbatim.

> **Pro Tip** – Clone this repository first so you always have an offline copy.
>
> ```bash
> # macOS / Linux / Windows PowerShell
> git clone <REPLACE_WITH_REPO_URL> artists‑github‑workshop
> cd artists‑github‑workshop
> code .            # opens VS Code in the repo
> ```

---

## 🗺️ Table of Contents

1. [Agenda & Learning Goals](#agenda--learning-goals)
2. [Section 1 – Why Git?](#section-1--why-git)
3. [Section 2 – Accounts & Installs](#section-2--accounts--installs)
4. [Section 3 – Core Git Workflow](#section-3--core-git-workflow)
5. [Section 4 – Collaboration & Recovery](#section-4--collaboration--recovery)
6. [Section 5 – GitHub Pages](#section-5--github-pages)
7. [Section 6 – AI‑Powered Workflows](#section-6--ai-powered-workflows)
8. [Reference Cheat Sheet](#reference-cheat-sheet)

---

## Agenda & Learning Goals

|       Time      | Block                                                                                                  | Goals                                                    |
| :-------------: | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------- |
| **00:00‑00:10** | Welcome & Wi‑Fi                                                                                        | Everyone online, repo cloned                             |
| **00:10‑00:40** | **Section 1** – What *is* Git?                                                                         | Understand version control concepts, repos, commits      |
| **00:40‑00:50** | **☕ Break 1**                                                                                          |                                                          |
| **00:50‑01:40** | **Section 2** – Accounts & Installs                                                                    | GitHub account ✅, Git & VS Code installed ✅              |
| **01:40‑01:50** | **☕ Break 2**                                                                                          |                                                          |
| **01:50‑02:50** | **Section 3** – Core Workflow                                                                          | Clone → edit → commit → push 🎨                          |
| **02:50‑03:00** | **☕ Break 3**                                                                                          |                                                          |
| **03:00‑03:50** | **Section 4** – Collaboration & Recovery<br>**Section 5** – GitHub Pages<br>**Section 6** – AI Helpers | PRs, branching, time‑travel, free websites, Rode Code AI |
| **03:50‑04:00** | Wrap‑up & next steps                                                                                   | Deploy Pages site, resources                             |

---

## Section 1 – Why Git?

### 1.1 What problems does Git solve for artists?

* Safe experimentation (branches) without wrecking the original artwork.
* Track progress snapshots; roll back instantly.
* Easy collaboration & attribution.
* Portfolio in the open – share a link, not a ZIP.

### 1.2 Core concepts in one slide

| Concept        | Plain‑English Analogy                      |
| -------------- | ------------------------------------------ |
| **Repository** | A magic folder that remembers every change |
| **Commit**     | A numbered save‑point with a message       |
| **Branch**     | A parallel storyline of your project       |
| **Remote**     | The cloud copy on GitHub                   |

---

## Section 2 – Accounts & Installs

### 2.1 Create a GitHub account (5 min)

1. Go to [https://github.com/signup](https://github.com/signup)
2. Pick a memorable username (part of your eventual Pages URL).
3. Choose the **Free** plan.
4. Verify email before moving on.

### 2.2 Install Git

<details>
<summary>🖥️ macOS (Homebrew)</summary>

```bash
brew install git
```

</details>

<details>
<summary>🪟 Windows 10/11</summary>

1. Download **Git for Windows** installer: [https://gitforwindows.org](https://gitforwindows.org)
2. Keep default options, *especially* "Git from the command line and also from 3rd‑party software".
3. Re‑open **PowerShell** after install.

</details>

Verify either way:

```bash
git --version   # expect 2.40+ as of 2025
```

### 2.3 First‑time Git config (all OSes)

```bash
git config --global user.name  "Your Name"
git config --global user.email "your@email.com"
git config --global init.defaultBranch main
```

### 2.4 Install VS Code

* macOS: `brew install --cask visual-studio-code`
* Windows: Download installer: [https://code.visualstudio.com](https://code.visualstudio.com)

### 2.5 Install VS Code extensions

| Extension                         | Purpose                     | Install Command                                                |
| --------------------------------- | --------------------------- | -------------------------------------------------------------- |
| **GitHub Pull Requests & Issues** | Review & PRs inside VS Code | `code --install-extension github.vscode-pull-request-github`   |
| **Git Graph**                     | Visual history              | `code --install-extension mhutchie.git-graph`                  |
| **Markdown Preview Enhanced**     | Render this guide           | `code --install-extension shd101wyy.markdown-preview-enhanced` |
| **Rode Code**                     | AI code assistant           | `code --install-extension rode.code`                           |

After install, reload VS Code.

### 2.6 Configure Rode Code with OpenAI key (2 min)

1. Grab your key: [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)
2. In VS Code → **Preferences › Settings** → search **Rode Code: Api Key**.
3. Paste key.
   *Keys are stored locally; revoke anytime.*

---

## Section 3 – Core Git Workflow

### 3.1 Cloning the workshop repo

```bash
# already done if you followed the very first step, else:
git clone <REPLACE_WITH_REPO_URL> artists‑github‑workshop
cd artists‑github‑workshop
```

### 3.2 The 7 essential commands

| Command                                      | What it does            | Demo Scenario              |
| -------------------------------------------- | ----------------------- | -------------------------- |
| `git status`                                 | What changed?           | After editing `sketch.psd` |
| `git add <file>`                             | Stage change            | `git add sketch.psd`       |
| `git commit -m "Add first colour pass"`      | Save point              | each milestone             |
| `git log --oneline --graph --decorate --all` | Visual history          | after several commits      |
| `git pull`                                   | Download remote commits | when collaborator pushes   |
| `git push`                                   | Upload your commits     | whenever ready             |
| `git checkout -b experiment‑neon`            | New branch              | trying a wild style        |

### 3.3 Guided Exercise

1. Open `images/concept1.png` → draw on a new layer.
2. Stage & commit your change.
3. Create a new branch `alt‑palette` and tweak colours.
4. Compare branches with **Git Graph**.
5. Merge back (`git merge alt‑palette`) or reset if unhappy (`git checkout main && git branch -D alt‑palette`).

---

## Section 4 – Collaboration & Recovery

### 4.1 Forks vs Branches

* Use *forks* for public open‑source contributions.
* Use *branches* for private team work.

### 4.2 Opening a Pull Request (PR)

```bash
# push branch to GitHub
git push -u origin experiment-neon
# then click "Compare & pull request" button on GitHub
```

*Tip:* Use **GitHub Pull Requests & Issues** panel inside VS Code to create & review PRs without leaving your editor.

### 4.3 Undo recipes

| Situation                      | Command                                     |
| ------------------------------ | ------------------------------------------- |
| Undo last commit, keep changes | `git reset --soft HEAD~1`                   |
| Discard unstaged edits         | `git checkout -- <file>`                    |
| Recover deleted branch         | `git reflog` then `git branch <name> <sha>` |

---

## Section 5 – GitHub Pages (free portfolio site)

1. On GitHub, go to **Settings › Pages**.
2. Source: **Deploy from a branch** → pick `main` and `/docs` folder.
3. Push any HTML/Markdown file into `/docs` – site goes live at `https://<username>.github.io/<repo>/`.
4. Custom domain? Add CNAME record + wait for DNS.

> **Exercise** – Use the provided `template‑site/` folder. Copy it into `/docs`, push, share the link!

---

## Section 6 – AI‑Powered Workflows

### 6.1 Commit message generation

Select changed files in **Source Control** tab → click ✨ **Rode Code › Suggest Commit Message**.

### 6.2 Image‑to‑prompt via Rode Code

1. Right‑click an image file → **Rode Code › Generate Alt‑Text**.
2. The plugin uses the OpenAI Vision model; commit the alt text as part of accessibility best practices.

### 6.3 Prompt ideas

* "Refactor this README into a beginner‑friendly tutorial."
* "Suggest color‑blind‑safe palette variations for palette.json."
  Rode Code will embed the suggestions as a Git patch you can stage.

---

## Reference Cheat‑Sheet

```bash
# Config (once)
git config --global user.name  "John Doe"
git config --global user.email "john@doe.com"

# Start
mkdir project && cd project
git init
git remote add origin https://github.com/user/project.git

git status                      # what changed
git add .                        # stage all
git commit -m "🎨 initial commit"  # commit
git push -u origin main          # first push

git pull                        # sync

git branch feature-x            # create branch
git checkout feature-x          # switch

git merge feature-x             # merge back
git branch -d feature-x         # delete local branch
```

---

### Further Resources

* **Pro Git** book (free): [https://git-scm.com/book/en/v2](https://git-scm.com/book/en/v2)
* **Oh Sh\*t, Git!?** quick fixes: [https://ohshitgit.com/](https://ohshitgit.com/)
* **GitHub Learning Lab** interactive tutorials.
* Follow‑up challenges in `extra‑challenges/` folder.

---

**End of Guide – Happy Creating!**
