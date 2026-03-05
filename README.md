# X Personality Analyzer

Give it any X (Twitter) username and it tells you what kind of person they are — powered by Gemini AI.

It scrapes their recent posts, sends them to Google Gemini, and gets back a full personality breakdown: MBTI type, Big Five traits, communication style, interests, emotions, and more.

## What you need

- Python 3.9+
- A free Gemini API key → [get one here](https://aistudio.google.com/apikey)
- An X account (for the cookie login)

## Setup

```bash
pip install -r requirements.txt
playwright install chromium
```

## How to use

1. Open `x_personality_analyzer.ipynb` in Jupyter, VS Code, or [Google Colab](https://colab.research.google.com/)
2. Run the install & import cells
3. Paste your Gemini API key in the config cell
4. Add your X cookies (see below)
5. Enter a username and wait for the report

## Adding cookies

The scraper needs your X login cookies to access profiles. Choose one method:

### Option A — Local (browser login)
Uncomment `await login_to_x()` in the login cell. A Chromium browser opens — log in to X and cookies are saved automatically.

### Option B — Colab / headless (paste cookies)
1. Install the **[Cookie-Editor](https://cookie-editor.com/)** extension in Chrome or Firefox
2. Go to [x.com](https://x.com) and make sure you're logged in
3. Click the Cookie-Editor icon → **Export** → **Export as JSON**
4. In the notebook, find the **"Paste your cookies here"** cell
5. Replace `COOKIES_JSON = []` with your exported cookies:
   ```python
   COOKIES_JSON = [{"name": "auth_token", "value": "abc...", "domain": ".x.com", ...}, ...]
   ```
6. Run the cell — it will say "Saved X cookies!"

> **Note:** The key cookies are `auth_token` and `ct0`. Cookie-Editor exports everything at once so you don't need to pick them manually. Cookies expire after a while — if scraping stops working, re-export fresh ones.

## What the report covers

- Personality summary
- MBTI type estimate
- Big Five traits (openness, conscientiousness, etc.)
- Communication style
- Interests and topics
- Emotional profile
- Social behavior
- Values, strengths, growth areas
- Fun facts

## Files

```
x_personality_analyzer.ipynb  ← the whole app
requirements.txt              ← dependencies
.x_cookies.json               ← your saved login (gitignored)
```

## Good to know

- You need to log in once (or paste cookies) so it can scrape posts
- Works on Google Colab — just paste cookies instead of using the browser login
- If Gemini is rate limited, it automatically tries other models
- The AI analysis is just for fun — it's not a real psychological assessment
- Be nice, don't spam scrape people
