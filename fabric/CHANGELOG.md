# Changelog

## 2.7.0

### Summary

This update improves CSAR integrations by making Raid Dens and CobbleSafari alerts clickable, adding UI support for both systems, improving Discord webhook behavior, and exposing several missing configuration options in the in-game config UI.

### Fixed

- Fixed Raid Dens UI and teleport actions expiring too quickly while the raid was still active
- Fixed Raid Dens compatibility being forced back to enabled when saving the server config UI
- Fixed missing UI exposure for the world-load chat message setting
- Fixed missing UI exposure for Mass Outbreak Discord webhook display settings
- Fixed CobbleSafari click targets so the alert tag and destination open the UI while informational text remains non-clickable
- Fixed personal Pokémon alert preferences incorrectly being able to trigger global Discord webhooks

### Added

- Added clickable Raid Dens alerts
- Added CSAR UI support for Raid Dens alerts
- Added clickable CobbleSafari alerts
- Added CSAR UI support for CobbleSafari alerts
- Added UI access from Raid Dens alert components
- Added UI access from CobbleSafari alert components
- Added `main.alert.sameDimensionOnly` to the in-game config UI as an alert reception option
- Added `main.messages.showWorldLoadChatMessage` to the in-game config UI
- Added `server.raidDens.enabled` to the in-game config UI
- Added Mass Outbreak Discord webhook display options to the in-game config UI
- Added configurable Mass Outbreak Discord webhook fields for:
  - position
  - world
  - biome
  - nearest player

### Changed

- Changed Raid Dens alerts so they now behave more consistently with classic CSAR alerts
- Changed CobbleSafari alerts so they now behave more consistently with classic CSAR alerts
- Changed Raid Dens and CobbleSafari teleport behavior so they now use the same anti-spam logic as classic CSAR alerts
- Changed Pokémon alerts triggered only by a player's personal `/csar config` preferences so they no longer send global Discord webhooks
- Changed global server alerts from `/csar server` and classic category alerts so they continue to send Discord webhooks when enabled
- Changed `main.sameDimensionOnly` so it is now stored in the alert section as `main.alert.sameDimensionOnly`
- Changed config migration so existing `main.sameDimensionOnly` values are moved automatically to the new alert config location

### Improved

- Improved Raid Den coordinates so they are now clickable and can be used for position teleportation
- Improved the nearest player entry in Raid Den alerts so it is now clickable and can be used for player teleportation
- Improved the Raid Dens UI so it now displays useful raid information, including:
  - Pokémon
  - level
  - difficulty
  - biome
  - nearest player
  - coordinates
- Improved the Raid Dens UI so it now supports `TP Pos` and `TP Player` actions
- Improved Raid Dens registry duration so UI and teleport actions remain valid for the expected raid lifetime
- Improved CobbleSafari destination names so they are now clickable and can open the CSAR UI
- Improved CobbleSafari `[Safari]` alert tags so they are now clickable and can open the CSAR UI
- Improved CobbleSafari coordinates so they are now clickable and can be used for position teleportation
- Improved the nearest player entry in CobbleSafari alerts so it is now clickable and can be used for player teleportation
- Improved the CobbleSafari UI so it now displays useful portal information, including:
  - destination
  - world
  - nearest player
  - coordinates
- Improved the CobbleSafari UI so it now supports `TP Pos` and `TP Player` actions
- Improved CobbleSafari registry duration to prevent UI and teleport actions from expiring too quickly
- Improved separation between alert reception settings and teleport restriction settings in the config UI
- Improved consistency between classic Pokémon alerts, Mass Outbreak alerts, Raid Dens alerts, and CobbleSafari alerts

### Notes

- Raid Dens and CobbleSafari keep the same teleport anti-spam behavior as classic CSAR alerts
- A single alert cannot be used to chain multiple teleport actions
- Glow actions are not added to Raid Dens or CobbleSafari because they are not suitable for these alert types
- CobbleSafari informational text is intentionally not clickable to keep alert interactions clear

## 2.6.1

### Summary

This update improves the Raid Dens and CobbleSafari integrations by making their alerts clickable and compatible with the CSAR UI system.

### Added

- Added clickable Raid Dens alerts
- Added CSAR UI support for Raid Dens alerts
- Added clickable CobbleSafari alerts
- Added CSAR UI support for CobbleSafari alerts

### Improved

- Improved Raid Dens alerts so they can now open a dedicated CSAR UI view
- Improved Raid Den coordinates so they are now clickable and can be used for position teleportation
- Improved the nearest player entry in Raid Den alerts so it is now clickable and can be used for player teleportation
- Improved the Raid Dens UI so it now displays useful raid information, including:
  - Pokémon
  - level
  - difficulty
  - biome
  - nearest player
  - coordinates
- Improved CobbleSafari alerts so they can now open a dedicated CSAR UI view
- Improved CobbleSafari coordinates so they are now clickable and can be used for position teleportation
- Improved the nearest player entry in CobbleSafari alerts so it is now clickable and can be used for player teleportation
- Improved the CobbleSafari UI so it now displays useful portal information, including:
  - destination
  - world
  - nearest player
  - coordinates
- Improved Raid Dens and CobbleSafari behavior so they now follow the same teleport anti-spam logic as classic CSAR alerts

## 2.6.0

### Summary

This update adds compatibility with Cobblemon Raid Dens, including dedicated raid alerts, raid Pokémon capture announcements, and a dedicated Discord webhook.

### Added

- Added optional compatibility with Cobblemon Raid Dens
- Added an in-game alert when a Raid Den appears
- Added Raid Den alert information for:
  - Pokémon
  - level
  - raid difficulty
  - nearest player
  - coordinates
  - biome
- Added a dedicated Discord webhook for Raid Den alerts
- Added a message when a player receives a Pokémon after a raid
- Added an option to enable or disable raid victory announcements
- Added an option to hide false despawn messages linked to raid bosses
- Added a dedicated sound for Raid Den spawn alerts
- Added volume and pitch settings for the Raid Den spawn sound
- Added Raid Dens options in `/csar server`
- Added Raid Dens player preferences in `/csar config`

### Improved

- Improved compatibility handling so Raid Dens options only appear when Cobblemon Raid Dens is installed
- Improved Raid Den spawn messages so they stay compact and readable on a single line
- Improved the Raid Den webhook so it focuses on the important raid information
- Improved Raid Den sound behavior so the sound only plays when the Raid Den appears, not on capture or victory

### Notes

- This compatibility is optional and has no effect if Cobblemon Raid Dens is not installed
- Raid Dens webhooks remain configured on the server side
- `/csar config` preferences allow each player to choose whether they want to receive Raid Den announcements

## 2.5.2

### Summary

This update improves CSAR sound handling with more precise server-side and player-side sound settings.

### Added

- Added volume and pitch settings for normal alerts
- Added per-category volume and pitch settings for:
  - Legendary
  - Mythical
  - Ultra Beast
  - Paradox
  - Starter
- Added per-variant volume and pitch settings for:
  - Alpha
  - Shiny
  - Radiant
- Added personal volume and pitch settings in `/csar config`

### Changed

- Changed sound editing so it is now more consistent between `/csar server` and `/csar config`
- Changed value editing for volume and pitch:
  - left-click now increases the value
  - right-click now decreases the value
- Changed the Sounds section structure to keep a clearer organization:
  - General
  - Categories
  - Variants

### Improved

- Improved sound customization precision for both server admins and players
- Improved consistency of the sound configuration workflow
- Improved readability of the Sounds section

### Notes

- Server settings define the base values
- Player settings allow each player to adjust volume and pitch to their own preferences

## 2.5.1

### Summary

This update mainly improves the CSAR configuration UI to make it cleaner, more readable, and more consistent between `/csar config` and `/csar server`.

### Fixed

- Fixed a stray vertical line visible in the left menu of the config UI
- Fixed the same visual issue in the personal configuration UI
- Fixed alignment in `Teleport > Permissions`
- Fixed the duplicate `Enabled` / `Disabled` visual state in the specific Pokémon configuration
- Fixed several UI texts that were too long or poorly aligned

### Changed

- Changed the UI option layout to use a more consistent structure:
  - option name on the left
  - state or value on the right
- Changed Discord webhook controls in the server UI so the `URL` and `Test` buttons are now more compact
- Changed some section ordering to make navigation more coherent
- Changed the outbreak warning text to be clearer:
  - `May spam chat and Discord alerts during a Mass Outbreak.`

### Improved

- Improved readability of the `Enabled`, `Disabled`, `Configured`, and `Not Configured` states
- Improved readability of the Discord webhook section in the server UI
- Improved readability of the Outbreaks section
- Improved overall visual consistency between personal and server configuration screens

### Notes

- This update does not change alert logic, webhook logic, or Mass Outbreak behavior
- This release is mainly a UI polish update

## 2.5.0

### Summary

This update fully reorganizes Discord webhook handling, adds Safari webhook support, improves Mass Outbreak detection, and introduces an option to prevent flooding from normal CSAR alerts during outbreaks.

### Fixed

- Fixed Mass Outbreak detection that could fail to trigger in-game alerts or Discord webhooks
- Added a fallback scanner to detect active Mass Outbreaks even when the main compatibility event is not fired
- Fixed behavior where Pokémon coming from a Mass Outbreak could trigger too many normal CSAR alerts
- Fixed the missing translation for the option controlling normal alerts for outbreak Pokémon

### Added

- Added a separate `webhooks.json` config file
- Added a dedicated webhook for Safari alerts
- Added Safari webhook options in the server configuration UI
- Added dedicated webhook URLs for spawns, captures, outbreaks, and Safari
- Added fallback support to the default webhook when a dedicated webhook URL is empty
- Added a configurable option to allow or block normal CSAR alerts for Pokémon coming from a Mass Outbreak
- Added a flood warning in the UI for the normal outbreak alert option
- Added a `LICENSE` file using All Rights Reserved

### Changed

- Changed Discord webhook handling so it is now separated from the main server config
- Changed webhook organization to make configuration cleaner and easier to manage
- Changed webhook migration flow so older webhook values can be moved into `webhooks.json`
- Changed Mass Outbreak alert detection so it no longer depends only on the initial compatibility hook
- Changed server behavior so admins can choose between the recommended anti-flood mode and a more permissive mode
- Changed the mod license to All Rights Reserved

### Improved

- Improved readability and maintainability of the webhook configuration
- Improved reliability of Mass Outbreak alerts and webhooks
- Improved outbreak-related spam control for normal CSAR alerts
- Improved server-side flexibility for Discord webhook routing

### Notes

- The mod license is now All Rights Reserved
- By default, normal Pokémon from a Mass Outbreak do not trigger normal CSAR alerts in order to avoid spam
- Important special alerts such as Shiny, Alpha, or Radiant can still be preserved according to the mod logic

## 2.4.1

### Summary

This small update adds a new configuration option for the world-load chat message and improves Alpha spawn alert information.

### Added

- Added a config option to disable the chat message shown when loading a world

### Improved

- Improved Alpha spawn alerts so Pokémon categories remain visible when a Pokémon is Alpha
- Alpha Pokémon can now correctly show both their category and variant, such as Starter + Alpha or Legendary + Alpha

### Notes

- The world-load chat message is still enabled by default
- Server owners can disable it with `messages.showWorldLoadChatMessage`

## 2.4.0

### Summary

This update fixes Starter detection so CSAR now correctly recognizes Starter evolutions as well.

### Fixed

- Fixed the Starter category so it no longer misses some Starter evolutions
- Added an internal fallback to recognize full Starter families from Generation 1 through Generation 9
- Fixed Blaziken / Braségali so it is now correctly detected as a Starter Pokémon

### Improved

- Improved Starter detection so it no longer depends only on the labels provided by Cobblemon
- Improved Starter alert reliability for evolved Starter Pokémon

### Notes

- This fix only affects Starter family detection

## 2.3.0

### Summary

This small polish update improves Discord webhook Pokémon images by using shiny sprites when the Pokémon is shiny.

### Added

- Added shiny sprite support for Discord webhook Pokémon images
- Added `{variant}` support in the Discord webhook image URL template

### Changed

- Changed Discord spawn webhooks so they now use the shiny Pokémon image when the spawned Pokémon is shiny
- Changed Discord capture webhooks so they now use the shiny Pokémon image when the captured Pokémon is shiny
- Changed non-shiny Pokémon handling so they continue to use the normal Pokémon image
- Changed existing webhook image templates using `/normal/` so they remain compatible and are automatically adapted for shiny Pokémon when needed

### Improved

- Improved Discord webhook visual accuracy for shiny Pokémon
- Improved consistency between the Pokémon variant shown in the webhook text and the Pokémon image displayed in the embed

### Notes

- Mass Outbreak webhook images continue to use the normal Pokémon image
- Some special Pokémon forms may still depend on PokémonDB sprite URL availability

## 2.2.0

### Summary

This update adds optional CobbleSafari portal alerts, expands Mass Outbreaks configuration, and introduces a full per-player configuration system so each player can control how they receive CSAR alerts without affecting others.

### Fixed

- Fixed CobbleSafari portal detection not triggering from the callback alone by adding a fallback active portal scanner
- Fixed CobbleSafari portal alerts not respecting per-player enable or disable preferences
- Fixed Mass Outbreaks personal preferences not being applied correctly after saving
- Fixed personal config UI text field alignment
- Fixed personal config UI brightness mismatch compared to the server config UI
- Fixed the personal config save message to include the `[CSAR]` prefix
- Fixed the clear personal Pokémon button appearing when there was nothing to clear
- Fixed personal Pokémon clear behavior by adding a confirmation step

### Added

- Added `/csar config` as the personal player configuration command
- Added `/csar server` as the global server or admin configuration command
- Added per-player alert display mode preferences:
  - Server default
  - Legacy only
  - UI only
  - Hybrid
- Added per-player Pokémon-specific alerts
- Added per-player Pokémon-specific add, remove, clear, and list support
- Added per-player custom sounds for specific Pokémon
- Added per-player custom messages for specific Pokémon
- Added per-player alert category preferences
- Added per-player alert variant preferences
- Added per-player sound preferences
- Added per-player custom sounds for categories and variants
- Added personal configuration UI for players
- Added global server configuration UI separation through `/csar server`
- Added optional CobbleSafari portal alert support
- Added CobbleSafari portal detection through an active portal fallback scanner
- Added CobbleSafari portal alerts with:
  - destination
  - nearest player
  - position
  - world
  - remaining time
- Added `[Safari]` prefix for CobbleSafari portal alerts
- Added configurable CobbleSafari server settings:
  - enable or disable portal alerts
  - enable or disable portal sounds
  - custom portal sound
  - sound volume
  - sound pitch
  - announce to all players
  - same-dimension-only alerts
  - show or hide destination
  - show or hide nearest player
  - show or hide position
  - show or hide world
  - show or hide remaining time
- Added per-player CobbleSafari preferences:
  - receive or ignore portal alerts
  - enable or disable personal portal sound
  - custom personal portal sound
  - show or hide allowed portal information
- Added optional Mass Outbreaks server configuration UI
- Added optional Mass Outbreaks player configuration UI
- Added per-player Mass Outbreaks preferences
- Added per-player Mass Outbreaks sound settings
- Added server-authority logic for compatibility alerts
- Added clean display names for custom dimensions, including `Arkensia`

### Changed

- Changed `/csar config` so it now opens the player's personal CSAR configuration
- Changed `/csar server` so it now opens the global server or admin CSAR configuration
- Changed server configuration so it remains the authority for global rules
- Changed player configuration so it now controls only the current player's preferences
- Changed CobbleSafari alerts to use `[Safari]` instead of `[CSAR]`
- Changed compatibility sections so they are now grouped under `Compatibilité / Compatibility`
- Changed CobbleSafari and Mass Outbreaks handling so they are treated as optional compatibility modules
- Changed player preferences so they now respect server limits
- Changed feature authority rules:
  - if the server disables a feature, players can no longer re-enable it personally
  - if the server allows a feature, each player can choose whether they want to receive it

### Improved

- Improved multiplayer usability by allowing each player to choose their own alert display style
- Improved server clarity by separating personal config and server config
- Improved CobbleSafari alert readability
- Improved CobbleSafari world display by showing clean names instead of technical dimension IDs
- Improved Fabric config hub readability by matching the overlay brightness more closely with the NeoForge version
- Improved personal configuration UI structure
- Improved personal Pokémon-specific UI with autocomplete, presets, custom sound, and custom message support
- Improved config safety by keeping server rules and player preferences separated
- Improved optional compatibility handling so CSAR remains usable without optional compat mods installed

### Notes

- CobbleSafari support is optional. CSAR does not require CobbleSafari to be installed
- Optional dependency for CobbleSafari portal alerts: `https://modrinth.com/mod/cobblesafari`
- Mass Outbreaks support is optional. CSAR does not require Mass Outbreaks to be installed
- Compatibility settings only appear when the related compatibility is available
- Server settings always have priority over player preferences
- Personal settings are stored in `player_alert_settings.json`
- Global server settings remain stored in the normal CSAR configuration files
- CobbleSafari and Mass Outbreaks alerts can now be controlled independently by the server and by each player

## 2.1.0

### Summary

This update adds specific Pokémon alerts, improves configuration reliability, adds sound preset helpers, and polishes Mod Menu integration.

### Added

- Added support for specific Pokémon alerts
- Added a dedicated `pokemon.json` configuration file for Pokémon-specific alert settings
- Added a `default` section in `pokemon.json` for global Pokémon alert defaults
- Added a `specific` section in `pokemon.json` for per-Pokémon alert overrides
- Added support for forcing alerts on specific Pokémon with `alwaysAlert`
- Added support for custom sounds on specific Pokémon
- Added support for custom messages on specific Pokémon
- Added in-game configuration UI support for specific Pokémon alerts under `Pokémon > Spécifiques`
- Added add and remove support for specific Pokémon entries in the config UI
- Added live Pokémon search suggestions when adding specific Pokémon
- Added search support for French names, English names, short species IDs, and full species IDs
- Added automatic species ID normalization, for example `ditto` becomes `cobblemon:ditto`
- Added sound preset selection in the config UI
- Added French and English sound preset labels in the UI
- Added `SOUND_PRESETS_FR.txt`
- Added `SOUND_PRESETS_EN.txt`
- Added Mod Menu contact links:
  - Website
  - Issues
- Added a Mod Menu icon for CSAR

### Changed

- Changed specific Pokémon alert configuration to use `pokemon.json` instead of `main.json`
- Changed newly created specific Pokémon entries to enable `alwaysAlert` by default
- Changed the config UI to separate Pokémon settings into:
  - Default
  - Specific
- Changed the specific Pokémon UI to hide the raw add button when valid suggestions are available
- Changed the specific Pokémon UI to keep a manual fallback add button when no suggestion is found
- Changed sound preset handling to allow quick selection while still keeping manual custom sound IDs possible
- Changed Mod Menu metadata so it no longer declares a `sources` link when the public GitHub repository is not a source-code repository

### Improved

- Improved configuration reliability with non-destructive missing-key merging
- Improved config migration behavior so existing config values are preserved when new keys are added by an update
- Improved config updates by automatically adding missing keys without overwriting user settings
- Improved migration safety for `main.json`, `server.json`, and `pokemon.json`
- Improved usability of specific Pokémon alerts by avoiding manual English-only species ID entry
- Improved the specific Pokémon setup workflow with live suggestions
- Improved sound customization discoverability with a short curated preset list
- Improved Mod Menu presentation with a proper icon and useful links

### Notes

- Specific Pokémon alerts are stored in `pokemon.json`
- Leaving `customSound` empty falls back to the normal or default sound behavior
- Leaving `customMessage` empty uses the normal CSAR message only
- The automatic config merge only adds missing keys and does not overwrite existing user values
- Hoopa Pyramid, Distortion Portal, Cobblemon Dungeons, and ticket-based dungeon detection are intentionally postponed to a future update until the correct hooks are fully confirmed

## 2.0.0

### Summary

CSAR now includes optional Cobblemon Mass Outbreaks support on Fabric through `cobblemonbreakouts`, with outbreak announcements aligned with the normal CSAR experience across chat, UI, and Discord.

### Added

- Added optional compatibility with Cobblemon Mass Outbreaks using the `PORTAL_SPAWN` trigger
- Added in-game outbreak announcements with clickable interactions
- Added outbreak support for the Pokémon page link
- Added outbreak support for teleporting to the nearest player
- Added outbreak support for teleporting to outbreak coordinates
- Added outbreak support for the Pokémon info UI
- Added outbreak support to the Discord webhook flow
- Added outbreak registry tracking so outbreak UI and teleport interactions can resolve reliably after the initial alert
- Added outbreak-specific internal click commands for UI and teleport actions
- Added category support for outbreaks in chat, UI, and Discord
- Added normalization for outbreak species IDs so category detection and Pokémon translation still work when the source does not include a namespace
- Added a dedicated render profile fix for Tornadus / Boréas in the 3D UI

### Changed

- Changed outbreak alerts to follow CSAR-style mode behavior:
  - `LEGACY_ONLY`
  - `HYBRID`
  - `UI_ONLY`
- Changed outbreak chat formatting so it now uses `[Mass Outbreaks]` instead of the longer `[CobbleSpawnAlert Reforged]` prefix
- Changed outbreak message interactions to match the intended UX:
  - `HYBRID`: `[Mass Outbreaks]` opens the UI, Pokémon name opens the external Pokémon page
  - `UI_ONLY`: Pokémon name opens the UI
  - `LEGACY_ONLY`: no UI click behavior
- Changed outbreak teleport interaction style so the nearest player name is clickable for player teleport and coordinates are clickable for coordinate teleport
- Changed outbreak coordinates display format to `[x, y, z]`
- Changed outbreak category display so categories appear inline in parentheses like normal spawn alerts
- Changed outbreak Pokémon names to render in white like normal spawn alerts
- Changed outbreak UI payload handling so outbreak screens only show data that is actually relevant

### Improved

- Improved outbreak webhook embeds so they now display cleaner and more consistent information:
  - Pokémon name
  - category when relevant
  - nearest player
  - position
  - world
  - biome
- Improved outbreak UI consistency with the normal CSAR Pokémon info screen
- Improved outbreak UI readability by removing fake spawn-only data such as IVs, EV yield, nature, ability, gender, and glow
- Improved the Pokémon info screen separator line so it no longer crosses through the image area
- Improved 3D UI presentation for Tornadus / Boréas with better vertical placement and scale

### Removed

- Removed the old outbreak-style oversized prefix from the final outbreak chat format
- Removed outbreak UI interactions from `LEGACY_ONLY`
- Removed glow from outbreak behavior by design

### Notes

- Outbreak support is optional and has no effect when Cobblemon Mass Outbreaks is not installed
- Outbreaks intentionally do not support glow
- Category support is intentionally kept for outbreaks because datapacks and custom server setups can expand outbreak content beyond the default configuration
- The current outbreak block is considered a stable checkpoint

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

- Improved clean translatable text system for in-game messages
- Improved stable enum-based category handling
- Improved cleaner internal handling for spawn and capture messages

### Removed

- Removed the legacy raw message template system
