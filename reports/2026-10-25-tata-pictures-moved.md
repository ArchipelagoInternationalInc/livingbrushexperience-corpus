# 2026-10-25: Madelyn's Ta-Ta pictures moved out of Live painting

A direct request from Scott in the Builder chat, made after update-05. **There was no PM brief for this.** The PM's page generator needs the same change; see the end of this report.

## In plain words

Scott pointed out that four pictures added to the Live painting gallery in update-05 are Ta-Ta Painting pictures. They now appear only in Madelyn's Ta-Ta Painting gallery. One of the four turned out to be a second copy of a picture the Ta-Ta gallery already had, so it shows once, not twice.

## What Scott asked, and what was decided

- Scott asked to move "the 4 Madelyn Ta-Ta paint photos" just added to Live painting into the Ta-Ta gallery only.
- Update-05 added only three pictures of Madelyn with portraits to Live painting. Before changing anything, I asked Scott which picture was the fourth. **Scott confirmed it is the photo of Scott and Madelyn in front of the event backdrop.**

## Identity

Unchanged from this morning's update-05 checks, and re-checked before committing: commits by ArchipelagoInternationalInc with the studio address, GitHub login ArchipelagoInternationalInc, and Vercel deployments created by the studio account.

## What changed

Three pages; no picture files were added or deleted:

| Page | Before | After |
|---|---|---|
| Live painting, gallery | 16 pictures | **12**: the four removed |
| Ta-Ta Painting, gallery | 6 pictures | **9**: three new pictures first, then the original six |
| Gallery page, "Ta-Ta Painting" filter | 6 | **9** |
| Gallery page, "Live painting and murals" filter | 16 | **12** |
| Gallery page, all work | 122 | **121** (one duplicate removed, see below) |

- **Duplicate removed.** One of the four moved pictures, "Live portrait at sea", is pixel-for-pixel the same photo as one the Ta-Ta gallery already had (Madelyn beside a finished portrait), saved under a different file name. After the move it showed twice on the Ta-Ta page. The extra copy was dropped from the Ta-Ta page and the Gallery page, and the original stays. Its file is still in the repo (nothing deleted); no page uses it.
- I checked the other three moved pictures against every Ta-Ta picture. None is a duplicate.
- **Captions and descriptions were not changed.** Apart from moving and de-duplicating those picture entries, the three pages are identical to before (checked by comparing each page with those entries taken out).
- **Not changed: the About us top picture.** It is the same photo of Scott and Madelyn in front of the backdrop. It is a page picture, not a gallery entry, so it stays unless Scott says otherwise.

## Commits (site repo, by the studio identity)

| Commit | What |
|---|---|
| `b16465a` | Move Madelyn's four Ta-Ta pictures from Live painting to the Ta-Ta gallery |
| `e56b525` | Ta-Ta gallery: drop a duplicate copy of an existing picture |
| `935adf0` | Add Ta-Ta move check screenshots |

## Live checks

A fresh, empty headless Chrome profile at 1920 and 390 wide, after the final commit. Results are identical at both widths.

- Live painting gallery: **12** pictures, none of the moved ones.
- Ta-Ta Painting gallery: **9** pictures, starting with the three moved ones, each photo appearing once (checked in the screenshot).
- Gallery page: the Ta-Ta filter shows **9**, including the three; the Live painting filter shows **12**, with none of them.
- No broken pictures and no sideways scrolling on any of the three pages.

Screenshots: `artifacts/screenshots/2026-10-25-tata-move/` in the private site repo.

## For the PM: generator change needed

This change was made by hand on the live pages, the same way `6fb327c` was. **If the pages are regenerated, the generator must include it**, or the next update will put these pictures back in Live painting and bring back the duplicate. In the generator:
1. Remove the three Madelyn-with-portrait pictures and the Scott-and-Madelyn backdrop photo from the Live painting gallery.
2. Add the Scott-and-Madelyn backdrop photo and the two non-duplicate portrait pictures (Madelyn hanging a portrait in the atrium; Madelyn with the blonde portrait) to the start of the Ta-Ta Painting gallery, tagged for the Ta-Ta filter on the Gallery page.
3. Leave out "Live portrait at sea" entirely; the Ta-Ta gallery already has the same photo.

The exact entries are in the site repo's commits `b16465a` and `e56b525`.
