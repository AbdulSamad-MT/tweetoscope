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

1. Open `x_personality_analyzer.ipynb` in Jupyter or VS Code
2. Run the cells top to bottom
3. Paste your Gemini API key in the config cell
4. First time? Run the login cell to save your X cookies
5. Enter a username and wait for the report

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

- You need to log in once so it can scrape posts with your cookies
- If Gemini is rate limited, it automatically tries other models
- The AI analysis is just for fun — it's not a real psychological assessment
- Be nice, don't spam scrape people
