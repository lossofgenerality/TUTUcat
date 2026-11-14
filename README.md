# Tutu Cat · トゥトゥ猫 — installable web app

A squishy ginger maths cat who talks, listens and wobbles on a discrete Laplacian.
Computational Classnotes · CC BY-NC-SA 4.0

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole app (Tutu, chat, mic, voices) |
| `manifest.webmanifest` | App name, colours and icons, so it can be installed |
| `sw.js` | Service worker: lets Tutu open offline |
| `icons/` | App icons (192, 512, maskable 512, Apple touch, favicon) |

Keep the folder structure as it is.

## 1. Put it online (HTTPS is required)

Installing only works from an `https://` address (or `localhost` for testing).
Upload the **whole folder** to any static host, for example:

- **GitHub Pages:** new repository → upload the files → Settings → Pages → deploy from the main branch.
- **Netlify:** drag the folder onto app.netlify.com/drop.
- **Your own server:** copy the folder into a web directory served over HTTPS.

To try it on your own computer first: in this folder run `python3 -m http.server 8000`,
then open http://localhost:8000.

## 2. Install it

- **Chrome / Edge (desktop, Android):** press **Install app** next to "Blobby cat edition",
  or use the install icon in the address bar.
- **iPhone / iPad (Safari):** Share → **Add to Home Screen**.

## 3. Let Claude answer (TUTUKernel)

Tutu answers through the CCN Cloud chat proxy at
`https://www.wolframcloud.com/obj/ccn2/TUTUKernel` (set in the config block at the top of `index.html`).
Deploy TUTUKernel from a signed-in Wolfram notebook, then type your CCN Cloud key into the app
and press **Connect Claude**. Without it, Tutu answers from his built-in phrasebook.

## Notes

- **Offline:** Tutu, his phrasebook and the browser voices work offline. Claude replies and
  Chrome's speech recognition need a connection.
- **Mic:** works in Chrome, Edge and Safari, not Firefox.
- **Updating:** after changing any file, raise `VERSION` in `sw.js` (for example `tutu-v2`)
  so installed copies pick up the change.
