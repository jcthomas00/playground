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

## Monthly Features images (for Constant Contact)

1. Save the images from the Resources for Living Monthly Features page
   (right-click → Save Image As)
2. Drop them into the "Monthly Features images" box in the app
3. Click "Download all as .zip" (or download each one)

Each image is re-saved as a standard RGB JPEG on a white background and keeps
its original name with a `.jpg` extension (e.g. `MonthlyFeatures_Box1.webp` →
`MonthlyFeatures_Box1.jpg`). That fixes files that are really WebP/PNG, or
progressive/CMYK JPEGs, which Constant Contact won't display. Dropping a file
with the same name again replaces the earlier one.

## Changing a header

Replace the image in the `headers/` folder (keep the same filename) and
redeploy with `npx vercel --prod`. Transparent PNGs are fine — they're
composited onto white automatically. To add or rename an output, edit the
`VARIANTS` list near the top of the script in `index.html`.

## If the layout ever shifts

The area each header occupies is defined in `MASTHEAD` in `index.html`,
in PDF points measured from the top-left of page 1: [x0, top, x1, bottom].
Adjust those numbers if the newsletter template changes.
