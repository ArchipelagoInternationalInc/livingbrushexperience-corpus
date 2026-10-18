# 2026-10-17: Pages back in sync with the generator, and the Programs panel stays on screen

Builder task LBX_BUILDER_TASK_02.

## In plain words

The PM's regenerated pages are live. They carry the same big-screen fix I had made by hand, now coming from the page generator, so future updates won't lose it. They also fix the Programs drop-down, which used to poke off the left edge of the screen. Nothing else on the pages changed. All checks passed. The Brevo key step was skipped, because Scott has not said a newer key is saved.

## Step 1. Identity checks

All passed. No mismatch.

| Check | What I saw |
|---|---|
| Next commit's author (site repo) | ArchipelagoInternationalInc, studio address |
| Next commit's author (machine-wide) | ArchipelagoInternationalInc, studio address (same address in lower case) |
| Authors of all commits in the site repo, including this task's two | ArchipelagoInternationalInc, studio address |
| GitHub login used to push | ArchipelagoInternationalInc |
| Site repo | `ArchipelagoInternationalInc/livingbrushexperience`, private |
| Reports notebook | `ArchipelagoInternationalInc/livingbrushexperience-corpus`, public |
| Vercel "created by" (last 20 deployments, including this one) | archipelagointernationalinc only |
| Before starting | Site repo clean, local and GitHub at the same commit (`b7b107c`) |

## Step 2. Differences from `6fb327c` (checked before committing)

`update-02.zip` replaced the same 21 pages. Compared with `6fb327c` on every page: 12 lines added, 4 removed. Every changed line is a style rule. **No page text, image, link or other markup changed.**

What differs, on every page:

1. **The same zoom fix, written differently.** Before, my fix edited the original rules in place. Now the original rules are back as they were, and short override rules come after them, with the comment "full-screen sizes undo the page zoom". The overrides cover the full-size picture viewer (width and height), the picture inside it (height limit), the phone menu (height limit), and the home page photo strip (left padding and scroll padding). Each divides by the zoom level.
2. **The zoom rules themselves are unchanged.** All 7 size steps still set the zoom level variable, and the numbers match on every page.
3. **One new rule:** the Programs panel starts under its button instead of centering on it, with the comment "start under the button so it never runs off the left edge".

I also checked that every override comes after the rule it overrides on all 21 pages. In a style sheet the later rule wins, so wrong order would silently undo the fix. Order is correct on all 21. This matches what the PM described; nothing else differed, so there was no reason to stop.

## Step 3. Commit

- **`ddce464`, "Regenerated pages: zoom fix in generator, Programs panel inside the screen".** Pushed to `main`. Vercel published it (deployment ready, created by the studio account). Confirmed live by fetching the page and finding the new Programs rule.
- **Changed files (21):** about.html, blacklight-bodypainting.html, bodypainting-workshops.html, bodypainting.html, couples-bodypainting.html, event-art.html, facepainting.html, fairy-hair.html, gallery.html, hosting.html, index.html, landscape-fantasy.html, live-model.html, live-painting.html, living-canvas.html, masterwork-portrait.html, performance.html, press.html, promotional-bodypainting.html, roller-skates.html, tata-painting.html.

## Step 4. Live checks

Method: a brand-new, empty headless Chrome profile (the same as a private window), driven over Chrome's DevTools connection. The page width is set directly, which also works at phone width, where an ordinary headless window would be cropped. Every number below was measured on the live site, after the deploy.

| Check | Result |
|---|---|
| **1600 wide**, Programs panel | Opens, all 17 programs. **Left edge 465 px, right edge 1518 px** of 1600. Fully on screen. No sideways scrolling. Before this update: left edge at −14 px |
| **1920 wide**, Programs panel | Opens, all 17 programs. **Left edge 564 px, right edge 1808 px** of 1920. Fully on screen. No sideways scrolling. Before: −2 px |
| **2560 wide**, full-size picture viewer | **Viewer 2560 × 1440, exactly the screen.** Picture spans 816 to 1744 across and 122 to 1298 down. Its center is at 1280, the exact middle of the screen, and it is fully inside the screen |
| **390 wide** (phone) | Zoom 1, so the phone layout is unchanged. No sideways scrolling. The phone menu opens with all 23 links, stops 10 px above the bottom of the screen, and scrolls. The gallery's picture viewer is 390 × 844, with the picture centered and fully inside |

Screenshots are in the private site repo, under `artifacts/screenshots/2026-10-17-update-02/` (commit `bbef9b1`): programs-open-1600.png, programs-open-1920.png, home-2560.png, viewer-2560.png, home-390.png, menu-open-390.png, viewer-390.png. I looked at each one, and each matches its measurement.

## Step 5. Brevo key: skipped

Scott has not said he has saved a new key in Doppler, so per the task this step was not done. Nothing about the key was touched.

Current state, for the PM: the key made earlier tonight is in Doppler and Vercel, works, and its contact-form test was delivered (previous report). The open item is the one already flagged: that key was briefly visible in a screenshot in the working chat, so it should be replaced. When Scott confirms a replacement is saved, the Builder will copy it to Vercel (Production and Preview), redeploy, send one test, confirm delivery in Brevo's log, and then tell Scott he can switch the old key off.

## What did not go as written

Nothing. Two small notes:
- The task asked for the old Programs-panel edges only as "report its left and right edges". The before-numbers (−14 px at 1600, −2 px at 1920) come from the previous report's measurements and are included only for comparison.
- The home page picture differs between screenshots. That is expected: the picture is a slideshow that crossfades on a timer. The comparison in step 2 confirms no images or markup changed.

## Commits in this task (site repo, both by the studio identity)

| Commit | What |
|---|---|
| `ddce464` | Regenerated pages: zoom fix in generator, Programs panel inside the screen |
| `bbef9b1` | Add update-02 check screenshots |
