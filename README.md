# GTA 000 Tools

`GTA 000 Tools` is a Blender add-on for building, previewing, importing, and exporting GTA V non-ELS siren configurations.

## Features
- Build non-ELS lightbar configurations in Blender
- Import existing `carcols.meta` files
- Export finished `carcols.meta` files
- Manage reusable flash pattern and colour libraries
- Configure up to 32 sirens
- Link sirens to scene meshes and armature bones
- Preview siren flash timing, colours, headlights, and taillights in Blender
- Swap two linked sirens without changing their configuration rows

## Blender Panels
The add-on appears in the 3D View sidebar under:
- `Tool`
- `GTA 000`

Main sections:
- `Lightbar Configuration`
- `Flash Patterns Library`
- `Colours`
- `Car Functions`
- `Simulation Preview`

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
7. Use the preview tools to check timing, pattern, and colour.
8. Export `carcols.meta`.

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

## Notes
- The add-on is designed around GTA V non-ELS siren workflows.
- Imported patterns and colours can be saved back into the library for reuse.
- If Blender UI previews stop updating after large changes, use `Refresh Pattern Previews`.
