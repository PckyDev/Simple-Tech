# Simple Tech Changelog

## 2026-03-07

### Feature Set E - Onboarding UX Refresh
- Disabled passive starter-objective reminder spam by default while keeping objective checks active.
- Changed starter progression messaging so completions announce the next objective instead of repeatedly re-sending reminders.
- Extended `/st objective` with `current`, `next`, and `status` views for a cleaner tutorial flow.
- Expanded objective output with concrete step-by-step instructions for the primitive loop.
- Gave first-time players a starter `primitive_hammer` and made the replacement recipe use `raw_iron + stick`.
- Split the primitive loop into clearer tutorial stages, including an explicit "find and hold the Primitive Hammer" step.
- Added `/st objective walkthrough` for a full guided starter sequence.
- Added working manual crafting-table interactions for Simple Tech crafting recipes so starter crafts like `primitive_hammer` no longer depend on the vanilla crafting-grid UI.

### Feature Pass - Migration Placeholder and Legacy Item Normalization
- Expanded schema migration handling into step-based placeholder tracking with applied-step status fields.
- Added legacy Simple Tech item detection fallback for older lore/name formats.
- Added `/stitem normalize` so held legacy items can be rebuilt to the current metadata standard.

### Feature Pass - Command-Driven Machine and Admin Panels
- Added `/st machine` panel output for targeted machines with recipe guides, progress bars, fuel indicators, and mode/control hints.
- Added `/st admin balance`, `/st admin inspect`, and `/st admin debug` command-driven admin panels.
- Marked the remaining GUI-framework checklist items complete in the tracker.

### Milestone 1 - `st_00_core.sk`
- Added core utility framework (messaging, permissions, config, cooldown, location keys).

### Milestone 2 - `st_01_items.sk`
- Added item registry and metadata builder.
- Added default item definitions and `/stitem` commands.

### Milestone 3 - `st_02_recipes.sk`
- Added recipe registry, search, validation, matching, and `/strecipe` commands.

### Milestone 4 - `st_03_gui.sk`
- Added command-driven menu framework (`/st`, paged recipe browsing).

### Milestone 5 - `st_04_machines_basic.sk`
- Added basic machine framework (`crusher`, `press`, `mixer`) with timed processing.

### Milestone 6 - `st_06_power_and_heat.sk`
- Added fuel/heat buffers and fuel value table.
- Wired fuel consumption into machine processing.

### Milestone 7 - `st_05_machines_advanced.sk`
- Added advanced assembler machine with queue processing and pattern memory.
- Added Speed Upgrade I integration.

### Milestone 8 - `st_07_logistics.sk`
- Added machine-to-machine logistics linking, filtering, and transfer rate controls.

### Milestone 9 - `st_08_world_interactions.sk`
- Added environment-based duration/output modifiers.
- Added chunk pause/resume behavior for machine loops.

### Milestone 10 - `st_09_balance_and_debug.sk`
- Added admin/debug command suite, machine inspection, force-finish, and audit controls.

### Documentation Sprint
- Added module header comments across all `st_00` through `st_09` scripts.
- Added project docs: `COMMANDS.md`, `ITEMS.md`, `RECIPES.md`, and `FEATURES.md` tracker updates.
- Added README current-status and documentation-index sections.
- Marked documentation checklist complete for Feature Set D.

### Feature Pass - Power, Upgrades, and UX
- Added passive upkeep drain API and fuel-paused machine behavior.
- Added assembler upgrades: Efficiency I, Yield I, and Capacity I with validation and incompatibility rules.
- Added effective machine stats output in `/stadvanced info`.
- Added progression summary command (`/st progress`) and recipe browser filters (`/st recipes tier`, `/st recipes type`).
- Added machine placement/break and error-event audit logging hooks.

### Feature Pass - Onboarding
- Added first-use onboarding prompts on join with starter guidance.
- Added staged starter objective tracker with automatic progression checks.
- Added periodic objective hint reminders and `/st objective` command.
- Wired `/st progress` into onboarding objective completion tracking.

### Feature Pass - Tier 0 Primitive Loop
- Added `primitive_hammer` starter tool item.
- Added manual processing interactions: grindstone raw iron crushing and anvil hand pressing.
- Added starter-first recipes for primitive hammer and manual casing assembly.

### Feature Pass - Logistics Controls
- Added directional IO config for links (`any`, cardinal directions, up/down).
- Added category tag filters (`allowtag` / `denytag`) alongside item-ID filters.
- Added logistics info output for IO mode and tag filter counts.

### Feature Pass - Smelter+
- Added `machine_smelter` recipes for enhanced smelting and slag recovery.
- Added heat-based fuel efficiency modifier for smelter processing.
- Added optional smelter bonus output chance and recyclable `slag` byproduct output.
- Added `/stmachine set ... smelter` support.

### Feature Pass - Press Upgrades
- Added component compression recipe support for the press (`copper_wire` -> `copper_coil`).
- Added `Speed Upgrade I` support for press machines.
- Added press upgrade visibility in `/stmachine info`.

### Feature Pass - Heat and Fuel Residue
- Added passive burner heat generation from nearby lava, fire, and campfire heat sources.
- Added `ash` fuel residue byproduct behavior for coal-based fuels.
- Expanded the item index and tracker coverage for heat/fuel systems.

### Feature Pass - Advanced Mixer
- Added optional third-input support to machine recipes.
- Added advanced three-input mixer recipe for `linker_tool`.
- Added mixer `batch` mode with wrench toggle and bonus batch output handling.
- Added mixer mode visibility in `/stmachine info`.

### Feature Pass - Machine Access Control
- Added owner/shared/public access helpers for machine locations.
- Added interaction access enforcement for basic and advanced machines.
- Added active-machine break protection with admin override flow.
- Added `/staccess` commands for info, claim, sharing, public mode, override break, and admin takeover.

### Feature Pass - Virtual Buffers
- Added virtual buffer registration and cached item storage.
- Added machine-output caching into linked buffers.
- Added automatic buffer push into linked buffers or compatible basic machines.
- Added `/stbuffer` commands for set, remove, info, and list operations.

### Feature Pass - Throughput Balancing
- Added shared machine duration balancing helpers for baseline and tier multipliers.
- Applied throughput balancing to basic and advanced machine processing times.
- Added configurable upgrade-cap helpers for machine/buffer upgrade limits.
- Added `throughput_upgrade_1` support for virtual buffers to increase transfer rate.

### Feature Pass - Safety and Confirmation
- Added short interaction locks for basic and advanced machines to reduce double-click race issues.
- Added reusable confirmation helper for destructive actions.
- Added confirmation flow to machine removal, buffer removal, audit clearing, and admin ownership takeover.
- Confirmed GUI session state remains isolated per-player through UUID-scoped menu data.

### Feature Pass - Feedback, World Modifiers, and Recovery
- Added shared actionbar and optional sound feedback hooks for machine start, pause, progress, and completion states.
- Added biome-based and height/depth-based environmental duration modifiers.
- Added machine integrity checks and stale metadata cleanup on changed backing blocks.
- Added schema version tracking, migration checkpoint fields, and `/stadmin recover <status|cleanup|repair|migrate>` recovery tools.
- Added snapshot-based persistence for machine progress, upgrades, and mode/config state with restore-on-load behavior.

### Feature Pass - Performance and QA Support
- Added indexed and cached machine recipe lookups with automatic invalidation on recipe reload.
- Added stale GUI session tracking plus periodic cleanup of stale GUI session data.
- Added periodic orphan machine cleanup hook for stale machine references.
- Added consistent icon language helpers for command-driven menu outputs.
- Added `TESTPLAN.md` covering manual test plans, edge cases, and regression validation.

### Feature Pass - Claim Hook Bridge
- Added optional claim-hook bridge checks for machine use, claiming, and break actions.
- Added `/stadmin claimhook <info|use|break|block|clear>` for external-claim compatibility testing and admin control.
- Wired claim-hook denial messages through shared access enforcement helpers.

### Feature Pass - Economy and Scheduler Optimization
- Added optional Simple Tech economy hooks with player balances, held-item valuation, and stack selling commands.
- Added machine-start economy charges for maintenance and advanced assembler activation.
- Added `/stwallet`, `/stvalue`, `/stsell`, and `/stadmin economy <on|off|status>` command support.

### Feature Pass - Full Balancing Pass
- Added default balance tables for machine duration multipliers, tier speed scaling, fuel upkeep, economy maintenance, activation costs, sell values, and upgrade caps.
- Expanded economy charge fallback logic so refinery starts participate in the same advanced activation balancing as assemblers.
- Added `/stbalance` summary/reporting support for live inspection of the current tuning profile.
- Marked Feature Set D balance work complete in the tracker and documentation.
- Reworked machine processing to use active-machine lists with two processing buckets for lighter scheduler load.
- Added idle sleep behavior by removing inactive machines from active processing loops.

### Feature Pass - Priority Routing
- Added multi-route logistics support with per-route priorities.
- Added `/stlogistics addlink <x,y,z[,priority]>` and extended `setlink` to support priorities.
- Added best-route target selection for dispatch and buffer push operations.
- Added route count visibility to logistics info output.

### Feature Pass - Refinery Expansion
- Reworked the refinery into a multi-stage chain with `slag_slurry` token processing before `refined_flux` output.
- Added refinery-specific byproduct capture through `spent_filter` outputs on separation recipes.
- Updated recipe/item documentation and tracker coverage for staged refinery processing.

### Feature Pass - Fuel Progression and Auto-Refuel
- Added `heat_briquette` and `thermal_cell` as mid-game and late-game fuel items with new mixer and assembler recipes.
- Added machine auto-refuel support that can pull a remembered fuel item from linked virtual buffers.
- Added `/stmachine autofuel` and `/stadvanced autofuel` controls plus info/status visibility for preferred fuel mode.

### Feature Pass - Electrolyzer and Fabricator
- Added abstracted `machine_electrolyzer` recipes with split-output ion byproducts and heat-aware efficiency scaling.
- Added `machine_fabricator` recipes for long-duration Tier 3 complex parts.
- Added recipe-level quality bonus support so fabricator runs can upgrade outputs such as `pristine_matrix`.

### Feature Pass - Refinery and Advanced Chains
- Added `refinery` as an advanced machine type with dedicated machine recipes.
- Added new refined-material items and advanced assembly chain outputs.
- Added refinery processing flow to the advanced machine module and admin registration command.
- Expanded assembler chains with reinforced casing and control-core production paths.
