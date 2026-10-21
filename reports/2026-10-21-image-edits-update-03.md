# 2026-10-21: Scott's image edits (update-03)

Builder task LBX_BUILDER_TASK_03.

## In plain words

Scott's picture changes are live. Some pictures were taken out of three galleries, the home page's couples section was swapped and moved, and the event art page has two new banners and new smaller pieces. Every count the PM asked for matches. No broken pictures, no sideways scrolling, on a big screen or a phone. Nothing went wrong.

## Step 1. Identity checks

All passed. No mismatch.

| Check | What I saw |
|---|---|
| Next commit's author (site repo) | ArchipelagoInternationalInc, studio address |
| Next commit's author (machine-wide) | ArchipelagoInternationalInc, studio address (same address in lower case) |
| Authors of every commit in the site repo | ArchipelagoInternationalInc, studio address, for all of them, including this task's two |
| GitHub login used to push | ArchipelagoInternationalInc |
| Site repo | `ArchipelagoInternationalInc/livingbrushexperience`, private |
| Reports notebook | `ArchipelagoInternationalInc/livingbrushexperience-corpus`, public |
| Vercel "created by" (deployment list, including this update's) | archipelagointernationalinc only |
| Before starting | Site repo and notebook clean. Local and GitHub at the same commit (`bbef9b1`) |

One small hiccup: my first Vercel check used a saved login that had expired and returned nothing. Checking through the Vercel command-line tool (which refreshes its login) worked and gave the result above. This was not an identity problem.

## Step 2. What changed

`update-03.zip` held the 21 pages and 10 new picture files. After unpacking, the only differences from the live site were:

- **10 added picture files:** five new pictures, each with a full-size version (`img/`) and a thumbnail (`img/t/`), exactly the ten the task named. All are real JPEG files and none replaced an existing file. (Their file names are in the private site repo's commit; some contain private first names, so they are not listed in this public notebook.)
- **6 changed pages:** `index.html`, `bodypainting.html`, `couples-bodypainting.html`, `tata-painting.html`, `event-art.html`, `gallery.html`. Each changed by 2 to 12 lines.
- **15 pages unchanged:** byte-for-byte identical to the live versions, so the commit doesn't include them.
- **Nothing deleted.** Pictures no longer used stay in the repo, as instructed.

Visible text that changed (picture captions and descriptions, plus the one moved section), page by page:

- Bodypainting, couples, Ta-Ta: only the captions and descriptions of removed pictures went. No other wording changed.
- Event art: captions and descriptions added for the new wedding and birthday banners, and one existing description lengthened ("framed with irises").
- Gallery: the same removals and additions as the program pages, since the gallery shows all programs.
- Home: the "Couples, painted as one" section moved to come right after "Painted into paradise". Its wording is unchanged. Its picture was swapped for a single front-and-back picture with a new caption, and one slideshow picture was swapped.

Every picture any page refers to exists in the repo (checked across all 21 pages before committing).

## Step 3. Commit

- **`3cecfb3`, "Scott's image edits: removals, home swap, new event art".** 16 files: the 6 pages plus the 10 pictures. Pushed to `main`. Vercel published it about 30 seconds later, created by the studio account.

## Step 4. Live checks

Method: a brand-new, empty headless Chrome profile (the same as a private window), driven over Chrome's DevTools connection, at 1920 × 1080 and at phone size, 390 × 844. On each page, every picture was forced to load and then checked for errors. All results below are from the live site, and they are identical at both widths.

| Check | Expected | Measured |
|---|---|---|
| Ta-Ta Painting gallery | 6 | **6** |
| Couples gallery | 5 | **5** |
| Bodypainting gallery | 11 | **11** |
| Event art, full-width banners | 5: three posters, then wedding, then birthday | **5, in that order**, each exactly the full width of its area (1508 px on the big screen, 358 px on the phone) |
| Event art, smaller pieces after the banners | 5 | **5**, after the banners |
| Home slideshow | 3 pictures | **3** |
| "Painted into paradise" | white band | **White band** (pure white background) |
| "Couples, painted as one" | black band, one picture, after "Painted into paradise" | **Dark band, 1 picture, directly after it** |
| Broken pictures | none | **None** on any of the 5 pages, at either width (11 to 46 pictures per page, all loaded) |
| The 10 new files, fetched directly | load | **All 10** returned OK, as JPEG images |
| Sideways scrolling | none | **None** on any page, at either width |

Each program page also has one large picture at the top, separate from its gallery. That's why the page totals are one higher than the gallery counts (7, 6 and 12).

Screenshots are in the private site repo under `artifacts/screenshots/2026-10-21-update-03/` (commit `37f2e05`). They are full-page shots of the 5 checked pages, at 1920 and 390 wide: 10 files. I looked at the event art and home shots: the banner order and the white then black bands match the numbers. In the full-page shots, the site's top bar appears partway down the image. That's a known side effect of how full-page captures handle a bar that stays pinned while scrolling; on the live site it is at the top.

## What did not go as written

Nothing.

## Commits in this task (site repo, both by the studio identity)

| Commit | What |
|---|---|
| `3cecfb3` | Scott's image edits: removals, home swap, new event art |
| `37f2e05` | Add update-03 check screenshots |
