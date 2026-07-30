# NOMALY content

Portfolio content for [nomaly.rocks](https://nomaly.rocks). The site reads this
repository at runtime, so publishing is a `git push` — no site rebuild, no
redeploy, no admin panel.

## How publishing works

The site fetches `work/` from this repository and revalidates every 10 minutes.
Push a change and it appears within that window. There is no write path in the
other direction: this repository is the only place project content is edited,
and git history is the audit trail.

If a file fails validation the site skips that one project and keeps serving the
rest. If *every* file fails, the site build fails loudly rather than publishing
an empty portfolio.

## Adding a project

Create `work/<slug>.md`. The filename is the URL slug — `work/atlas-workspace.md`
becomes `/work/atlas-workspace` and `/tr/work/atlas-workspace`.

Everything lives in the YAML frontmatter. The body after the closing `---` is
ignored today and is reserved for a future long-form section.

```yaml
---
order: 5                    # ascending; decides grid order and "next project"
year: "2026"                # string, quoted
code: OPS-05                # short technical label shown above the title
placeholder: true           # true prints the "Representative brief" label
link: https://github.com/…  # optional; adds a "Source" row to the detail page
image: my-project.png       # optional; file name of an image in this directory
stack: [Next.js, PostgreSQL]  # not translated, joined with " / "
en:
  name: Project Name
  summary: >-
    One or two sentences. Shown in the grid and as the meta description.
  client: Client name
  role: What we did
  tags: [Product system, Automation]
  challenge: >-
    Section 01.
  solution: >-
    Section 02.
  result: >-
    Section 03.
tr:
  name: Proje Adı
  summary: >-
    ...
  client: Müşteri adı
  role: Yaptığımız iş
  tags: [Ürün sistemi, Otomasyon]
  challenge: >-
    ...
  solution: >-
    ...
  result: >-
    ...
---
```

### Rules

- **Both `en` and `tr` are required**, with every field filled. The site is
  bilingual and a missing locale would render a half-empty page, so validation
  rejects the file instead. There is no "translate later" state.
- `order` decides three things at once: position in the two-column grid, which
  project the "next" link goes to, and which generated visual signature the
  project gets. Ties fall back to alphabetical slug.
- `placeholder: true` is the honest default for unverified work. Set it to
  `false` only when the client name, role, and outcome in the file are real and
  you are allowed to publish them. When it is `false` the site prints the `code`
  where the "Representative brief" label used to be.
- `link` is optional and must be a full URL. Use it when the work can actually
  be inspected — a public repository, a live product — not as a decorative
  credential. It renders as a "Source" row beside client, year, role, and stack.
- `image` is optional. Commit the file into `work/` next to the markdown and put
  its **file name only** in the field — no folders, no external URL, and no SVG.
  Without it the project gets the site's generated field pattern, which is a
  deliberate look rather than a missing-image state, so ship an image only when
  it says more than the pattern does. Name it after the slug
  (`opensourcegym.md` → `opensourcegym.png`) so files stay paired.

  The image is cropped to fill its slot, roughly 4:3 on the detail page and
  wider in the grid, so keep the subject away from the edges. Around 1440px wide
  is plenty; nothing resizes it, so a multi-megabyte export is downloaded whole.
  Replacing an image under the same name can take a few minutes to appear —
  GitHub's raw CDN caches it — while a new file name is immediate.
- Use `>-` for prose. It folds line breaks into spaces and drops the trailing
  newline, so you can wrap long paragraphs in the file without wrapping them on
  the page.
- Keep `year` quoted. Unquoted `2026` parses as a number and is rejected.
- Slugs are permanent URLs. Renaming a file breaks the live link and any
  inbound traffic to it.

## Removing a project

Delete the file. It disappears from the grid, the sitemap, and the "next"
rotation within the revalidation window. The detail URL then 404s.
