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

## 4. Going live is now AUTOMATIC

**For this repo (`ev-lp-mutual` → `ev.mutualelectricnw.com`): pushing to GitHub
auto-publishes to the live site in ~30 seconds. No manual Hostinger upload.**

Hostinger is connected to this repo via Git auto-deploy, scoped **only** to the
`ev.mutualelectricnw.com` site — it cannot touch the main WordPress site at
`mutualelectricnw.com`. So the moment you `git push`, the change goes live.

After pushing, wait ~30s and hard-refresh the live page (**Cmd + Shift + R**).

> Set up & verified 2026-05-16. NOTE: other Lanello client sites are not
> auto-deployed yet — those still need their own setup before "push = live"
> applies to them.

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
#   ...that's it. Auto-deploys to ev.mutualelectricnw.com in ~30s. Hard-refresh to see it.
```
