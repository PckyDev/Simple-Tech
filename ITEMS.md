# Simple Tech Item Index

This document lists default item IDs registered in `st_01_items.sk`.

## Raw / Intermediate

- `raw_copper_chunk` - Raw Copper Chunk
- `crushed_iron` - Crushed Iron
- `ash` - Ash
- `slag` - Slag
- `heat_briquette` - Heat Briquette
- `slag_slurry` - Slag Slurry
- `spent_filter` - Spent Filter
- `refined_flux` - Refined Flux
- `electrolyte_gel` - Electrolyte Gel
- `ion_fragment` - Ion Fragment
- `treated_plate` - Treated Plate

## Components

- `iron_plate` - Iron Plate
- `copper_wire` - Copper Wire
- `copper_coil` - Copper Coil
- `control_core` - Control Core
- `charged_mesh` - Charged Mesh
- `fabrication_matrix` - Fabrication Matrix
- `pristine_matrix` - Pristine Matrix
- `precision_lens` - Precision Lens

## Primitive Tools

- `primitive_hammer` - Primitive Hammer

## Machine Parts

- `machine_casing` - Machine Casing
- `reinforced_casing` - Reinforced Casing
- `thermal_cell` - Thermal Cell

## Machine Kits

- `crusher_kit` - Crusher Kit
- `press_kit` - Press Kit
- `mixer_kit` - Mixer Kit
- `smelter_kit` - Smelter Kit
- `assembler_kit` - Assembler Kit
- `refinery_kit` - Refinery Kit
- `electrolyzer_kit` - Electrolyzer Kit
- `fabricator_kit` - Fabricator Kit

## Upgrades

- `speed_upgrade_1` - Speed Upgrade I
- `throughput_upgrade_1` - Throughput Upgrade I
- `efficiency_upgrade_1` - Efficiency Upgrade I
- `yield_upgrade_1` - Yield Upgrade I
- `capacity_upgrade_1` - Capacity Upgrade I

## Utility Tools

- `tech_wrench` - Tech Wrench
- `linker_tool` - Linker Tool
- `status_meter` - Status Meter

## Notes

- Display metadata is generated from item definition fields (tier, rarity, description).
- Item ID is encoded in lore as `&8ID: <id>`.
- Legacy Simple Tech items with older lore/name formats can be rebuilt in-hand with `/stitem normalize`.
- To list runtime IDs in-game: `/stitem list`.
