# OnTarget

OnTarget is a personalized literature tracking and AI analysis system.

This GitHub Pages site is a static project page. It can introduce the project, document installation, and link to the source code, but it cannot run the Flask backend or execute literature-fetching and AI-analysis APIs.

## Custom API Configuration

OnTarget supports user-level API settings in the web app:

- Provider: DeepSeek, OpenAI, Anthropic, supported domestic providers, or Custom API
- API key: encrypted before storage
- API Base URL: accepts either provider roots such as `https://api.openai.com` or versioned roots such as `https://api.openai.com/v1`
- Model: for example `deepseek-chat`, `gpt-4o-mini`, or `qwen-plus`

For server-level defaults, copy `.env.example` to `.env` and configure:

```env
API_PROVIDER=custom
API_KEY=your-api-key
API_BASE_URL=https://api.example.com
MODEL=your-model-name
```

## Run Locally

```bash
git clone https://github.com/liqin26/OnTarget.git
cd OnTarget
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
copy .env.example .env
python app.py
```

Then open `http://localhost:5500` or the configured `WEB_PORT`.

## Source Code

[GitHub repository](https://github.com/liqin26/OnTarget)
