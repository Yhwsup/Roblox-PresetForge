# Preset Forge

A Roblox Studio plugin for capturing how an Instance is configured and reapplying
it anywhere. Select a Part, UI element, light or any other Instance, save its
properties, attributes, tags and appearance children (like UICorner or PointLight)
as a named preset, then merge that preset onto one or many other Instances.

Presets are **merge-only**: applying one never deletes, reparents or renames
anything. Every apply is a single undo step (Ctrl+Z).

## Features

- Capture and apply: save a preset from a selection, then apply it to the
  Selection, all descendants, everything with a tag, or everything of a class.
- Diff preview: see what will change per target and per property, untick
  anything you don't want, and skip values that already match. Handles 1000+ targets.
- Presets can extend other presets: a child preset applies its base first,
  then its own overrides. Circular chains are refused.
- Shared-property capture**: select several Instances and capture only the
  properties they all agree on.
- Scene drift audit: bind targets to a preset, then audit the place to find
  Instances that have drifted. Re-normalize only the drifted ones, or unbind them.
- Quick-apply palette: pin presets and apply them with the 1–9 number keys.
- Undoable library and version history: deleting or renaming a preset has its
  own undo step, and each preset keeps its recent versions so you can restore one.
- Import and export the library as JSON.
- AI agent support (optional): a scripting API usable from `execute_luau`
  (Claude Code, Codex, roblox-mcp-pro). An optional localhost bridge is off by default.

No third-party dependencies. The library is stored with Studio plugin settings.

## Install

1. Download `PresetForge.rbxmx`.
2. Put it in your Studio Plugins folder:
   - Windows: `%LOCALAPPDATA%\Roblox\Plugins\`
   - macOS: `~/Documents/Roblox/Plugins/`
3. Restart Studio. A **Preset Forge** toolbar appears.

To build from source: `rojo build default.project.json --plugin -o PresetForge.rbxmx`,
or `python3 tools/build_rbxmx.py` if you don't have Rojo.

## Status

Please report any errors from the Output window as issues.
