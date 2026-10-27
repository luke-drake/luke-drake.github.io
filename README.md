# Luke Drake — author site

A small Hugo site with no outside theme. Everything you'll normally edit is plain text.

## Where things live
| To change… | Edit |
|---|---|
| Buy links, email, short bio, newsletter (see `NEWSLETTER-SETUP.md`), profile links (ORCID, BYU page…) | `hugo.toml` |
| Home page sections | `content/_index.md` |
| The Book (description, praise, formats/prices, contents) | `content/book.md` |
| About | `content/about.md` |
| Podcasts (add an episode link when it airs) | the `podcasts:` list at the top of `content/media.md` |
| Speaking & Contact | `content/speaking.md` |
| Scholarship / publications | `content/scholarship.md` |
| Photos and downloads | `static/images/`, `static/press/` |
| Colors and fonts | `static/css/site.css` (top of file) |

Yellow dashed boxes marked **PLACEHOLDER** are things still to fill in. They come from `{{< ph >}}…{{< /ph >}}` in the markdown; delete the whole tag when done.

## Preview locally
Install Hugo (extended), then run `hugo server` in this folder and open http://localhost:1313.

## Publish free on GitHub Pages (when ready)
1. Create a GitHub repo and push this folder (the `_src/` folder is ignored on purpose: it holds the original CV and photo files).
2. Repo Settings → Pages → Source: **GitHub Actions**. The included `.github/workflows/hugo.yml` builds and deploys on every push.
3. Optional: add a custom domain in Settings → Pages (about $10–20/year from any registrar), then set `baseURL` in `hugo.toml`.
