# Mythbolt — Field Instruments

Rev 2 of mythbolt.com. A rack of working security instruments rather than a brochure,
styled as a Ghibli workshop — lamplight, brass, aged paper tags, dust in the beam.

Every panel performs the technique it describes, live, against the visitor's own browser
and input. Six instruments: passive fingerprint, path normalisation, timing side channel,
hash avalanche, search space, and a Forer-effect demonstration.

## Layout
- `index.html` — the deployable page (generated; don't edit by hand)
- `src/index.body.html` — the source. Edit this.
- `build.sh` — regenerates `index.html`

Single self-contained file. No bundler, no dependencies, no framework.
Shippori Mincho + Courier Prime from Google Fonts; all CSS, JS and artwork inline.

Colour is semantic: **brass = the instrument, vermilion = you / the gap, moss = agreement.**

## Constraints this build holds to
- **Nothing is transmitted.** No analytics, no cookies, no network calls after load.
  The only request the page ever makes is the webfont in `<head>`.
- **No client names, no findings, no methodology.** Every instrument demonstrates a
  publicly documented concept. Nothing here reflects a real engagement.
- **SubtleCrypto** (instrument I-04) needs a secure context — works on https and
  localhost, inert over `file://`.

## Local
```bash
./build.sh && python3 -m http.server 8791   # then open http://127.0.0.1:8791
```
