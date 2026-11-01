# Marbell Music — standalone static website

Open index.html directly in a browser. No installation, build, framework,
backend or connection to the Lovable application is required. All eight pages,
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
- founder.html: Founder page (Marta Białka), linked from the homepage as "Founder"
- connect/index.html: Business card QR redirect; GitHub Pages serves it at /connect/
- css/style.css: Plain CSS, including local font definitions and animations
- js/script.js: Optional vanilla JavaScript entry point (no libraries)
- assets/images: Artist images, both optimized About Us photographs and favicon
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
About Us includes the current supplied copy and both uncropped photographs, with
sections aligned to the introduction and the closing statement sized at 20px
on desktop and 14px on phones.

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

## Business card QR redirect (/connect)

connect/index.html is the page behind https://marbellmusic.com/connect, the URL
printed on the business cards. It immediately forwards visitors to a
configurable destination and shows a clickable Continue link as a fallback.

To change the destination later, edit connect/index.html and update the two
marked spots near the top and bottom of the file:
1. the meta refresh url in <head> (currently url=../founder.html)
2. the CONNECT_DESTINATION value in the <script> at the bottom

Use relative paths: ../founder.html (Founder), ../about/index.html (About Us)
or ../index.html (Homepage). No server, database or build step is involved,
so the printed QR code never needs to change.

The existing React/TypeScript application has not been modified or deleted.
