# bubbledare.mothlark.com

Static website for **Bubble Dare**, served by GitHub Pages from `main` / root.

The game was called Bubble Flap until October 2026, when App Review rejected it under
guideline 4.1(a) (Copycats) for reading as Flappy Bird. The site moved from
bubbleflap.mothlark.com to bubbledare.mothlark.com at the same time. Keep "Flap",
"Flappy" and other games' names out of the copy, and the bird green (the game's default, Kiwi).

Plain HTML and CSS: no build step, no JavaScript, no web fonts, no cookies, and nothing loaded from third parties.

```
/                 index.html      landing page
/christmas/       christmas/      the Christmas season (1 Dec to 6 Jan) and its press kit
/support/         support/        support page and FAQ (App Store "Support URL")
/privacy/         privacy/        privacy policy (App Store "Privacy Policy URL")
/404.html                         GitHub Pages "not found" page
/app-ads.txt                      authorised ad sellers (AdMob); Marketing URL must be this site
/assets/css/site.css              all styles (light and dark mode)
/assets/css/christmas.css         the Christmas page only, on top of site.css
/assets/img/                      icon.svg, favicon-32.png, apple-touch-icon.png, og-image.png, shot-*.webp
CNAME, .nojekyll, robots.txt, sitemap.xml
```

Preview locally: `python3 -m http.server 8000`, then open http://localhost:8000

## URLs for App Store Connect

| Field | URL |
|---|---|
| Marketing URL | https://bubbledare.mothlark.com/ |
| Support URL | https://bubbledare.mothlark.com/support/ |
| Privacy Policy URL | https://bubbledare.mothlark.com/privacy/ |

## Launch checklist

Every spot to change is marked with a `LAUNCH:` comment in the HTML.

- [x] **App Store button**: both buttons in `index.html` link to `https://apps.apple.com/app/bubble-dare/id6816718972`
      (no country code, so visitors land in their own storefront). Optional: swap in Apple's official
      "Download on the App Store" badge from https://developer.apple.com/app-store/marketing/guidelines/,
      saved under `assets/img/` (nothing is loaded from third parties).
- [x] **Smart App Banner**: `<meta name="apple-itunes-app" content="app-id=6816718972">` in `index.html`.
- [x] **Screenshots**: `assets/img/shot-*.webp`, gameplay cropped from the game repo's 6.7-inch store screenshots.
- [x] **Privacy policy**: updated 30 Sep 2026 for Google AdMob ads (consent form, tracking prompt, ad partners).
      Keep it in step with the game's Privacy card and `docs/privacy-policy.md` / `docs/PRIVACY.md` in the game repo.
- [ ] **App Privacy in App Store Connect**: with ads it is no longer "Data Not Collected"; answer it as
      `docs/PRIVACY.md` in the game repo says (Google Mobile Ads SDK data types).
- [ ] **app-ads.txt**: after launch, link the App Store listing in AdMob and check AdMob → Apps → app-ads.txt
      shows "Found"; it can take a day or two to be crawled.
- [ ] **Support FAQ**: check the answers against the final game, e.g. the minimum iOS version.
- [ ] **Sitemap**: update `lastmod` dates in `sitemap.xml` when pages change.
- [ ] **Link previews**: after deploying, check them with a message to yourself in iMessage or Slack.

## The Christmas page

`/christmas/` shows what the season adds to the game and holds the press kit. It's the
"supplemental materials" link in the App Store featuring nomination and the link for
December posts.

Everything on it comes from the game repo's Christmas custom product page renders
(`store/custom-product-pages/christmas/` in bubble-flap), which are rendered from the live
build:

- `assets/img/christmas/hero-*.webp` and `og-christmas.png`: the header art
  (`creative-assets/header-3840x1646.png`).
- `assets/img/christmas/shot-*.webp`: the gameplay inside the 6.3" screenshots, 1080 px wide.
- `christmas/press/`: the full-size iPhone 6.3" and iPad 13" screenshots, the header art,
  the app icon, a `README.txt` fact sheet, and all of them in
  `bubble-dare-christmas-press-kit.zip`.

The Yule Lads calendar on the page follows the game's `Seasons.yule_lads_on` (none until
12 Dec, one more a day to 13 on Christmas Eve, one fewer a day to none on 6 Jan), and the
gold baubles are the special dailies in `Daily.SPECIAL` (21, 24, 25, 26 Dec and 1 Jan).
If either changes in the game, change the page.

Next year: re-render the screenshots from the build that's live then, and replace the
files above with the same names.
