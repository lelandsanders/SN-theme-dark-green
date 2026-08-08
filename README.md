# Forest Dark

A dark forest-green theme for Standard Notes.

Deep green-tinted surfaces instead of neutral grey, a moss-and-fern accent
ramp, and a tag list where the selected row is the lightest surface in the
theme sitting on the darkest — so you can always tell what's highlighted.

Works on web, desktop, and mobile.

## Install

Preferences → General → Advanced Settings → Install Custom Plugin, then paste:

```
https://cdn.jsdelivr.net/gh/lelandsanders/SN-theme-dark-green@main/ext.json
```

Then activate it under Appearance → Themes.

## Repo layout

```
SN-theme-dark-green/
├── ext.json          descriptor Standard Notes reads
├── forest-dark.css   the theme itself
├── package.json      version + sn.main (desktop zip installs)
├── README.md
└── LICENSE
```

Every path is at the repo root. If you move the CSS, update `sn.main` in
`package.json` and `url` in `ext.json` to match.

## Customizing

Edit only the palette block at the top of `forest-dark.css`. Everything
below it references those values, so one hex change propagates through the
whole theme.

To preview a change without publishing, open the app's dev tools
(desktop: View → Toggle Developer Tools), find `:root` in the Styles panel,
and edit the variables live.

## Releasing a change

1. Bump `version` in **both** `package.json` and `ext.json` — they must match.
2. Update the version in `ext.json`'s `url` and `download_url`.
3. Commit and push.
4. Tag a release on GitHub (`v1.0.1`), which generates the source zip that
   `download_url` points at.

## Things that break installs

**The URL must serve raw JSON.** A `github.com/.../blob/...` link returns an
HTML page and the install will fail. Use the jsDelivr URL above, or
`raw.githubusercontent.com`.

**The repo must be public.** jsDelivr can't reach private repos.

**Branch name matters.** These URLs use `@main`. If your default branch is
`master`, change it.

**jsDelivr caches branch URLs for up to 7 days.** This is the usual reason a
theme edit doesn't show up. Either point `url` at a version tag (as it is
here) or purge manually:

```
https://purge.jsdelivr.net/gh/lelandsanders/SN-theme-dark-green@main/forest-dark.css
```

**Mobile caches the CSS indefinitely.** Long-press the theme name in the
themes list to force a re-download.

## License

MIT
