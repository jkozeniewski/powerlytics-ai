# Powerlytics AI Executive Briefing — Interactive Website

A static, responsive Powerlytics-branded presentation with a YouTube video player and timestamped chapter navigation. No paid hosting, database, build step, or JavaScript framework is required.

## 1. Upload the video

1. Sign in to YouTube Studio: https://studio.youtube.com/
2. Click **Create → Upload videos**, and select the original Zoom `.mp4` (approximately 18:54 long).
3. Under **Visibility**, choose **Unlisted** (not Private, since private videos cannot be embedded for general viewers).
4. Complete the upload and processing, then copy the YouTube video link.
5. Check that embedding is allowed for the video. If YouTube limits embedding, viewers can still use the “Open on YouTube” link.

**Privacy:** An unlisted video is not access-controlled. Anyone who gets its link, including someone who sees the page source, can watch or share it. GitHub Pages websites are public. Do not use this setup for confidential or restricted company recordings.

## 2. Video already connected

The unlisted video is configured in `config.js`: https://youtu.be/cnTVfNVBaMg. No further setup is needed unless you change the video.

## 2a. Change the video later

Edit `config.js` and replace the empty string with your video ID, e.g.:

```js
window.POWERLYTICS_VIDEO_ID = 'YOUR_11_CHARACTER_ID';
```

The ID is the text after `v=` in `youtube.com/watch?v=...` or after `youtu.be/`.

For a private preview, you can instead open the site and use **Video setup** to paste the URL. That saves the ID only in your current browser; other viewers will not see the video unless you also set `config.js`.

## 3. Publish free on GitHub Pages

1. Create a new **public** GitHub repository, e.g. `powerlytics-ai-briefing`.
2. Upload **all** website files from this folder to the repository root (`index.html`, `styles.css`, `app.js`, `config.js`, and `assets/powerlytics-logo.png`).
3. In repository **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
4. GitHub will provide a link like `https://YOUR_USERNAME.github.io/powerlytics-ai-briefing/` after deployment.
5. Open that link and test each timestamp. Share that link with your CEO.

GitHub's free Pages availability and interface can change; follow its current Pages documentation if the menus differ.

## How the presentation works

- Four presentation sections: prospecting, interactive sales decks, meeting intelligence/CRM, and signal-based outreach.
- Clickable timestamps seek the *same embedded YouTube player* to the selected moment and start playback.
- Previous/Next buttons, section dots, and left/right keyboard arrows navigate between sections.
- The browser URL stores the selected timestamp as `?t=SECONDS`, allowing a deep link to that point.
- The “Open on YouTube” link opens the video at the selected timestamp.
- The content is based on the provided 18:54 Zoom transcript. The **5–10 hours/week** figure is explicitly labeled an illustrative estimate, not a verified outcome.

## Timestamp map

| Section | Start | Additional moments |
|---|---|---|
| AI prospecting | 00:04 | 01:57, 09:08 |
| Interactive sales presentations | 03:11 | 05:52, 07:24 |
| Meeting intelligence and CRM | 10:31 | 11:24, 13:07, 15:51 |
| Signal-based outreach | 17:19 | 17:50, 18:32 |

## Files

- `index.html` — page content and structure
- `styles.css` — responsive Powerlytics styling
- `app.js` — interactive navigation and timestamp/video behavior
- `config.js` — set the YouTube video ID for all viewers
- `assets/powerlytics-logo.png` — Powerlytics logo from the supplied brand materials

Typography uses the Google-hosted **Source Sans 3** family, the current continuation of Source Sans Pro. The website uses the branded blue/purple palette. The font will fall back to Source Sans Pro or Arial if the external font cannot load.
