# CampusIQ — College FAQ Chatbot (Team T5)

A small working browser-based version of the College FAQ Chatbot presentation.

## Run locally
1. Keep `index.html` and `kb.json` in the same folder.
2. Open a terminal in this folder and run:
   - Windows: `py -m http.server 8000`
   - macOS/Linux: `python3 -m http.server 8000`
3. Open `http://localhost:8000` in your browser.

Opening `index.html` directly may work in some browsers, but using a local server is recommended so `kb.json` loads reliably.

## How the demo works
- The UI runs in the browser.
- It tokenizes the question and compares it to stored question patterns using TF-IDF-style weights and cosine similarity.
- If the best score is at least 0.30, the stored answer is shown; otherwise the bot gives a safe fallback.
- No external AI API is used. This follows the presentation's principle that answers come from a college-specific knowledge base rather than a ChatGPT wrapper.

## IMPORTANT before real users use it
The knowledge base contains **sample/demo answers**, not verified information for a specific college. Replace `college_name`, `notice`, each `answer`, and the `patterns` in `kb.json` with accurate official details. Don't publish sample phone numbers, fees, dates, or policies as facts.

## Deploy online
You can deploy this static folder to a static hosting provider (for example, GitHub Pages or Netlify). Upload both `index.html` and `kb.json` together. Once hosted, share the public URL with students.

## Current limitations
- Browser-side, keyword-pattern matching; it is not a large language model and does not understand every paraphrase.
- No admin login or online database; edits to `kb.json` require updating/redeploying the file.
- No persistent chat history; refresh clears the chat.
- The knowledge base must be reviewed and maintained by the college.
