# Tokenizer Visualizer

See approximate token boundaries in any text, color-coded, with a live token and character count. No server, no tracking, no third-party scripts.

**Live demo:** https://0xelitesystem.github.io/tokenizer-visualizer/

## Use

Open `index.html` in any modern browser, or visit the GitHub Pages link in the repo description.

Paste or type text. The tool splits it locally and shows:

- Every token, color-coded so you can see where one ends and the next begins
- An approximate token count
- A character count (Unicode code points)
- A chars-per-token ratio

Whitespace tokens are marked with a dotted outline so you can see them too.

### Honest caveat

This is an **approximation**, not any specific model's exact tokenizer. It uses a GPT-style regular expression that splits on word boundaries, contractions, numbers, punctuation, and runs of whitespace. Real production tokenizers (byte-pair encoding, SentencePiece, tiktoken, and so on) merge and split sub-words with a learned vocabulary, so their counts will differ. Use this for intuition and rough sizing, not for billing or hard limits.

## Why this exists

Most token counters either call a remote API or bundle a large model-specific vocabulary. This is a single file that gives you a quick, private feel for how text breaks into tokens, with no network calls and no dependencies. When you need exact counts for a specific model, use that model's official tokenizer.

## Privacy

Everything runs in your browser. The text you paste never leaves your machine. Verify by viewing the page source or by opening DevTools and watching the network tab, no requests are made.

## Run locally

```bash
git clone https://github.com/0xelitesystem/tokenizer-visualizer
cd tokenizer-visualizer
# Open index.html in your browser, or:
python -m http.server 8000
```

## Build

There is no build. It is a single HTML file.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [prompt-token-meter](https://github.com/0xelitesystem/prompt-token-meter), estimate prompt size as you type
- [regex-tester](https://github.com/0xelitesystem/regex-tester), test regular expressions in your browser
- [gradient-generator](https://github.com/0xelitesystem/gradient-generator), build CSS gradients visually
