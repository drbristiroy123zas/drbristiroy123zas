Dr. Oendrila Roy — website
==========================

Plain static HTML. No build step, no framework. Open any .html file directly in a
browser, or serve the folder to preview links/relative paths exactly as they will
behave live:

    cd ~/MEGA/dr_oendrila_roy_website
    python3 -m http.server 8000
    # then visit http://localhost:8000

Files
-----
index.html                  Home
about.html                  About / credentials
clinical-expertise.html     Clinical expertise (6 topic sections)
patient-information.html     Patient & family information, FAQ, glossary
research-publications.html   Publications
contact.html                Contact form + hospital details
patients-families.html       Redirect stub -> patient-information.html (old URL)
404.html                    Not-found page (GitHub Pages serves this automatically)
robots.txt, sitemap.xml     Search-engine files
assets/css/styles.css       ALL styling. Design tokens (colours, type, spacing) at the top.
assets/img/                 favicon.svg, portrait.jpg, flow-lines.svg, contours.svg

Shared header and footer
------------------------
The <header class="site-header"> and <footer class="site-footer"> blocks are
identical on every page (marked with comments). If you change one, change it on
all pages. Only the nav link with aria-current="page" differs per page.

Parallax
--------
Any element with data-parallax="0.2" drifts as its section scrolls. The number is
strength (~0.05–0.3; negative reverses direction). It turns itself off under the
OS "reduce motion" setting. Layer styles: parallax-layer--flow, --contour, --dots.

Before launch — search every file for "to-confirm" and fill in:
  - NMC / West Bengal Medical Council registration number (about.html)
  - Languages spoken, society memberships (about.html)
  - Outpatient timings + appointment number, response time (contact.html)
  - "Reviewed on" date for patient-information.html
  - Facebook page URL — footer "Professional" list on every page: replace
    href="#" on the "Facebook (add link)" item with the real URL and drop
    the class="to-confirm" (also remove the TODO comment above it)
Also:
  - contact.html form: replace YOUR_ACCESS_KEY with a real Web3Forms/Formspree key
  - If a custom domain is added: add a file named CNAME with the bare domain,
    and change every "https://droendrilaroy.github.io" to the new domain
    (canonical tags, og:url, og:image, sitemap.xml, robots.txt).

Deploying to GitHub Pages
-------------------------
Put these files at the root of the repo droendrilaroy/droendrilaroy.github.io,
then in the repo: Settings -> Pages -> Build and deployment -> Source =
"Deploy from a branch", branch = main, folder = / (root). No build needed.
