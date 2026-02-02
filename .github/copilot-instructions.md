This repository is a mostly-static personal/site collection with HTML pages, teaching materials (LaTeX), and media assets.

Objective
- Help contributors and AI agents quickly find and edit source files, preview the site locally, and rebuild LaTeX artifacts where present.

Key places to look
- Root HTML entry: index.html — serves as the site entry.
- Lecture material: `aulas/` — many subfolders contain their own `index.html` and local `tex/` sources (example: `aulas/0840-servidores-web/tex/0840-Servidores_web.tex`).
- Course materials and manuals: `e-forma/` — contains several LaTeX projects (look for `document.tex`, `0839-Manual-Linux-Servicos_de_redes.tex` and variants).
- Static assets: `img/` and per-folder `img/` subdirectories — update image references here.
- Examples, experiments, games: `exp/`, `jogos/` — useful for frontend/JS edits.

Project patterns and constraints
- Site is composed of many nested `index.html` files using relative links. Do not change file locations without updating internal relative links.
- Many TeX build artifacts are committed (`*.aux`, `*.toc`); when editing LaTeX, focus on `*.tex` source files and run a fresh build locally to regenerate outputs.
- Filenames and directories use Portuguese and include accented characters or spaces in some historical files; prefer using existing filenames when referencing them to avoid breaking links.

Local preview and build commands
- Quick HTML preview (recommended):

  python3 -m http.server 8000

  Then open http://localhost:8000/ in your browser from the repo root.
- Build a LaTeX source (from the folder containing the `.tex` file):

  latexmk -pdf document.tex

  or

  pdflatex document.tex && bibtex document || true && pdflatex document.tex

  (Replace `document.tex` with the specific `.tex` such as `0839-Manual-Linux-Servicos_de_redes.tex`.)

Patterns for edits
- HTML edits: update the nearest `index.html` for page content; navigation is mostly relative. Use a temp server to verify links.
- LaTeX edits: change `.tex` in place; ignore committed `.aux/.toc` when editing — regenerate with `latexmk`.
- Adding images: put new assets in the nearest `img/` directory and reference them with a relative path from the HTML or TeX file that uses them.
- When renaming/moving files, search for other `index.html` in parent/child folders for relative links that must be updated.

Examples (paths inside repo)
- Edit lecture source: aulas/0840-servidores-web/tex/0840-Servidores_web.tex
- Rebuild manual: e-forma/0839-Linux-serviços_de_redes/0839-Manual-Linux-Servicos_de_redes.tex
- Preview site root: open index.html or run `python3 -m http.server` at repo root

Notes for AI agents
- Prefer non-destructive edits: change HTML/TeX sources only; do not remove generated files unless instructed.
- Verify link correctness by running the local server and checking the updated page in a browser (or a link-checker tool).
- Ask the maintainer if you need to change URL structure, move directories, or prune generated artifacts — many links are fragile and manually maintained.

If anything above is unclear or you want the guidance tailored (e.g., add CI build commands, linting, or preferred LaTeX toolchain), tell me which area to expand.
