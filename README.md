# Steven Wang — Portfolio

Personal portfolio site. Mechanical Engineering, University of Waterloo.
Static HTML, CSS and vanilla JavaScript. No framework, no build step.

## Publishing on GitHub Pages

1. Create a repository. To publish at `https://<username>.github.io`, name the
   repository `<username>.github.io`. Any other name publishes at
   `https://<username>.github.io/<repo>/`.
2. Upload the contents of this folder to the repository root, so that
   `index.html` sits at the top level rather than inside a subfolder.
3. Repository → **Settings** → **Pages** → under *Build and deployment*, set
   **Source** to *Deploy from a branch*, branch `main`, folder `/ (root)`.
4. Save. The first build takes a minute or two.

## Layout

```
index.html                  the whole site: markup, styles, script
assets/img/                 photographs and CAD renders
assets/docs/                résumé and research note, linked from the page
.nojekyll                   serve files as-is, skip Jekyll processing
```

## Editing

Content lives in the `CONTENT` object near the top of the `<script>` block in
`index.html`: projects, experience, research and subteams. Each project and
research entry carries its own copy, figures and metadata. The header comment
at the top of `index.html` explains the fields.

- **Adding a figure**: drop the file in `assets/img/`, then set
  `img:"assets/img/your-file.webp"` on the matching figure entry. Figures with
  no `img` are skipped, so a slot stays invisible until it has a picture.
- **Replacing the résumé**: overwrite `assets/docs/Steven-Wang-Resume.pdf`, and
  re-export page one to replace the preview image in the résumé section.
- **"In progress" badges**: a research row shows one until it has a `paper`
  block; a subteam tile shows one while `wip:true` is set.

## Notes

- Routing is hash based (`#/projects/…`), so deep links work on GitHub Pages
  without any server configuration or redirect rules.
- Fonts load from Google Fonts. To remove that external request, download the
  four families into `assets/fonts/` and swap the `<link>` for `@font-face`.
- Respects `prefers-reduced-motion`: the loader, entrance and idle animations
  all stand down.
