# St. Cecilia Academy — Freshman Powderpuff Playbook

An animated playbook for the freshman Powderpuff team. Every play runs as an
animation; a girl picks her position and watches only herself.

**Live:** https://cprand-stack.github.io/powderpuff/

## Layout

- `index.html` — the app. One self-contained file: no build step, no
  dependencies, images inlined. This is the source of truth.
- `build.py` — assembles `docs/` (the hosted site) and `artifact.html`.
- `docs/` — what GitHub Pages serves.
  - `index.html` landing page (View / Add to my phone)
  - `play/` the app as an installable PWA (manifest, service worker, icons)

## Deploying

```
python3 build.py && git commit -am "…" && git push
```

The service worker is versioned by a hash of the app, so every push invalidates
the previous cache and nobody gets a stale playbook.
