# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project somewhat adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).  The MINOR version number is bumped when there are breaking changes in the pret projects.

The **"Breaking Changes"** listed below are changes that have been made in the decompilation projects (e.g. pokeemerald), which porymap requires in order to work properly. If porymap is used on a project that is not up-to-date with the breaking changes, then porymap will likely break or behave improperly.

## [Unreleased]
### Fixed
- Fix bug in zoomed metatile selector where a large selection rectangle was being rendered.
- Fix bug where edited map icons were not rendered properly.
- Fix bug where right-click copying a tile from the tileset editor's metatile layers wouldn't copy the x/y flip status.

## [1.2.1] - 2019-02-16
### Added
- Add ability to zoom in and out the map metatile selector via a slider at the bottom of the metatile selector window.

### Fixed
- Fix crash when creating a new map from a layout that has no pre-existing maps that use it.
- Fix bug where `var_value`, `trainer_type` and `trainer_sight_or_berry_tree_id` JSON fields were being interpreted as integers.

## [1.2.0] - 2019-02-04
### Breaking Changes
- New JSON map data format in pokeemerald and pokeruby from commits  [82abc164dc9f6a74fdf0c535cc1621b7ed05318b](https://github.com/pret/pokeemerald/commit/82abc164dc9f6a74fdf0c535cc1621b7ed05318b) and [a0ba1b7c6353f7e4f3066025514c05b323a0123d](https://github.com/pret/pokeruby/commit/a0ba1b7c6353f7e4f3066025514c05b323a0123d).

### Added
- Add "magic fill" mode to fill tool (hold down CTRL key). This fills all matching metatiles on the map, rather than only the contiguous region.
- Add ability to import tileset palettes (JASC, .pal, .tpl, .gpl, .act).
- Add ability to export tileset tiles as indexed .png images. The currently-selected palette is used.
- Restore window sizes the next time the application is opened.
- Add ability to import metatiles from Advance Map 1.92 (.bvd files).
- Add About window that contains porymap information and changelog. (Found in file menu `Help > About Porymap`)
- Add option to show player's in-game view when hovering the mouse on the map.
- Add option to show an outline around the currently-hovered map tile. Its size depends on the size of the current metatile selection.
- Add ability to define custom fields for map header and all events.

### Changed
- Collapse the map list by default.
- Collision view now has a transparency slider to help make it easier to view the underlying metatiles.
- When importing tileset tiles from an image that is not indexed, the user can also provide a palette for the image. This is for the scenario where the user exports tiles and a palette from Advance Map.
- When creating a new map, the user specifies all of the map properties in a new window prompt.
- New maps can be created using existing layouts by right-clicking on an existing layout folder in the map list panel when sorted by "Layout".
- The map list panel now has "expand-all" and "collapse-all" buttons.
- Events without sprites are now partially transparent so the underlying metatile can be seen. (Warps, signs, etc.)
- Changed the Trainer checkbox to a combobox, since there are actually 3 valid values for the trainer type.
- Multiline comments are now respected when parsing C defines.
- The tiles image in the tileset editor will no longer flip according to the x/y flip checkboxes. The individual tile selection still flips, though.

### Fixed
- Fix bug where smart paths could be auto-enabled, despite the checkbox being disabled.
- Fix crash that could occur when changing the palette id in the tileset palette editor.
- Fix crash that could occur when shrinking the number of metatiles in a tileset.
- Fix bug where exported tile images from Advance Map were not handled correctly due to Advance Map using incorrect file extensions.

## [1.1.0] - 2018-12-27
### Breaking Changes
- New map header format in pokeemerald from commit [a1ea3b5e394bc115ba9b86348c161094a00dcca7](https://github.com/pret/pokeemerald/commit/a1ea3b5e394bc115ba9b86348c161094a00dcca7).

### Added
- Add `porymap.project.cfg` config file to project repos, in order to house project-specific settings, such as `base_game_version=pokeemerald`.
- Write all logs to `porymap.log` file, so users can view any errors that porymap hits.
- Changelog

### Changed
- Add `porymap.cfg` base config file, rather than using built-in system settings (e.g. registry on Windows).
- Properly read/write map headers for `pokeemerald`.
- Overhauled event editing pane, which now contains tabs for each different event. Events of the same type can be iterated through using the spinner at the top of the tab. This makes it possible to edit events that are outside the viewing window.

### Fixed
- Creating new hidden-item events now uses a valid default flag value.
- Fix bug where tilesets were sometimes not displaying their bottom row of metatiles.
- Fix bug where porymap crashes on startup due to missing map headers.
- Fix tileset editor crash that only happened on macOS.
- Fix minor bug when parsing C defines.
- Write `MAP_GROUPS_COUNT` define to `maps.h`.
- Fix bug where opening multiple projects and saving would cause junk to be written to `layouts_table.inc`.
- Fix porymap icon on macOS.

## [1.0.0] - 2018-10-26
This was the initial release.

[Unreleased]: https://github.com/huderlem/porymap/compare/1.2.1...HEAD
[1.2.1]: https://github.com/huderlem/porymap/compare/1.2.0...1.2.1
[1.2.0]: https://github.com/huderlem/porymap/compare/1.1.0...1.2.0
[1.1.0]: https://github.com/huderlem/porymap/compare/1.0.0...1.1.0
[1.0.0]: https://github.com/huderlem/porymap/tree/1.0.0
