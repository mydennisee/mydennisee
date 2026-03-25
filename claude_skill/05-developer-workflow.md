# 05 — Developer Workflow & Tooling

## What I Do

Maintain a disciplined development workflow across AI/ML projects, data pipelines, and web-based technical artefacts. Work is version-controlled, reproducible, and built to communicate — both to machines and to people.

---

## How I Approach It

### Version Control (Git)
- Every project is a git repo from day one — no exceptions
- Commit messages explain the *why*, not just the *what*
- Pull before push — rebase preferred over merge for clean history
- Branches for features; main/production is always stable
- Remote conflicts resolved via rebase, not force-push

### Project Structure
- Separate concerns: raw data, processed data, features, models, API, documentation
- Config files (paths, parameters) separated from logic — no hardcoded values
- Reproducibility by default: environment file + seed + version-locked dependencies

### Python Development
- Modular functions — one function, one responsibility
- Type hints where ambiguity exists
- Scripts vs. notebooks: notebooks for exploration and presentation, scripts for production
- Logging over print statements in production code

### API & Serving Layer
- FastAPI for production REST endpoints — typed, documented, fast
- Separate concerns: extraction logic, storage logic, serving logic
- Input validation at the API boundary — not buried in business logic

### Web & Visual Communication
- HTML/CSS for technical architecture diagrams and portfolio artefacts
- Design system consistency — define CSS variables once, reference everywhere
- SVG for programmatic diagrams — version-controllable, no external dependencies
- Dark theme as default for technical audiences

### Environment & Infra
- Virtual environments per project — no global package pollution
- GPU environments managed separately (CUDA version pinned)
- Secrets in environment variables — never committed to git
- Dockerfile or requirements.txt at minimum for every project that others will run

---

## Tools & Stack

| Category | Tools |
|----------|-------|
| Version control | Git, GitHub |
| Languages | Python, SQL, Bash, HTML/CSS/SVG |
| API | FastAPI |
| Environment | venv, conda, Docker |
| GPU | CUDA, RAPIDS, RTX hardware |
| Notebooks | Jupyter |
| CLI | gh (GitHub CLI), standard Unix tools |

---

## How I Build Technical Artefacts

| Artefact | Approach |
|----------|----------|
| Architecture diagrams | Custom SVG or HTML — dark theme, self-contained, version-controlled |
| GitHub profile | README.md with design system aligned to portfolio |
| Portfolio site | Pure HTML/CSS/JS — no build step, deploys to GitHub Pages |
| Model documentation | Markdown — structured, machine-readable, stored alongside code |
| Pipeline documentation | Inline + README — schema, lineage, and operational notes |

---

## Demonstrated in This Profile

Everything visible at `github.com/mydennisee` and `mydennisee.github.io` was built following these practices:

- Custom SVG diagrams committed to repo — no external image services
- Portfolio site: zero build-step HTML, deploys to GitHub Pages free tier
- Design system defined in CSS variables — consistent across all pages
- Git history clean: meaningful commits, conflict resolution via rebase
- No inline secrets or hardcoded paths anywhere in the codebase

---

## My Standard: What "Done" Looks Like

- Code runs on a fresh clone with documented setup steps
- No secrets in the repository — checked before every commit
- Architecture can be explained from the README alone
- Visual artefacts are self-contained — no broken external dependencies
- Technical documentation written for the next person, not just for now
