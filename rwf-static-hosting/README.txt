RWF static website bundle

Upload every file and folder inside the "site" directory to your web host's
public web root (often named public_html, www, or dist). Keep the assets
directory and all root-level files together with index.html.

This is a compiled static website, not the editable React/TypeScript source.
It contains HTML, JavaScript, CSS, images, and public assets.

Single-page app routing:
Configure the host to serve /index.html for unknown page paths such as
/shop, /faq, and /shipping-returns. Without this fallback, direct visits or
refreshes on those routes may show a host 404.

Backend-dependent features:
The contact form, music player, and payment checkout call the website's API
under /api. To keep those features working, host the API server and route
https://your-domain.example/api/* to it, or configure an equivalent same-origin
proxy. The static files alone do not contain the API server.

The site uses root-relative asset paths, so deploy it at the domain root.
