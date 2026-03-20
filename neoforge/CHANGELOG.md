# Changelog

## 1.0.2

### Summary
NeoForge 1.0.2 update bringing the main feature set of the Fabric 1.0.2 version to NeoForge.

### Added
- Added expanded alert commands:
  - `/csar alerts`
  - /csar alerts status
  - /csar alerts on
  - /csar alerts off
  - /csar alerts toggle
- Added category alert management:
  - /csar alerts category
  - /csar alerts category status
  - /csar alerts category reset
  - /csar alerts category <type> on/off/toggle
- Added variant alert management:
  - /csar alerts variant
  - /csar alerts variant status
  - /csar alerts variant reset
  - /csar alerts variant <type> on/off/toggle
- Added player reset options for global, category, and variant alert settings
- Added persistent per-player alert preferences
- Added sound commands:
  - /csar sound
  - /csar sound status
  - /csar sound on
  - /csar sound off
  - /csar sound toggle
- Added category sound management:
  - /csar sound category
  - /csar sound category status
  - /csar sound category reset
  - /csar sound category <type> on/off/toggle
- Added variant sound management:
  - /csar sound variant
  - /csar sound variant status
  - /csar sound variant reset
  - /csar sound variant <type> on/off/toggle
- Added preview commands:
  - /csar alerts preview category <type>
  - /csar alerts preview variant <type>
- Added configurable spawn alert anti-spam based on:
  - same species
  - same chunk
  - same dimension
- Added improved per-player sound handling for alerts

### Improved
- Improved player setting persistence with cleaner JSON save/load handling
- Improved alert and sound status displays with clearer ON/OFF sections
- Improved category and variant filtering logic
- Improved GG click handling and execution flow
- Improved translatable text coverage for command feedback and messages
- Improved Pokémon name resolution for FR / EN displays
- Improved Discord webhook formatting and readability
- Improved Discord webhook support for FR / EN / EN+FR / FR+EN layouts
- Improved overall NeoForge feature parity with the Fabric 1.0.2 version

### Notes
- This update brings the main 1.0.2 command, settings, preview, anti-spam, translation, and webhook improvements to NeoForge.

## 1.0.1

### Summary
First public NeoForge release of CobbleSpawnAlert Reforged.

### Added
- First public NeoForge release of CobbleSpawnAlert Reforged
- Spawn alerts for important Cobblemon Pokémon
- Capture notifications
- Clickable chat actions
- Rare category support:
  - Legendary
  - Mythical
  - Ultra Beast
  - Paradox
  - Starter
- Alpha, Shiny, and Radiant support
- Teleport helper actions
- Category-based glow actions
- Discord webhook support
- Configurable sounds and display options
- FR / EN localization support

### Improved
- Ported the mod to NeoForge
- Commands adapted for NeoForge
- Clean translatable text system for in-game messages
- Stable enum-based category handling
- Cleaner internal handling for spawn and capture messages
- Tested with Cobblemon 1.6.1 and 1.7.3

### Removed
- Removed the legacy raw message template system
