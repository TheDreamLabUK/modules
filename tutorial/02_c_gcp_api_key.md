# Chapter 2c: Setting up a Google Cloud API Key for AI

To use AI-powered features in [Roo Code](./06_ai_workflows_roo_code.md) (and many other AI tools), you'll often need an API key from a cloud provider. This key allows the tool to communicate with powerful AI models. We'll focus on getting a free API key from [Google Cloud Platform (GCP)](https://cloud.google.com/) to use with Google's Gemini models.

The workshop emphasised that this step "will be incredibly useful for you for everything, and you can plug it into all the tools that you use."

## 2c.1 Understanding Google Cloud Free Tier & Credits

*   **Free Credits:** As a new user to Google Cloud Console, you are often eligible for a significant amount of free credits (e.g., $300 for 90 days). This is a "huge benefit" and an "Easter egg" of the setup process.
*   **Card Details:** To activate these credits and use GCP services, Google will likely require you to provide credit card details.
    *   **Caution:** While the goal is to use the services for free (especially with rate-limiting, discussed later), be aware that cloud platforms are designed to make it easy to spend money if you exceed free tiers or misconfigure services. The workshop noted, "this is how they get you... they offer you the freebie, and then if you kind of run the stops on it, then it starts charging you." However, the instructor also mentioned, "I haven't ever spilled out into my card on this."
*   **Rate Limiting:** We will later configure Roo Code with a rate limit. The theory is that "if we get you set up today with the rate limiter, it should never spend anything," and might not even tap into your $300 free credits, preserving them for other experiments.

## 2c.2 Steps to Get Your Google Cloud API Key (approx. 10-20 mins)

The GCP console can be "one of the most... complicated sets of menus on the internet." Follow these steps carefully. The interface may have changed slightly since the workshop, but the core actions should be similar.

1.  **Sign in to Google Cloud Console:**
    *   Go to [https://console.cloud.google.com/](https://console.cloud.google.com/).
    *   Sign in with your Google account. If you don't have one, you'll need to create it.
    *   You'll likely see an offer to "Start your free trial with $300 in credit." Agree to the terms and proceed. This is where you'll likely need to enter payment details. The workshop participants confirmed this step.
    *   If you encounter issues with card verification (as one participant did: "it doesn't like either of my bank cards"), you might need to try a different card or contact Google support. For the workshop, a temporary shared key was provided as a backup, but the goal here is for you to get your own.

2.  **Create or Select a Project:**
    *   AI services in GCP are associated with a "project."
    *   After signing in and activating your trial, you may be prompted to create your first project, or you might land on a dashboard.
    *   Look for an option to create a **"NEW PROJECT"** or select an existing one if you have one. This is often found via a project selector dropdown at the top of the page or under "IAM & Admin" > "Create a Project" in the navigation menu (the "hamburger icon" ☰).
    *   Give your project a name (e.g., "My AI Experiments," "Workshop Demo Project," or "Vertex Gemini Project"). The name doesn't critically affect functionality for our purposes. "Any old project name doesn't matter," was the advice.
    *   Click **"CREATE"**.

3.  **Navigate to API Credentials:**
    *   Once your project is created and selected, open the main navigation menu (☰).
    *   Scroll down and find **"APIs & Services."**
    *   Within "APIs & Services," click on **"Credentials."**

4.  **Create an API Key:**
    *   On the "Credentials" page, click the **"+ CREATE CREDENTIALS"** button (usually at the top).
    *   Select **"API key"** from the dropdown menu.
    *   An API key (a long string of characters) will be generated and displayed.
    *   **Important:** Copy this key immediately and store it in a safe, private place (like a password manager). You will need this key for Roo Code.
    *   You can close the "API key created" dialog for now. You can always view the key again from the Credentials page by clicking "SHOW KEY."

5.  **Enable the Gemini API (Crucial Step!):**
    *   Initially, your new API key might be "unrestricted" but not yet permitted to access specific AI services. During the workshop, a freshly created key resulted in a "forbidden" error when tested, because the necessary API wasn't enabled.
    *   In the navigation menu (☰), go to **"APIs & Services"** again.
    *   This time, select **"Library"** (or you might see "Enabled APIs & services" which then has a button to go to the library or "+ ENABLE APIS AND SERVICES").
    *   In the API Library, you'll see a search bar. Type **"Gemini API"** into the search bar and press Enter.
    *   You should see "Gemini API" in the search results (possibly among others like "Vertex AI Gemini API"). Select the primary "Gemini API."
    *   Click the **"ENABLE"** button for the Gemini API. This might take a few moments.

6.  **Verify API Key (Optional but Recommended):**
    *   Once the Gemini API is enabled, your previously created API key *should* now have permission to use it. The workshop confirmed this: "In theory, the credentials we created over here... this API key should just be able to use that."

7.  **Restrict Your API Key (Security Best Practice):**
    *   While the workshop sometimes skipped this for speed, the original `workshop.md` and general security advice strongly recommend restricting your API key. This limits what the key can do and helps prevent misuse if it's ever compromised.
    *   Go back to **"APIs & Services" > "Credentials."**
    *   Find your API key in the list and click on its name or the pencil icon to edit it.
    *   Under **"API restrictions"**:
        *   Select **"Restrict key."**
        *   From the dropdown ("Select APIs"), choose the **"Gemini API"** (and any other specific APIs you intend this key to use, e.g., "Vertex AI API" if you explore that later).
    *   Under **"Application restrictions"** (optional, for added security):
        *   You can restrict usage to specific IP addresses, etc. For local tools like VS Code extensions, this can be tricky if your IP changes. You can often leave this as "None" for simplicity when starting.
    *   Click **"SAVE."**

You now have a Google Cloud API key, hopefully configured securely, and ready to be used with Roo Code in VS Code. Remember to keep this key confidential.

The workshop experience showed this can be a fiddly process: "It's a pain in the arse that interface... but you won't stop me slow you down today because we've got the key." The key takeaway is that you need *an* API key that is *enabled* for the "Gemini API."

---

Next: [2d. Configuring Roo Code in VS Code](./02_d_roo_code_config.md)