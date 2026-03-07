# Recipes and Processing

Simple Tech supports both crafting-style and machine-style recipes.

## How Crafting Works

Simple Tech recipe data is stored as two-input crafting recipes plus machine recipes.

Important: the starter crafting recipes are not made through the normal vanilla crafting-table grid.

Instead, Simple Tech uses a manual crafting-table interaction:

1. put the first ingredient in your hand
2. keep the other ingredient in your inventory
3. sneak-right-click a crafting table

For the crafting recipes documented here, there are two important patterns:

### `crafting_shaped`

- ingredient order matters
- input 1 must be treated as the left or first ingredient
- input 2 must be treated as the right or second ingredient

### `crafting_shapeless`

- ingredient order does not matter
- you only need the listed ingredients together

## Exact Starter Crafting Walkthrough

### `primitive_hammer_recipe`

This is the first replacement craft most players care about.

- Type: `crafting_shaped`
- Input 1: `raw_iron`
- Input 2: `stick`
- Output: `primitive_hammer` x1
- Unlock Tier: 0

Meaning:

- hold `raw_iron` in your hand
- keep `stick` in your inventory
- sneak-right-click a crafting table
- because it is `crafting_shaped`, keep that order

If you are debugging the recipe in-game, run:

- `/strecipe view crafting_shaped primitive_hammer_recipe`

### `iron_plate_manual`

- Type: `crafting_shapeless`
- Inputs: `crushed_iron` + `crushed_iron`
- Output: `iron_plate` x1

Meaning:

- hold one `crushed_iron` in your hand
- keep another `crushed_iron` in your inventory
- sneak-right-click a crafting table
- any order is fine because it is shapeless

### `starter_casing_manual`

- Type: `crafting_shapeless`
- Inputs: `iron_plate` + `copper_wire`
- Output: `machine_casing` x1

Meaning:

- hold either `iron_plate` or `copper_wire`
- keep the other ingredient in your inventory
- sneak-right-click a crafting table

### `coil_basic`

- Type: `crafting_shaped`
- Input 1: `copper_wire`
- Input 2: `iron_plate`
- Output: `copper_coil` x1

Because it is shaped, the documented order matters.

Meaning:

- hold `copper_wire` in your hand
- keep `iron_plate` in your inventory
- sneak-right-click a crafting table

## Recipe Types

### Crafting Recipes

#### `crafting_shapeless`
- `iron_plate_manual`
  - Inputs: `crushed_iron` + `crushed_iron`
  - Output: `iron_plate` x1
  - Duration: 4
  - Unlock Tier: 0

#### `crafting_shaped`
- `primitive_hammer_recipe`
  - Inputs: `raw_iron` then `stick`
  - Output: `primitive_hammer` x1
  - Duration: 5
  - Unlock Tier: 0

- `coil_basic`
  - Inputs: `copper_wire` then `iron_plate`
  - Output: `copper_coil` x1
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
  - Output: `iron_plate` x1
  - Duration: 10
  - Fuel Cost: 6

### `machine_mixer`
- `casing_mix`
  - Inputs: `iron_plate` + `copper_coil`
  - Output: `machine_casing` x1
  - Duration: 14
  - Fuel Cost: 8
  - Byproduct Chance: 15

- `heat_briquette_blend`
  - Inputs: `ash` + `slag`
  - Output: `heat_briquette` x2
  - Duration: 12
  - Fuel Cost: 6

## Advanced Machine Recipes

### `machine_assembler`
- `wrench_assembly`
- `meter_assembly`
- `control_core_assembly`
- `reinforced_casing_assembly`
- `meter_assembly_advanced`
- `thermal_cell_assembly`

### `machine_refinery`
- `slag_slurry_prep`
- `slurry_separation`
- `plate_treating`

### `machine_electrolyzer`
- `gel_stabilizing`
- `coil_energizing`

### `machine_fabricator`
- `matrix_fabrication`
- `lens_polishing`

## Processing Concepts

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
3. use a crafting table with the Simple Tech manual interaction, not the vanilla crafting-grid UI
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
