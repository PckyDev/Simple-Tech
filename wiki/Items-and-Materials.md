# Items and Materials

Simple Tech uses vanilla items with controlled metadata.

## Item Metadata Rules

Every Simple Tech item has:

- an internal ID
- a display name
- a tier
- a rarity
- a short description

The item ID is embedded in lore as `&8ID: <id>`.

Legacy metadata can be normalized in-hand with:

- `/stitem normalize`

## Raw and Intermediate Materials

- `raw_copper_chunk`
- `crushed_iron`
- `ash`
- `slag`
- `heat_briquette`
- `slag_slurry`
- `spent_filter`
- `refined_flux`
- `electrolyte_gel`
- `ion_fragment`
- `treated_plate`

## Components

- `iron_plate`
- `copper_wire`
- `copper_coil`
- `control_core`
- `charged_mesh`
- `fabrication_matrix`
- `pristine_matrix`
- `precision_lens`

## Primitive Tools

- `primitive_hammer`

## Machine Parts

- `machine_casing`
- `reinforced_casing`
- `thermal_cell`

## Upgrades

- `speed_upgrade_1`
- `throughput_upgrade_1`
- `efficiency_upgrade_1`
- `yield_upgrade_1`
- `capacity_upgrade_1`

## Utility Tools

- `tech_wrench`
- `linker_tool`
- `status_meter`

## Category Notes

### Fuels

- basic vanilla fuels still work where applicable
- `heat_briquette` is a mid-game industrial fuel
- `thermal_cell` is a late-game high-output fuel

### Recycling Materials

- `slag` and `ash` act as residue/byproduct materials
- some recipes deliberately recycle them into useful outputs

### Advanced Processing Materials

- `slag_slurry` abstracts fluid-like refinery processing through items
- `electrolyte_gel` and `ion_fragment` feed Tier 3 chains
- `pristine_matrix` is a quality-upgraded fabricator result

## Helpful Commands

- `/stitem list`
- `/stitem give <id> [amount]`
- `/stvalue`
- `/stsell [amount]`
