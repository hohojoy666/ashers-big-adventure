# Asher's Big Adventure

## Project Brief

Asher's Big Adventure is a baby-themed Roblox obby starring a baby named Asher. Players customize a baby avatar with a name, skin tone, and onesie color, then traverse a coin-filled level with baby-themed hazards. The player must collect enough coins to claim the Super Milk Bottle at the finish.

## Roblox Studio MCP Workflow

- Active Studio place: `Asher's Big Adventure`.
- Before changing the place, verify the active Studio instance with `list_roblox_studios` and `set_active_studio` if needed.
- Use `execute_luau` for world building, instance setup, and one-shot Studio automation.
- ALWAYS create and edit scripts (Script, LocalScript, ModuleScript) with `multi_edit`. Scripts created via `execute_luau` do NOT persist and are lost on reload.
- After building, verify with `search_game_tree`, then tell the user to save the place (Ctrl+S) to persist changes to disk.
- Use `start_stop_play`, `get_console_output`, and `screen_capture` for verification.

## Core Game Rules

- Avatar customizer scope is simple: baby name, skin tone, and onesie/outfit color.
- Obstacles send players back to their last checkpoint.
- Coins are required: `REQUIRED_COINS = 10`.
- Keep the experience bright, gentle, and baby-themed.
- Marketplace publishing cannot be done through MCP. Assets can be prepared in Studio, but upload, pricing, moderation, and UGC bundle assembly must happen in Roblox Studio / Creator Dashboard.

## Naming

- Place runtime folders under `Workspace/Level`.
- Place saleable asset packages under `Workspace/MarketplaceAssets`.
- Keep persistent context mirrored in `ReplicatedStorage/ProjectNotes`.
