# Assets

## In-Place Asset Packages

Saleable candidates are organized in Roblox Studio under `Workspace/MarketplaceAssets`.

### Milk Bottle

- `MilkBottle/UGC`: `AsherMilkBottleAccessory_UGCReady`, a wearable accessory candidate with a `Handle` and `RightGripAttachment`.
- `MilkBottle/CreatorStore`: `AsherMilkBottle_Model_CreatorStoreReady`, a clean model for other creators.

### Baby Bundle

- `BabyBundle/UGC`: baby body parts plus accessory candidates for pacifier, bonnet, and bib.
- `BabyBundle/CreatorStore`: `AsherBabyBundle_ModelPack_CreatorStoreReady`, a model pack for developers.

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
- `generate_mesh` failed during this implementation with: `Model generation should only be called from the server`. Primitive upload-ready assets were created instead.
