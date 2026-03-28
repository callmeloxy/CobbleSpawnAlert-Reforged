# Changelog

## 1.4.2

### Summary
This update is a small bug-fix / polish release focused on improving the in-game UI presentation and fixing `/csar help` on Fabric.

### Fixed
- Fixed `/csar help` on Fabric so the `Actions` section now properly includes:
  - `/csar glow <spawnId>`
  - `/csar tp <spawnId>`
  - `/csar tpplayer <spawnId>`
- Fixed the unified config hub background so it no longer applies the heavy dark fullscreen overlay

### Changed
- Changed the unified config hub rendering to keep the world more visible behind the UI
- Changed the Fabric help output so it now matches the expected action commands more closely

### Improved
- Improved readability of the unified config UI by removing the overly dark background veil
- Improved overall visual clarity of the in-game config hub
- Improved consistency between Fabric and NeoForge for `/csar help`

### Notes
- This update is focused on polish and small bug fixes
- No new major features were added in this release

## 1.4.1

### Summary
This update is a small bug-fix / polish release focused on improving the readability of the `/csar sound` status output.

### Fixed
- Fixed the `/csar sound` status flow so it no longer feels split into multiple repeated menus

### Changed
- Changed `/csar sound`
- Changed `/csar sound status`
- Both commands now show the full sound status in a single structured menu with:
  - Global sound status
  - Category sound status
  - Variant sound status

### Improved
- Improved readability of the sound status output
- Improved consistency of the sound settings menu
- Improved overall polish of the command feedback for sound settings

### Notes
- The detailed category and variant sound commands are still available
- This update is focused on polish rather than new major features

## 1.4.0

### Summary
This update adds a unified in-game config hub for Main, Pokemon, and Server settings. It replaces the old separated config screens with a single consistent UI flow and integrates Teleport, Commands, and Discord Webhook settings directly into the same hub.

### Fixed
- Fixed multiple inconsistencies between the old config screens and the new unified hub flow
- Fixed the server config save pipeline in the in-game UI
- Fixed `Fallback Teleport` integration in the server snapshot and save flow
- Fixed visual inconsistencies between Main, Pokemon, and Server config sections
- Fixed and cleaned up FR / EN translation support for the active config UI
- Fixed payload / snapshot alignment issues in the unified config system

### Added
- Added `/csar config`
- Added a unified in-game config hub
- Added left sidebar navigation with collapsible groups:
  - `Main`
  - `Pokemon`
  - `Server`
- Added Main sections directly inside the hub:
  - `Alerts`
  - `Display`
  - `Sounds`
  - `Pokemon Click`
  - `GG`
  - `Glow`
  - `Anti-Spam`
  - `Pokemon Info UI`
- Added `Pokemon > Default` directly inside the hub
- Added `Server > Teleport` directly inside the hub
- Added `Server > Commands` directly inside the hub
- Added `Server > Discord Webhook` directly inside the hub
- Added internal groups for `Server > Teleport`:
  - `General`
  - `Coords Teleport`
  - `Air Safety`
  - `Anti-Spam`
  - `Target / Loading`
  - `Permissions`
  - `Fallback Teleport`
- Added full server snapshot support for:
  - `Teleport`
  - `Commands`
  - `Discord Webhook`
  - `Fallback Teleport`

### Changed
- Changed the in-game config flow to use one unified hub instead of multiple disconnected config screens
- Changed `Main`, `Pokemon`, and `Server` config pages to share the same shell, navigation model, and footer actions
- Changed the active config UI to rely on translatable text for FR / EN support
- Changed the server config workflow so Teleport, Commands, and Discord Webhook are edited from the same UI system

### Improved
- Improved overall UI consistency across the in-game config system
- Improved navigation with a single shared sidebar and section structure
- Improved readability with consistent accordions and grouped sections
- Improved config save / reset flow with clearer modified / saved state feedback
- Improved maintainability by consolidating the main editable config surfaces into one system
- Improved translation coverage for the unified config hub

### Removed
- Removed old legacy config screens that were no longer part of the main flow:
  - `MainConfigUiScreen.java`
  - `PokemonConfigUiScreen.java`
  - `ServerTeleportConfigUiScreen.java`
  - `ConfigPlaceholderScreen.java`

### Notes
- `Pokemon > Overrides` remains intentionally deferred to a future dedicated editor
- This update focuses on unifying and stabilizing the in-game config experience rather than adding new gameplay features

## 1.3.0

### Summary
This update adds full 3D Pokémon rendering support to the custom spawn info UI, while keeping the existing 2D sprite mode available as an alternative. It also introduces render mode commands, improves UI rendering behavior across different Pokémon shapes, and fixes false despawn messages after captures.

### Fixed
- Fixed false despawn messages appearing after a Pokémon was captured
- Fixed capture cleanup flow so captured Pokémon are marked and removed correctly before optional follow-up logic
- Fixed UI render mode switching so both 2D and 3D modes work correctly from config and commands
- Fixed several 3D render edge cases across different Pokémon sizes and shapes
- Fixed shiny and radiant 3D rendering validation issues during testing

### Added
- Added 3D Pokémon rendering support in the custom info UI
- Added UI render modes:
  - `SPRITE_2D`
  - `MODEL_3D`
- Added `renderMode` to the UI config
- Added `/csar ui rendermode status`
- Added `/csar ui rendermode sprite_2d`
- Added `/csar ui rendermode model_3d`
- Added help entry for UI render mode in `/csar help`
- Added render profile support for different Pokémon shapes:
  - `COMPACT`
  - `STANDARD`
  - `WIDE`
  - `LONG`
- Added separate generated config comment helper files:
  - `CONFIG_COMMENTS_EN.txt`
  - `CONFIG_COMMENTS_FR.txt`

### Changed
- Changed the custom Pokémon info UI so it can display either a 2D sprite or a 3D model
- Changed UI rendering flow to support profile-based 3D framing instead of a single generic setup
- Changed config generation to keep the main config focused on real settings while moving extra explanations into separate helper files
- Changed despawn handling so capture-related unloads are processed more safely

### Improved
- Improved 3D framing and readability for different Pokémon body types
- Improved rendering support for compact, standard, wide, and long Pokémon silhouettes
- Improved static 3D portrait presentation in the UI with a clean transparent background
- Improved render mode usability by exposing it through commands and config
- Improved overall UI flexibility by keeping 2D and 3D available side by side
- Improved capture and despawn interaction reliability

### Notes
- `MODEL_3D` is intended as the new advanced UI render option
- `SPRITE_2D` remains available as a simpler alternative or fallback
- This update focuses on UI rendering and stability, not on replacing the legacy alert system

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
- Improved the clean translatable text system for in-game messages
- Improved stable enum-based category handling
- Improved cleaner internal handling for spawn and capture messages

### Removed
- Removed the legacy raw message template system
