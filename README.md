# BC STEM Tutor

An AI-powered tutoring app for BC secondary school STEM courses, built on the Anthropic API and deployed via Netlify.

## Subjects Covered

- Pre-Calculus 11
- Pre-Calculus 12
- Chemistry 11
- Physics 11
- Calculus 12

All content aligned to the BC Ministry of Education curriculum.

## Project Structure

```
bc-stem-tutor/
├── index.html              ← Single-page app (UI, logic, styles)
├── curriculum.js           ← All subject config: topics, system prompts
├── netlify/
│   └── functions/
│       └── chat.js         ← Netlify serverless function (Anthropic API proxy)
└── netlify.toml            ← Netlify build config
```

## Adding or Editing a Subject

Everything lives in `curriculum.js`. Each subject is an object with:

- `id` — unique string identifier
- `label` — display name
- `grade` — e.g. "Grade 11"
- `icon` — symbol shown on the subject card
- `topics[]` — array of topic chip labels
- `systemPrompt(name)` — function returning the system prompt string

To add a subject, copy an existing block and edit it. No other files need changing.

## Local Development

You'll need the [Netlify CLI](https://docs.netlify.com/cli/get-started/).

```bash
npm install -g netlify-cli
netlify dev
```

Set your `ANTHROPIC_API_KEY` in a `.env` file or in the Netlify dashboard under Site Settings → Environment Variables.

## Deployment

1. Push to GitHub
2. Connect the repo in [Netlify](https://app.netlify.com)
3. Set `ANTHROPIC_API_KEY` in Site Settings → Environment Variables
4. Deploy

Netlify will auto-deploy on every push to `main`.

## Environment Variables

| Variable | Description |
|---|---|
| `ANTHROPIC_API_KEY` | Your Anthropic API key |
