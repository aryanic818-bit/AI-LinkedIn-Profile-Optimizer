# AI-LinkedIn-Profile-Optimizer# 💼 LinkedIn Profile Optimizer

Paste your LinkedIn headline and About section and get:

- **3 headline options** in different styles (each within LinkedIn's 220-character limit)
- a **rewritten About section** with a strong opening, short paragraphs and a call to action
- **keyword suggestions** that recruiters search for, with where to use each one
- **extra tips** for the rest of your profile
- a side-by-side look at your original text, and a downloadable Markdown file

Built with [Streamlit](https://streamlit.io) and Google's Gemini Flash model (`gemini-3.5-flash`).
If the model is busy, the app retries automatically and switches to a backup Flash model.

> The AI never invents facts. Where a number or result would help, it leaves a [bracketed placeholder] for you to fill in with something true.

## Files

| File | Purpose |
|------|---------|
| `app.py` | The Streamlit app |
| `requirements.txt` | Python dependencies |
| `README.md` | This guide |

## Run locally

1. Install Python 3.9+ and get a free API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
2. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set your key (or paste it into the app's sidebar):
   - Mac/Linux: `export GEMINI_API_KEY="your-key"`
   - Windows (PowerShell): `$env:GEMINI_API_KEY="your-key"`
4. Start the app:
   ```bash
   streamlit run app.py
   ```

## Put it on GitHub

1. Create a free account at [github.com](https://github.com) and click **New repository** (for example `linkedin-optimizer`, set to **Public**; do not add any files).
2. Create a `.gitignore` file in your project folder with these lines, so your key is never uploaded:
   ```
   .streamlit/secrets.toml
   __pycache__/
   ```
3. In your project folder, run:
   ```bash
   git init
   git add app.py requirements.txt README.md .gitignore
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/linkedin-optimizer.git
   git push -u origin main
   ```
   (No Git? On GitHub choose **Add file → Upload files** and drag the files in.)

## Deploy on Streamlit Community Cloud

1. Go to [share.streamlit.io](https://share.streamlit.io) and sign in with GitHub.
2. Click **Create app**, choose your repository, branch `main`, and main file `app.py`.
3. Open **Advanced settings → Secrets** and paste:
   ```toml
   GEMINI_API_KEY = "your-key"
   ```
4. Click **Deploy**. In a minute or two you get a public link to share.

## Notes and limits

- The About section needs at least 30 words. LinkedIn allows up to 2,600 characters in About, and the app warns you if a result is over the limit.
- The optional "target role or industry" field makes the keywords much more relevant. Fill it in.
- Your text is sent to Google's Gemini API. Do not paste phone numbers, addresses or other private details.
- Review every suggestion before posting. Keep only what is true about you.
- You can change the model name in the sidebar if Google releases a newer Flash model.
