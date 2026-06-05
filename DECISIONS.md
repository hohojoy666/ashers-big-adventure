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
