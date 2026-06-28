# DiaMatch AI

**The Diamond Appraisal & Layout Assistant** — a luxury B2B web tool for jewelers and diamond traders.

Upload GIA/IGI/HRD grading certificates, Rapaport price matrices, photos, videos, and links, then chat with an AI gemologist powered by Google Gemini 2.5 Flash.

## Features

### Core
- **The Vault** — upload PDFs, CSVs, images, video, audio, text, and paste links
- **Asset Viewer** — preview all source types with zoom, edit, copy, and download tools
- **Resizable layout** — drag handles to resize vault / viewer / chat; layout persists in localStorage
- **The Chat Trader** — ask about layout matching, trade appraisals, and gemology
- **Source citations** — AI cites exact filenames (e.g. `[GIA-123456.pdf]`)
- **Bring your own API key** — paste your Gemini key in the header (stored in `sessionStorage` only)

### Power Tools
- **Trade** — match pairs, appraisal, compare table, blind spot audit
- **Marketing** — social media generator, diamond passport
- **Sales** — negotiation simulator, fluorescence Q&A

### Studio (new)
Generate structured outputs from vault data with preview and export:

| Tool | Output | Export |
|------|--------|--------|
| Slide deck | JSON slides + carousel preview | `.pptx` |
| Trade report | Markdown dossier | `.pdf` |
| Data table | Sortable table | `.csv`, `.xlsx` |
| Infographic | Luxury layout preview | `.png` |
| Video kit | Script, scenes, SRT captions | `.srt`, `.json`, optional `.mp4` |
| Insurance letter | Formal appraisal letter | `.pdf` |
| RFQ email | Supplier inquiry draft | `.pdf` |
| WhatsApp blurb | Broker listing copy | Copy |
| Price memo | Trade memo with Rapaport refs | `.pdf` |
| Parcel labels | Printable label specs | `.png` |
| QC checklist | Pre-shipment checklist table | `.csv`, `.xlsx` |
| Vault CSV | One-click vault export | `.csv` |

Studio outputs can be **opened in the Asset Viewer**, **saved to The Vault** (GEN badge), or **downloaded** from chat action buttons.

**Video MP4** generation is best-effort via Google's Veo API when available on your key. If unavailable, the full production kit (script, scenes, SRT, thumbnail prompts) is always delivered.

## Use cases

1. **Layout matching** — *"Find matching pairs for earrings from all uploaded certs."*
2. **Instant appraisal** — *"Based on the Rapaport matrix, what is the maximum trade value?"*
3. **Client presentation** — Studio → Slide deck → Download PPTX
4. **Trade documentation** — Studio → Trade report or Insurance letter → Download PDF

## Getting started

1. Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey)
2. Open `index.html` in your browser (or visit the live demo below)
3. Paste your API key in the header — the status dot turns green when detected
4. Upload documents to The Vault and start chatting or use Studio tools

## Tech stack

- Single-file `index.html` (HTML + Tailwind CSS CDN + vanilla JavaScript)
- [PDF.js 3.4.120](https://mozilla.github.io/pdf.js/) for client-side PDF text extraction
- [marked.js](https://marked.js.org/) for chat Markdown rendering
- [PptxGenJS](https://gitbrent.github.io/PptxGenJS/), [html2pdf.js](https://github.com/eKoopmans/html2pdf.js), [SheetJS](https://sheetjs.com/), [html2canvas](https://html2canvas.hertzen.com/) — loaded on demand for Studio exports
- [Gemini 2.5 Flash](https://ai.google.dev/) via REST API

## Limitations

- Text-based PDFs work best; scanned/image-only certificates may not extract text
- Max 15 files, 20 MB each (50 MB for video)
- API key is stored in `sessionStorage` only (cleared when the tab closes)
- Veo MP4 generation depends on API access and a selected image source
- Link previews in iframes may be blocked by some websites

## Local testing

1. Open `index.html` directly in Chrome/Edge, or run a local server:
   ```bash
   python -m http.server 3456
   ```
2. Visit `http://localhost:3456`
3. Use sample files in `sample-data/` (GIA cert PDFs + Rapaport CSV) for testing

## Live demo

**https://diamatch-ai.vercel.app**

GitHub: **https://github.com/MS-at-HRevival/diamatch-ai**

## License

MIT
