# The Kolpixel Archive — Studio Kolpixel

A personal multi-page creative archive built with HTML, CSS and JavaScript.

## What's new in v3

- Crimson, scarlet, antique-gold and ivory homepage using the Studio Kolpixel seal.
- Separate colour identities: UNSEEN (teal), Ez Goredes (olive/gold), Chess (blue), Kriegsspiel (field green), journal (sepia), Waterloo (blue-grey/brass).
- Clear notice that stories are not ready for publication.
- Future project cards for Napoleonic archival portraits inspired by the atmosphere of The Walten Files, an analog psychological-horror concept, and other studio experiments.
- Seven-turn Waterloo battle study, including historical moves, command decisions, responses, consequences, schematic map and hypothetical decision exercises.
- Local algorithmic Archive Assistant that fetches and searches the text of the listed site pages. It is not a generative AI service and does not send questions to an AI provider.
- Existing two-player legal chessboard and Kriegsspiel terrain/unit sandbox retained.

## Project structure

```text
kolpixel_archive_v3/
├── index.html
├── styles.css
├── script.js
├── README.md
├── assets/kolpixel-logo.png
├── projects/unseen.html
├── projects/ez-goredes.html
├── journal/the-marshals-evening.html  # labelled development draft
└── tools/
    ├── waterloo.html
    ├── chess.html
    └── kriegsspiel.html
```

## Run locally

From this folder run:

```bash
python -m http.server 8000
```

Open `http://localhost:8000`. A local server is required for the Archive Assistant to fetch and index the other pages, and for the module-based chess rules library.

## Archive Assistant: what it does and does not do

The assistant is a client-side retrieval prototype. It fetches the known HTML pages, extracts visible text, ranks matching paragraphs against the visitor's question and links to relevant pages. It does not use a large language model, does not generate original reasoning, does not connect to an AI provider and does not send questions to a server.

For a real AI assistant, add a small serverless/backend endpoint and call the model from that endpoint. Never put an API key in browser JavaScript or public GitHub Pages files. The backend should retrieve relevant page text, send only the necessary excerpts to the model, and return a cited answer. Add new page paths to the `pages` array in `script.js` so the local assistant can index them.

## Waterloo study

The page condenses the battle into seven study turns using the Brown University Library timeline and National Army Museum account. The map is schematic, not to scale. Times are approximate. Decision exercises are hypothetical and clearly separated from recorded events.

## Chess and Kriegsspiel

- Chess uses chess.js 1.4.0 loaded from jsDelivr. It needs internet access and supports legal two-player local moves, promotion choice, undo, reset, board flip and PGN export. No computer opponent is included.
- Kriegsspiel is a scenario setup sandbox. It supports terrain painting, unit placement, unit movement, deletion, local-browser saving and JSON export. It is not a complete adjudication engine.

## Free publishing with GitHub Pages

1. Create a public GitHub repository, for example `kolpixel-archive`.
2. Upload the contents of this folder to the repository root.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, choose `main` and `/ (root)`, then save.
5. Use the public GitHub Pages URL after deployment.

GitHub Pages is static hosting. The local assistant works by fetching static pages in the visitor's browser. A real generative AI assistant requires a secure backend or serverless function; never expose an AI API key in this public repository.

## Before launch

- Review the historical Waterloo study if adding more detail.
- Keep story pages labelled as drafts until each story is ready.
- Add an author/contact link and community invitation when ready.
- Add new project pages to the assistant's source list.
- Check mobile layouts and keyboard navigation.
