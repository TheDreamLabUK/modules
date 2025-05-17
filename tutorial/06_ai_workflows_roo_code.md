# Chapter 6: AI-Powered Workflows with Roo Code

This chapter brings together the [Git](https://git-scm.com/)/[GitHub](https://github.com/) foundation and your [VS Code](https://code.visualstudio.com/) setup with the power of Artificial Intelligence. We'll focus on using the [Roo Code extension](./02_d_roo_code_config.md), connected to your [Google Gemini API key](./02_c_gcp_api_key.md), to create an "AI-powered coding assistant" integrated directly into your editor.

The workshop described this as the point where "suddenly what you've got is the world's strongest AI... connected through a Vibe coding agent into GitHub. Then you've got absolutely everything you need to build projects."

## 6.1 What is Roo Code? (Recap)

As outlined in the original `workshop.md` and discussed:

[Roo Code](https://marketplace.visualstudio.com/items?itemName=RooAI.roo-code) is a VS Code extension that acts as an AI co-pilot. It allows you to:

*   **Generate Code:** Ask it to write functions, classes, or boilerplate based on descriptions.
*   **Explain Code:** Select code and ask for a plain English explanation.
*   **Refactor Code:** Get suggestions to improve or restructure existing code.
*   **Debug:** Ask for help identifying and fixing bugs.
*   **Answer Questions:** Get quick programming-related answers without leaving VS Code.
*   **Generate Documentation:** Create docstrings, comments, or even entire Markdown documents.

It uses your configured API key to communicate with powerful AI models like Google Gemini. The workshop emphasized its utility: "This is like connecting the AI directly to your file system but with checks and balances."

## 6.2 How to Use Roo Code: The "Vibe Coding" Approach

"Vibe coding" was a central theme in the workshop – an iterative, exploratory, and often conversational way of working with the AI.

1.  **Open the Roo Code Sidebar:**
    *   Click the Roo Code icon (the kangaroo) in the VS Code Activity Bar.

2.  **Interact via Chat:**
    *   Type questions or instructions into the Roo Code chat panel.
    *   **Be Specific (but also Conversational):** Instead of "write code," try "write a Python function that takes a list of numbers and returns their sum." Or, as the workshop demonstrated for project layout: "Lay out a project in this git directory for eye tracking in Python with a readme and all of the best directories."
    *   **Iterate:** If the first response isn't perfect, refine your question, ask follow-up questions, or provide more context. "If it gets confusing, you just ask it what the fuck's going on and it will tell you... Just keep asking it... until eventually you sort of break through."

3.  **Leverage Editor Context:**
    *   **Selection:** Select a piece of code in your editor *before* asking a question or giving an instruction. Roo Code will use the selected code as context (e.g., "Explain this selected code," "Refactor this function to be more efficient," "Suggest color‑blind‑safe palette variations for this palette.json").
    *   **Active File/Project:** Roo Code can consider the content of your currently active file and even other files in your project (especially if you've enabled "Read" in Auto-Approve settings). This allows for deep contextual understanding. "You can put all of your project documents into your directory here... and say just look through this lot and make me a document out of it."

4.  **Apply Suggestions & Manage Output:**
    *   Roo Code might offer code snippets, patches, or entire file structures.
    *   You can copy these, or Roo Code might directly write/modify files if "Write" is enabled in Auto-Approve.
    *   **Crucially, use Git:** "You can't work with AI unless you're using this [version control] because it will smash up everything that it made before all the time... So you need to be doing source control." Commit your changes frequently so you can roll back if the AI generates something undesirable.

5.  **Control Roo Code Modes:**
    *   Remember the **Ask**, **Code**, and **Architect** modes at the bottom of the Roo Code panel. Switch between them based on your needs. For generating project structures or writing code, ensure you're in **Code** mode.

6.  **Manage Rate Limiting & Costs:**
    *   If you configured the 30-second rate limit, Roo Code will pause between operations. "Your rate limiter should have kicked in at 30 seconds. This is how it remains free."
    *   If you need faster responses for intensive work and are willing to use your Google Cloud free credits (or pay), you can create another Roo Code profile *without* the rate limit enabled and switch to it.
    *   Keep an eye on the cost ticker in Roo Code if you're on an un-rate-limited profile: "You see the little cost ticker there? That's real cost... if you wanted to put it into unconstrained mode, you can keep an eye on your cost up there."

## 6.3 Prompt Ideas for Creative Technologists

The `workshop.md` and transcript offered several ideas:

*   **Project Scaffolding:** "Lay out a project in this git directory for an eye tracker in Python with a readme and all of the best directories."
*   **Documentation:** "Refactor this README into a beginner‑friendly tutorial."
*   **Creative Asset Generation/Modification:** "Suggest color‑blind‑safe palette variations for palette.json." (Roo Code might embed suggestions as a Git patch).
*   **Complex Document Creation:** "Make a directory called horizon-bid and populate it with a project structure for an academic bid... including Mermaid, Gantt charts, and costing plan templates."
*   **Diagrams as Code:** "Create me a complex and delightful Gantt chart for bootstrapping a creative technology agency called Dreamloop" (using Mermaid syntax, which can then be rendered).
    ```mermaid
    gantt
        dateFormat  YYYY-MM-DD
        title Dreamloop Agency Bootstrap
        section Foundation
        Research & Planning       :a1, 2024-01-01, 30d
        Legal & Financial Setup   :a2, after a1, 14d
        section Branding & Online Presence
        Brand Identity Development :b1, after a1, 21d
        Website & Portfolio Dev   :b2, after b1, 45d
        section Operations
        Service Definition        :c1, after a2, 14d
        Tooling & Workflow Setup  :c2, after c1, 30d
    ```
*   **Understanding Existing Code:** "Describe this project" (after cloning a complex repository like ComfyUI).

The key is experimentation. "Think of something off the cuff... Honestly, you don't know what ballpark you're in until you've tried it. This is wildly jagged frontier vibe code madness. It will do anything you ask."

## 6.4 The Power of AI with Local File Access

A significant advantage of using Roo Code in VS Code over web-based AI chat interfaces is its ability to read from and write to your local file system (with your permission via Auto-Approve settings).

*   **Contextual Understanding:** It can read multiple files in your project to understand the broader context, leading to more relevant and accurate suggestions.
*   **Bulk Operations:** It can generate entire directory structures, fill them with template files, or refactor code across multiple files. "You can get it to lay out whole directory structures and fill them with text files and do an enormous amount of bulk work in a way that you just can't do with the other interfaces."
*   **Persistent Memory (within session):** The AI's "understanding" of your project grows as you interact with it within a session.

This local integration, combined with robust version control via Git, creates a highly dynamic and powerful development environment. "The whole of the AI is connected to the whole of the documents, the whole of the time on your own system in a private way, connected to the version management system, connected to the rest of the team."

The workshop concluded that this setup provides "the ultimate version of AI tool working." The learning curve involves "three months of frustrated, repeatedly asking it what the fuck's going on" but ultimately leads to a profound new way of working.

---

Next: [Chapter 8: Advanced Typesetting: LaTeX with WSL2, TeXLive, and VS Code](./08_latex_wsl_vscode.md)