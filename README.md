# 🚀 Semantic Release Starter Template

![Release](https://img.shields.io/github/v/release/bilalstackio/semantic-release-starter-template)
![Commits](https://img.shields.io/github/commit-activity/m/bilalstackio/semantic-release-starter-template)
![Build](https://img.shields.io/github/actions/workflow/status/bilalstackio/semantic-release-starter-template/release.yml?label=release%20build)
![License](https://img.shields.io/github/license/bilalstackio/semantic-release-starter-template)


This is a modern starter template for Node.js projects using **semantic-release**, **commitlint**, **husky**, and **GitHub Actions**. It automates changelog generation, versioning, and GitHub releases — all from conventional commits.

---

## 🔧 Features

- ✅ **Semantic versioning** powered by [`semantic-release`](https://semantic-release.gitbook.io/)
- 📝 Automatic **changelog generation**
- 🚀 **GitHub release publishing**
- 💬 Enforced **conventional commits** using `commitlint` and `commitizen`
- 🛡️ **Husky** pre-commit & commit-msg hooks
- 🧪 Optional **lint-staged** for clean commits
- ⚙️ Ready-to-use **CI/CD workflows** (including FTP deploy)
- 📦 Not designed for npm publishing — perfect for custom apps

---

## 🧑‍💻 Getting Started

### 1. Clone & Install

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
npm install
```

### 2. Setup Husky

```bash
npm run prepare
```

### 3. Make Your First Commit

Use the CLI to follow conventional commit format:

```bash
npm run commit
```

---

## 🚀 Release Automation

On every push to `main`, a GitHub release will be created **if your commits follow conventional format**.

### ✅ Example Commit

```bash
feat: add login page [skip ci]
```

No need to bump versions or update changelogs manually — `semantic-release` handles it.

---

## 📁 Project Structure

```
├── .github/workflows/
│   ├── release.yml       # GitHub Action: automatic versioning & release
│   └── deploy.yml        # Optional: FTP deploy on release
├── .husky/               # Pre-commit & commit-msg hooks
├── CHANGELOG.md          # Auto-generated changelog
├── .releaserc.json       # Semantic release config
├── .commitlintrc.json    # Commitlint rules
├── package.json          # All scripts and dev tools
├── .gitignore            # Modern exclusions
```

---

## 🔑 Environment Variables

Set these secrets in your GitHub repo under **Settings → Secrets and variables → Actions**:

| Secret Name     | Description                    |
|-----------------|--------------------------------|
| `GH_TOKEN`       | GitHub PAT for releases        |
| `FTP_HOST`       | FTP host for deploy (optional) |
| `FTP_USERNAME`   | FTP username (optional)        |
| `FTP_PASSWORD`   | FTP password (optional)        |

> Your `GH_TOKEN` should have `repo` scope.

---

## 💡 Commit Guidelines

This project uses [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).

```
feat:     A new feature
fix:      A bug fix
chore:    Tooling or dev-related changes
docs:     Documentation only
refactor: Non-functional refactoring
```

Use `npm run commit` to stay compliant.

---

## 🚦 What Triggers a Release?

Semantic Release uses **Conventional Commits** to determine when and how to bump versions.

| Commit Prefix       | Example                           | Release Type | Description                     |
|---------------------|-----------------------------------|--------------|---------------------------------|
| `feat:`             | `feat: add login form`            | **Minor**    | Adds a new feature              |
| `fix:`              | `fix: correct login bug`          | **Patch**    | Fixes a bug                     |
| `perf:`             | `perf: optimize image loading`    | **Patch**    | Performance improvement         |
| `BREAKING CHANGE:`  | _In commit body (any type)_       | **Major**    | Introduces breaking API change |

### ❌ These do **not** trigger a release (by default):

- `chore:` – maintenance, tooling updates
- `docs:` – documentation only
- `style:` – formatting, whitespace, etc.
- `refactor:` – code changes without feature/fix
- `test:` – test-related only

> 📝 To trigger a release, always use the correct prefix and follow conventional commit rules.


## 📦 Node & Tooling

- Node version: `>=20.10.0`
- You can use `.nvmrc` for auto version switching:
  ```bash
  echo "20.10.0" > .nvmrc
  ```

---

## 📜 License

[MIT](./LICENSE) — free to use, fork, and modify.

---

## 🙌 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you'd like to change.

---

## 🧠 Inspiration

Built to save time on every new project. Fork it, extend it, automate your workflow, and never think about versioning again.
