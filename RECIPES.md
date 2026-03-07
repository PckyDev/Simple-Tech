# Simple Tech Recipe Index

This document lists default recipes from `st_02_recipes.sk`.

Important: Simple Tech crafting recipes now use the normal crafting-table grid.

How to craft a Simple Tech crafting recipe:

1. open a crafting table
2. place the listed ingredients into the 3x3 crafting grid
3. take the result from the output slot

Notes:

- `crafting_shaped` recipes now use full 3x3 patterns
- blank spaces in the pattern must remain empty
- use `/strecipe view crafting_shaped <id>` to inspect an exact pattern in-game

## Crafting Recipes

### `crafting_shaped`
- `iron_plate_manual`
  - Pattern:
    - `C C`
    - `C C`
    - `. . .`
  - Key: `C = crushed_iron`
  - Output: `iron_plate` x2
  - Duration: 4
  - Unlock Tier: 0

- `primitive_hammer_recipe`
  - Pattern:
    - `R R`
    - `. S .`
    - `. S .`
  - Key: `R = raw_iron`, `S = stick`
  - Output: `primitive_hammer` x1
  - Duration: 5
  - Unlock Tier: 0

- `starter_casing_manual`
  - Pattern:
    - `I W I`
    - `W . W`
    - `I W I`
  - Key: `I = iron_plate`, `W = copper_wire`
  - Output: `machine_casing` x2
  - Duration: 6
  - Unlock Tier: 1

- `coil_basic`
  - Pattern:
    - `. W .`
    - `W I W`
    - `. W .`
  - Key: `W = copper_wire`, `I = iron_plate`
  - Output: `copper_coil` x2
  - Duration: 6
  - Unlock Tier: 1

- `reinforced_casing_craft`
  - Pattern:
    - `. H .`
    - `B C B`
    - `. H .`
  - Key: `H = heat_briquette`, `B = iron_plate`, `C = machine_casing`
  - Output: `reinforced_casing` x1
  - Duration: 8
  - Unlock Tier: 1

- `control_core_craft`
  - Pattern:
    - `. C .`
    - `. L .`
    - `. C .`
  - Key: `C = copper_coil`, `L = linker_tool`
  - Output: `control_core` x1
  - Duration: 8
  - Unlock Tier: 1

- `crusher_kit_recipe`
  - Pattern:
    - `. I .`
    - `. C .`
    - `I . I`
  - Key: `I = iron_plate`, `C = machine_casing`
  - Output: `crusher_kit` x1

- `press_kit_recipe`
  - Pattern:
    - `I I I`
    - `. C .`
    - `. I .`
  - Key: `I = iron_plate`, `C = machine_casing`
  - Output: `press_kit` x1

- `mixer_kit_recipe`
  - Pattern:
    - `W . W`
    - `. C .`
    - `W . W`
  - Key: `W = copper_wire`, `C = machine_casing`
  - Output: `mixer_kit` x1

- `smelter_kit_recipe`
  - Pattern:
    - `I I I`
    - `H C H`
    - `. H .`
  - Key: `I = iron_plate`, `H = heat_briquette`, `C = machine_casing`
  - Output: `smelter_kit` x1

- `assembler_kit_recipe`
  - Pattern:
    - `. R .`
    - `W C W`
    - `. R .`
  - Key: `R = reinforced_casing`, `W = copper_wire`, `C = control_core`
  - Output: `assembler_kit` x1
  - Unlock Tier: 2

- `refinery_kit_recipe`
  - Pattern:
    - `. T .`
    - `H C H`
    - `. T .`
  - Key: `T = treated_plate`, `H = heat_briquette`, `C = reinforced_casing`
  - Output: `refinery_kit` x1
  - Unlock Tier: 2

- `electrolyzer_kit_recipe`
  - Pattern:
    - `. C .`
    - `F R F`
    - `. C .`
  - Key: `C = copper_coil`, `F = refined_flux`, `R = reinforced_casing`
  - Output: `electrolyzer_kit` x1
  - Unlock Tier: 2

- `fabricator_kit_recipe`
  - Pattern:
    - `. M .`
    - `G R G`
    - `. M .`
  - Key: `M = charged_mesh`, `G = electrolyte_gel`, `R = reinforced_casing`
  - Output: `fabricator_kit` x1
  - Unlock Tier: 3

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

## Runtime Discovery

- List recipe types: `/strecipe list`
- List recipes in type: `/strecipe list <type>`
- View details: `/strecipe view <type> <id>`
- Search recipes: `/strecipe search <query>`
