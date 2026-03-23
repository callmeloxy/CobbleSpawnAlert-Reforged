# Changelog

## 1.2.1

### Summary
This update improves onboarding and overall mod readability with a `/csar help` command and a lightweight welcome message shown when a player joins.

### Added
- Added the `/csar help` command
- Added a translatable help page for the main commands
- Added alerts, sounds, UI, actions, and links sections to the help page
- Added clickable links in the help page for Discord, GitHub, and BH
- Added a small welcome message shown when a player joins
- Added a clickable `/csar help` shortcut in the welcome message
- Added clickable Discord, GitHub, and BH links in the welcome message

### Improved
- Improved command accessibility for new players
- Improved onboarding with a short and useful welcome message
- Improved overall readability with a centralized help entry point
- Improved Discord link clarity with an explicit `Discord FR Only` hover text
- Improved BisectHosting link presentation with a short and discreet `BH` format

### Notes
- The welcome message is designed as lightweight join-time information
- Discord is labeled as `FR Only`
- BH uses the public short link selected for in-game display

## 1.2.0

### Summary
This update adds a player-based capture indicator system, with per-player rendering in the Pokémon info UI and in legacy / hybrid alerts.

### Added
- Added a player-based capture indicator system
- Added a small Poké Ball icon in the custom Pokémon info UI when the viewed player has already captured the species
- Added a green checkmark indicator in legacy / hybrid alert messages when the receiving player has already captured the species
- Added hover text on the chat capture indicator for better readability

### Changed
- Capture state is now resolved individually for each player instead of relying on shared spawn UI data
- Legacy alert messages are now built per player when capture state is needed
- Radiant alert text now displays only the Radiant symbol instead of combining Shiny and Radiant symbols
- Kept the 1.1.0 visual release decision for Radiant UI rendering:
  - Radiant keeps its Radiant text identity
  - Radiant continues to use shiny-image fallback in the UI

### Notes
- Capture detection currently checks species-level caught state only
- Form-specific or variant-specific caught-state logic is not part of this version

## 1.1.0

### Summary
This update introduces a full Pokémon info UI system for spawn alerts, with configurable display modes, 2D Pokémon images, and quick access actions.

### Fixed
- Fixed HYBRID mode so Shiny and Radiant symbols are preserved correctly in legacy-style alerts
- Fixed several UI layout / interaction polish issues during the 1.1.0 implementation process
- Fixed Pokémon image routing so base / shiny / radiant variants resolve correctly

### Added
- Added a custom Pokémon info UI for spawn alerts
- Added three UI display modes:
  - `LEGACY_ONLY`
  - `UI_ONLY`
  - `HYBRID`
- Added clickable UI opening from spawn alerts depending on selected mode
- Added 2D Pokémon image support in the info UI
- Added UI actions:
  - Dex
  - Glow
  - TP Player
  - TP Pos
- Added top-right close button to the info UI
- Added configurable UI content options for:
  - image
  - category
  - variant
  - level
  - biome
  - nearest player
  - coordinates
  - IVs
  - IV total
  - EV yield
  - nature
  - ability
  - gender
- Added configurable UI action button options
- Added UI management commands:
  - `/csar ui`
  - `/csar ui status`
  - `/csar ui on`
  - `/csar ui off`
  - `/csar ui toggle`
  - `/csar ui mode legacy_only`
  - `/csar ui mode ui_only`
  - `/csar ui mode hybrid`

### Improved
- Improved spawn alert readability by moving detailed Pokémon information into a dedicated UI
- Improved overall user experience for viewing spawn details
- Improved FR / EN rendering consistency in the Pokémon info UI
- Improved image coverage for Pokémon shown in the UI
- Improved handling of Shiny / Radiant / Alpha labels in the UI

## 1.0.3

### Summary
Targeted hotfix to fix multilingual display issues in the Discord webhook.

### Fixed
- Fixed biome display in the Discord webhook when using French mode
- Fixed Pokémon category translation in the Discord webhook
- Fixed Discord webhook language mode handling for:
  - `EN_ONLY`
  - `FR_ONLY`
  - `EN_AND_FR`
  - `FR_AND_EN`

### Improved
- Added a dedicated biome name resolver for cleaner and easier-to-maintain biome handling
- Improved consistency between Pokémon names, categories, and biome names in the Discord webhook
- Improved overall reliability of the Discord webhook multilingual rendering

## 1.0.2

### Summary
This update improves alert customization, adds alert previews and configurable anti-spam, and brings major polish to the Discord webhook integration.

### Fixed
- Fixed false spawn alerts triggered by already owned Pokémon being sent out by players
- Fixed Shiny / Radiant alert logic depending on player settings
- Fixed multiple command feedback messages
- Fixed handling of some special Pokémon names in previews and Discord webhooks
- Improved GG command behavior for plain text messages, slash commands, empty templates, per-player limits, and wrong-dimension checks

### Added
- Added alert reset commands
- Added per-player sound settings
- Added sound commands and per-category / per-variant sound controls
- Added an alert preview system
- Added configurable anti-spam for spawn alerts
- Added anti-spam config options:
  - `antiSpam.enabled`
  - `antiSpam.cooldownSeconds`

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
