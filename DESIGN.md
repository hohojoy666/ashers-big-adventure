# Design

## Game

`Asher's Big Adventure` is a baby-themed obby. The player customizes a baby avatar, collects coins, avoids baby obstacles, and wins by reaching the Super Milk Bottle after collecting enough coins.

## Current Scope

- Customizer: name, skin tone, outfit/onesie color.
- Obstacles: respawn at the last checkpoint.
- Coins: required to finish.
- Required coin count: 10.
- Total placed coins: 18.
- Level shape: single linear path with checkpoints.

## Runtime Structure

- `ReplicatedStorage/Config`: shared tunables.
- `ReplicatedStorage/Remotes`: `Customize`, `CoinCollected`, `Finished`, `Message`, `ObstacleHit`.
- `ServerScriptService/GameServer`: customization, checkpoint tracking, coin tallying, obstacle respawn, finish gate.
- `StarterPlayerScripts/ClientController`: customizer UI, HUD, sleep/fade effect, win/need-more-coins messages.
- `Workspace/Level`: platforms, checkpoints, coins, obstacles, finish.
- `Workspace/NurseryBase`: themed home-base lobby room around the customization spawn (floor, pastel walls, doorway, flush `Porch` slab to the StartPad, rug, window, crib, signage).
- `Workspace/Baseplate`: themed soft-grass ground that the whole level sits on; doubles as the fall-recovery surface.
- `ServerScriptService/SafetyRespawn`: standalone fall recovery. Tracks the last checkpoint each player touched and teleports them back there (or the StartPad) whenever they hit the ground. Works without GameServer; remove if GameServer's own respawn is restored.

## Level Beats

1. Player spawns in the Nursery Base room on the customization pad.
2. Player enters baby name and chooses skin/onesie colors.
3. Player heads through the "To the Adventure" doorway and starts the obby, collecting coins.
4. Checkpoints save progress.
5. Spinning Sleep Drum and Bubble Bath send the player back to the last checkpoint.
6. Super Milk Bottle finish: framed by a FINISH arch/banner and a glowing pad. Reaching it shows a "You Win!" celebration screen. (The original 10-coin gate lives in GameServer; the standalone `FinishLine` script celebrates on arrival because coin tallying is unavailable while GameServer is empty.)

## Standalone Scripts (added while GameServer is empty)

- `ServerScriptService/SafetyRespawn`: checkpoint tracking + fall recovery.
- `ServerScriptService/FinishLine`: shows the win celebration when a player touches `SuperMilkBottleFinish`. Builds a `WinScreen` ScreenGui in the player's PlayerGui and plays a victory sound. Remove/merge if GameServer's coin-gated finish is restored.
