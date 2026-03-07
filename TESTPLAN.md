# Simple Tech Manual Test Plan

## 2026-03-07

This document tracks the current manual validation checklist for Simple Tech.

---

## 1) Item Creation Tests

- Give each core item with `/stitem give <id>`.
- Confirm display name, lore, and ID detection are correct.
- Create or keep one older-format Simple Tech item, run `/stitem normalize`, and confirm the held item is rebuilt with current lore and still resolves to the same ID.
- Verify `primitive_hammer`, `tech_wrench`, `throughput_upgrade_1`, `speed_upgrade_1`, `efficiency_upgrade_1`, `yield_upgrade_1`, and `capacity_upgrade_1` resolve to the expected item IDs.
- Confirm `slag` and `ash` remain identifiable after drop/pickup cycles.

## 2) Recipe Validity Tests

- Run `/strecipe validate` and confirm no invalid entries are reported.
- Test at least one recipe from each category:
  - `crafting_shaped`
  - `machine_crusher`
  - `machine_press`
  - `machine_mixer`
  - `machine_smelter`
  - `machine_assembler`
- Confirm 2-input and 3-input machine recipes match the expected output.
- Confirm cached lookup behavior still returns the same recipe after `/stadmin reload-state recipes`.
- Confirm Simple Tech crafting recipes appear and complete through the normal 3x3 crafting-table grid.
- Confirm `primitive_hammer_recipe` only matches the full hammer silhouette.
- Confirm `iron_plate_manual` only matches the 2x2 crushed-iron plate pattern.
- Confirm recipes with blanks fail if extra items are placed in required empty cells.
- Confirm each machine kit recipe creates the expected placeable machine item.
- Confirm finishing the starter objective track promotes the player to Tier 1.
- Confirm obtaining `reinforced_casing` or `control_core` promotes the player to Tier 2.
- Confirm obtaining `electrolyzer_kit`, `charged_mesh`, or `electrolyte_gel` promotes the player to Tier 3.

## 3) Machine Chain Tests

- Primitive loop: raw iron -> crushed iron -> iron plate.
- Mechanical loop: crusher -> press -> mixer, and confirm the press returns `iron_plate x2` and `copper_coil x2` while the mixer returns `machine_casing x2` and `heat_briquette x3`.
- Smelter loop: crushed input -> smelter output -> optional `slag` recovery path, and confirm `raw_copper_chunk` now returns `copper_wire x3`.
- Advanced loop: assembler queue with at least two valid recipes, and confirm the reduced assembly durations/fuel costs apply for `wrench_assembly`, `meter_assembly`, and one Tier 2 or Tier 3 assembly.
- Place each basic machine kit and confirm the block auto-registers as the matching machine.
- Break each placed machine and confirm the correct machine kit is returned.
- Refinery loop: `slag` -> `slag_slurry` -> `refined_flux`, and confirm prep now returns `slag_slurry x2`, the cheaper separation/treating timings complete correctly, and `spent_filter` appears from the separation stage.
- Fuel loop: craft `heat_briquette`, craft `thermal_cell`, and confirm their fuel buffers exceed coal/blaze-rod values.
- Electrolyzer loop: process `slag_slurry` and `copper_coil`, then confirm `electrolyte_gel x2`, `charged_mesh x1`, and `ion_fragment` byproducts appear.
- Fabricator loop: craft `fabrication_matrix` and `precision_lens`, confirm the shorter advanced timings apply, and repeat until at least one `pristine_matrix` quality-bonus result appears.
- Logistics loop: machine output -> linked buffer -> linked machine.

## 4) GUI Interaction Tests

- Open `/st`, `/st progress`, `/st status`, and `/st recipes`.
- Run `/st objective`, `/st objective next`, `/st objective walkthrough`, and `/st objective status`; confirm they show the current step, next step, full tutorial sequence, and onboarding state without spamming repeated hints.
- Verify the tutorial clearly explains the primitive loop: grindstone for `raw_iron -> crushed_iron`, then anvil for `2 crushed_iron -> iron_plate`.
- Confirm the tutorial now includes a separate "find and hold the Primitive Hammer" step before asking the player to use it.
- Join as a new player and confirm you receive a starter `primitive_hammer` exactly once.
- Open `/st machine` while targeting both a basic machine and an advanced machine; confirm the panel shows recipe guide, progress, and fuel/heat or fuel/energy details.
- Open `/st admin balance`, `/st admin inspect`, and `/st admin debug`; confirm the balance shortcuts, machine inspector data, and debug action list render correctly.
- Confirm page navigation with `/stnext` and `/stprev`.
- Confirm recipe filter modes:
  - `/st recipes tier <n>`
  - `/st recipes type <type>`
  - `/strecipe search <query>`
- Confirm icon language is consistent across menu and recipe outputs.
- Confirm inventory click/drag does not allow item movement in any Simple Tech titled menu.

## 5) Edge Case Tests

### Full inventory outputs
- Fill player inventory and trigger outputs that drop to the world or dispatch to logistics.
- Confirm no duplicated or silently deleted items occur.

### Machine broken mid-process
- Start a machine, then attempt removal with and without admin override.
- Confirm normal players are blocked and admin override path is explicit.

### Reload during active processing
- Start active basic and advanced machines.
- Reload scripts/server state.
- Confirm snapshot restore preserves progress, recipe, upgrades, and mode/config state.

### Multiple users same machine
- Have two players interact with the same machine in quick succession.
- Confirm locks prevent duplicate starts or double consumption.
- Confirm ownership and shared/public rules behave correctly.

## 6) Regression Checklist

- No dupe bugs during repeated starts, reloads, or break/re-register cycles.
- No item deletion bugs when machine output cannot enter logistics.
- No stuck machine states after fuel pause, chunk unload, reload, or cleanup/repair.
- No stale GUI session buildup after players disconnect.
- No stale machine references remain after orphan cleanup or integrity checks.

## 7) Recovery and Admin Validation

- Run `/stadmin recover status`.
- Confirm `/stadmin recover status` shows the last applied migration step and the legacy item normalizer command.
- Run `/stadmin recover cleanup` on intentionally orphaned data.
- Run `/stadmin recover repair` on intentionally incomplete metadata.
- Run `/stadmin recover migrate` and confirm schema version remains stable.
- Confirm rollback checkpoint fields are populated in data variables after migration checks.

## 8) Balance Validation

- Run `/stbalance` and confirm duration, upkeep, economy, and upgrade-cap summary lines are populated.
- Run `/stbalance duration::machine::assembler` and confirm the current value matches the summary output.
- Change one value with `/stbalance duration::machine::assembler 1.2`, verify the new report output, then restore the default.
- Enable economy hooks with `/stadmin economy on` and confirm `/stadmin economy status` mirrors the current balance profile.
- Sell `slag`, `refined_flux`, and one advanced crafted component to confirm configured sell values scale upward with progression.

## 9) Auto-Refuel Validation

- Link a machine to a virtual buffer containing only `heat_briquette`.
- Run `/stmachine autofuel on` or `/stadvanced autofuel on`, then add one `heat_briquette` manually to teach the preferred fuel ID.
- Drain the machine fuel buffer and confirm it automatically consumes one linked-buffer fuel item and resumes running.
- Repeat with `thermal_cell` on an advanced machine and confirm the preferred fuel shown in the info/status output updates correctly.
