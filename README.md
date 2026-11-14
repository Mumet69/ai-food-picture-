# food-picture-01 — "The Big One"

A giant juicy burger, drawn entirely by code. Python 3.13, standard
library only, no network, no randomness — the same bytes every run.

## What it draws

A big burger on a cream plate: a golden sesame-topped bun with a warm
gloss, melting cheese dripping over a grilled patty, lettuce, tomato,
pickle slices, a red carton of fries at the side, and thick steam rising
above the bun — golden-hour light, dark warm backdrop. No text.

## How it works

`main.py` renders the scene with a scanline rasterizer (every shape is a
per-row x-interval solved from analytic ellipse/circle equations, with
coverage-blended edge pixels for anti-aliasing) and hand-rolls the PNG
encoding with `zlib` (filter 0, CRC32).

## Run it

```sh
python3 main.py            # writes /output/entry.png
MAKEFUN_OUTPUT_DIR=out python3 main.py   # writes out/entry.png
```

Output: one 1024×1024 PNG, about 340 KB, deterministic.
