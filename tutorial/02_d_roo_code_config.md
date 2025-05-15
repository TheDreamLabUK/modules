# Chapter 2d: Configuring Roo Code in VS Code

With your Google Cloud API key in hand, it's time to connect it to the [Roo Code](https://marketplace.visualstudio.com/items?itemName=RooAI.roo-code) extension in VS Code. This will enable AI-powered assistance directly within your editor.

## 2d.1 Accessing Roo Code Settings

1.  **Open Roo Code:**
    *   In VS Code, locate the Roo Code icon in the Activity Bar (usually on the far left side). It often looks like a kangaroo. Click it to open the Roo Code panel.
    *   The workshop described this: "You should now have a little kangaroo down here. This right-hand interface is the code that you're working on... Over here on the very top right of the screen, is a button that pulls out its integrated Copilot... We're going to do the better one. Because Gemini's interface turns out to be better through Roo Code."

2.  **Find the Settings/Configuration:**
    *   The Roo Code interface might have changed since the workshop. Look for a settings icon (often a cogwheel ⚙️) or a configuration profile section within the Roo Code panel.
    *   The workshop mentioned: "In settings up here, what we want to do is add in the API key that we got before." And later, "Have you got settings at the top right? Yeah, I've tried that, and it doesn't do anything. Oh, that's annoying." This highlights that UI elements can shift. Persist in looking for a configuration or profile management area.

## 2d.2 Configuring a Profile for Google Gemini

Roo Code uses profiles to manage different AI model configurations. You might have a "default" profile, or you might need to create/edit one.

1.  **Profile Name (Optional but Recommended):**
    *   You can often name or rename profiles. The workshop suggested: "You can change this to, something more meaningful, so this is Gemini Pro 2.5 coder... Rate limited. So I'm going to remind myself that this is the rate limited one." This is helpful if you set up multiple profiles later (e.g., one with rate limiting, one without).
    *   To edit/create a profile, look for an "edit" button or a way to add a new configuration.

2.  **API Provider:**
    *   Select **"Google Gemini"** from the list of available API providers.

3.  **API Key:**
    *   This is where you'll paste the Google Cloud API key you created in [Chapter 2c](./02_c_gcp_api_key.md).
    *   "Go back to your browser... Click show key, copy the long text string that you see there, and then go back over to Roo Code and paste it into the API key box."

4.  **Model Selection:**
    *   Roo Code will offer a list of available models for the selected provider. For Google Gemini, you want the most capable one available under the free tier or your credits.
    *   The workshop recommended: **"Gemini 2.5 Pro Preview 0.5.0.6"** (the exact version number might vary over time). "This is by far the most powerful of the models. It's wildly expensive, but it's free if it's every 30 seconds."

5.  **Rate Limit (Crucial for Free Usage):**
    *   This setting is key to potentially avoiding charges and staying within free usage parameters.
    *   Set the rate limit to **`30000` milliseconds (which is 30 seconds)**.
    *   The workshop stated: "Down here in rate limit, you want that on 30 seconds. In theory, subject to them changing the backend terms and conditions, that should keep you on the side of free."
    *   And also: "The rate limiter being on is good because A, it's quite generous because 30 seconds is how long it takes to read the last thing it did and committed in anyway."

6.  **Save Configuration:**
    *   Once all settings are entered, look for a "Save," "Apply," or "Done" button to save the profile configuration. "Once you've got all that in, you can click save and done."

## 2d.3 Understanding Roo Code Modes (Ask vs. Code)

At the bottom of the Roo Code panel, you'll likely see different operational modes. The workshop highlighted two primary ones:

*   **Ask Mode:** "Ask won't write stuff. It'll just answer questions." Use this when you want explanations or information without modifying your files.
*   **Code Mode:** "Code will write stuff to your actual hard drive." This mode is for generating or modifying code and other project files.
*   **Architect Mode:** "Architect can write markdown documents... but it won't write code code." Useful for planning and documentation.

The advice was: "The only two you really need to think about for now are ask and code... For most of the purposes, for you guys, it's just going to be code. Because it doesn't matter if it's smashing stuff out. Because what we're going to use is Git to do all that version control."

## 2d.4 Auto-Approve Settings

For Roo Code to write files or make changes, you might need to adjust its "Auto-Approve" settings.
The workshop mentioned: "I'm going to go into this auto approve bit down here. This is super important. Read and write we want. So write, read, do want."
Look for these settings, likely near the bottom of the Roo Code panel, and ensure it has permission to at least read files for context and write files if you're in Code mode and want it to generate project structures or code.

## Testing Your Setup

Once configured, you can test it by typing a simple prompt into the Roo Code chat input, like "Explain what Git is in simple terms." If it responds, your API key and configuration are likely working. If you get errors, double-check:
*   The API key is correctly pasted.
*   The Gemini API was successfully enabled in your Google Cloud project.
*   You've selected a valid model in Roo Code.

The workshop noted the iterative nature of this: "They constantly update, they're constantly changing. It's almost not worth having a workflow written down because these boxes change all the time. All you need to know is there are multiple profiles... It's got to be Google Gemini... The API key goes in this box. And the model wants to be ProPreview 0506."

With Roo Code configured, your VS Code environment is now supercharged with AI capabilities!

---

Next: [Chapter 3: The Core Git Workflow](./03_core_workflow.md)