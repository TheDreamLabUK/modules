# Chapter 5: GitHub Pages: Your Free Portfolio Site

One of the most exciting features of [GitHub](https://github.com/) for creative technologists is **[GitHub Pages](https://pages.github.com/)**. It allows you to host a static website directly from your GitHub repository, completely free. This is perfect for portfolios, project showcases, documentation sites, or simple blogs.

The workshop highlighted this as "probably the most powerful bit from all of your point of view in terms of you can host your own stuff and it's free... everybody wants a free website, why wouldn't you?"

## 5.1 How GitHub Pages Works

GitHub Pages takes HTML, CSS, and JavaScript files (and Markdown files, which it can convert to HTML) from a specific branch and folder in your repository and publishes them as a website.

*   **Static Sites:** GitHub Pages is designed for static sites. This means the content is pre-built and served as-is to users. It doesn't support server-side languages like PHP, Python (e.g., Django/Flask), or Node.js backends directly in the way traditional web hosts do. However, you can build very rich interactive experiences using client-side JavaScript frameworks (like React, Vue, Angular) and then deploy the static build output to GitHub Pages.
*   **URL Structure:**
    *   **User/Organization Site:** If you name a repository `<username>.github.io` (where `<username>` is your GitHub username or organization name), the content from its `main` branch (usually from the root or a `/docs` folder) will be served at `https://<username>.github.io`. You can only have one such site per account/organization.
    *   **Project Site:** For any other repository, you can enable GitHub Pages. The site will typically be available at `https://<username>.github.io/<repository-name>/`.

## 5.2 Setting Up GitHub Pages for a Repository

Here's the general process, based on the `workshop.md` instructions:

1.  **Prepare Your Website Files:**
    *   Your website needs at least an `index.html` file at the root of where it will be served from. You can also have CSS files, JavaScript files, images, etc.
    *   For simplicity, you can place all your website files in the root of your repository or, more commonly, in a dedicated folder named `/docs` within your repository.

2.  **Push Your Files to GitHub:**
    *   Ensure your website files (e.g., `index.html`, CSS, JS) are committed to your local Git repository and pushed to GitHub.

3.  **Configure GitHub Pages Settings:**
    *   On GitHub, navigate to your repository.
    *   Click on the "**Settings**" tab for that repository.
    *   In the left sidebar of the Settings page, scroll down and click on "**Pages**".

4.  **Choose a Source:**
    *   Under "Build and deployment", for "Source", select "**Deploy from a branch**".
    *   **Branch:**
        *   Select the branch you want to deploy from (usually `main`).
        *   Select the folder within that branch:
            *   Choose `/(root)` if your website files are in the root of the branch.
            *   Choose `/docs` if your website files are in a folder named `docs` on that branch. This is a common and recommended practice.
    *   Click "**Save**".

5.  **Wait for Deployment:**
    *   GitHub will start building and deploying your site. This might take a few minutes.
    *   The Pages settings page will update to show the URL where your site is published (e.g., `https://<username>.github.io/<repository-name>/`).
    *   "Push any HTML/Markdown file into `/docs` – site goes live at `https://<username>.github.io/<repo>/`."

## 5.3 Example: Deploying a Simple Site

Let's imagine you have a repository named `my-portfolio`.

1.  Create a folder named `docs` in your local `my-portfolio` repository.
2.  Inside the `docs` folder, create an `index.html` file with simple content:
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <title>My Awesome Portfolio</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <h1>Welcome to My Portfolio!</h1>
        <p>Check out my amazing projects.</p>
    </body>
    </html>
    ```
3.  Also inside `docs`, create a `style.css` file:
    ```css
    body {
        font-family: sans-serif;
        margin: 20px;
        background-color: #f0f0f0;
    }
    h1 {
        color: navy;
    }
    ```
4.  Commit these files and push them to GitHub:
    ```bash
    git add docs/index.html docs/style.css
    git commit -m "Add initial website files for GitHub Pages"
    git push
    ```
5.  Go to your `my-portfolio` repository settings on GitHub, then to "Pages."
6.  Set the source to "Deploy from a branch," choose the `main` branch, and the `/docs` folder. Save.
7.  After a few minutes, your site should be live at `https://yourusername.github.io/my-portfolio/`.

The `workshop.md` included an exercise: "> **Exercise** – Use the provided `template‑site/` folder. Copy it into `/docs`, push, share the link!" This encourages hands-on practice.

## 5.4 Custom Domains

GitHub Pages also supports custom domains. If you own a domain name (e.g., `www.yourcreative.space`), you can configure it to point to your GitHub Pages site. This involves:

1.  Adding your custom domain in the GitHub Pages settings for your repository.
2.  Configuring DNS records (usually `CNAME` or `A` records) with your domain registrar to point to GitHub's servers.
    "Custom domain? Add CNAME record + wait for DNS."

This process can take some time for DNS changes to propagate.

GitHub Pages is a fantastic way to quickly get your work online. While the workshop decided "we're not going to do the web page stuff today we can come back to that another time... because it's more complicated," knowing it exists and the basic setup is a valuable part of your GitHub toolkit.

---

Next: [Chapter 6: AI-Powered Workflows with Roo Code](./06_ai_workflows_roo_code.md)