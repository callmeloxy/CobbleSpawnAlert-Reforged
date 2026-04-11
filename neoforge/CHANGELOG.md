# Changelog

## 2.0.0

### Summary
CSAR now includes optional Cobblemon Mass Outbreaks support on NeoForge, with outbreak announcements integrated into the normal CSAR flow across chat, UI, teleport actions, and Discord webhook output.

### Fixed
- Fixed the NeoForge outbreak compat hook so outbreak announcements now trigger correctly.
- Fixed NeoForge outbreak UI opening from the alert flow.
- Fixed outbreak teleport actions on NeoForge.
- Fixed outbreak webhook flow on NeoForge.
- Fixed multiple NeoForge translation mismatches so outbreak texts and related messages are aligned with the Fabric 2.0.0 wording.
- Fixed `/csar reload` output on NeoForge so it matches the expected prefixed message style.

### Added
- Added optional compatibility with Cobblemon Mass Outbreaks on NeoForge.
- Added automatic ingame announcements for new outbreaks.
- Added outbreak support for the Pokémon info UI.
- Added outbreak support for teleporting to the nearest player.
- Added outbreak support for teleporting to outbreak coordinates.
- Added outbreak support for Discord webhook announcements.
- Added outbreak message support for biome, world, nearest player, and position display.
- Added configurable `massOutbreaks` server settings for chat and Discord behavior.

### Changed
- Changed NeoForge outbreak handling to follow the normal CSAR announcement flow instead of using a separate disconnected system.
- Changed outbreak announcements to respect the configured language display order in the same way as the main CSAR webhook flow.
- Changed NeoForge text resources so key messages now match the intended Fabric 2.0.0 phrasing more closely.

### Improved
- Improved NeoForge parity with the Fabric 2.0.0 outbreak implementation.
- Improved consistency between ingame alerts, UI interactions, and Discord webhook output for outbreaks.
- Improved optional compatibility behavior so CSAR continues to work correctly even when Cobblemon Mass Outbreaks is not installed.

### Notes
- Cobblemon Mass Outbreaks support is optional and has no impact when the mod is not installed.
- This update focuses on integrating outbreak announcements into the existing CSAR experience on NeoForge rather than creating a separate alert system.
- Outbreak alerts support UI and teleport actions, but do not include glow behavior.

## 1.4.1

### Summary
This NeoForge 1.4.1 update fixes a server startup issue and restores a more complete and structured `/csar help` output in-game.

### Fixed
- Fixed a NeoForge server startup issue.
- Fixed `/csar help` on NeoForge so it no longer shows only the reduced help index.
- Fixed the in-game help output to restore the detailed sections for alerts, sounds, UI, actions, and links.

### Improved
- Improved the readability of `/csar help` on NeoForge.
- Improved consistency between the NeoForge help output and the expected Fabric behavior.

### Notes
- This is a small NeoForge bugfix and parity update focused on server stability and help command behavior.

## 1.4.0

### Summary
This update adds a unified in-game config hub for Main, Pokemon, and Server settings. It replaces the old separated config screens with a single consistent UI flow and integrates Teleport, Commands, and Discord Webhook settings into the same hub.

### Fixed
- Fixed multiple inconsistencies between the old config screens and the new unified hub flow.
- Fixed the server config save pipeline in the in-game UI.
- Fixed `Fallback Teleport` integration in the server snapshot and save flow.
- Fixed FR / EN translation support issues in the active config UI.
- Fixed payload / snapshot alignment issues in the unified config system.

### Added
- Added `/csar config`.
- Added a unified in-game config hub.
- Added left sidebar navigation with collapsible `Main`, `Pokemon`, and `Server` groups.
- Added Main sections directly inside the hub: `Alerts`, `Display`, `Sounds`, `Pokemon Click`, `GG`, `Glow`, `Anti-Spam`, and `Pokemon Info UI`.
- Added `Pokemon > Default`, `Server > Teleport`, `Server > Commands`, and `Server > Discord Webhook` inside the unified hub.

### Changed
- Changed the config workflow from multiple separated screens to one unified hub.
- Changed navigation to use grouped sidebar sections instead of isolated config pages.
- Changed the in-game config editing flow to keep Main, Pokemon, and Server settings inside one consistent UI structure.

### Improved
- Improved readability and consistency across the full in-game config UI.
- Improved feature parity between config sections.
- Improved the long-term maintainability of the config screen structure.

### Notes
- This update is focused on the new unified config hub and the 1.4.0 UI / config workflow.

## 1.0.2

### Summary
NeoForge 1.0.2 update bringing the main feature set of the Fabric 1.0.2 version to NeoForge.

### Added
- Added expanded alert commands:
  - `/csar alerts`
  - `/csar alerts status`
  - `/csar alerts on`
  - `/csar alerts off`
  - `/csar alerts toggle`
- Added category alert management:
  - `/csar alerts category`
  - `/csar alerts category status`
  - `/csar alerts category reset`
  - `/csar alerts category <type> on/off/toggle`
- Added variant alert management:
  - `/csar alerts variant`
  - `/csar alerts variant status`
  - `/csar alerts variant reset`
  - `/csar alerts variant <type> on/off/toggle`
- Added player reset options for global, category, and variant alert settings
- Added persistent per-player alert preferences
- Added sound commands:
  - `/csar sound`
  - `/csar sound status`
  - `/csar sound on`
  - `/csar sound off`
  - `/csar sound toggle`
- Added category sound management:
  - `/csar sound category`
  - `/csar sound category status`
  - `/csar sound category reset`
  - `/csar sound category <type> on/off/toggle`
- Added variant sound management:
  - `/csar sound variant`
  - `/csar sound variant status`
  - `/csar sound variant reset`
  - `/csar sound variant <type> on/off/toggle`
- Added preview commands:
  - `/csar alerts preview category <type>`
  - `/csar alerts preview variant <type>`
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
- Added the first public NeoForge release of CobbleSpawnAlert Reforged.
- Added spawn alerts for important Cobblemon Pokémon.
- Added capture notifications.
- Added clickable chat actions.
- Added rare category support:
  - Legendary
  - Mythical
  - Ultra Beast
  - Paradox
  - Starter
- Added Alpha, Shiny, and Radiant support.
- Added teleport helper actions.
- Added category-based glow actions.
- Added Discord webhook support.
- Added configurable sounds and display options.
- Added FR / EN localization support.

### Improved
- Improved the port to NeoForge.
- Improved command support for NeoForge.
- Improved the translatable text system for in-game messages.
- Improved enum-based category handling.
- Improved internal handling for spawn and capture messages.
- Improved compatibility testing with Cobblemon 1.6.1 and 1.7.3.

### Removed
- Removed the legacy raw message template system.
