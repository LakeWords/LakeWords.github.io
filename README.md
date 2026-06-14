# LakeWords Developer Guide

This README is a practical guide for getting set up and working in this repository.

## 1) What this repo is

This is a static website project.

- Main site files live in `docs/`
- HTML pages are in folders like `docs/contact/` and `docs/events/`
- CSS/JS/images usually live under `docs/assets/`

Because this is static, most edits are plain HTML/CSS/JS file changes.

## 2) Tools you need

These tools are already installed on this machine. If you set up a new machine later, install:

- [Cursor](https://www.cursor.com/)
- [Git](https://git-scm.com/)
- Xcode Command Line Tools (macOS): `xcode-select --install`
- A GitHub account

Check your install in terminal:

```bash
git --version
```

## 3) Open and explore in Cursor

1. Open Cursor.
2. Open this folder (`LakeWords.github.io`).
3. In the file tree, open `docs/`.
4. Click around pages and assets to get familiar with structure.

Tips for working efficiently:

- Use Cursor's **Source Control** tab for most git actions.
- Keep the browser open side-by-side to preview changes.
- Save files often (`Cmd+S`).

## 4) First-time setup (clone the repo)

If you have not cloned yet:

```bash
git clone <https://github.com/LakeWords/LakeWords.github.io.git>
cd LakeWords.github.io
```

If you already have the repo locally:

```bash
cd /path/to/LakeWords.github.io
git pull
```

## 5) Preview the site locally

**Simplest:** open `docs/index.html` in Chrome (or any browser). The site is static HTML, CSS, and JS with relative paths, so navigation, styles, and images work from the file system.

**Optional — local HTTP server:** only if you want URLs to look like production (`http://` instead of `file://`) or you are debugging something that behaves differently over `file://` (for example, form `fetch()` to external APIs). From the repo root:

```bash
cd docs
python3 -m http.server 8000
```

Then open `http://localhost:8000/` (keep the terminal running; stop with `Ctrl+C`). If port 8000 is busy, pick another port, e.g. `python3 -m http.server 8001`.

## 6) Basic day-to-day workflow

Use this loop every time you work:

1. In bottom-left branch menu, switch to `main`.
2. Open **Source Control** (`Cmd+Shift+G`) and click **Sync/Pull** to get latest.
3. Create a new branch from branch menu: `your-name/short-feature-name`.
4. Make a small change and save.
5. Preview in the browser (open `docs/index.html`, or use the optional local server from section 5).
6. In **Source Control**, review changed files and stage with `+`.
7. Enter commit message and click **Commit**.
8. Click **Publish Branch** (first push) or **Sync Changes**.
9. Open pull request on GitHub.

Terminal fallback (if needed):

```bash
git checkout main
git pull
git checkout -b your-name/short-feature-name
git add .
git commit -m "Update homepage hero text"
git push -u origin your-name/short-feature-name
```

## 7) GUI-first git actions (and command equivalents)

- **Check file changes** in Source Control  
  Equivalent: `git status`

- **Pull latest changes** with Sync/Pull  
  Equivalent: `git pull`

- **Create/switch branch** from bottom-left branch picker  
  Equivalent: `git checkout -b <branch-name>`

- **Stage files** with `+` in Source Control  
  Equivalent: `git add <file>` or `git add .`

- **Commit** using the message box + Commit button  
  Equivalent: `git commit -m "message"`

- **Publish/Push** with Publish Branch or Sync Changes  
  Equivalent: `git push`

If you want commit history, use Timeline/Source Control UI or:
`git log --oneline`

## 8) How to work with Cursor + AI safely

Cursor can speed you up a lot. Use it in small steps:

1. Ask for one change at a time.
2. Review every file diff before accepting.
3. Run local preview after each change.
4. Commit only when the site still looks correct.

Good prompt examples:

- "Update the button style in `docs/assets/site.css` to match the heading color."
- "Add a new section to `docs/index.html` under the newsletter block."
- "Refactor this repeated HTML into cleaner structure without changing visuals."

## 9) Editing habits that prevent mistakes

- Make small commits instead of one giant commit.
- Write commit messages that describe intent.
- Do not edit many unrelated files in one PR.
- Refresh browser after every saved change.
- If something breaks, use git history to backtrack.

## 10) Common issues

- **I changed code but browser looks the same**  
  Hard refresh (`Cmd+Shift+R`) and confirm you are previewing the right file or URL.

- **My branch says behind main**  
  Switch to `main`, pull, then update your branch.

- **I committed to main by mistake**  
  Stop and ask for help before pushing.

- **I do not understand a file**  
  Ask Cursor to explain the file section before editing it.

## 11) Suggested first tasks

- Fix typo on a page
- Change spacing/font size in one section
- Update a button label
- Add one new content block to an existing page

Use small, focused changes and iterate.

## 12) Quick cheat sheet

GUI-first flow in Cursor:

1. Branch picker -> switch to `main`
2. Source Control -> **Sync/Pull**
3. Branch picker -> create branch
4. Edit files and save
5. Source Control -> stage (`+`) -> commit
6. **Publish Branch** / **Sync Changes**
7. Open PR on GitHub

Terminal fallback:

```bash
# from repo root
git status
git pull
git checkout -b your-name/task-name

# after edits (preview by opening docs/index.html in a browser)
git add .
git commit -m "Describe what changed"
git push -u origin your-name/task-name
```
