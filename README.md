# Justin Leonard, portfolio site

A static nine-page portfolio: the one-page overview, three creative case studies, and a UX section (a landing page plus four UX case studies).

| Page | File |
|---|---|
| Overview | `index.html` |
| Trailer wrap case study | `trailer-wrap.html` |
| Dealer website concept case study | `website-concept.html` |
| Horror game case study | `horror-concept.html` |
| UX and product design landing page | `ux.html` |
| Research tool case study | `research-tool.html` |
| Agency platform case study | `agency-platform.html` |
| Find case study | `find.html` |
| NOXIE game UX case study | `noxie.html` |

Everything the pages use is in `assets/` (images, videos, share images). All links between pages are relative, so the folder works from any address, including a sub-path. Fonts load from Google Fonts; the Vimeo and LinkedIn links are the only other outside links.

## Preview locally

From inside this folder:

```
python3 -m http.server 8000
```

Then open http://localhost:8000/ in a browser. Opening `index.html` straight from the file system also works, but the server is closer to how the live site behaves.

## Publish

- Ready for GitHub Pages as-is: `index.html` at the root and an empty `.nojekyll` file so the folder is served unchanged.
- **Leave out `_checks/`.** It holds the pre-publish screenshots and is not part of the site. Delete it from the published copy, or publish everything except that folder.
- Once the address is known, set `SITE_URL` in the build script (`../_site-build/build_site.py`) and rebuild, so the share images and page links in the Open Graph tags become full addresses. Most social sites ignore relative share images.

## Rebuild

The pages are generated. Edit the build script, not the HTML:

```
cd ../_site-build
python3 build_site.py          # pages plus any missing or changed media
python3 check_site.py ../site  # links, assets, anchors and banned words
```
