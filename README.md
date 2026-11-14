# Thomas & Christeena — Wedding Invitation

Static site (plain HTML/CSS/JS, no build step, no external dependencies — fonts are self-hosted).
Theme: Romantic Lavender & Ivory (soft gradients, gold hairlines, gentle falling petals; no illustrated flowers). Default language Malayalam, with an English switch (top-right, remembered in localStorage).

## Files
- `index.html` — whole site (styles, markup, bilingual `I18N` object, scripts)
- `assets/couple.jpg` — couple photograph (unaltered, resized to 1350×1800)
- `assets/bw-1.jpg … bw-5.jpg` — extra gallery photos, converted to black & white and cropped 4:5
- `assets/og.jpg` — 1200×630 WhatsApp / Open Graph preview
- `assets/fonts/` — Cormorant Garamond, Jost, Great Vibes, Noto Serif/Sans Malayalam (woff2)

## Deploy (Vercel / Netlify / any static host)
1. Upload this folder as-is (no build command, publish directory = the folder root).
2. **Set your real domain for link previews.** Open Graph needs absolute URLs. `index.html` currently uses
   `https://thomas-christeenamol.vercel.app`. If your live address differs, run once:
   `sed -i 's#https://thomas-christeenamol.vercel.app#https://YOUR-DOMAIN#g' index.html`
3. Re-share the link on WhatsApp. If an old preview is cached, test with a new `?v=2` on the URL.

## Editing text
All visible text is in the `I18N` object near the bottom of `index.html` (`ml` and `en`). Elements use `data-i18n="key"`.
Malayalam spellings of the house names (അയല്ലുകുന്നേൽ, എഴുത്തുപള്ളിയിൽ), parents' names and places were transliterated — please verify them with the families.

## Notes
- Reception shows the venue only: no time, date or separate map link was supplied.
- The ceremony "View Location" button uses https://maps.app.goo.gl/4JTQti3FNdo2aKZZ6.
- Music: `assets/music.mp3` starts when a guest taps the entrance button (browsers block audio before a tap) and loops; a round button at bottom-right pauses/plays. Replace the file to change the track; empty `data-src` on `<audio id="wedding-song">` to remove music.
- More photos: add `<figure>` blocks inside `.gallery-grid`; the lightbox (swipe/arrows) picks them up.
- Countdown target: 18 Jan 2027, 11:00 AM IST (`2027-01-18T11:00:00+05:30`). Reduced-motion preferences are respected.
