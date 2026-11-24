# Chemist Working Hub

Teaching hub for **Chemistry 2 (EC025)**, Semester 2, Session 26/27.
Nurulfarhana Khamis, Chemistry Unit.

The site has four pages:

- **Home**: greeting, semester reaction profile, today's classes, this week's lessons and what's coming up.
- **Scheme of Work**: the 18-week SOW, colour-coded by lecture, tutorial and practical, with past weeks greyed out, the current and next week highlighted, and public holiday reminders.
- **Timetable**: weekly teaching timetable, one colour per class, with the Tuesday 4:00pm consultation hour.
- **Notes & To-do**: private task list (Urgent, Important, Less urgent, No rush) and quick notes.

It is a plain static website: `index.html` holds everything, so there is nothing to install or build.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole website |
| `favicon.svg` | The small icon shown in the browser tab |
| `render.yaml` | Settings Render reads to host the site |
| `README.md` | This guide |

---

## Step 1: Put the files on GitHub

1. Sign in at [github.com](https://github.com) (create a free account if needed).
2. Click **+** (top right) → **New repository**.
3. Name it `chemist-working-hub`, choose **Public**, and click **Create repository**.
4. On the new repository page, click **uploading an existing file**
   (or **Add file → Upload files**).
5. Unzip the download, open the `chemist-working-hub` folder, select all four files, and drag them into the upload box.
   The files must sit at the top level of the repository, not inside another folder.
6. Click **Commit changes**.

## Step 2: Publish it on Render

1. Go to [render.com](https://render.com) and sign in with your GitHub account.
2. Click **New** → **Static Site**.
3. Connect GitHub if asked, then pick the `chemist-working-hub` repository.
4. Fill in:
   - **Name**: `chemist-working-hub`
   - **Branch**: `main`
   - **Build Command**: `echo "No build step needed"` (or leave blank if Render allows it)
   - **Publish Directory**: `.` (a single full stop)
5. Click **Create Static Site**.

After a minute or so the site goes live at an address like
`https://chemist-working-hub.onrender.com` (Render shows the exact link at the top of the page).

**Alternative:** instead of **Static Site**, choose **New → Blueprint** and pick the repository.
Render reads `render.yaml` and fills in the settings for you.

Static sites are free on Render. Every time you change a file on GitHub, Render updates the live site automatically.

---

## Updating the content

Open `index.html` on GitHub, click the pencil icon (**Edit this file**), make the change, then click **Commit changes**. The live site updates within a minute or two.

Use **Ctrl + F** (or **Cmd + F** on Mac) in the GitHub editor to find these sections:

| To change | Search for | Example line |
|---|---|---|
| Scheme of Work weeks | `const WEEKS` | `{w:2, s:"2026-11-23", e:"2026-11-27", L:{t:"3.0 Electrochemistry",h:1}, ...}` |
| Semester breaks | `const BREAKS` | `{name:"Mid semester break", s:"2027-02-06", e:"2027-02-14", after:11, ...}` |
| Public holidays | `const HOLIDAYS` | `{d:"2027-01-22", name:"Thaipusam"},` |
| Timetable | `const SESSIONS` | `{d:2, s:16, e:17, consult:true},` (d = day, 1 Mon to 5 Fri; s/e = start/end hour, 24-hour clock) |
| Class colours | `--b2:` | `--b2:#BFDBFE; --b2d:#1D4ED8;` (light fill, then darker edge) |

Dates are written as `YYYY-MM-DD`. When Johor announces a special holiday, add a line to `const HOLIDAYS`, for example:

```js
{d:"2027-03-29", name:"Special state holiday"},
```

**Preview another date:** add `?now=2027-01-21T10:00` to the end of the site address (before any `#`) to see how the site looks on that day and time, for example
`https://chemist-working-hub.onrender.com/?now=2027-01-21T10:00#sow`.

---

## Good to know

- **Public site.** Anyone with the link can see the Scheme of Work and timetable, and the daily greeting says "Good morning, Farhana".
- **Notes and to-dos stay private.** They are saved only in the browser where you type them, so other visitors never see them. Because of that, they do not move between devices by themselves.
  - Use **Download backup** on the Notes & To-do page to save a copy.
  - Use **Restore backup** on another device or browser to load it there.
  - Clearing your browser's data deletes the saved list, so download a backup now and then.
- **Daily voice briefing.** The first visit each day reads out the greeting and that day's classes using the device's built-in voice.
  - Browsers only allow sound after the first tap or key press on a page. If the page opens silently, the briefing starts at your first tap.
  - The voice sounds different on Windows, Mac, Android and iPhone.
- **Times follow Malaysia time** (UTC+8), whatever time zone the device is set to.
