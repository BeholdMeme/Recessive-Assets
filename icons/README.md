# icons/

Drop the exporter's output here:

- the morph PNGs (`sunset.png`, `pastel.png`, …)
- `manifest.json` (lets `/icons-list/steam-itemdefs` auto-build the schema)

They are served at:

    http://<this-host>:8000/icons/<file>.png

Helpers:

- `GET /icons-list`                    — list everything being served, with URLs
- `GET /icons-list/steam-itemdefs?appid=YOUR_APPID`
                                       — the Steam itemdef JSON, icon_url filled in

IMPORTANT: Steam fetches icons from a PUBLIC URL. `127.0.0.1` works for your own
game/browser but NOT for Steam's servers. To let Steam ingest them, either
deploy this backend to a public host or expose it temporarily with a tunnel
(e.g. cloudflared / ngrok) and set RECESSIVE_PUBLIC_BASE_URL to that address.
