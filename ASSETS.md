# Assets

## In-Place Asset Packages

Saleable candidates are organized in Roblox Studio under `Workspace/MarketplaceAssets`.

### Milk Bottle

- `MilkBottle/UGC`: `AsherSuperMilkBottle_Back`, a mesh-based Back accessory candidate with a `Handle` MeshPart, `BodyBackAttachment`, `MeshId = rbxassetid://138465822038126`, and `TextureID = rbxassetid://85992883196584`. A legacy primitive candidate, `AsherMilkBottleAccessory_UGCReady`, is still kept in the same folder.
- `MilkBottle/CreatorStore`: `AsherMilkBottle_Model_CreatorStoreReady`, a clean model for other creators.

### Baby Bundle

- `BabyBundle/UGC`: baby body parts plus accessory candidates for pacifier, bonnet, and bib.
- `BabyBundle/CreatorStore`: `AsherBabyBundle_ModelPack_CreatorStoreReady`, a model pack for developers.

### Classic Clothing (2D)

- `assets/asher_tshirt_512.png`: upload-ready classic T-shirt graphic (square 512x512), a caped "super milk bottle" mascot with an "ASHER" banner on a pastel mint background. Suggested name: "Asher Super Milk Bottle Tee".
- `assets/asher_tshirt.png`: original generated art (1536x1024) kept as the source.
- Note: classic T-shirts display on classic/blocky avatar bodies only (front torso). Upload via Creator Hub > Marketplace > T-Shirt; listing costs a Robux fee and requires moderation. The MCP cannot perform the upload.

## Publishing Checklist

1. Open Studio's Asset Manager.
2. Inspect each candidate package and verify scale, orientation, attachments, and naming.
3. Upload Creator Store models as model assets.
4. For Avatar Marketplace / UGC items, upload through the Avatar item flow in Studio / Creator Dashboard.
5. Configure thumbnail, description, price, and sale settings in Creator Dashboard.
6. Submit for Roblox moderation.

## Important Limits

- The MCP cannot publish, price, moderate, or list assets for sale.
- Avatar Marketplace publishing requires UGC eligibility and Roblox account requirements.
- A true avatar bundle is assembled in Creator Dashboard from uploaded body/accessory parts.
- Mesh generation works in Studio edit mode. Do not run asset generation or accessory assembly while the place is in Play mode; Play-mode changes are temporary and generator calls may fail.
