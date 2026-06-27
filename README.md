# DiaMatch AI

**The Diamond Appraisal & Layout Assistant** — a luxury B2B web tool for jewelers and diamond traders.

Upload GIA/IGI/HRD grading certificates, Rapaport price matrices, and supplier stock sheets, then chat with an AI gemologist powered by Google Gemini 2.5 Flash.

## Features

- **The Vault** — upload multiple PDFs and CSVs (certs, Rapaport sheets, parcel lists)
- **Certificate Viewer** — inspect extracted text from selected documents
- **The Chat Trader** — ask about layout matching, trade appraisals, and gemology
- **Source citations** — AI cites exact filenames (e.g. `[GIA-123456.pdf]`)
- **Bring your own API key** — paste your Gemini key in the header (never stored in code)

## Use cases

1. **Layout matching** — *"Find matching pairs for earrings from all uploaded certs with identical color, clarity, and table % within 0.05mm tolerance."*
2. **Instant appraisal** — *"Based on the Rapaport matrix, what is the maximum trade value for this stone given its fluorescence drawback?"*

## Getting started

1. Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey)
2. Open `index.html` in your browser (or visit the live demo below)
3. Paste your API key in the header — the status dot turns green when detected
4. Upload documents to The Vault and start chatting

## Tech stack

- Single-file `index.html` (HTML + Tailwind CSS CDN + vanilla JavaScript)
- [PDF.js 3.4.120](https://mozilla.github.io/pdf.js/) for client-side PDF text extraction
- [Gemini 2.5 Flash](https://ai.google.dev/) via REST API

## Limitations

- Text-based PDFs work best; scanned/image-only certificates may not extract text
- Max 15 files, 20 MB each
- API key is stored in `sessionStorage` only (cleared when the tab closes)

## Local testing

1. Open `index.html` directly in Chrome/Edge, or run a local server:
   ```bash
   python -m http.server 3456
   ```
2. Visit `http://localhost:3456`
3. Use sample files in `sample-data/` (GIA cert PDFs + Rapaport CSV) for testing

## Deploy to GitHub

1. Create a new **public** repository named `diamatch-ai` on GitHub
2. Push this project:
   ```bash
   git remote add origin https://github.com/YOUR_USERNAME/diamatch-ai.git
   git branch -M main
   git push -u origin main
   ```

## Deploy to Vercel

1. Sign in at [vercel.com](https://vercel.com) with GitHub
2. **Add New → Project** → import `diamatch-ai`
3. Framework preset: **Other** | Build command: *(empty)* | Output: `/`
4. Deploy and copy your live URL (e.g. `https://diamatch-ai.vercel.app`)
5. Update the live demo URL in this README

## Submission checklist

- [ ] Live Vercel URL
- [ ] Public GitHub repo URL
- [ ] Screenshot showing uploaded document, Certificate Viewer text, and chat response with `[filename]` citation

## License

MIT
