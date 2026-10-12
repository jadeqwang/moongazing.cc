# moongazing.cc

The watch site for **望明月 Moongazing**, an animated music video by Jade Wang: an astronaut spends thirteen months at an international base at the Moon's south pole, while her family looks up at it from Earth. One static page: the film, the lyrics, and why the film's International Moonbase looks different from moonbases in movies, with the real technology behind each part of it.

Words by Jade Wang, from her poem "To Li Bai" (*Oyez Review*, 2007); Chinese lines by Li Bai; closing lines by Zhang Jiuling.

The film's code (every frame drawn in ink, silk and gold by JavaScript) and the full, sourced tour of the base live in [jadeqwang/moongazing-public-version](https://github.com/jadeqwang/moongazing-public-version).

## The film

The film is live on [YouTube](https://www.youtube.com/watch?v=_j_IVgA-pf8) and embedded on the page. Its video id (the part after `watch?v=`) is set in the one constant near the top of the `<script>` in `index.html`:

```js
const YOUTUBE_ID = '_j_IVgA-pf8';
```

While it is empty, the frame shows the title card with "Film coming soon", and the lyrics and timestamps are plain text. Once it is set, the page loads the YouTube player (privacy-enhanced, youtube-nocookie.com); tapping a lyric line plays the film from that line, with the sung line lighting up as it plays, and the timestamps in the Moonbase section play the film from that moment.

No video files are kept in this repo. The stills in `img/` are frames of the film.

## Deploy

It is a plain static site: `index.html`, the favicons and `img/`, no build step.

Cloudflare Pages: connect this repo, framework preset "None", build command empty, build output directory `/`, then add `moongazing.cc` under Custom domains. Any other static host works the same way: serve the repo root.

To preview locally: `python3 -m http.server` in the repo root, then open http://localhost:8000.
