# Simple Tech Recipe Index

This document lists default recipes from `st_02_recipes.sk`.

Important: Simple Tech crafting recipes use the manual crafting-table interaction, not the normal vanilla crafting-table grid.

How to craft a Simple Tech crafting recipe:

1. hold the first ingredient in your hand
2. keep the other ingredient in your inventory
3. sneak-right-click a crafting table

## Crafting Recipes

### `crafting_shapeless`
- `iron_plate_manual`
  - Inputs: `crushed_iron` + `crushed_iron`
  - Output: `iron_plate` x1
  - Duration: 4
  - Unlock Tier: 0

### `crafting_shaped`
- `primitive_hammer_recipe`
  - Inputs: `raw_iron` + `stick`
  - Output: `primitive_hammer` x1
  - Duration: 5
  - Unlock Tier: 0

- `coil_basic`
  - Inputs: `copper_wire` + `iron_plate`
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
  - Inputs: `iron_plate` + `copper_wire`
  - Output: `tech_wrench` x1
  - Duration: 16
  - Fuel Cost: 10

- `meter_assembly`
  - Inputs: `copper_coil` + `iron_plate`
  - Output: `status_meter` x1
  - Duration: 18
  - Fuel Cost: 12

- `control_core_assembly`
  - Inputs: `refined_flux` + `copper_coil`
  - Output: `control_core` x1
  - Duration: 22
  - Fuel Cost: 12

- `reinforced_casing_assembly`
  - Inputs: `treated_plate` + `machine_casing`
  - Output: `reinforced_casing` x1
  - Duration: 22
  - Fuel Cost: 12

- `meter_assembly_advanced`
  - Inputs: `reinforced_casing` + `control_core`
  - Output: `status_meter` x1
  - Duration: 24
  - Fuel Cost: 14

- `thermal_cell_assembly`
  - Inputs: `refined_flux` + `reinforced_casing`
  - Output: `thermal_cell` x1
  - Duration: 26
  - Fuel Cost: 16

### `machine_refinery`
- `slag_slurry_prep`
  - Input: `slag`
  - Output: `slag_slurry` x1
  - Duration: 10
  - Fuel Cost: 8

- `slurry_separation`
  - Input: `slag_slurry`
  - Output: `refined_flux` x1
  - Duration: 16
  - Fuel Cost: 10
  - Byproduct: `spent_filter` x1

- `plate_treating`
  - Input: `iron_plate`
  - Output: `treated_plate` x1
  - Duration: 12
  - Fuel Cost: 8

### `machine_electrolyzer`
- `gel_stabilizing`
  - Input: `slag_slurry`
  - Output: `electrolyte_gel` x1
  - Duration: 18
  - Fuel Cost: 12
  - Byproduct: `ion_fragment` x1

- `coil_energizing`
  - Input: `copper_coil`
  - Output: `charged_mesh` x1
  - Duration: 20
  - Fuel Cost: 14
  - Byproduct: `ion_fragment` x1

### `machine_fabricator`
- `matrix_fabrication`
  - Inputs: `charged_mesh` + `control_core`
  - Output: `fabrication_matrix` x1
  - Duration: 36
  - Fuel Cost: 18
  - Quality Bonus: `pristine_matrix` (20%)

- `lens_polishing`
  - Inputs: `electrolyte_gel` + `treated_plate`
  - Output: `precision_lens` x1
  - Duration: 40
  - Fuel Cost: 20

## Runtime Discovery

- List recipe types: `/strecipe list`
- List recipes in type: `/strecipe list <type>`
- View details: `/strecipe view <type> <id>`
- Search recipes: `/strecipe search <query>`
