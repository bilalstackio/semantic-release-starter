# semantic-release Starter Template

This is a ready-to-use starter template for fully automated releases using [`semantic-release`](https://semantic-release.gitbook.io/semantic-release/) with support for:

- Conventional Commits  
- GitHub Actions  
- Automatic version bumping  
- Automatic changelog generation  
- Commit linting with Husky and Commitlint  
- Skipping linting for release commits (`[skip ci]`)

---

## 🚀 Getting Started

### 1. Clone or Extract the Template

Unzip or clone this template into your project directory.

### 2. Install Dependencies

```bash
npm install
```

### 3. Add Your GitHub Token

Add a `GH_TOKEN` with repo permissions to your GitHub repository secrets.

Go to:

```
GitHub → Settings → Secrets → Actions → New Repository Secret
```

Add:

- Name: `GH_TOKEN`
- Value: `<your_personal_access_token>`

### 4. Enable GitHub Actions

Make sure your repo has GitHub Actions enabled.

### 5. Make a Release Commit

Use Conventional Commits to trigger a release. Example:

```bash
git commit -m "feat: add user login feature"
```

Once merged into `main`, the GitHub workflow will:

- Determine the next version
- Update `CHANGELOG.md`
- Bump the version in `package.json`
- Commit and push the changes
- Create a GitHub release

---

## 📁 Included Files

- `.releaserc.json` – Semantic Release configuration
- `.commitlintrc.json` – Commitlint rules
- `.github/workflows/release.yml` – Release workflow
- `.husky/commit-msg` – Skips linting for `[skip ci]` commits
- `package.json` – npm config with scripts and dev dependencies

---

## 🛠️ Customizing

- Change branch name in `.releaserc.json`
- Use `pnpm` or `yarn` instead of `npm` if needed
- To publish to npm, set `"npmPublish": true` in `.releaserc.json`

---

## 🧪 Local Dry Run (Optional)

```bash
npx semantic-release --dry-run
```

---

## ✅ Requirements

- Node.js 18+
- GitHub repo with `GH_TOKEN` secret
- At least one commit using Conventional Commits

---

## 📦 License

[MIT](./LICENSE)
