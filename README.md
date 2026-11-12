# Plainspoken

An AI text humanizer that runs in your browser, and can do the rewriting on your own phone or computer with no account or key. Paste text written by ChatGPT, Claude or any other model. Plainspoken highlights the phrases that give it away, then rewrites it so it reads like a person wrote it.

**Use it here: https://caspxau.github.io/plainspoken/**

## What it does

- **Spots AI tells as you type.** It highlights about 40 common giveaways ("delve", "tapestry", "it's worth noting", "in today's fast-paced world", "Moreover,", "not just X, but Y", em dashes) and lists how often each one shows up.
- **Scores the text from 0 to 100.** The score combines how many tells there are, how much sentence length varies (people vary it a lot) and whether the text uses contractions.
- **Rewrites it on your device, or with Claude.** Pick a tone (Casual, Neutral, Professional, Academic) and how much to change (Light touch, Rewrite, From scratch). The rewrite keeps every fact and is told to remove each tell that was found. The result gets its own score so you can compare.
- **Fixes what still reads as AI.** After a rewrite the AI tells panel switches to the Humanized text and lists what's still flagged, including style issues such as every sentence being the same length. **Fix these tells** runs a second pass that changes only those spots and leaves the rest word for word; **Quick fix** does an instant offline swap; **Undo** goes back.
- **Shows progress.** A bar under Humanized shows loading, reading and writing, with a time-left estimate based on how fast your device actually runs.
- **Quick clean.** An instant word swap (utilize → use, em dashes → commas, adds contractions) that works offline with no key.

## On this device (free, private, offline)

Choose **Rewrite with → On this device** and the rewrite runs in your browser on your own hardware. Nothing you paste is sent anywhere.

- **With a GPU** (WebGPU: Chrome or Edge on Windows, macOS, ChromeOS and Android; Safari 26 on iPhone, iPad and Mac) it uses [WebLLM](https://github.com/mlc-ai/web-llm) with Qwen3.5 in three sizes: Small (0.4 GB, phones), Medium (1.1 GB, most laptops), Large (2.4 GB, PCs with a good GPU).
- **Without one** (for example Chrome on Linux) it falls back to llama.cpp compiled to WebAssembly ([wllama](https://github.com/ngxson/wllama)) on the CPU, using every core. Small is 0.5 GB, Medium 1.2 GB. It's slower: on a 2017 dual-core laptop a short paragraph takes about a minute.
- The model downloads once from Hugging Face and stays in the browser's storage. After that it works offline. **Remove** deletes it again.
- You can install the page as an app (Add to Home Screen on a phone, the install icon in the address bar on a computer). A service worker keeps the page available offline.
- Small local models make lighter edits than Claude, so the result also gets a Quick clean pass.

## Claude (API key)

Rewrites call the Anthropic API with **your own API key**, billed to your Anthropic account. Create a key at [console.anthropic.com](https://console.anthropic.com/settings/keys) and paste it into the page.

- The key is saved only in your browser's local storage. The page has no server and sends the key only to `api.anthropic.com`.
- You can pick Claude Opus 5.5 (best), Sonnet 5.5 (cheaper) or Haiku 5.5 (cheapest). A rewrite of a few paragraphs costs a few cents or less.
- Don't use a shared or work key on a computer other people use.

Opened as a [claude.ai artifact](https://claude.ai), the page uses the viewer's Claude account instead and needs no key.

## Run it yourself

No build step. Host the folder anywhere static over HTTPS (or `python3 -m http.server` for localhost). Opening `index.html` straight from disk works for Claude and Quick clean, but on-device models need the page served so the service worker can run.

## A note on detectors

The score is a rough guide, not an AI detector. No rewrite can promise to pass GPTZero, Turnitin or similar tools, and you're responsible for following the rules of your school or workplace.

## License

MIT
