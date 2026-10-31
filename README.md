# Marbell Music — standalone static website

Open index.html directly in a browser. No installation, build, framework,
backend or connection to the Lovable application is required. All six pages,
images, icons, fonts and CSS are included locally. External artist links open
in a new tab; phone and email links use the device's configured applications.

## GitHub Pages

1. Back up your existing MartaMaya/marbellmusic repository contents.
2. Copy the CONTENTS of static-export to the root of that repository (not the
   containing static-export folder). Include .nojekyll and CNAME.
3. In GitHub Settings → Pages, choose Deploy from a branch and select your
   publishing branch and / (root). No custom build workflow is needed.
4. Confirm the custom domain is marbellmusic.com. CNAME is already included;
   keep or configure your domain's GitHub Pages DNS records separately.

## Files

- index.html: Home
- contact.html: Contact
- artists.html: Promoted Artists
- about/index.html: About Us; GitHub Pages serves this directory at /about/
- about.html: An equivalent directly openable About Us page
- bartek-derylo.html and wolniej.html: Individual artist profiles
- css/style.css: Plain CSS, including local font definitions and animations
- js/script.js: Optional vanilla JavaScript entry point (no libraries)
- assets/images: Artist images, optimized About Us photograph and favicon
- assets/fonts: Local Inter font files and font license
- assets/audio: Reserved for real audio files (currently empty)

## Existing limitations preserved, not invented features

The current audio widget is decorative: it displays “PLAYING: The Long Way”,
a waveform and previous/pause/next symbols, but has no audio source, playback
handlers or functional controls. The static version preserves that appearance
and animation. Actual playback needs a supplied, licensed audio file; a native
HTML audio player with vanilla JavaScript controls is the static alternative.
No audio file or song URL has been invented.

“The team” still has no destination or supplied page content and remains inactive.
About Us now includes the supplied exact copy and full-composition photograph.

Old framework URLs such as /contact or /artists/bartek-derylo become
contact.html or bartek-derylo.html. Internal navigation uses these portable
relative paths, supporting file://, custom domains and GitHub project subpaths.
Update any bookmarks or external links to the old framework URLs.

About Us additionally supports direct navigation and refresh at /about on the
custom domain: GitHub Pages redirects that directory URL to /about/ and serves
about/index.html. The homepage links directly to about/index.html so it also
works when opened offline. No server rules or JavaScript redirects are needed.

To change an artist's links, edit that artist's HTML file. Include only supplied
platform URLs; omit missing platforms and omit the section if there are none.
Keep target="_blank", rel="noopener noreferrer" and artist-specific labels.

The existing React/TypeScript application has not been modified or deleted.
