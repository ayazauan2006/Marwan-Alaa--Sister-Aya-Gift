# Alaa & Marwan — Wedding Invitation Site

A single-page bilingual (English / Arabic) wedding invitation, in the same
spirit as the TikTok example you sent: cover envelope → "Open" → ceremony
intro → couple names → photo gallery → reception info with a live
countdown + calendar → RSVP → venue map → dress code → schedule →
guestbook.

## Files
- `index.html` — the entire site (HTML + CSS + JS in one file)
- `images/` — put your real photos here (see below)
- `music/` — put your own licensed song file here (see below)

## 1. Add your photos
Open `index.html`, find the two `<figure>` blocks under `Photo Gallery`
(search for `gallery.ph1` / `gallery.ph2`), and replace the placeholder
`<div class="photo-placeholder">…</div>` with:
```html
<img src="images/marwan-kid.jpg" alt="Marwan">
```
and similarly for Alaa. Drop the actual image files into the `images/`
folder with matching names.

## 2. Add your music
I can't include "We Malo" or "Getlak" myself — both are commercially
released Amr Diab songs, and I'm not able to source or embed copyrighted
audio. To use either track (or anything else), export/rip the file
yourself from a source you're licensed to use it from, name it
`song.mp3`, and drop it into the `music/` folder. The floating music
button and the auto-play-on-open behavior are already wired up to that
file — nothing else to change.

## 3. Edit the date/venue/schedule
All the wedding details live near the top of the `<body>` and inside the
`i18n` object in the `<script>` tag at the bottom — search for:
- `WEDDING_DATE` — controls the live countdown
- `Romanica Venue, Moqattam` — venue name + Google Maps embed query
- the `sched.*` rows — the evening timeline

The Arabic and English text are both in the `i18n` object, so update
both languages when you change a date or detail.

## 4. About the guestbook
The "Send Wishes" form currently saves messages in the *visitor's own
browser* (localStorage) — it works instantly with no setup, but each
guest only sees wishes typed on their own phone, not a shared list. If
you want every guest's message to land somewhere you and Marwan can
actually read them, the easiest options are:
- **Formspree** (formspree.io) — free tier, just point the form at your
  Formspree endpoint instead of the localStorage code.
- **Google Sheets** via a simple Apps Script web app.
The exact spot to change is marked with a comment in `index.html`
(search for "NOTE: This stores wishes").

## 5. Deploy it
Easiest free options, no coding needed beyond what's here:
- **Netlify Drop**: go to app.netlify.com/drop and drag the whole
  folder in — you get a live link instantly.
- **GitHub Pages**: create a repo, upload these files, enable Pages in
  repo Settings → Pages.
- **Vercel**: `vercel` CLI or drag-and-drop import, same idea.

Whichever you use, share the resulting link the same way as the
`chungdoi.com` one in your video (WhatsApp, etc).
