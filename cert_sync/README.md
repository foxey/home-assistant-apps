# cert-sync (Home Assistant App)

Receives an ACME certificate pushed by a [cert-sync](https://github.com/foxey/cert-sync)
server over Redis and installs it for Home Assistant Core's `http:` integration —
no Traefik involved on this side.

Because the certificate is a wildcard issued for the Traefik deployment (e.g.
`*.app.example.com`), Home Assistant's `base_url` must use a hostname that
matches it.

See `DOCS.md` for configuration.

The image is built and published by [cert-sync](https://github.com/foxey/cert-sync)'s
own CI — this app folder just points Supervisor at it via `config.yaml`'s `image:`
field, so there's nothing to build here.
