# 2026-10-25: New photos, face art and a burlesque video (update-05)

Builder task LBX_BUILDER_TASK_05 (final).

## In plain words

The new photos and the video are live. The About us and Performance pages have new top pictures. Facepainting, Live painting and Performance have new pictures at the start of their galleries. The home page's "At sea" strip opens with Madelyn dancing in white lace. The Performance page has a new video of Madelyn on stage at sea, which plays with sound and starts in under a second. Every check passed on a big screen and a phone, with no broken pictures and no sideways scrolling.

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
| Vercel "created by" (deployment list, including this update's) | the studio account only |
| Before starting | Site repo and notebook clean. Local and GitHub at the same commit (`d670171`) |

**Did update-04 run? Yes,** on 2026-10-21 (commit `6bb8fe9`, report filed that day). This update carries the same rule, and it was already in place, so nothing was skipped or doubled.

## Step 2. What changed

The zip held 45 files. After unpacking:

- **21 pages changed. 24 files added:** 22 picture files (11 new pictures, each full size and thumbnail), plus 1 video and its cover picture in a new `vid/` folder.
- **Nothing else changed, and nothing was deleted.** None of the added files replaced an existing one, and every picture and video any page refers to exists.
- **Page text:** the only visible text changes are captions and descriptions for the new pictures, and the new video section on the Performance page (heading "Madelyn on stage at sea", one sentence, and the player). Two top pictures were swapped (About us and Performance), so the old top pictures' descriptions changed with them. The old Performance top picture is still in that page's gallery, and no gallery lost a picture. No other wording changed on any page.
- **Every page also gained 3 identical style lines.** They lay out the video section and are shared by all pages, which is why all 21 changed and not only the ones with new pictures.
- **The video file:** 5.9 MB, 40 seconds, portrait shape (720 × 1280), with both picture and sound. It is arranged to start playing before it has fully downloaded. The page loads nothing from it until someone presses play, so it doesn't slow the page down. The site serves it as a proper video and supports skipping ahead.

## Step 3. Commit

- **`cd17e7c`, "New photos, face art and burlesque video".** 45 files: 21 changed and 24 added. Pushed to `main`. Live about 25 seconds later, deployment created by the studio account.

## Step 4. Live checks

Method: a brand-new, empty headless Chrome profile (the same as a private window), driven over Chrome's DevTools connection, at 1920 × 1080 and at phone size, 390 × 844. Every result below is identical at both widths.

| Check | Result |
|---|---|
| About us, top picture | **Scott and Madelyn in performance dress in front of the event backdrop aboard ship** ✔ |
| Performance, top picture | **Madelyn in jeweled face art** ✔ |
| Performance, gallery | Starts with 5 new pictures (burlesque, dancing in the lounge, two "white lace night" pictures, balloon costume night), then all 11 earlier pictures. 16 in total ✔ |
| Facepainting, gallery | **Starts with the three new face-art pictures** (jewels and face art, a masquerade mask on a guest, silver masks with two guests), then the existing ones ✔ |
| Live painting, gallery | **1. Scott and Madelyn (new), 2. the toucan banner (Scott and Madelyn painting three toucans), 3 to 5. three new pictures of Madelyn with portraits** ✔ |
| Home "At sea" strip | **First: Madelyn dancing in white lace in the lounge.** The second white-lace picture is 9th of 12 ✔ |
| Home "Couples, painted as one" | **Whole picture shown**, its own shape: 681 × 673 on the big screen, 358 × 354 on the phone ✔ |
| Broken pictures | **None** on About us, Performance, Facepainting, Live painting, Home or the Gallery page (16 to 122 pictures per page, all loaded) ✔ |
| Sideways scrolling | **None** on any of those pages, at either width ✔ |

The caption on the toucan picture reads "Scott and Madelyn painting together". Its description names the three toucans, which is how I confirmed it's the toucan banner.

**Video ("Madelyn on stage at sea"):**

| | 1920 wide | 390 wide |
|---|---|---|
| File size | 5.9 MB | 5.9 MB |
| Start time (press play to moving picture) | **0.68 s** | **0.58 s** |
| Playing 4 seconds later | yes, at about 3.7 s into the video | yes, at about 3.9 s |
| Sound | **on**: not muted, volume full, sound data being played | **on**, same |
| Length | 39.9 s | 39.9 s |

How the video was tested, honestly: the check clicked the middle of the video, then gave the player its play command, the same as pressing its play button. Start time is measured from that click. A headless browser has no speakers, so "with sound" means the player was unmuted at full volume and was actually decoding the video's sound while playing. Nobody listened to it.

Screenshots: 16 files in the private site repo under `artifacts/screenshots/2026-10-25-update-05/` (commit `45ce2f3`). At both widths: the About us top, the Performance top, gallery and video, the Facepainting gallery, the Live painting gallery, the home "At sea" strip, and the home couples picture.

## What did not go as written

1. **The zip wasn't there at first.** The first look found no `update-05.zip` on this Mac. Scott saved it into the deploy folder, then the task went ahead. The Desktop folder has also been renamed since earlier tasks (two dashes now start its name). The brief's old folder name doesn't exist any more, but it's the same folder.
2. **Two screenshots retaken.** The first About-us and Performance top screenshots caught the page mid-scroll (the site scrolls smoothly). I made the scroll instant and retook all of them. The measurements were unaffected.
3. On a big screen, the Live painting gallery is laid out in columns that fill top to bottom. So the toucan banner appears under the first picture, not beside it. The order is as specified; this is how that gallery has always laid out.

## Commits in this task (site repo, both by the studio identity)

| Commit | What |
|---|---|
| `cd17e7c` | New photos, face art and burlesque video |
| `45ce2f3` | Add update-05 check screenshots |
