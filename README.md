# GTA 000 Tools

`GTA 000 Tools` is a Blender add-on for building GTA V non-ELS lightbar setups, managing grouped asset libraries, previewing linked scene content, and exporting `carcols.meta` data.

## What The Add-on Does
- Build full non-ELS lightbar setups inside Blender
- Import existing `carcols.meta` files and continue editing them
- Export updated `carcols.meta` files
- Manage reusable flash pattern and colour libraries
- Configure up to 32 sirens
- Link sirens, doors, bonnet, boot, and other scene parts to armature bones
- Preview lightbar behaviour in Blender without leaving the scene
- Manage a grouped asset library with search, tags, categories, thumbnails, Append, and Link tools
- Use Sollumz-dependent helpers for wheel preview and polygon Light ID workflows when Sollumz is installed

## Panel Layout
The add-on can appear in the `GTA 000` tab, the `Tool` tab, or both depending on Preferences.

### General
- `Lightbar Setup`
- `Lightbar Simulation`
- `Useful Tools`

### Vehicle
- `Body Openings`
- `Extras`
- `Lighting`
- `Light IDs`
- `Wheel Preview`

### Asset Library
- `Assets`
- `Asset Details`

### Config Libraries
- `Lightbars`
  - `Flash Patterns`
  - `Colours`
- `Assets`
  - `Categories`
  - `Sub-Categories`
  - `Tags`

### Updates and Information
- `Updates`
- `Asset Library Path`
- `Information`

## Installation
1. Open Blender.
2. Go to `Edit > Preferences > Add-ons`.
3. Click `Install from Disk...`.
4. Select `gta000tools.zip`.
5. Enable `GTA 000 Tools`.

## Optional Sollumz Integration
Sollumz is not required for the main lightbar workflow, but it is useful for some vehicle tools.

With Sollumz installed and enabled you can:
- use `Preview Wheel Instances`
- work with polygon `Light IDs` in a Sollumz-style workflow
- use some fragment and vehicle scene helpers more reliably

If Sollumz is missing or disabled, GTA 000 Tools shows a warning and gives you an install or enable button.

## Quick Start
### Lightbar Workflow
1. Open `General > Lightbar Setup`.
2. Set `vehicle_name`, `siren_id`, `BPM`, and `Scale Factor`.
3. Set headlight and taillight patterns if needed.
4. Add sirens from `Siren Actions`.
5. Configure each siren.
6. Link each siren to its mesh and bone.
7. Use `Lightbar Simulation` to preview the active siren or all sirens.
8. Export `carcols.meta` when the setup is ready.

### Asset Library Workflow
1. Add library roots in Preferences or in `Updates and Information > Asset Library Path`.
2. Scan the libraries.
3. Browse assets in `Asset Library > Assets`.
4. Use filters, view mode, and sort mode to narrow the list.
5. `Append`, `Link`, or select an asset to inspect it in `Asset Details`.

### Vehicle Workflow
1. Use `Vehicle > Lighting` to preview headlights, indicators, taillights, and extra lights.
2. Use `Vehicle > Light IDs` in `Edit Mode > Face Select` to assign or select polygon Light IDs.
3. Use `Vehicle > Body Openings` to configure bonnet, boot, and door movement.
4. Use `Vehicle > Extras` to show or hide extras.
5. Use `Vehicle > Wheel Preview` if Sollumz is installed.

## Preferences
Open `Edit > Preferences > Add-ons > GTA 000 Tools`.

Important settings:
- `Panel Location`: show panels in `GTA 000`, `Tool`, or both
- `Icon Colour Mode`: `Default`, `Light`, or `Dark`
- `Alpha Features > Rotators`: show or hide rotator setup controls
- `Asset Preview Size (px)`: target preview size for Asset Library thumbnails
- `Asset Library` settings: library roots, grouping mode, auto refresh, preview generation

## Helpful Built-in Tools
### Useful Tools
- Set scale on or off for the working siren
- Duplicate or renumber a siren
- Match origin to another object
- Set origins to bones
- Move linked bones to origins
- Reset active or all sirens back to stored defaults

### Right-click Menu
A `GTA 000 Tools` submenu is added to the viewport context menu.

Depending on mode, it can include:
- origin tools
- bone tools
- mesh assignment tools
- Light ID tools in `Edit Mode > Face Select`

## Documentation
Wiki pages in this repository:
- [Home](wiki/Home.md)
- [Installation and Setup](wiki/01-Installation-and-Setup.md)
- [Quick Start](wiki/02-Quick-Start.md)
- [Lightbar Setup](wiki/03-Lightbar-Configuration.md)
- [Flash Patterns Library](wiki/04-Flash-Patterns-Library.md)
- [Colours](wiki/05-Colours.md)
- [Sirens](wiki/06-Sirens.md)
- [Object and Bone Linking](wiki/07-Object-and-Bone-Linking.md)
- [Useful Tools](wiki/08-Useful-Tools.md)
- [Preview and Simulation](wiki/09-Preview-and-Simulation.md)
- [Import and Export](wiki/10-Import-and-Export.md)
- [Vehicle Tools](wiki/11-Car-Functions-and-Extras.md)
- [Troubleshooting](wiki/12-Troubleshooting.md)
- [Body Openings](wiki/13-Body-Openings.md)
- [Asset Library](wiki/14-Asset-Library.md)
- [Updates and Information](wiki/15-Updates-and-Information.md)

## Notes
- `Show All Flash Previews` only affects UI swatches. It does not limit viewport timeline preview.
- Siren filters only affect the setup panels and shared siren preview panel.
- If performance drops heavily while previewing, collapse preview-heavy sections and test with `Auto Rebuild` turned off.
- For the best results with vehicle fragments, install and enable Sollumz.
