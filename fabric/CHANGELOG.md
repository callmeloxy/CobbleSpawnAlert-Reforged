# Changelog

## 1.0.2

### Summary
This update improves alert customization, adds alert previews and configurable anti-spam, and brings major polish to the Discord webhook integration.

### Added
- Added alert reset commands
- Added per-player sound settings
- Added sound commands and per-category / per-variant sound controls
- Added an alert preview system
- Added configurable anti-spam for spawn alerts
- Added anti-spam config options:
  - `antiSpam.enabled`
  - `antiSpam.cooldownSeconds`

### Fixed
- Fixed false spawn alerts triggered by already owned Pokémon being sent out by players
- Fixed Shiny / Radiant alert logic depending on player settings
- Fixed multiple command feedback messages
- Fixed handling of some special Pokémon names in previews and Discord webhooks
- Improved GG command behavior for plain text messages, slash commands, empty templates, per-player limits, and wrong-dimension checks

### Improved
- Improved per-player alert preferences
- Improved per-player sound preferences
- Improved status command rendering
- Improved command suggestions for category and variant types
- Improved persistence of player settings
- Improved Discord webhook rendering and structure
- Improved bilingual EN / FR Discord webhook display
- Improved Discord embed readability
- Improved translation and translatable texts
- Improved internal command structure and alert logic

## 1.0.1

### Summary
This update fixes false alerts from player-owned Pokémon, adds per-player alert toggles, and introduces a clickable `(Shiny)` label for shiny Pokémon without a rare category.

### Fixed
- Fixed false spawn alerts triggered by already owned Pokémon being sent out
- Fixed player-owned Pokémon being treated as wild spawn alerts

### Added
- Added per-player alert toggles
- Added per-type alert toggles for:
  - Legendary
  - Mythical
  - Ultra Beast
  - Paradox
  - Starter
  - Alpha
  - Shiny
  - Radiant
- Added alert status command
- Added persistent player alert preferences
- Added clickable `(Shiny)` label for shiny Pokémon without a rare category
- Added clearer alert command structure with:
  - `/csar alerts category ...`
  - `/csar alerts variant ...`
- Added command suggestions for category and variant alert types

### Improved
- Improved alert filtering logic for multi-tag spawns
- Improved player customization of alert visibility
- Improved overall reliability of spawn detection
- Radiant now properly takes priority over Shiny for alert filtering

## 1.0.0

### Summary
Initial release of CobbleSpawnAlert Reforged.

### Added
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
- Clean translatable text system for in-game messages
- Stable enum-based category handling
- Cleaner internal handling for spawn and capture messages

### Removed
- Removed the legacy raw message template system
