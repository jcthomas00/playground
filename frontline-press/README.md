# FrontLine Press

A one-page web app for the monthly newsletter run: drop in the 3 base PDFs
(FE, FS, SFE) and it generates all 9 branded editions, correctly named,
downloadable individually or as one zip.

Everything runs in the browser — no server, no accounts, and the PDFs never
leave your computer. Vercel just hosts the static page.

## Deploy to Vercel (one time, ~2 minutes)

Option A — Vercel CLI (simplest):
1. Open Terminal and `cd` into this folder
2. Run: `npx vercel`
3. Log in when prompted (creates a free account if you don't have one),
   accept the defaults, and it prints your live URL
4. Run `npx vercel --prod` once to make that URL permanent

Option B — GitHub:
1. Push this folder to a GitHub repo
2. On vercel.com, click "Add New Project", import the repo, deploy
   (no build settings needed — it's a static site)

## Monthly use

1. Convert the 3 Publisher files to PDF as usual
2. Open your app URL, drop the 3 PDFs in
3. Check the auto-detected date fields (e.g. "July 2026" / "Julio de 2026")
4. Click "Generate 9 PDFs", then "Download all 9 as .zip"

## Changing a header

Replace the image in the `headers/` folder (keep the same filename) and
redeploy with `npx vercel --prod`. Transparent PNGs are fine — they're
composited onto white automatically. To add or rename an output, edit the
`VARIANTS` list near the top of the script in `index.html`.

## If the layout ever shifts

The area each header occupies is defined in `MASTHEAD` in `index.html`,
in PDF points measured from the top-left of page 1: [x0, top, x1, bottom].
Adjust those numbers if the newsletter template changes.
