# Managing Categories, New, and Updated Tags

The public website reads the repo folder structure automatically — you never need to edit `index.html` for any of this. Everything below is done by adding/removing files in the repo, the same way you already drop files into `New Models/` or `Updated Models/`.

## How an asset gets its category

Every asset in `Assets/` gets a category two possible ways:

1. **Explicit (what this repo now uses for every asset)** — a copy of the asset's `.fbx` sits inside `All Models/<CategoryName>/`. Whatever category folder it's in, that's the category shown on the site. This always wins.
2. **Automatic guess (fallback only)** — if an asset has no matching file anywhere under `All Models/`, the site guesses a category from keywords in the filename (baked into the site code). Anything that doesn't match a keyword lands in "Misc."

Since every current asset already has an explicit `All Models/` entry, the automatic guess never actually kicks in anymore — but it's still there as a safety net if you ever forget to add one.

## To set or change an asset's category

1. Go to the `All Models/` folder in the repo.
2. If the category you want doesn't exist yet, just create a new folder for it (any name — it becomes a filter button on the site automatically).
3. Add a copy of the asset's `.fbx` file into that folder. **The file's content doesn't matter — only the filename.** You can literally re-upload the exact same `.fbx` you already put in `Assets/`.
4. To move an asset to a different category, delete its old copy from the old `All Models/<Name>/` folder and add a copy to the new one.
5. To remove a category entirely, delete its folder — any assets in it fall back to the automatic keyword guess (usually "Misc").

That's it — no code changes, ever.

## Current categories (as of this writing)

- Electronics — Computer Tower, Flashlight
- Explosives — Hand Bomb
- Garden — Watering Can
- Misc — Abstract Zeus Sculpture, Red Pen, Trash Can
- Nature — Dead Pine Tree, Pine Tree, Tree Rounded
- Sports — Baseball Bat, Bowling Ball, Bowling Pin
- Tools — Crowbar, Hammer Claw, Screwdriver, Wrench
- Vehicles — Airplane
- Weapons — Fire Axe, Molotov, Sword 1 (Shortsword), Sword 2 (Katana)

## New / Updated tags work the same way

- Drop a copy of an asset's `.fbx` into `New Models/` to flag it as a brand-new release. Remove it once it's no longer the current week's drop.
- Drop a copy into `Updated Models/` instead if it's an older/migrated asset that got re-exported or improved, rather than something brand new.
- Same rule as above: only the filename matters, not the content.

## Top-level folder map

- `Assets/` — the actual downloadable `.fbx` files.
- `Icons/` — render/thumbnail images shown on the site.
- `New Models/` — markers for this week's brand-new asset(s).
- `Updated Models/` — markers for migrated/re-exported older assets.
- `All Models/` — category markers, one subfolder per category.
- `Devlogs/` — one `.txt` file per devlog post, shown on the site newest first.

## Adding a devlog post

1. Create a text file in `Devlogs/` named `YYYY-MM-DD Title.txt`, for example `2026-09-27 Lantern.txt`. The date in the filename becomes the post date, and the rest becomes the title.
2. Put just the post text inside (no title line needed). `**bold**` and plain links work.
3. Commit it. The post appears on the site automatically, and deleting the file removes it.
