# Simple Tech

A modular Skript-based tech ecosystem for vanilla Minecraft servers.

Simple Tech adds automation, processing chains, power-like progression, and utility systems **without custom textures or custom blocks**. It uses vanilla blocks/items plus custom names, lore, recipes, metadata, and GUIs to create a scalable tech experience.

---

## 1) Project Goals

### Core goals
- Keep a vanilla visual style.
- Feel intuitive for new players.
- Support deep progression for advanced players.
- Be modular, so features can be enabled/disabled by script file.
- Be maintainable for long-term expansion.

### Hard constraints
- No resource pack requirement.
- No custom block models/textures.
- No custom entities required.
- Everything must be representable with vanilla items/blocks and Skript logic.

### Design inspirations
- Create mod: approachable mechanical progression and transport/processing feel.
- Modern Industrialization: clean tiered processing, machine chains, and scalable complexity.

---

## 2) Design Philosophy

Simple Tech should feel like “what vanilla might look like with light industrial gameplay.”

### Principles
- **Readable:** every machine/item has clear purpose and in-game description.
- **Composable:** outputs from one machine become inputs to others.
- **Tiered:** early game is cheap and simple, late game is efficient and complex.
- **Consistent:** same naming, GUI patterns, and recipe language everywhere.
- **Safe:** no irreversible actions without confirmation/feedback.
- **Low-noise onboarding:** tutorial guidance should appear at meaningful milestones, not as repeating chat spam.

---

## 3) Technical Approach (Skript)

Because we are not adding real custom blocks, “machines” are represented by:
- A placed vanilla block (machine base).
- Optional marker item in the block name/lore or linked variable data.
- Interaction handlers (right-click, inventory click, break/place, hopper events).
- Per-machine state in variables (progress, buffers, upgrades, owner, mode).

### Data model patterns
- Global settings: `{st.config::*}`
- Per-player: `{st.player::%uuid of player%::*}`
- Per-machine by location: `{st.machine::%world%:%x%:%y%:%z%::*}`
- Recipe cache/indexes: `{st.recipe::<type>::<id>::*}`
- GUI session state: `{st.gui::%uuid of player%::*}`

### Naming conventions
- Prefix all options/variables/functions with `st`.
- Use lowercase snake-like keys for IDs: `crushed_iron`, `steam_press`.
- Keep script filenames prefixed by module number for load/read order.

---

## 4) Planned Folder Structure

```text
simple tech/
	README.md
	st_00_core.sk
	st_01_items.sk
	st_02_recipes.sk
	st_03_gui.sk
	st_04_machines_basic.sk
	st_05_machines_advanced.sk
	st_06_power_and_heat.sk
	st_07_logistics.sk
	st_08_world_interactions.sk
	st_09_balance_and_debug.sk
```

### Module responsibilities
- `st_00_core.sk`: constants, utility functions, permission checks, parsing helpers.
- `st_01_items.sk`: custom item registration helpers (name/lore flags, give/check functions).
- `st_02_recipes.sk`: recipe definitions and recipe lookup logic.
- `st_03_gui.sk`: reusable menu framework (pagination, buttons, confirmation slots).
- `st_04_machines_basic.sk`: entry-tier machines and simple processors.
- `st_05_machines_advanced.sk`: multi-step processors, upgraded machines.
- `st_06_power_and_heat.sk`: abstract energy/heat/fuel systems.
- `st_07_logistics.sk`: item movement, filters, routing behavior.
- `st_08_world_interactions.sk`: environmental effects, ore washing, water/heat bonuses.
- `st_09_balance_and_debug.sk`: admin commands, tuning values, diagnostics.

### Module-to-Features map
- `st_00_core.sk` -> Core Framework, Performance, Persistence, Multiplayer Safety
- `st_01_items.sk` -> Custom Item System, Progression Tiers
- `st_02_recipes.sk` -> Recipe System, Economy & Balance
- `st_03_gui.sk` -> GUI Framework, Player Experience & UX
- `st_04_machines_basic.sk` -> Basic Machines, Tier 0/Tier 1 loops
- `st_05_machines_advanced.sk` -> Advanced Machines, Tier 2/Tier 3 loops, Upgrades
- `st_06_power_and_heat.sk` -> Heat / Power / Fuel Systems
- `st_07_logistics.sk` -> Logistics & Automation
- `st_08_world_interactions.sk` -> World Interactions
- `st_09_balance_and_debug.sk` -> Admin & Debug Tooling, QA & Test Coverage, final balance passes

Tracking checklist lives in [FEATURES.md](FEATURES.md).

---

## 5) Progression Model

### Tier 0: Primitive Tech
- Manual processing tools.
- Low-throughput conversion recipes.
- No persistent machine power required.

### Tier 1: Mechanical
- First placeable machines.
- Fuel-driven processing.
- Basic automation support.

### Tier 2: Industrial
- Multi-input recipes.
- Byproducts and secondary outputs.
- Throughput upgrades and machine modes.

### Tier 3: Advanced Automation
- Cross-machine chains.
- Better logistics and filtering.
- Efficiency/overclock tradeoffs.

---

## 6) Item System (Vanilla-Based “Custom Items”)

Custom items are vanilla items with controlled metadata:
- Display name
- Lore
- Optional enchant glow (hidden enchants)
- Persistent ID in lore or stored identification strategy

### Example item categories
- Components: plates, rods, gears, circuits
- Processed materials: crushed ore, dusts, ingots
- Machine parts: casings, coils, press heads
- Utilities: wrench, linker, recipe book

### Rules
- Every custom item must have:
	- `id`
	- human-readable `name`
	- `tier`
	- short `description`
- No two items share the same `id`.

---

## 7) Recipe System

Support multiple recipe styles:
- Crafting-grid style recipes.
- Machine recipes with `input -> output`.
- Multi-output recipes with chances/byproducts.
- Timed recipes.
- Heat or fuel gated recipes.

### Recipe schema (conceptual)
- `id`
- `type` (`crafting`, `pressing`, `smelting_plus`, etc.)
- `inputs::*`
- `outputs::*`
- `duration`
- `energy_cost` or `fuel_cost`
- `requirements::*` (tier, machine level, catalyst)

---

## 8) GUI System

GUIs are essential for usability and should be standardized.

### Required GUI types
- Main Tech Menu
- Recipe Browser
- Machine Status Screen
- Item/Component Guide
- Admin Balance Menu

### GUI UX standards
- Slot 0/8 reserved for navigation/back/close patterns.
- Color-coded status indicators:
	- Green = ready/active
	- Yellow = waiting/input missing
	- Red = blocked/error
- Every actionable slot has hover/lore guidance.
- Every machine has a consistent status layout (progress, input, output, mode).

---

## 9) Machine Patterns

Each machine should follow one standard lifecycle:
1. Placement/register machine state.
2. Validate structure/context.
3. Accept inputs.
4. Process over time.
5. Emit outputs/byproducts.
6. Persist state and recover on reload.

### Suggested starter machines
- Crusher (ore -> crushed ore)
- Press (ingot -> plate)
- Mixer (2+ ingredients -> compound)
- Burner/Boiler (fuel to heat buffer)
- Basic Assembler (component combinations)

---

## 10) Commands & Permissions

### Player-facing
- `/st` opens main menu.
- `/st recipes [query]` opens filtered recipe browser.
- `/st help` gives usage summary.

### Admin-facing
- `/st reload` reloads Simple Tech scripts/config variables.
- `/st give <player> <item_id> [amount]`
- `/st debug machine` inspect targeted machine data.
- `/stbalance` shows current balance defaults and key tuning values.
- `/stbalance <key> [value]` inspects or edits a balance key.

### Permission nodes
- `simpletech.use`
- `simpletech.recipes`
- `simpletech.admin`
- `simpletech.debug`

---

## 11) Balancing Guidelines

- Early-tier recipes should be inexpensive and teach the system.
- Mid-tier should reward automation over manual crafting.
- Late-tier should reward optimization, not raw grind only.
- Avoid item duplication exploits with strict output/input checks.
- Keep processing times meaningful but not frustrating.

---

## 12) Performance & Safety

- Prefer scheduled loops over per-tick heavy scans.
- Track active machines list rather than scanning entire worlds.
- Cache recipe lookups by ID/type.
- Use guard clauses aggressively in click/place/break events.
- Add fail-safe rollback for destructive inventory operations.

---

## 13) Testing Checklist

### Functional
- Item creation and identification works reliably.
- Recipe matching is deterministic.
- GUI actions always map to correct machine/data.
- Machine state survives reloads/restarts.

### Multiplayer
- Two players using same machine cannot dupe items.
- GUI sessions are isolated per player.
- Permission checks are always enforced.

### Edge cases
- Full output inventories.
- Missing fuel mid-process.
- Broken machine during processing.
- Server reload during active operations.

---

## 14) Implementation Roadmap

### Phase 1 (Foundation)
- Core utilities
- Item registry helpers
- Recipe registry and lookup
- Main menu + recipe browser GUI

### Phase 2 (First playable loop)
- Crusher + Press machines
- 10–20 basic recipes
- One fuel/heat mechanic

### Phase 3 (Expansion)
- Advanced machines and byproducts
- Logistics features (filters/routing)
- Upgrades and machine tiers

### Phase 4 (Polish)
- Balance pass
- Better feedback/audio/messages
- Debug/admin tooling finalization

---

## 15) Definition of Done (MVP)

Simple Tech MVP is complete when:
- Players can craft and use at least 3 machines.
- There is a clear Tier 0 -> Tier 1 progression path.
- Recipe browser GUI is functional and discoverable.
- At least 25 custom item definitions exist.
- No known item duplication or deletion bugs remain.

---

## 16) Next Build Step

Recommended first script to implement: `st_00_core.sk`

It should include:
- common options
- message formatter function
- item ID encode/decode helpers
- location key helpers
- permission helper wrappers

Then implement `st_01_items.sk` and `st_02_recipes.sk` before any machine logic.

---

## 17) Current Status

As of 2026-03-07, Milestones 1 through 10 are implemented in the script set:

- Core framework, item registry, recipe registry
- Command-driven GUI/menu flow
- Basic and advanced machines (including assembler queue/pattern behavior)
- Fuel/heat mechanics
- Logistics linking and filtering
- World interaction modifiers and chunk-safe processing
- Admin/debug controls and audit log system
- Snapshot-based persistence, migration checkpoints, and recovery tooling
- Recipe lookup caching and periodic cleanup tasks
- Optional economy hooks for machine-start costs and item selling
- Active-list machine scheduling with bucketed processing for idle sleep behavior
- Priority-based multi-route logistics dispatch
- Advanced refinery support and extended Tier 2/Tier 3 assembly chains
- Multi-stage refinery chains with slurry-token staging and captured byproduct outputs
- Fuel progression now includes `heat_briquette` and `thermal_cell`, plus optional linked-buffer auto-refuel for machines
- Advanced machine set now includes an abstracted `electrolyzer` and `fabricator` with split outputs, quality bonuses, and longer Tier 3 production chains
- Default balance tables for durations, upkeep, economy charges, sell values, and upgrade caps
- Balance reporting through `/stbalance` and `/stadmin economy status`
- Migration status now tracks applied schema steps and exposes a legacy-item normalization placeholder path through `/stitem normalize`
- Command-driven machine/admin panels now cover machine slot guides, progress/fuel indicators, balance shortcuts, machine inspection, and debug action menus

For live progress, see [FEATURES.md](FEATURES.md).

## 18) Documentation Index

- Project scope and architecture: [README.md](README.md)
- Feature progress tracker: [FEATURES.md](FEATURES.md)
- Command reference: [COMMANDS.md](COMMANDS.md)
- Item index: [ITEMS.md](ITEMS.md)
- Recipe index: [RECIPES.md](RECIPES.md)
- Milestone changelog: [CHANGELOG.md](CHANGELOG.md)
- Manual test plan: [TESTPLAN.md](TESTPLAN.md)

