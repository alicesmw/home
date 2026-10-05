# alicewong.org

Personal academic site for Alice (Sook Mun) Wong — Assistant Lecturer, Department of Philosophy,
The University of Hong Kong.

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio)
theme. Published to <https://alicewong.org> via GitHub Pages.

## How publishing works

Push to `main` → `.github/workflows/deploy.yml` builds the site with Jekyll and force-pushes the
built output to the `gh-pages` branch → GitHub Pages serves `gh-pages` at alicewong.org.

**Never edit `gh-pages` by hand.** It is overwritten on every deploy. All edits go on `main`.

The root `CNAME` file holds the custom domain. It is copied into the build output on every run, which
is what keeps the domain attached even though `gh-pages` is force-pushed each time. Don't delete it.

`baseurl` in `_config.yml` must stay **blank**. The custom domain serves this repo from the domain
root; setting a baseurl would break every stylesheet and link on the site.

## Where the content lives

| What | Where |
| --- | --- |
| Homepage bio | `_pages/about.md` |
| Publications, talks, abstracts | `_bibliography/papers.bib` |
| CV (and the auto-generated CV PDF) | `_data/cv.yml` |
| Research project pages | `_projects/*.md` |
| Courses | `_teachings/*.md` |
| Teaching page prose | `_pages/teaching.md` |
| Email, LinkedIn, GitHub links | `_data/socials.yml` |
| Site title, description, theme settings | `_config.yml` |

Adding a publication means adding a BibTeX entry to `_bibliography/papers.bib`. Mark the ones to
feature on the homepage with `selected = {true}`.

## The other two workflows

- `render-cv.yml` regenerates `assets/rendercv/rendercv_output/Alice_Wong_CV.pdf` with
  [RenderCV](https://rendercv.com/) whenever `_data/cv.yml` changes. That PDF is what the download
  button on the CV page points to.
- `prettier.yml` auto-formats and commits. If it pushes a formatting commit after yours, that's expected.

## Running it locally

Optional — you can edit entirely through GitHub's web UI if you prefer.

```bash
bundle install
bundle exec jekyll serve   # http://localhost:4000
```

Leave the baseurl alone when serving locally; it's already blank.
