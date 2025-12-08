# UrAppKitchen Landing Site

Welcome! This repository hosts the UrAppKitchen landing site, built with [Hugo](https://gohugo.io/).

## 🚀 Quick Start

### Prerequisites
- **Hugo**: `brew install hugo`
- **Node.js** (via fnm):
  ```bash
  brew install fnm
  fnm install --lts
  ```

### Setup & Run
1. **Install dependencies**:
   ```bash
   npm install
   ```
2. **Run development server**:
   ```bash
   npm run dev
   ```
   The site will be available at `http://localhost:1313`.

## 📂 Project Structure

| Path | Description |
|------|-------------|
| `content/english/` | Main content (blog posts, projects, author profiles). |
| `archetypes/` | Templates for new content. |
| `static/images/` | Static assets (images). |
| `layouts/` | HTML templates and theme overrides. |
| `config/` | Site configuration files. |

## 📝 Contribution Workflow

### 1. Branching Strategy
- **Base Branch**: `dev` (Always branch from here, do not commit directly).
- **Production Branch**: `main` (Do not commit directly).
- **Short-lived Branches**:
Contributors must create their own short-lived branch for every PR based on `dev`.

**Branch Naming Convention**:
Use your username as a name for your branches.

### 2. Creating Content
1. **Sync with dev**:
   ```bash
   git checkout dev && git pull origin dev
   git checkout -b <username>
   ```
2. **Create file**:
   ```bash
   hugo new english/blog/my-post.md
   ```
3. **Edit Front Matter**:
   - Set `draft: false` to publish.
   - Ensure `title`, `date`, `author`, and `image` are set.

### 3. Commit Guidelines
We use specific prefixes for commit messages:

| Prefix | Usage | Example |
|--------|-------|---------|
| `blog:` | New blog posts | `blog: add intro-to-hugo` |
| `project:` | New projects | `project: add mobile-app-case-study` |
| `update:` | Content edits | `update: fix typos in about page` |
| `misc:` | Config/Style | `misc: update footer links` |

### 4. Pull Request
- Add one or multiple commits to complete your whole project
- Verify that no further edits are needed
- Push your branch: `git push -u origin <username>/my-new-post`
- Open a PR targeting **`dev`**, name it properly so people know what is this set of commits doing.
- Ensure the checklist (meta data, images, links) is complete.
- The maintainers will merge `dev` into `main` when suitable

### 5. Post-Merge Cleanup
GitHub automatically deletes merged branches. To keep your local repo clean:

1. **Enable auto-pruning** (one-time setup):
   ```bash
   git config --global fetch.prune true
   ```

2. **Delete local branches** that are gone on remote:
   ```bash
   git fetch -p && git branch -vv | awk '/: gone]/{print $1}' | xargs -r git branch -d
   ```

3. **If you are using GitHub in VS Code** enable pruning on fetch in Settings.

## 🛠 Troubleshooting
- **Content not showing?** Check if `draft: true` in the front matter.
- **Broken images?** Ensure images are in `static/images/` and referenced correctly (e.g., `image: "images/blog/pic.jpg"`).

---
*Happy Contributing!*
