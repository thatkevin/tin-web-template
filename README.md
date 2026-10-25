# The Tin — GigKit site template

The site template for **The Tin Music and Arts** (Coventry), rendered live by
[GigKit](https://github.com/thatkevin/gigkit). This is the venue-owned template
repo for GigKit's "pull your template from a GitHub repo" feature (#686).

## How it's used

A GigKit Site points its **template repo URL** at this repo. On publish (and, once
a webhook is configured, on every push) GigKit fetches the repo and renders the
site live from these files — no build step runs here.

## Structure

Jekyll-style layout. GigKit's live renderer understands:

- `_config.yml` — template config.
- `_layouts/` — page layouts (`default`, `event`, `page`, …); the page body is
  rendered into `{{ content }}`.
- `index.html`, `404.html`, and the page folders (`about/`, `events/`, `rooms/`,
  `news/`, …) — each an extensionless page resolved by path.
- `images/` — static assets served alongside the pages.

Dynamic content (events, news, rooms, etc.) is injected by GigKit as
`site.data.*` at render time; the templates read it with Liquid.

## Styling

Tailwind via the **Play CDN** (`cdn.tailwindcss.com`) with an inline
`tailwind.config` in `_layouts/default.html` — so the template is self-contained
and needs no build/compile step. (GigKit's production deploy may swap this for a
precompiled stylesheet; the source of truth lives here.)

## Editing

Edit the files and push. With the GigKit push webhook enabled, changes go live
automatically; otherwise hit **Publish** in the GigKit admin to pull the latest.
