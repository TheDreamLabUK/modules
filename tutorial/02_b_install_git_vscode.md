# Chapter 2b: Installing Git & VS Code

With your GitHub account ready, the next step is to install the core local tools: [Git](https://git-scm.com/) itself and [Visual Studio Code (VS Code)](https://code.visualstudio.com/), our recommended code editor.

## 2b.1 Install Git

[Git](https://git-scm.com/) is the version control system that runs on your computer. Even if you primarily use GitHub's web interface, Git needs to be installed locally for many operations, especially when working with VS Code.

**macOS Users:**
If you're on a Mac, Git might already be installed as part of the Xcode Command Line Tools. You can check by opening Terminal (Applications > Utilities > Terminal) and typing:
```bash
git --version
```
If it's not installed, or you want the latest version, [Homebrew](https://brew.sh/) is the recommended way:
```bash
brew install git
```
The workshop transcript notes: "you get Git automatically as a Mac user, it's built in, right? We [Windows users] have to jump through some additional hoops." While often true, ensuring you have a recent version via Homebrew is good practice.

**Windows 10/11 Users:**
1.  Download the **Git for Windows** installer from the official site: [https://gitforwindows.org](https://gitforwindows.org).
2.  Run the installer. It's generally safe to keep the default options, but pay special attention to the option "Git from the command line and also from 3rd‑party software" – ensure this is selected. This allows tools like VS Code to use Git.
3.  After installation, you might need to re-open any command prompt windows (like Git Bash, Command Prompt, or PowerShell) for the changes to take effect.

**Verify Installation (All Operating Systems):**
Open your terminal (Terminal on macOS, Git Bash or PowerShell on Windows) and type:
```bash
git --version
```
You should see a version number, ideally 2.40 or newer (as of early 2025).

## 2b.2 First-Time Git Configuration

After installing Git, there are a few global configuration settings you should apply. These tell Git who you are, which is important because this information is embedded in every commit you make. Open your terminal and run these commands, replacing the placeholder text with your actual name and the email address you used for your GitHub account:

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
git config --global init.defaultBranch main
```
*   `user.name`: Your full name.
*   `user.email`: The email associated with your GitHub account.
*   `init.defaultBranch main`: Sets the default branch name for new repositories to `main`, which is the current standard.

## 2b.3 Install Visual Studio Code (VS Code)

[VS Code](https://code.visualstudio.com/) is a free, powerful, and highly popular source code editor developed by Microsoft. It has excellent built-in support for Git and a vast library of extensions to customise its functionality.

As mentioned in the workshop, "VS Code... it's a full-on programming API. It's a little bit of a bastard, but what I'm going to do is show you just the minimum amount that you need to do to connect it up to GitHub."

**macOS Users:**
The easiest way is often via [Homebrew](https://brew.sh/):
```bash
brew install --cask visual-studio-code
```
Alternatively, download it directly from [https://code.visualstudio.com](https://code.visualstudio.com).

**Windows Users:**
Download the installer from the official website: [https://code.visualstudio.com](https://code.visualstudio.com). Run the installer, keeping the default options is usually fine. Adding VS Code to your PATH and enabling "Open with Code" context menus can be very helpful.

Once installed, launch VS Code. You'll be greeted with a welcome screen. You can explore the "Learn Fundamentals" if you wish, but we'll be guiding you through the necessary steps.

## 2b.4 Install Recommended VS Code Extensions

VS Code's power is significantly enhanced by its extensions. You can find and install extensions from the Extensions view in VS Code (click the square icon in the Activity Bar on the left, or press `Ctrl+Shift+X` or `Cmd+Shift+X`).

Here are the key extensions mentioned in the workshop:

1.  **Roo Code (formerly RooCommandLine / Roo AI):**
    *   **Purpose:** This is the AI code assistant we'll be using. It connects to AI models (like Google Gemini, which we'll set up with an API key) to provide code generation, explanation, refactoring, and more, directly within VS Code.
    *   **Install:** Search for `Roo Code` in the Extensions Marketplace and install it. The workshop noted some confusion with forks: "It used to be called Roo Line. It's now called Roo Code... Generally speaking, the one at the top is the one that's been downloaded the most, so it's generally speaking the one you want. So Roo Code previously RooCommandLine, that one's fine."
    *   We will configure this in [Chapter 2d](./02_d_roo_code_config.md).

2.  **Git Graph:**
    *   **Purpose:** Provides a visual representation of your Git repository's branch history, making it much easier to understand merges, branches, and commit history.
    *   **Install:** Search for `Git Graph` (often by mhutchie) and install it.

3.  **Markdown Preview Mermaid Support (or Markdown Preview Enhanced):**
    *   **Purpose:** Enhances VS Code's built-in Markdown preview, crucially adding support for [Mermaid diagrams](https://mermaid.js.org/intro/). Mermaid allows you to create diagrams (flowcharts, sequence diagrams, Gantt charts, etc.) using a text-based syntax, which is incredibly useful for documentation.
    *   **Install:** Search for `Markdown Preview Mermaid Support` or `Markdown Preview Enhanced` and install one. The workshop specifically mentioned installing a Markdown renderer with Mermaid support: "search Markdown and then install Markdown preview mermaid support, install that one... Mermaid is the diagrams as code, and it makes everything better."

**A Note on Installing Extensions:**
The workshop cautioned: "Extensions can be installed in the extension browser. Be a little careful with this as it's possible to install malicious code." Stick to well-known and highly-rated extensions. The ones listed above are widely used and trusted.

After installing extensions, VS Code might prompt you to reload. It's a good idea to do so to ensure the extensions are activated correctly.

With Git and VS Code installed and configured, you're well on your way to having a complete local development setup.

---

Next: [2c. Setting up a Google Cloud API Key for AI](./02_c_gcp_api_key.md)