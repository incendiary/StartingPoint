# StartingPoint

Project templates for Python, C#, and C++ repositories. Each template includes pre-commit hooks (gitleaks, formatters), CI pipelines, and a CLAUDE.md publication-readiness audit prompt.

---

## Quickstart

```bash
# Clone this repo once
git clone git@github.com:incendiary/StartingPoint.git
cd StartingPoint

# Spin up a new project
./new-project.sh <language> <repo-name>
```

### Examples

```bash
./new-project.sh python  my-python-tool
./new-project.sh csharp  SharpLoader
./new-project.sh cpp     exploit-helper
```

The script creates a private GitHub repo under your account, seeds it from the right template, and pushes the initial commit. It then prints the exact next steps for that language.

---

## What's in each template

| File | Purpose |
|------|---------|
| `CLAUDE.md` | Publication-readiness audit prompt — paste into Claude to start the review |
| `.pre-commit-config.yaml` | gitleaks (pattern) + TruffleHog (verified) + language formatter |
| `.github/workflows/ci.yml` | Lint, build, test, gitleaks + TruffleHog on push/PR |
| `.gitignore` | Comprehensive ignores for the language |
| `README.md` | Project README with roadmap table |
| `pyproject.toml` | Python: Black, Ruff, isort config |
| `.editorconfig` | C#: Microsoft conventions + naming/compiler warnings |
| `.clang-format` | C++: Google-based style, 100-char columns |
| `.clang-tidy` | C++: Core Guidelines + modernize checks |
| `CMakeLists.txt` | C++: CMake scaffold with optional test build |

---

## Roadmap table (per project)

Each generated README contains a roadmap you fill in as you go:

| # | Status | Description |
|---|--------|-------------|
| #1 | ⬜ Todo | Secret scan |
| #2 | ⬜ Todo | Dependency audit |
| #3 | ⬜ Todo | Code quality pass |
| #4 | ⬜ Todo | Tooling |
| #5 | ⬜ Todo | Tests |
| #6 | ⬜ Todo | Documentation |
| #7 | ⬜ Todo | Branch protection |

Status key: ⬜ Todo · 🔄 In Progress · ✅ Done

---

## Using CLAUDE.md

After running `new-project.sh`, open the project in Claude Code. The `CLAUDE.md` in the project root will be loaded automatically. Fill in the four context fields at the top (Type, Authorization, Release intent, Audience), then tell Claude to start the audit.

---

## Contributing to StartingPoint

```bash
git clone git@github.com:incendiary/StartingPoint.git
cd StartingPoint
pip install pre-commit
pre-commit install
```

**Universality rule:** any security or tooling addition must be applied consistently across:
- All three template `.pre-commit-config.yaml` files
- All three template `.github/workflows/ci.yml` files
- The StartingPoint root `.pre-commit-config.yaml`
- The StartingPoint root `.github/workflows/ci.yml`

If you add a tool in one place, add it everywhere before committing.
