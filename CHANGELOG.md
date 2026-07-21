# Changelog

All notable changes made in this fork are listed here, satisfying LGPL-2.1
§2(a)'s requirement to state what was changed and when. Upstream history
before the fork point is in [incheon-kim/tarkov-settings](https://github.com/incheon-kim/tarkov-settings)'s
own commit log.

**Fork point:** upstream v1.2.1.0 (last upstream release, 2023-10-14), which
had been unmaintained since then with several unresolved crash reports.

## [1.5.0.0] - 2026-07-21
### Changed
- Renamed the program and its files to match this repo's name: the exe is
  now `tarkov-gamma-vibrance-tool.exe`, the window title/tray tooltip read
  "tarkov-gamma-vibrance-tool", and the settings file is
  `tarkov-gamma-vibrance-tool.config.json`. Older settings filenames are
  migrated automatically on first load.

## [1.4.1.0] - 2026-07-21
### Changed
- Renamed `settings.json` to `tarkov-settings.config.json` so it's
  identifiable as belonging to this app instead of looking like a random,
  safe-to-delete file. Existing `settings.json` files are migrated
  (moved, not copied) automatically.

## [1.4.0.0] - 2026-07-21
### Added
- Global hotkeys for color profiles (`RegisterHotKey`/`WM_HOTKEY`). Bind a
  key combination to a saved profile via the new Set/Clear buttons;
  pressing it applies that profile instantly, even while another window
  (including EFT itself) has focus. Implements upstream issues
  [#1](https://github.com/incheon-kim/tarkov-settings/issues/1) and
  [#12](https://github.com/incheon-kim/tarkov-settings/issues/12).

## [1.3.0.1] - 2026-07-21
### Changed
- Repo renamed from `tarkov-settings-fixed` to `tarkov-gamma-vibrance-tool`;
  updated the in-app update-checker and download URLs to match so they
  don't keep pointing at the old name.

## [1.3.0.0] - 2026-07-21
### Added
- Color profiles: save and load multiple named sets of
  Brightness/Contrast/Gamma/Saturation via new Save/Load/Del buttons.
  Implements the README's "Profiles" TODO item.

## [1.2.2.0] - 2026-07-21
### Fixed
- Crash when the NVIDIA display handle becomes invalid (RDP session
  change, closing the NVIDIA Control Panel, monitor sleep/hotplug) by
  catching `NVIDIAApiException` in `NVIDIA.Saturation`/`NVIDIA.Load`
  instead of letting it propagate out of a `WinEventHook` callback.
  Matches crashes reported in upstream issues
  [#3](https://github.com/incheon-kim/tarkov-settings/issues/3) and
  [#17](https://github.com/incheon-kim/tarkov-settings/issues/17).
- Settings not saving when closing the window with the title bar's X
  button — previously only saved via the tray icon's Exit item. Now
  saves on both paths.
- Settings file path anchored to the exe's own folder
  (`AppDomain.CurrentDomain.BaseDirectory`) instead of the process's
  current working directory, which could differ depending on how the
  exe was launched.
- App crashing on a corrupted/invalid settings file — now resets to
  defaults with a warning dialog instead.
- Possible `NullReferenceException` in the process-focus watcher when
  the focused window's process had already exited.
### Added
- `EscapeFromTarkovArena` added to the default monitored process list.
  Implements upstream issue [#23](https://github.com/incheon-kim/tarkov-settings/issues/23).
