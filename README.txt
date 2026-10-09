PIXORIK WEBSITE (v2, refreshed design) — READY TO HOST
================================
Everything is wired up. All app logos and screenshots are connected.

FOLDER STRUCTURE
  pixorik/
    index.html                 <- the website (open this)
    README.txt                 <- this file
    assets/
      brand/pixorik-logo.svg   <- your Pixorik logo (used in nav + footer)
      ux/ux-1.png, ux-2.png    <- UI/UX design banners
      icons/                   <- app logos (auto-shown on cards)
      shots/                   <- app screenshots (auto-shown in popups)

WHAT'S ALREADY DONE
  - Every app card shows its real logo (except Saginaw - no logo was
    provided, shows a gradient initial instead; fine as fallback).
  - Every app popup shows its real screenshots.
  - Nav and footer show the Pixorik logo.
  - v2: new light look built on the logo colours (navy + sky blue).
  - Hero screen strip: edit the STRIP list in index.html to change
    which screenshots scroll across the top.
  - App list: edit the APPS list in index.html to add/remove apps.
  - Screenshots containing personal data (names/phones/addresses) were
    removed for privacy: 1 towing screen, 1 CLIP screen, 1 Tipsy screen.

3 THINGS TO DO BEFORE GOING LIVE
  1) FORM: go to web3forms.com, get a free key, and in index.html
     replace  YOUR_WEB3FORMS_KEY_HERE  with it. Then form emails reach you.
  2) EMAIL: replace hello@pixorik.com with your real email (footer + form).
  3) TEAM PHOTOS (optional): drop headshots in assets/ and swap the
     VP / PM initials in the two team cards for <img> tags.
  4) NDA CHECK: confirm with Vineet which government/healthcare apps
     (mosquito, UC Davis) may be shown publicly. To remove one, delete
     its block from the APPS list in index.html.

HOW TO HOST (easiest)
  - Go to netlify.com (free). Drag the whole "pixorik" folder onto it.
  - It goes live with a free URL. Later connect your pixorik.com domain.
