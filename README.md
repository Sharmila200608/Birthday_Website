# BirthDay Website ❤

A one-page birthday website. Everything — text, styling, animations, and
all the photos — lives inside a single `index.html` file. No build step,
no database, no environment variables. Nothing to configure.

## 1. Run it locally in VS Code

You don't even need to install anything, but for a proper local server:

1. Open this folder in VS Code.
2. Install the **Live Server** extension (by Ritwick Dey) from the
   Extensions tab, if you don't already have it.
3. Right-click `index.html` → **Open with Live Server**.
4. It opens in your browser at `http://127.0.0.1:5500` (or similar).

If you'd rather not install anything: just double-click `index.html`
and it'll open directly in your browser. Everything still works.

## 2. Editing content

Open `index.html` in VS Code and use **Find** (`Ctrl+F` / `Cmd+F`) to
jump to the text you want to change — all the wording is plain, readable
text inside the HTML, section by section (opening, birthday, story,
gallery, quiz, letters, future, final).

To swap or add a photo: photos are embedded as base64 data, so replacing
one means re-encoding a new image. If you want to change photos later,
just tell me which ones and I'll generate an updated file for you —
much easier than editing base64 by hand.

## 3. Deploy to Vercel

**Easiest way (no terminal):**

1. Go to [vercel.com](https://vercel.com) and sign up / log in (free).
2. Click **Add New → Project**.
3. Choose **"Deploy without Git"** / drag-and-drop, and drag this whole
   folder (or just `index.html`) into the upload area.
4. Click **Deploy**. Vercel gives you a live link in under a minute.

**Using the Vercel CLI instead:**

```bash
npm install -g vercel
cd pattu-birthday-website
vercel
```

Follow the prompts (log in, confirm project settings, accept defaults).
It deploys and gives you a URL immediately. Run `vercel --prod` to push
it to your permanent production URL.

**Using GitHub:**

1. Push this folder to a new GitHub repo.
2. On [vercel.com](https://vercel.com), click **Add New → Project**,
   import that repo, and click **Deploy**. No settings needed — it's
   a static site, Vercel figures it out automatically.

Once deployed, send him the `https://your-project-name.vercel.app` link
directly — no Claude sign-in wall, no login of any kind. It just opens.

## 4. Adding background music (optional)

The music button is already wired up, it just has no track loaded yet.
Open `index.html`, find this line near the top of `<body>`:

```html
<audio id="bgm" loop preload="none"></audio>
```

Add a `src`, either to a file you host alongside `index.html`:

```html
<audio id="bgm" loop preload="none" src="song.mp3"></audio>
```

or to a direct link to a hosted audio file. Drop the mp3 file in this
same folder if you go the local-file route, then redeploy.

## 5. Timing it for midnight

Since it's a plain static file, there's no server to "wake up" or cold
start — the link works instantly the moment it's deployed. Deploy it
any time before midnight, then just send the link at 12:00 AM.
