# Plainspoken

An AI text humanizer that runs in your browser. Paste text written by ChatGPT, Claude or any other model. Plainspoken highlights the phrases that give it away, then rewrites it so it reads like a person wrote it.

**Use it here: https://caspxau.github.io/plainspoken/**

## What it does

- **Spots AI tells as you type.** It highlights about 40 common giveaways ("delve", "tapestry", "it's worth noting", "in today's fast-paced world", "Moreover,", "not just X, but Y", em dashes) and lists how often each one shows up.
- **Scores the text from 0 to 100.** The score combines how many tells there are, how much sentence length varies (people vary it a lot) and whether the text uses contractions.
- **Rewrites it with Claude.** Pick a tone (Casual, Neutral, Professional, Academic) and how much to change (Light touch, Rewrite, From scratch). The rewrite keeps every fact and is told to remove each tell that was found. The result gets its own score so you can compare.
- **Quick clean.** An instant word swap (utilize → use, em dashes → commas, adds contractions) that works offline with no key.

## API key

Rewrites call the Anthropic API with **your own API key**, billed to your Anthropic account. Create a key at [console.anthropic.com](https://console.anthropic.com/settings/keys) and paste it into the page.

- The key is saved only in your browser's local storage. The page has no server and sends the key only to `api.anthropic.com`.
- You can pick Claude Opus 5.5 (best), Sonnet 5.5 (cheaper) or Haiku 5.5 (cheapest). A rewrite of a few paragraphs costs a few cents or less.
- Don't use a shared or work key on a computer other people use.

Opened as a [claude.ai artifact](https://claude.ai), the page uses the viewer's Claude account instead and needs no key.

## Run it yourself

It's a single file with no build step. Download `index.html` and open it, or host it anywhere static.

## A note on detectors

The score is a rough guide, not an AI detector. No rewrite can promise to pass GPTZero, Turnitin or similar tools, and you're responsible for following the rules of your school or workplace.

## License

MIT
