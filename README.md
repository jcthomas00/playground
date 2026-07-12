# Playground

A collection of small standalone apps, each living in its own folder and deployed separately on Vercel.

## Apps

| App | Folder | What it does |
| --- | --- | --- |
| FrontLine Press | [`frontline-press/`](frontline-press/) | Drop in the 3 base newsletter PDFs and it generates all 9 branded editions in the browser, downloadable individually or as one zip. |

## Deploying an app to Vercel

Each app gets its own Vercel project pointing at its subfolder:

1. On vercel.com, click **Add New → Project** and import this repo
2. Under **Root Directory**, pick the app's folder (e.g. `frontline-press`)
3. Deploy — the static apps here need no build settings

Repeat for each new app; every project deploys independently when its folder changes.
