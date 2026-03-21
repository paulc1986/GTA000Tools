# GTA 000 Tools

`GTA 000 Tools` is a Blender add-on for building, previewing, importing, and exporting GTA V non-ELS siren configurations.

## Features
- Build non-ELS lightbar configurations in Blender
- Import existing `carcols.meta` files
- Export finished `carcols.meta` files
- Manage reusable flash pattern and colour libraries
- Configure up to 32 sirens
- Link sirens to scene meshes and armature bones
- Configure bonnet, boot, standard door, and sliding door helpers with captured open/closed states
- Preview siren flash timing, colours, headlights, and taillights in Blender
- Auto rebuild the siren preview timeline when preview settings change
- Apply siren hidden/shown scale states and restore default transforms from a tools panel
- Check GitHub for updates and install the latest addon zip from inside Blender
- Swap two linked sirens without changing their configuration rows

## Blender Panels
The add-on appears in the 3D View sidebar under:
- `Tool`
- `GTA 000`

Main sections:
- `Lightbar Configuration`
- `Flash Patterns Library`
- `Colours`
- `Body Openings`
- `Car Functions`
- `Useful Tools`
- `Simulation Preview`
- `Updates`

## Installation
1. Open Blender.
2. Go to `Edit > Preferences > Add-ons`.
3. Click `Install from Disk...`.
4. Select `gta000tools.zip`.
5. Enable `GTA 000 Tools`.

## Basic Workflow
1. Set the main lightbar values:
   - `vehicle_name`
   - `siren_id`
   - `BPM`
   - `Scale Factor`
2. Build or edit the flash pattern library.
3. Build or edit the colour library.
4. Add the required siren count.
5. Configure each siren.
6. Link each siren to its mesh and bone.
7. Configure body openings if the vehicle needs bonnet, boot, or door setup.
8. Use `Useful Tools` to set siren scale states, copy a centred origin from a helper object, or reset siren transforms.
9. Use the preview tools to check timing, pattern, and colour.
10. Export `carcols.meta`.

## Lightbar Configuration
Use this section for vehicle-wide settings.

Key fields:
- `vehicle_name`: exported to `<name>` in `carcols.meta`
- `siren_id`: exported to `<id value="..."/>`
- `BPM`: master timing for flash previews and siren timing
- `Scale Factor`: shared hidden-scale factor for the setup
- `Headlight Flash Patterns`: left and right headlight patterns
- `Taillight Flash Patterns`: left and right taillight patterns

If the preview swatches stop updating after import or heavy edits, use `Refresh Pattern Previews`.

## Flash Patterns Library
Use this section to manage reusable flash patterns.

Each pattern stores:
- `name`
- `bits` as a 32-bit sequence
- `sequencer` value

Available actions:
- add
- duplicate
- remove
- repeat a shorter pattern to 32 bits
- generate the opposite pattern
- import the pattern library
- export the pattern library

If an imported siren pattern does not already exist in the library, it will appear as `Unsaved Pattern`. You can save it to the library from the siren settings.

## Colours
Use this section to manage reusable siren colours.

Included defaults cover common emergency-light colours such as:
- amber
- blue
- red
- white
- green
- pink
- purple
- no colour

You can also add custom colours and use them directly on sirens.

## Non-ELS Sirens
Each siren row shows:
- status icon
- siren name
- live preview swatch

Status icon meaning:
- `Light`: mesh and bone are linked correctly
- `Error`: one or more required links are missing

Hover the error icon to see what is missing.

### Siren Actions
From `Siren Actions` you can:
- add 20 sirens
- add 32 sirens
- add sirens 21-32
- remove sirens 21-32
- remove all sirens
- swap two linked sirens

### Siren Swap
`Swap Two Sirens` lets you pick two sirens that already have a linked mesh and bone.

It swaps the physical scene assets only:
- mesh names are swapped
- bone names are swapped
- child bone links are updated

The siren configuration rows stay in place.

Use this when the correct light is in the wrong siren slot.

## Siren Configuration
For each siren you can configure:
- `siren_type`: `Flasher` or `Rotator`
- `Pattern`
- `Colour`
- `Flash Preview`
- `Direction`
- `sync_to_bpm`
- advanced lighting values

### Flashers
Flashers use a selected flash pattern from the library, or `Unsaved Pattern` if the imported pattern is not yet saved.

### Rotators
Rotators use BPM-based speed options and support clockwise or anti-clockwise rotation.

## Object/Bone Linking
Each siren can be linked to:
- a mesh object
- a siren bone on an armature

Main actions:
- `Auto-Detect Sirens/Bones`
- `Assign Selected Object to Siren`
- `Place Bone at Selected Origin`

If a siren has a mesh but no linked bone, the add-on shows an inline warning in the siren settings.

## Useful Tools
Use this section for scene-side siren helpers that are not part of the preview timeline controls.

Main actions:
- `Set Siren Scale (Off)`
- `Set Siren Scale (On)`
- `Set Origin to Selected Object`
- `Reset Active Siren`
- `Reset All Sirens`

`Set Siren Scale (Off)` and `Set Siren Scale (On)` apply the configured hidden or shown state to the working siren. If the siren list selection does not match, the add-on can resolve the siren from the active object.

`Set Origin to Selected Object` copies the origin from a separate helper object onto the working siren mesh while keeping the visible siren geometry in place.

`Reset Active Siren` and `Reset All Sirens` restore the stored default transforms after preview playback or manual testing.

## Importing `carcols.meta`
Importing a `carcols.meta` file can populate:
- vehicle name
- siren ID
- BPM
- headlight and taillight patterns
- siren flash or rotator settings
- colours
- advanced siren values
- scale factor

If imported preview swatches appear stuck, use `Refresh Pattern Previews`.

## Exporting `carcols.meta`
The add-on can export a game-ready `carcols.meta` using the current Blender configuration.

Export includes:
- vehicle-wide settings
- headlight and taillight flash patterns
- active siren values
- default inactive siren entries where required
- siren number comments in the output

## Car Functions
This section includes scene-side helpers for:
- headlights
- taillights
- indicators
- extra lights
- extras visibility

These controls are intended for viewport simulation only.

## Simulation Preview
Use this section to simulate sirens in the scene and generate timeline keyframes.

Main actions:
- `Simulate Siren Off`
- `Simulate Siren On`
- `Simulate All Sirens Off`
- `Simulate All Sirens On`
- `Clear Timeline`
- `Generate Individual Siren Preview`
- `Generate All Sirens Preview`

Enable `Auto Rebuild Timeline` if you want preview-affecting changes to clear and regenerate the timeline automatically.

## Updates
Use the `Updates` panel in Blender to manage addon updates from the GitHub repository.

Main actions:
- `Check for Updates`
- `Install Update`
- `Open GitHub Repo`

The panel also shows:
- current installed version
- latest version found on GitHub
- last checked time
- whether a Blender restart is required after installation

Enable `Check for Updates on Startup` if you want the add-on to notify you when a newer version is available.

## Detailed Documentation
More detailed GitHub Wiki-ready pages are available in [wiki/Home.md](wiki/Home.md).

## Notes
- The add-on is designed around GTA V non-ELS siren workflows.
- Imported patterns and colours can be saved back into the library for reuse.
- If Blender UI previews stop updating after large changes, use `Refresh Pattern Previews`.

## Body Openings
Use the `Body Openings` panel for bonnet, boot, hinged doors, and sliding doors.

Each opening lets you:
- assign the mesh
- place a linked bone on the parent skeleton
- choose hinged or sliding behavior
- select which rotation or slide axes are active
- capture `Closed` and `Open` states from the current manual transform
- preview either captured state back onto the linked mesh or bone

Placed body-opening bones always point toward vehicle front (`Y+`).
