# bubbledare.mothlark.com

Static website for **Bubble Dare**, served by GitHub Pages from `main` / root.

The game was called Bubble Flap until October 2026, when App Review rejected it under
guideline 4.1(a) (Copycats) for reading as Flappy Bird. The site moved from
bubbleflap.mothlark.com to bubbledare.mothlark.com at the same time. Keep "Flap",
"Flappy" and other games' names out of the copy, and the bird green (the game's default, Kiwi).

Plain HTML and CSS: no build step, no JavaScript, no web fonts, no cookies, and nothing loaded from third parties.

```
/                 index.html      landing page
/support/         support/        support page and FAQ (App Store "Support URL")
/privacy/         privacy/        privacy policy (App Store "Privacy Policy URL")
/404.html                         GitHub Pages "not found" page
/app-ads.txt                      authorised ad sellers (AdMob); Marketing URL must be this site
/assets/css/site.css              all styles (light and dark mode)
/assets/img/                      icon.svg, favicon-32.png, apple-touch-icon.png, og-image.png
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

- [ ] **App Store button**: replace both "Coming soon" buttons in `index.html` with Apple's official
      "Download on the App Store" badge, from https://developer.apple.com/app-store/marketing/guidelines/.
      Link it to `https://apps.apple.com/app/id<APP_ID>`.
- [ ] **Smart App Banner**: uncomment `<meta name="apple-itunes-app" content="app-id=…">` in `index.html`.
- [ ] **Screenshots**: put three landscape screenshots in `assets/img/` and swap them into the "Take a look" section.
- [x] **Privacy policy**: updated 30 Sep 2026 for Google AdMob ads (consent form, tracking prompt, ad partners).
      Keep it in step with the game's Privacy card and `docs/privacy-policy.md` / `docs/PRIVACY.md` in the game repo.
- [ ] **App Privacy in App Store Connect**: with ads it is no longer "Data Not Collected"; answer it as
      `docs/PRIVACY.md` in the game repo says (Google Mobile Ads SDK data types).
- [ ] **app-ads.txt**: after launch, link the App Store listing in AdMob and check AdMob → Apps → app-ads.txt
      shows "Found"; it can take a day or two to be crawled.
- [ ] **Support FAQ**: check the answers against the final game, e.g. the minimum iOS version.
- [ ] **Sitemap**: update `lastmod` dates in `sitemap.xml` when pages change.
- [ ] **Link previews**: after deploying, check them with a message to yourself in iMessage or Slack.
