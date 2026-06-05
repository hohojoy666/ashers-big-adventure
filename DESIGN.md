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

## Level Beats

1. Player spawns on the customization pad.
2. Player enters baby name and chooses skin/onesie colors.
3. Player starts the obby and collects coins.
4. Checkpoints save progress.
5. Spinning Sleep Drum and Bubble Bath send the player back to the last checkpoint.
6. Super Milk Bottle finish checks for 10 coins.
