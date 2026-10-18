# Printloo

Turn a slide deck into an ink-friendly, print-ready PDF — right in your browser.

Built for students who get lecture slides as PPTs/PDFs and want a compact, printable version: multiple slides stacked per page, dark slides auto-inverted to save ink, and leftover pages padded automatically so nothing gets cut off.

**Live demo:** _add your deployed link here once you enable GitHub Pages_

## Features

- **Upload a PDF or slide screenshots** (JPG/PNG), in any order you choose
- **Stack 2, 4, or 6 slides per sheet**, one on top of the other, on A4 or Letter paper
- **Auto-invert dark slides** so they print on white instead of burning through ink — or toggle any slide manually
- **Auto-pad** short leftover pages (repeat the first slide, repeat the last slide, or leave a blank cell)
- **100% client-side** — files are rendered and the PDF is built entirely in your browser; nothing is uploaded to a server

## Usage

1. Open `index.html` (or the deployed link) in any modern browser.
2. Upload your slide PDF, or a batch of screenshots in reading order.
3. Choose slides-per-sheet, paper size, and padding behavior.
4. Click **Build printable PDF**, review the preview, then **Download**.

## Run locally

No build step — it's a single static HTML file.

```bash
git clone https://github.com/<your-username>/printloo.git
cd printloo
# open index.html directly, or serve it:
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploy to GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select the `main` branch and `/ (root)` folder.
4. Save — your app will be live at `https://<your-username>.github.io/printloo/` within a minute or two.

## How it works

- [pdf.js](https://mozilla.github.io/pdf.js/) renders PDF pages to canvas in the browser.
- Each page's average brightness is sampled to decide whether to auto-invert it.
- Pages are composited onto sheet-sized canvases in stacked order.
- [jsPDF](https://github.com/parallax/jsPDF) assembles the sheets into a downloadable PDF.

## License

MIT — see [LICENSE](LICENSE).
