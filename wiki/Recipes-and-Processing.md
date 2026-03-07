# Recipes and Processing

Simple Tech supports both crafting-style and machine-style recipes.

## How Crafting Works

Simple Tech recipe data is stored as shaped crafting recipes plus machine recipes.

Important: crafting recipes now use the normal vanilla crafting-table grid.

For current player-crafted recipes:

1. open a crafting table
2. place the full recipe pattern into the 3x3 grid
3. take the output from the result slot

For the crafting recipes documented here, there are two important patterns:

### `crafting_shaped`

- ingredient order matters
- the full shape matters
- blank cells in the pattern must stay empty
- recipes can use repeated ingredients to create a believable silhouette

## Exact Starter Crafting Walkthrough

### `primitive_hammer_recipe`

This is the first replacement craft most players care about.

- Type: `crafting_shaped`
- Pattern:
  - `R R .`
  - `. S .`
  - `. S .`
- Key: `R = raw_iron`, `S = stick`
- Output: `primitive_hammer` x1
- Unlock Tier: 0

Meaning:

- place 2 `raw_iron` and 2 `stick` in the exact hammer pattern
- take `primitive_hammer` from the result slot

If you are debugging the recipe in-game, run:

- `/strecipe view crafting_shaped primitive_hammer_recipe`

### `iron_plate_manual`

- Type: `crafting_shaped`
- Pattern:
  - `C C .`
  - `C C .`
  - `. . .`
- Key: `C = crushed_iron`
- Output: `iron_plate` x2

Meaning:

- place 4 `crushed_iron` in a 2x2 square
- take `2 iron_plate` from the result slot

### `starter_casing_manual`

- Type: `crafting_shaped`
- Pattern:
  - `I W I`
  - `W . W`
  - `I W I`
- Key: `I = iron_plate`, `W = copper_wire`
- Output: `machine_casing` x2

Meaning:

- place iron plates on the corners and copper wire around the sides
- take `2 machine_casing` from the result slot

### `coil_basic`

- Type: `crafting_shaped`
- Pattern:
  - `. W .`
  - `W I W`
  - `. W .`
- Key: `W = copper_wire`, `I = iron_plate`
- Output: `copper_coil` x2

Meaning:

- wrap copper wire around a centered iron plate
- take `2 copper_coil` from the result slot

## Recipe Types

### Crafting Recipes

#### `crafting_shaped`
- `primitive_hammer_recipe`
  - Hammer silhouette using `raw_iron` and `stick`
  - Output: `primitive_hammer` x1
  - Duration: 5
  - Unlock Tier: 0

- `iron_plate_manual`
  - 2x2 plate pattern using `crushed_iron`
  - Output: `iron_plate` x2
  - Duration: 4
  - Unlock Tier: 0

- `starter_casing_manual`
  - Framed casing pattern using `iron_plate` and `copper_wire`
  - Output: `machine_casing` x2
  - Duration: 6
  - Unlock Tier: 1

- `coil_basic`
  - Coil ring pattern using `copper_wire` around `iron_plate`
  - Output: `copper_coil` x2
  - Duration: 6
  - Unlock Tier: 1

## Basic Machine Recipes

### `machine_crusher`
- `iron_raw_to_crushed`
  - Input: `raw_iron`
  - Output: `crushed_iron` x2
  - Duration: 8
  - Fuel Cost: 4

### `machine_press`
- `plate_pressing`
  - Input: `iron_ingot`
  - Output: `iron_plate` x2
  - Duration: 9
  - Fuel Cost: 5

- `wire_coiling`
  - Input: `copper_wire`
  - Output: `copper_coil` x2
  - Duration: 7
  - Fuel Cost: 5

### `machine_mixer`
- `casing_mix`
  - Inputs: `iron_plate` + `copper_coil`
  - Output: `machine_casing` x2
  - Duration: 12
  - Fuel Cost: 7
  - Byproduct Chance: 10

- `heat_briquette_blend`
  - Inputs: `ash` + `slag`
  - Output: `heat_briquette` x3
  - Duration: 10
  - Fuel Cost: 5

- `linker_mix_advanced`
  - Inputs: `iron_plate` + `copper_wire` + `copper_coil`
  - Output: `linker_tool` x1
  - Duration: 16
  - Fuel Cost: 9

### `machine_smelter`
- `smelt_crushed_iron`
  - Input: `crushed_iron`
  - Output: `iron_plate` x1
  - Duration: 12
  - Fuel Cost: 8
  - Byproduct Chance: 25

- `smelt_raw_copper`
  - Input: `raw_copper_chunk`
  - Output: `copper_wire` x3
  - Duration: 11
  - Fuel Cost: 7
  - Byproduct Chance: 15

- `slag_recovery`
  - Input: `slag`
  - Output: `crushed_iron` x1
  - Duration: 10
  - Fuel Cost: 4

## Advanced Machine Recipes

### `machine_assembler`
- `wrench_assembly`
  - Inputs: `iron_plate` + `copper_wire`
  - Output: `tech_wrench` x1
  - Duration: 14
  - Fuel Cost: 8

- `meter_assembly`
  - Inputs: `copper_coil` + `iron_plate`
  - Output: `status_meter` x1
  - Duration: 16
  - Fuel Cost: 10

- `control_core_assembly`
  - Inputs: `refined_flux` + `copper_coil`
  - Output: `control_core` x1
  - Duration: 20
  - Fuel Cost: 11

- `reinforced_casing_assembly`
  - Inputs: `treated_plate` + `machine_casing`
  - Output: `reinforced_casing` x1
  - Duration: 20
  - Fuel Cost: 11

- `meter_assembly_advanced`
  - Inputs: `reinforced_casing` + `control_core`
  - Output: `status_meter` x1
  - Duration: 22
  - Fuel Cost: 12

- `thermal_cell_assembly`
  - Inputs: `refined_flux` + `reinforced_casing`
  - Output: `thermal_cell` x1
  - Duration: 24
  - Fuel Cost: 14

### `machine_refinery`
- `slag_slurry_prep`
  - Input: `slag`
  - Output: `slag_slurry` x2
  - Duration: 8
  - Fuel Cost: 6

- `slurry_separation`
  - Input: `slag_slurry`
  - Output: `refined_flux` x1
  - Duration: 14
  - Fuel Cost: 8
  - Byproduct: `spent_filter` x1

- `plate_treating`
  - Input: `iron_plate`
  - Output: `treated_plate` x1
  - Duration: 10
  - Fuel Cost: 6

### `machine_electrolyzer`
- `gel_stabilizing`
  - Input: `slag_slurry`
  - Output: `electrolyte_gel` x2
  - Duration: 16
  - Fuel Cost: 10
  - Byproduct: `ion_fragment` x1

- `coil_energizing`
  - Input: `copper_coil`
  - Output: `charged_mesh` x1
  - Duration: 18
  - Fuel Cost: 12
  - Byproduct: `ion_fragment` x1

### `machine_fabricator`
- `matrix_fabrication`
  - Inputs: `charged_mesh` + `control_core`
  - Output: `fabrication_matrix` x1
  - Duration: 32
  - Fuel Cost: 16
  - Quality Bonus: `pristine_matrix` (20%)

- `lens_polishing`
  - Inputs: `electrolyte_gel` + `treated_plate`
  - Output: `precision_lens` x1
  - Duration: 34
  - Fuel Cost: 17

## Processing Concepts

## Unlock Flow

- Tier 0 crafts cover the primitive loop.
- Finishing the starter track promotes you to Tier 1 automatically.
- Tier 1 crafts open machine parts, coils, and basic machine kits, and the first machines now clearly outscale manual crafting.
- Crafting industrial parts like `reinforced_casing` or `control_core` promotes you into Tier 2.
- Building into electrolyzer-grade components promotes you into Tier 3 for fabricator access, where gel, mesh, and fabrication timings are now less punishing.

### Timed Processing

Recipes store a duration and count down while the machine remains fueled and valid.

### Fuel Cost

Basic and advanced machine recipes can consume fuel points.

### Byproducts

Some recipes produce side outputs such as:

- `slag`
- `spent_filter`
- `ion_fragment`

### Quality Bonuses

Fabricator recipes can upgrade the final output using recipe-level quality bonus metadata.

Example:

- `matrix_fabrication` can produce `pristine_matrix` instead of `fabrication_matrix`

## Discovery Commands

- `/st recipes`
- `/st recipes tier <0-3>`
- `/st recipes type <recipe_type>`
- `/strecipe list`
- `/strecipe view <type> <id>`
- `/strecipe search <query>`

## Troubleshooting: "I can't craft Primitive Hammer"

If you are confused specifically about `primitive_hammer`, check this list:

1. new players should already receive one on first join
2. the replacement recipe is `raw_iron` then `stick`
3. use the exact shaped pattern in the normal crafting table grid
4. the recipe ID is `primitive_hammer_recipe`
5. use `/strecipe view crafting_shaped primitive_hammer_recipe` to verify the server has the recipe registered
6. if you are an admin tester and just need one quickly, use `/stitem give primitive_hammer 1`

After you have it:

- hold it in your hand
- sneak-right-click a grindstone with `raw_iron` in inventory
- sneak-right-click an anvil with `2 crushed_iron` in inventory

## Design Notes

The recipe system is built to support:

- unlock tiers
- human-readable descriptions
- filter/search flows
- byproduct metadata
- quality-output metadata
- reload-safe indexing and caching
