# bubbleflap.mothlark.com

Static website for **Bubble Flap**, served by GitHub Pages from `main` / root.
Plain HTML and CSS: no build step, no JavaScript, no web fonts, no cookies, and nothing loaded from third parties.

```
/                 index.html      landing page
/support/         support/        support page and FAQ (App Store "Support URL")
/privacy/         privacy/        privacy policy (App Store "Privacy Policy URL")
/404.html                         GitHub Pages "not found" page
/assets/css/site.css              all styles (light and dark mode)
/assets/img/                      icon.svg, favicon-32.png, apple-touch-icon.png, og-image.png
CNAME, .nojekyll, robots.txt, sitemap.xml
```

Preview locally: `python3 -m http.server 8000`, then open http://localhost:8000

## URLs for App Store Connect

| Field | URL |
|---|---|
| Marketing URL | https://bubbleflap.mothlark.com/ |
| Support URL | https://bubbleflap.mothlark.com/support/ |
| Privacy Policy URL | https://bubbleflap.mothlark.com/privacy/ |

## Launch checklist

Every spot to change is marked with a `LAUNCH:` comment in the HTML.

- [ ] **App Store button**: replace both "Coming soon" buttons in `index.html` with Apple's official
      "Download on the App Store" badge, from https://developer.apple.com/app-store/marketing/guidelines/.
      Link it to `https://apps.apple.com/app/id<APP_ID>`.
- [ ] **Smart App Banner**: uncomment `<meta name="apple-itunes-app" content="app-id=…">` in `index.html`.
- [ ] **Screenshots**: put three landscape screenshots in `assets/img/` and swap them into the "Take a look" section.
- [ ] **Privacy policy**: check the developer name, and confirm the game really collects nothing beyond Game Center
      (no analytics, crash reporting, ads or third-party SDKs). If that changes, update `/privacy/` **before** release.
- [ ] **App Privacy in App Store Connect**: answer it to match the policy (for a game that only uses Game Center,
      this is normally "Data Not Collected"; check Apple's current guidance).
- [ ] **Support FAQ**: check the answers against the final game, e.g. the minimum iOS version.
- [ ] **Sitemap**: update `lastmod` dates in `sitemap.xml` when pages change.
- [ ] **Link previews**: after deploying, check them with a message to yourself in iMessage or Slack.
