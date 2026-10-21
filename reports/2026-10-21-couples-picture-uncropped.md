# 2026-10-21: The couples picture on the home page, uncropped (update-04)

Builder task LBX_BUILDER_TASK_04.

## In plain words

The couples picture on the home page now shows whole: both figures and the full caption at the bottom, with nothing cut off the sides. Before, about a fifth of its width was trimmed away. "Painted into paradise" looks exactly as it did, down to the pixel. Nothing went wrong.

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
| Before starting | Site repo and notebook clean. Local and GitHub at the same commit (`37f2e05`) |

## Step 2. Comparison with the live files

`update-04.zip` held the 21 pages and no pictures. Result: **exactly as expected.**

- All 21 pages differ from the live versions by **one added line and nothing removed**.
- That line is the same on every page, and it is the last thing in the page's style block: `.collage.solo .big{aspect-ratio:auto}.collage.solo .big img{height:auto;object-fit:contain}`.
- Apart from that line, every page is byte-for-byte identical to the live version, so page text, links and pictures did not change.

The rule only affects home-page sections that show one single picture. There are two: "Painted into paradise" and "Couples, painted as one". The two other picture sections on the home page (sponsors, and "Painter, host and showgirl") use several pictures and are not affected.

## Step 3. Commit

- **`6bb8fe9`, "Home: single pictures keep their own shape".** 21 pages, one line added to each. Pushed to `main`. Live about 15 seconds later (checked by fetching the page). Deployment created by the studio account.

## Step 4. Live checks

Method: a brand-new, empty headless Chrome profile (the same as a private window), driven over Chrome's DevTools connection, at 1920 × 1080 and at phone size, 390 × 844. Both pictures were measured on the live site **before** the update and again **after** it, so "looks the same" is a measurement, not an impression.

**Couples, painted as one** (the picture is almost square: 760 × 751)

| Width | Before: shown size | Before | After: shown size | After |
|---|---|---|---|---|
| 1920 | 681 × 852 | Cropped: forced into a tall box, about 21% of its width cut off the sides | **681 × 673** | **Whole picture, its own shape, nothing cut** |
| 390 | 358 × 448 | Cropped, as above | **358 × 354** | **Whole picture, its own shape, nothing cut** |

In the screenshots, both figures and all three lines of the caption at the bottom of the picture are visible at both widths, with the side edges intact.

**Painted into paradise** (a wide picture: 760 × 479)

| Width | Before | After |
|---|---|---|
| 1920 | 681 × 429, whole picture | **681 × 429, whole picture: identical** |
| 390 | 358 × 226, whole picture | **358 × 226, whole picture: identical** |

**Sideways scrolling:** none, at either width.

Screenshots are in the private site repo under `artifacts/screenshots/2026-10-21-update-04/` (commit `d670171`): couples-1920.png, couples-390.png, paradise-1920.png, paradise-390.png.

## What did not go as written

Nothing on the site. One thing in my own checking: the first set of "couples" screenshots caught the page mid-scroll (the site scrolls smoothly) and showed the paradise section instead. I changed the screenshot step to jump instantly to the picture and took them again. The measurements were not affected; they don't depend on scrolling.

## Commits in this task (site repo, both by the studio identity)

| Commit | What |
|---|---|
| `6bb8fe9` | Home: single pictures keep their own shape |
| `d670171` | Add update-04 check screenshots |
