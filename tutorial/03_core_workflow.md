# Chapter 3: The Core Git Workflow

Now that your environment is set up, it's time to learn the fundamental [Git](https://git-scm.com/) workflow. This is the cycle of operations you'll perform repeatedly when working on projects. We'll cover cloning a repository, the essential commands, and a hands-on exercise.

The workshop aimed to "get to the point where you can just switch it on, vibe code, and then start to figure out the source management stuff." This chapter focuses on that source management.

## 3.1 Cloning a Repository (Getting an Existing Project)

Often, you'll start by "cloning" an existing repository from [GitHub](https://github.com/) (or another remote source) to your local machine. This creates a local copy of the project, including all its files and history.

**Steps to Clone:**

1.  **Find the Repository URL:**
    *   On GitHub, navigate to the main page of the repository you want to clone.
    *   Look for a green button that usually says "**<> Code**". Click it.
    *   A dropdown will appear. Ensure **HTTPS** is selected (it's usually the default).
    *   Copy the URL provided. It will look something like `https://github.com/username/repository-name.git`.
    *   The workshop mentioned an alternative for VS Code: "If you just close whatever you've got... this welcome screen is fine... What we want to do is clone a Git repo... provide the repository URL... It's actually just the thing that's at the top here [browser URL bar]." While the browser URL can sometimes work, the dedicated clone URL from the "<> Code" button is more reliable.

2.  **Clone using VS Code (Recommended):**
    *   Open VS Code.
    *   If you see the Welcome page, click on "**Clone Git Repository...**".
    *   Paste the repository URL you copied into the prompt that appears and press Enter.
    *   VS Code will then ask you to select a **local folder** on your computer where the repository should be cloned. Choose or create a suitable directory.
    *   VS Code will clone the repository. Once done, it will likely ask, "Would you like to open the cloned repository?" Click "**Open**."

3.  **Clone using the Command Line (Alternative):**
    *   Open your terminal (Git Bash, PowerShell, or Terminal on macOS).
    *   Navigate to the directory where you want to store the project (`cd path/to/your/projects_folder`).
    *   Run the command: `git clone <repository_url>` (replace `<repository_url>` with the actual URL).
    *   This will create a new folder with the repository's name in your current directory. You can then open this folder in VS Code (`File > Open Folder...`).

The workshop demonstrated this: "I'm going to paste in that thing [the URL]... It's asking me where to put it... Select as repository destination... Pulling the whole of that project. It's not just pulling the code, it's pulling the whole of that Git history."

## 3.2 The 7 Essential Git Commands

While VS Code provides a graphical interface for many Git operations (which we'll explore), understanding the underlying commands is beneficial. Here are the essentials, as listed in the original `workshop.md`:

| Command                                      | What it does                                     | Typical Scenario                                     |
| -------------------------------------------- | ------------------------------------------------ | ---------------------------------------------------- |
| [`git status`](https://git-scm.com/docs/git-status)                                 | Shows what files have changed or are untracked.  | Run frequently to see the state of your working directory. |
| [`git add <file_or_folder>`](https://git-scm.com/docs/git-add) or `git add .` | Stages changes, preparing them for a commit. `.` stages all changes. | After editing files and before committing.           |
| [`git commit -m "Your message"`](https://git-scm.com/docs/git-commit)           | Saves the staged changes to your local repository with a descriptive message. | After staging changes, to create a snapshot.         |
| [`git log`](https://git-scm.com/docs/git-log) (e.g., `git log --oneline --graph --decorate --all`) | Shows the commit history.                        | To review past commits and project evolution.        |
| [`git pull`](https://git-scm.com/docs/git-pull)                                   | Fetches changes from the remote repository and merges them into your current local branch. | Before starting work, or when a collaborator pushes. |
| [`git push`](https://git-scm.com/docs/git-push)                                   | Uploads your local commits to the remote repository. | When you're ready to share your committed changes.   |
| [`git checkout -b <new_branch_name>`](https://git-scm.com/docs/git-checkout)      | Creates a new branch and switches to it.         | When starting a new feature or experiment.           |
| [`git branch`](https://git-scm.com/docs/git-branch)                               | Lists, creates, or deletes branches.             | To see current branches or manage them.              |
| [`git merge <branch_name>`](https://git-scm.com/docs/git-merge)                     | Combines the history of the specified branch into the current branch. | To integrate completed features back into `main`.    |

**Visualising the Local Workflow:**

```mermaid
graph TD
    A[Working Directory: Files you edit] -- git add --> B(Staging Area: Files marked for next commit);
    B -- git commit --> C(Local Repository: Project history);
    C -- git push --> D{Remote Repository (GitHub)};
    D -- git pull --> C;
```

## 3.3 Guided Exercise: Your First Local Project, Commits, and Branches

Let's put this into practice without connecting to a remote GitHub repository yet. This focuses on your local Git workflow.

1.  **Create a Project Folder (if you haven't already):**
    *   In VS Code, go to `File > Open Folder...`.
    *   Create a new folder on your computer (e.g., `my-git-practice`) and open it.
    *   The workshop described this: "Go into the file explorer and create a project directory... We'll call it my first project."

2.  **Initialize a Git Repository:**
    *   Open the Source Control panel in VS Code (the icon with three circles connected by lines, or `Ctrl+ShiftG` / `Cmd+Shift+G`).
    *   You should see a button like "**Initialize Repository**". Click it.
    *   This runs `git init` in your project folder, turning it into a local Git repository.
    *   The workshop: "Once you're in that folder, you can go back to source control and do initialize repository."

3.  **Create and Modify a File:**
    *   In the VS Code Explorer (top left icon), right-click in the empty space of your `my-git-practice` folder and select "New File...".
    *   Name it `README.md`.
    *   Add some text to it, for example:
        ```markdown
        # My Git Practice Project

        This is my first project using Git!
        ```
    *   Save the file (`Ctrl+S` / `Cmd+S`).

4.  **Check Status and Stage Changes:**
    *   Go to the Source Control panel. You should see `README.md` listed under "Changes" with a "U" (untracked) or "M" (modified) next to it.
    *   Hover over `README.md` and click the **`+` (Stage Changes)** icon. This runs `git add README.md`. The file will move to "Staged Changes."

5.  **Commit Changes:**
    *   In the "Message" box at the top of the Source Control panel, type a descriptive commit message, e.g., "Create initial README.md".
    *   Click the **Commit** button (often a checkmark icon ✔️) or press `Ctrl+Enter` / `Cmd+Enter`.
    *   This runs `git commit -m "Create initial README.md"`.
    *   The workshop: "In this commit message here I'm going to say... vibe coded a... tracker... and then vibe smashed a horizon... I'm gonna hit commit there."

6.  **Make More Changes and Commit:**
    *   Open `README.md` again. Add another line: `Learning the core Git workflow.` Save it.
    *   Go back to Source Control. Stage the change (`+` icon).
    *   Commit with a message like "Add workflow note to README".

7.  **Create a Branch:**
    *   At the bottom-left of the VS Code window, you'll usually see the current branch name (likely `main`). Click on it.
    *   A command palette will open at the top. Select "**+ Create new branch...**".
    *   Enter a name for your new branch, e.g., `feature/add-details`. Press Enter.
    *   You are now on the `feature/add-details` branch.

8.  **Work on the New Branch:**
    *   In `README.md`, add another section:
        ```markdown
        ## Features
        - Learning branching
        ```
    *   Save the file.
    *   Stage and commit this change on the `feature/add-details` branch with a message like "Add features section".

9.  **Switch Branches and Observe:**
    *   Click the branch name (`feature/add-details`) in the bottom-left again.
    *   Select `main` from the list to switch back to the main branch.
    *   Notice that `README.md` reverts to the version *before* you added the "Features" section. This is because those changes are isolated on the `feature/add-details` branch.

10. **Merge the Branch (Optional for this exercise):**
    *   To bring the changes from `feature/add-details` into `main`:
        *   Ensure you are on the `main` branch.
        *   Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`), type `Git: Merge Branch...`, and select it.
        *   Choose `feature/add-details` from the list of branches to merge.
    *   The "Features" section will now appear in `README.md` on the `main` branch.
    *   Commit the merge (VS Code might do this automatically or prompt you).

11. **View History (Using Git Graph Extension):**
    *   Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
    *   Type `Git Graph: View Git Graph` and select it.
    *   A new tab will open showing a visual representation of your commits and branches. This is incredibly helpful for understanding your project's history.

This exercise covers the fundamental local Git cycle: modify, stage, commit, branch, and merge. The workshop emphasised the importance of version control with AI: "You can't work with AI unless you're using this [version control] because it will smash up everything that it made before... So you need to be doing source control."

---

Next: [Chapter 4: Collaboration & Recovery](./04_collaboration_recovery.md)