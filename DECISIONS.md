# Decisions

## 2026-06-04

- Game concept: baby-themed Roblox obby starring Asher.
- Avatar customizer: simple name, skin tone, and outfit color.
- Obstacle failure behavior: respawn at last checkpoint.
- Coins: required for finishing; required count is 10.
- Marketplace assets: prepare both Avatar Marketplace / UGC candidates and Creator Store model versions.
- Baby bundle: include baby body plus matching accessories.
- Persistence: maintain this companion git workspace plus `ReplicatedStorage/ProjectNotes` inside the Roblox place.
- GitHub: target is a new public personal `github.com` repo, pushed early once `gh auth login -h github.com` is complete and the `owner/repo` is provided.
- GitHub repo created and pushed: https://github.com/hohojoy666/ashers-big-adventure
- Persistence lesson: Roblox scripts must be created with `multi_edit` (not `execute_luau`) or they are lost on reload. Save the place (Ctrl+S) to persist to disk.

## 2026-06-13

- First flagship sellable UGC asset: `AsherSuperMilkBottle_Back`, a mesh-based Back accessory staged in Studio at `Workspace.MarketplaceAssets.MilkBottle.UGC`.
- The accessory uses a low-poly generated Super Milk Bottle mesh (`rbxassetid://138465822038126`) and texture (`rbxassetid://85992883196584`), scaled to about 2.35 studs tall with a `BodyBackAttachment`.
- The first smoother mesh failed Roblox avatar validation because its mesh resolution was 5440, above the 4000 maximum; the upload candidate was replaced with a lower-poly handle, `Massless=false`, and no custom Attributes.

## 2026-06-04 (cohesion + fall fix)

- Cohesion + falling: themed the `Baseplate` into soft grass so the whole level shares one ground, and replaced the narrow nursery `Walkway` with a flush `Porch` slab so there are no side gaps between the nursery doorway and the StartPad.
- Fall recovery: added a standalone `ServerScriptService/SafetyRespawn` Script that tracks the last checkpoint each player touched and teleports them back (or to the StartPad) when they hit the ground. Validated in Play mode: falling from bare ground returned to StartPad, and after touching Checkpoint1 it returned to Checkpoint1.
- IMPORTANT FINDING: the currently open place is a Studio auto-recovery snapshot in which the core scripts (`GameServer`, `ClientController`, `Config`, `ProjectNotes`) are EMPTY; only `Workspace.Pacifier.LaunchScript` retained code. The git repo never stored the Luau source, so these scripts cannot be restored from the repo. Recommend reopening the real saved place (or restoring/rebuilding those scripts) — without them, customization, coins, obstacles, and the finish gate do not run. `SafetyRespawn` was written to be self-contained for this reason.
- Finish was invisible and inert (the `SuperMilkBottleFinish` trigger had `Transparency = 1` and its win logic lived in the empty GameServer). Added visible finish decor (`Level.Finish.FinishDecor`: glowing pad, pink arch, FINISH banner; trigger now faintly visible) and a standalone `ServerScriptService/FinishLine` script that shows a "You Win!" screen + victory sound on touch. Validated in Play mode: walking into the bottle created `PlayerGui.WinScreen`. The 10-coin requirement is omitted for now because coin tallying needs GameServer.
