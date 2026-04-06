# Contributing to CSS Course

Thank you for your interest in improving this course. All contributions are welcome.

## How to Contribute

### Report an Error
Open a GitHub Issue with the label `bug`. Include:
- Which module/exercise file
- What the error is (paste the error message)
- Your R version and OS

### Suggest an Improvement
Open a GitHub Issue with the label `enhancement`. Include:
- Which module it applies to
- What you would add or change and why
- Any supporting references

### Submit a Pull Request

1. **Fork** the repository
2. **Create a branch**: `git checkout -b feature/your-improvement`
3. **Make your changes** — see guidelines below
4. **Test**: Knit the affected `.Rmd` file and confirm it renders
5. **Commit**: `git commit -m "Brief description of change"`
6. **Push**: `git push origin feature/your-improvement`
7. **Open a PR** against the `main` branch

## Content Guidelines

### Academic Standards
- All citations must be real, verified papers with real DOIs
- Dataset URLs must be live and accessible
- R code must run as written (test before submitting)

### Style
- Use the `theme_css()` ggplot theme defined in `R/theme_css.R`
- All plots must have: `title`, `subtitle` (if needed), `x`, `y`, `caption` (citing data)
- Code chunks should be annotated with comments
- Chunk names must be unique within each file

### Dual-Track Requirements
Every new exercise question must be labelled:
- 🟦 (Undergraduate) — interpretation focus, guided structure
- 🟥 (Graduate) — methodological critique, open-ended, literature engagement
- 🟦🟥 (Both tracks) — required for everyone

### Prohibited
- Fabricated citations or DOIs
- Datasets that require institutional access without a free alternative
- Code that calls external APIs without instructions for key setup
- Content that has not been tested in R ≥ 4.3.0

## Code of Conduct

This project follows the [Contributor Covenant Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/).

Be respectful. Be accurate. Be open to criticism.

---

*Questions? Open an Issue.*
