# Customization Guide

## 1. Change colors from one place

The palette is used in two spots:

**README badges & stats** (edit `README.md`):
- Quick-link badge colors: `LinkedIn-0077B5`, `GitHub-0b1020`, `Email-D14836`
- Stats URL query params: `bg_color=050816`, `title_color=22d3ee`, `icon_color=8b5cf6`, `text_color=cbd5e1`, `border_color=1e293b`
- Streak URL: `background=050816`, `ring=8b5cf6`, `fire=22d3ee`, `currStreakNum=cbd5e1`
- Profile counter: `color=06b6d4`

**SVG assets** (each `assets/*.svg`):
- Primary text gradient: `#22d3ee` â†’ `#8b5cf6` â†’ `#06b6d4` (stop colors in `gText` / `gBorder` gradients)
- Card background: `#070a17` â†’ `#0b1020` (`gBg` / `edug` / `certg` / `footbg` / `cdBg` / `pwBg` / `pwg`)
- Card border/stroke: `rgba(148,163,184,0.12)` and gradient borders `url(#gBorder)` / `url(#cdBorder)` / `url(#pwBorder)`
- Glow orbs: `#8b5cf6` and `#22d3ee` with `opacity="0.09-0.11"`
- Muted text: `#94a3b8`; heading text: `#f8fafc`

To re-theme globally, swap the three gradient stops (`#22d3ee`, `#8b5cf6`, `#06b6d4`) and the two background stops (`#070a17`, `#0b1020`) in every SVG, and update the matching `*_color` params in the README stats URLs.

## 2. Add a new project card

1. Create `assets/<project>.svg` (viewBox `0 0 520 470`, `width="100%"`), modeled on `campusdesk.svg` / `pulsewatch.svg`:
   - glass card rect (`rx="20"`, stroke gradient border)
   - title, one-line description, 3 highlight lines, tech tag chips, "View repository" `<a>` link
2. Add an architecture diagram `assets/<project>-arch.svg` if desired.
3. In `README.md`, add a `<td>` cell next to an existing project card inside the "Featured Projects" table, or add a new table row. Keep max two cards per row so the layout stays responsive (`width="100%"`).
4. Repo links: replace `https://github.com/shruthikuragayala-02/<project>` with the real repository URL.

## 3. Update the links

- `README.md` quick links: LinkedIn, GitHub, `mailto:` â€” edit the `href` attributes.
- Profile counter badge: change `username=shruthikuragayala-02` in the komarev URL.
- Certifications: edit the two Google Drive `href` URLs in `assets/certifications.svg`.
- Project repository links: edit the `<a href>` in `assets/campusdesk.svg` and `assets/pulsewatch.svg` (and any new card).

## 4. Snake contribution animation

- Workflow: `.github/workflows/snake.yml`
- Action: `Platane/snk@v3` runs on push to `main`, hourly schedule, and manual dispatch.
- Output branch: `github-profile-snake` (the `git-auto-commit-action` commits `dist/*` there).
- The README references: `https://raw.githubusercontent.com/shruthikuragayala-02/shruthikuragayala-02/github-profile-snake/dist/github-profile-snake.svg`
- To change frequency, edit the `cron` value. To disable scheduled runs, remove the `schedule:` block.

## 5. No fabrications

Do not add an Experience section, internships, metrics, awards, or phone number. Only the facts provided in the brief may appear.
