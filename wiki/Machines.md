# Machines

Simple Tech machines are represented by vanilla blocks plus stored per-location state.

Players can now craft machine kits and place them directly. Admin `/stmachine set` and `/stadvanced set` still work for setup/testing, but normal progression no longer depends on admin registration.

## Basic Machines

### Crusher

Purpose:

- converts raw inputs into crushed materials

Highlights:

- progress timer
- fuel cost support
- starter machine loop

### Press

Purpose:

- compresses ingots/components into crafted parts
- gives clear early-game throughput gains over manual plate and coil crafting

Highlights:

- doubled plate production from `iron_ingot -> iron_plate x2`
- doubled coil production from `copper_wire -> copper_coil x2`
- speed upgrade support

### Mixer

Purpose:

- combines multiple inputs into crafted machine parts or fuel blends

Highlights:

- 2-input recipes
- 3-input support
- better early automation yields for `machine_casing` and `heat_briquette`
- `single` and `batch` modes
- wrench-based mode toggle

### Smelter+

Purpose:

- enhanced smelting and residue generation

Highlights:

- optional bonus output chance
- improved `raw_copper_chunk -> copper_wire x3` throughput
- fuel efficiency interaction through heat
- recyclable `slag` output path

## Advanced Machines

### Assembler

Purpose:

- component-based crafting and queued output production

Highlights:

- pattern memory
- quicker industrial part assembly after the throughput balance pass
- queue handling
- capacity upgrades

### Refinery

Purpose:

- staged industrial refinement

Highlights:

- `slag` -> `slag_slurry x2`
- `slag_slurry` -> `refined_flux`
- byproduct capture such as `spent_filter`

### Electrolyzer

Purpose:

- energy-gated Tier 3 material conversion

Highlights:

- split outputs
- larger `electrolyte_gel` batches for Tier 3 ramp-up
- `ion_fragment` byproducts
- heat and efficiency interaction

### Fabricator

Purpose:

- long-duration advanced manufacturing

Highlights:

- expensive inputs
- quality bonus system
- faster late-game cycles after the automation balance pass
- late-game precision components

## Common Machine Features

- active / idle state
- progress tracking
- stored output state
- fuel buffer
- optional heat buffer
- ownership and access enforcement
- persistence and recovery support
- audit and debug visibility

## Machine Kit Placement

- Craft the machine kit item.
- Place it like a normal block.
- The placed block auto-registers as the matching Simple Tech machine.
- Breaking the machine returns the matching kit item, unless normal break protection blocks the action.

## Machine Control Commands

### Basic

- `/stmachine set <crusher|press|mixer|smelter>`
- `/stmachine info`
- `/stmachine remove`
- `/stmachine list`
- `/stmachine autofuel <on|off|status>`

### Advanced

- `/stadvanced set <assembler|refinery|electrolyzer|fabricator>`
- `/stadvanced info`
- `/stadvanced remove`
- `/stadvanced list`
- `/stadvanced autofuel <on|off|status>`

## Machine Panel Commands

- `/st machine`
- `/st admin inspect`

The command-driven machine panels provide:

- input/output guide
- progress indicator
- fuel and heat or energy summary
- queue and mode summary
- byproduct and quality info where relevant

## Access and Safety

Machines support:

- owner-only management
- shared access
- public access mode
- break protection while active
- one-time admin override break flow
