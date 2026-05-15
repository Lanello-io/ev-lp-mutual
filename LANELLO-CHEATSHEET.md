# Lanello — Landing Page Editing Cheat Sheet

Plain-English daily guide for editing client landing pages.
Written for the **Mutual Electric** repo; the same steps work for any Lanello client repo.

---

## Where things live
- Your projects folder: `~/Documents/Lanello`
- This client's project: `~/Documents/Lanello/ev-lp-mutual`
- The main file you edit: `index.html`

---

## 1. Start a work session (every time)

Open the **Terminal** app, then run these one at a time (copy–paste each line, press Enter):

```
cd ~/Documents/Lanello/ev-lp-mutual
```
Moves you into the project folder. (`cd` = "change directory".)

```
git pull
```
Downloads the latest version from GitHub first, in case your developer changed
something. **Always do this before editing** so you don't work on an old copy.

```
claude
```
Starts a Claude Code session inside the project. Now you can ask Claude to make
copy/layout changes, preview them, and push them. To leave Claude, type `/exit`.

---

## 2. Preview before you save

Ask Claude to open the page, or run it yourself:

```
open index.html
```
Opens the page in your browser so you can see how it looks before saving.

---

## 3. Save your changes & upload to GitHub

When you're happy with the edits, run these three, one at a time:

```
git add -A
```
"Put all my changed files in the envelope." (Stages every change.)

```
git commit -m "Short note about what you changed"
```
Saves a snapshot on your Mac. Replace the quoted text with a real description,
e.g. `git commit -m "Updated hero headline and phone number"`.

```
git push
```
Uploads your saved snapshot to GitHub.

---

## 4. IMPORTANT — make the change actually go live

**Pushing to GitHub does NOT update the client's live website.**

The live Mutual Electric site is hosted on **Hostinger**. After you push, you must:

1. Log in to **Hostinger** → the Mutual Electric site → **File Manager**.
2. Upload the changed file(s) (usually `index.html`) into the site's folder,
   replacing the old version.
3. Hard-refresh the live site (**Cmd + Shift + R**) to confirm it updated.

> **GitHub = your backup & version history.
> Hostinger = the actual live website.
> BOTH steps are needed every time.**

---

## Troubleshooting

- **`git push` says "Permission denied" or "403"**
  Your GitHub account doesn't have Write access to this repo yet.
  Send your developer this message:
  > "Please give my GitHub account `Hinkam-Lanello` **Write** access to
  > `Lanello-io/ev-lp-mutual` — add it as a collaborator with Write permission,
  > or to a Lanello-io team that has write access."

- **`git pull` mentions a "conflict" or "local changes"**
  Don't force anything. Start `claude` and say: "git pull gave me a conflict."

- **You see `.DS_Store` in `git status`**
  Harmless macOS junk file. Safe to ignore.

- **Anything looks scary or unexpected**
  Stop. Don't run delete/reset/force commands. Start `claude` and describe
  exactly what you see. Your history on GitHub is safe — almost everything
  is recoverable.

---

## The whole loop, at a glance

```
cd ~/Documents/Lanello/ev-lp-mutual
git pull
claude
#   ...make edits, preview with:  open index.html  ...
git add -A
git commit -m "what you changed"
git push
#   ...then upload the changed file(s) to Hostinger File Manager for the client
```
