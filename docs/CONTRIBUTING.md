---
sidebar_position: 5
title: Contributing
---

# Contributing to OurSpace

Thanks for taking the time to contribute to **OurSpace**, RJAH’s staff wellbeing portal built with love, code, and caffeine.

This guide will help you get set up, follow our coding standards, and submit changes the right way.

## Getting Started

1. **Clone the repo**

```bash
git clone https://github.com/rjah-nhs/ourspace.git
cd ourspace
```

2. **Install dependencies**

```bash
composer install
npm install
```

> 💡 You’ll need PHP, Composer, and Node.js installed on your machine.

3. **Spin up a local WordPress environment**

We recommend using [Local](https://localwp.com/) for zero-config development.

---

## Branching

- Use `main` as your base branch.
- Create feature branches like:
  - `feature/add-footer-widget`
  - `bugfix/fix-header-spacing`
  - `chore/update-dependencies`

---

## Release Notes

For every new version, add a markdown file in the [release-notes](https://github.com/RJAH-OurSpace/Our-Space/tree/main/release-notes) folder named after your version tag, e.g.:

```
release-notes/v1.2.0.md
```

Include a brief, friendly changelog. Example:

```markdown
# What's New in v1.2.0

- 🧭 Added site map support
- 🐛 Fixed mobile menu overlap bug
- 🧼 Cleaned up widget area markup
```

---

## Code Quality & Linting

We follow the [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/wordpress-coding-standards/).

Before pushing code, make sure you:

```bash
npm run lint
```

Or run our fixer:

```bash
npm run fix
```

On pull requests:
- **Errors** will fail the build.
- **Warnings** will appear as comments via reviewdog.

More info in LINTING.md

---

## Pull Requests

1. Push your feature branch
2. Open a pull request with:
   - A clear title
   - A link to any related issues
   - A summary of what changed and why
3. Wait for the CI checks to pass
4. Request a review (or assign someone)

---

## Releasing

Once a pull request has been merged and tested:

```bash
git checkout main
git pull
git tag v1.2.0
git push origin v1.2.0
```

This will trigger our GitHub Action to:

- Zip the theme from `src/`
- Read the corresponding `release-notes/v1.2.0.md`
- Publish a GitHub release automatically

See RELEASE_WORKFLOW.md for full details.