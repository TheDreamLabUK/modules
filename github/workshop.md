# GitHub – 4 Hour Hands‑On Workshop

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

---

## Agenda & Learning Goals

|       Time      | Block                                                                                                  | Goals                                                    |
| :-------------: | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------- |
| **00:00‑00:10** | Welcome & Wi‑Fi                                                                                        | Everyone online, repo cloned                             |
| **00:10‑00:40** | **Section 1** – What *is* Git?                                                                         | Understand version control concepts, repos, commits, ghpages      |
| **00:40‑00:50** | **☕ Break 1**                                                                                          |                                                          |
| **00:50‑01:40** | **Section 2** – Accounts & Installs                                                                    | GitHub account ✅, Git & VS Code installed ✅              |
| **01:40‑01:50** | **☕ Break 2**                                                                                          |                                                          |
| **01:50‑02:50** | **Section 3** – Core Workflow                                                                          | Clone → edit → commit → push 🎨                          |
| **02:50‑03:00** | **☕ Break 3**                                                                                          |                                                          |
| **03:00‑03:50** | **Section 4** – Collaboration & Recovery<br>**Section 5** – GitHub Pages<br>**Section 6** – AI Helpers | PRs, branching, time‑travel, free websites, Roo Code AI |
| **03:50‑04:00** | Wrap‑up & next steps                                                                                   | Deploy Pages site, resources                             |

---

## Section 1 – Why Git?

### 1.1 What problems does Git solve for creative technologists?

* Safe experimentation (branches) without wrecking the original work.
* Track progress snapshots; roll back instantly.
* Easy collaboration & attribution.
* Portfolio in the open – share a link, not a ZIP.
* Open source public footprint - find collaborators

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
3. Re‑open **git bash** after install.

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

Extensions can be installed in the extension browser. Be a little careful with this as it's possible to install malicious code.
Let's see an example.
https://github.com/mjbvz/vscode-markdown-mermaid


| Extension                         | Purpose                     | Install Command                                                |
| --------------------------------- | --------------------------- | -------------------------------------------------------------- |
| **Git Graph**                     | Visual history              | `search git graphh`                  |
| **Markdown Preview Enhanced**     | Render this guide           | `search markdown mermaid` |
| **Roo Code**                     | AI code assistant           | `search roo code`                           |

After install, reload VS Code.

### 2.6 Setting up Google Cloud and API Key (10 min)

To use AI-powered features in Roo Code (and many other AI tools), you'll often need an API key from a cloud provider. Here’s how to get one from Google Cloud Platform (GCP):

1.  **Sign in to Google Cloud Console:**
    *   Go to [https://console.cloud.google.com/](https://console.cloud.google.com/).
    *   If you don't have an account, you'll need to sign up. Google often provides free credits for new users.
2.  **Create or Select a Project:**
    *   AI services are typically associated with a project.
    *   At the top of the page, click the project selector.
    *   Either select an existing project or click "**NEW PROJECT**".
    *   Give your project a name (e.g., "My AI Experiments") and click "**CREATE**".
3.  **Enable Necessary APIs (Example: Vertex AI):**
    *   Once your project is selected, use the navigation menu (hamburger icon ☰) and go to **APIs & Services > Library**.
    *   Search for the API you intend to use (e.g., "Vertex AI API" for many Google AI models, or the specific API Roo Code requires).
    *   Click on the API and then click "**ENABLE**".
    *   *(Note: The specific API needed will depend on the AI tool or service you're configuring. Check the Roo Code documentation if a specific Google Cloud API is mentioned.)*
4.  **Create an API Key:**
    *   In the navigation menu, go to **APIs & Services > Credentials**.
    *   Click "**+ CREATE CREDENTIALS**" at the top of the page.
    *   Select "**API key**" from the dropdown.
    *   Your API key will be created and displayed. **Copy this key immediately and store it securely.** You'll need it for Roo Code.
5.  **Restrict Your API Key (Highly Recommended):**
    *   For security, it's crucial to restrict your API key.
    *   In the API key list on the Credentials page, find your newly created key and click the pencil icon (Edit API key) or its name.
    *   Under "**API restrictions**":
        *   Select "**Restrict key**".
        *   From the dropdown, choose the specific API(s) the key should have access to (e.g., "Vertex AI API").
    *   Under "**Application restrictions**" (optional, for added security):
        *   You can restrict usage to specific IP addresses, websites, etc. For local tools like VS Code extensions, this might be less straightforward if your IP address changes frequently.
    *   Click "**SAVE**".

You now have a Google Cloud API key ready to be used. Make sure to keep it confidential.

---
### 2.7 Configure Roo Code with Google Cloud API Key (5 min)

1.  Use the Google Cloud API Key you created in **Section 2.6**.
2.  In VS Code → **Preferences › Settings** (or `Cmd+,` / `Ctrl+,`).
3.  Search for **Roo Code: Api Key** and paste your key there.
4.  Search for **Roo Code: Rate Limit Timeout** and set it to `30000` (milliseconds, for 30 seconds).
    *API keys are stored locally in your VS Code settings. You can revoke them anytime from the Google Cloud Console.*

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

### 6.1 What is Roo Code?

Roo Code is a VS Code extension that acts as an AI-powered coding assistant. It integrates directly into your editor, allowing you to leverage artificial intelligence to help with various coding tasks, such as:

*   **Code generation:** Ask Roo Code to write functions, classes, or boilerplate code based on your descriptions.
*   **Code explanation:** Select a piece of code and ask Roo Code to explain what it does in plain English.
*   **Refactoring:** Get suggestions on how to improve or restructure existing code.
*   **Debugging:** Ask for help in identifying and fixing bugs.
*   **Answering questions:** Get quick answers to programming-related questions without leaving your editor.
*   **Generating documentation:** Create docstrings or comments for your code.

It uses the API key you configured (from Google Cloud in our setup) to communicate with powerful AI models.

### 6.2 How to use Roo Code

Once installed and configured with your API key:

1.  **Open the Roo Code sidebar:** Look for the Roo Code icon in the VS Code activity bar (usually on the left).
2.  **Interact via chat:** You can type questions or instructions directly into the Roo Code chat panel.
    *   Be specific with your requests. For example, instead of "write code," try "write a Python function that takes a list of numbers and returns their sum."
3.  **Use context from your editor:**
    *   **Selection:** Select a piece of code in your editor before asking a question. Roo Code will often use the selected code as context for its response (e.g., "Explain this selected code," or "Refactor this function to be more efficient").
    *   **Active File:** Roo Code can also consider the content of your currently active file.
4.  **Apply suggestions:** Roo Code might offer code snippets or patches. You can usually copy these directly or apply them with a click.
5.  **Iterate:** If the first response isn't perfect, refine your question or ask follow-up questions.

Experiment with different prompts and selected code to see how Roo Code can best assist your workflow.

### 6.3 Prompt ideas

* "Refactor this README into a beginner‑friendly tutorial."
* "Suggest color‑blind‑safe palette variations for palette.json."
  Roo Code will embed the suggestions as a Git patch you can stage.

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


