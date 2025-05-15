# Chapter 1: Why Git? Understanding Version Control

Before diving into the "how," let's explore the "why." What is [Git](https://git-scm.com/), what is [GitHub](https://github.com/), and what problems do they solve, especially for creative technologists?

## 1.1 What Problems Does Git Solve?

Imagine working on a complex creative project – a piece of software, an interactive installation, a detailed design, or even a lengthy written work. You might encounter scenarios like:

*   Wanting to try a radical new idea but being afraid of messing up your current progress.
*   Accidentally deleting a crucial part of your work and wishing you could go back in time.
*   Collaborating with others and struggling to merge different versions or track who did what.
*   Needing to share your project with collaborators or clients without sending cumbersome ZIP files.

Git is a **version control system** designed to address these very challenges. It allows you to:

*   **Experiment Safely:** Create "branches" (parallel versions) of your project to try new things without affecting the main work. If an experiment doesn't pan out, you can easily discard it.
*   **Track Progress & Roll Back:** Save "commits" (snapshots) of your project at various stages. Each commit has a message describing the changes. This creates a detailed history, allowing you to revert to any previous state instantly.
*   **Collaborate Effectively:** Git helps manage contributions from multiple people, making it easier to merge changes and understand the project's evolution. It provides clear attribution for every change.
*   **Showcase Your Work:** Platforms like GitHub allow you to host your Git repositories online, creating a public (or private) portfolio. This is far more professional and accessible than emailing files.
*   **Engage with Open Source:** GitHub is the hub for open-source software. Having a presence there allows you to contribute to projects, find collaborators, and build a public footprint in the creative technology community. As the workshop highlighted, it's "the plug hole around which all of this circles."

## 1.2 Core Git Concepts in Plain English

Here are the fundamental ideas in Git, simplified:

| Concept        | Plain‑English Analogy                                       |
| -------------- | ----------------------------------------------------------- |
| **Repository** | A "magic folder" that remembers every change made to its contents. Often called a "repo." |
| **Commit**     | A numbered save-point with a descriptive message. Think of it as taking a snapshot of your project at a specific moment. |
| **Branch**     | A parallel storyline or version of your project. Allows you to work on different features or ideas independently. |
| **Remote**     | The cloud copy of your repository, typically hosted on a platform like [GitHub](https://github.com/). This is how you share and back up your work. |

We can visualise this flow:

```mermaid
graph LR
    A[Local Computer] -- git add --> B(Staging Area);
    B -- git commit --> C(Local Repository);
    C -- git push --> D[Remote Repository (GitHub)];
    D -- git pull / git clone --> A;
    C -- git branch --> E(New Branch);
    E -- git checkout --> C;
    E -- git merge --> C;
```

## 1.3 Git vs. GitHub: What's the Difference?

This is a common point of confusion:

*   **Git:** Is the underlying version control software. It's a command-line tool that runs locally on your computer. Linus Torvalds, the creator of Linux, developed Git to manage the Linux kernel development. You can use Git entirely offline without ever touching GitHub.
*   **GitHub:** Is a web-based platform that provides hosting for Git repositories. It adds a web interface, collaboration features (like Pull Requests, issue tracking), user management, and other services (like [GitHub Pages](./05_github_pages.md)) on top of Git.

Think of it this way: Git is the engine, and GitHub is one popular make and model of a car that uses that engine. While there are other Git hosting services (like GitLab or Bitbucket), GitHub is the most widely used, especially in the open-source world.

For the purposes of this tutorial, while we'll be installing and using Git locally, our primary interaction with a remote service will be through GitHub. As the workshop noted, "you don't need to worry about the difference, you can just think of it as GitHub... GitHub is built on Git."

---

Next: [Chapter 2: Essential Setup: Accounts & Installations](./02_setup_overview.md)