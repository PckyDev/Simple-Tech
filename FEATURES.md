# Simple Tech - Features Tracker

Use this file as the master implementation checklist for the Simple Tech ecosystem.

Architecture and module responsibilities are documented in [README.md](README.md).

## Module Crosswalk (README -> FEATURES)

- [x] `st_00_core.sk` -> Sections 1, 14, 16, 17
- [x] `st_01_items.sk` -> Sections 2, 5
- [x] `st_02_recipes.sk` -> Sections 3, 13
- [x] `st_03_gui.sk` -> Sections 4, 12
- [x] `st_04_machines_basic.sk` -> Sections 5, 6
- [x] `st_05_machines_advanced.sk` -> Sections 5, 7, 10
- [x] `st_06_power_and_heat.sk` -> Section 8
- [x] `st_07_logistics.sk` -> Section 9
- [x] `st_08_world_interactions.sk` -> Section 11
- [x] `st_09_balance_and_debug.sk` -> Sections 15, 18, 19, 20

## Recommended Build Order

- [x] Milestone 1: `st_00_core.sk`
- [x] Milestone 2: `st_01_items.sk`
- [x] Milestone 3: `st_02_recipes.sk`
- [x] Milestone 4: `st_03_gui.sk`
- [x] Milestone 5: `st_04_machines_basic.sk`
- [x] Milestone 6: `st_06_power_and_heat.sk`
- [x] Milestone 7: `st_05_machines_advanced.sk`
- [x] Milestone 8: `st_07_logistics.sk`
- [x] Milestone 9: `st_08_world_interactions.sk`
- [x] Milestone 10: `st_09_balance_and_debug.sk`

## Goal Tracking

- [ ] **MVP Goal Reached**
- [ ] **Beta Goal Reached**
- [ ] **Release Candidate Goal Reached**
- [ ] **v1.0 Goal Reached**

---

## 1) Core Framework

- [x] Core script architecture (`st_00_core` to `st_09`)
  - [x] Standardized variable naming and key schema
  - [x] Shared utility functions (messages, math, location keys)
  - [x] Standard error/fail message helpers
  - [x] Shared cooldown and permission helpers
- [x] Global config layer
  - [x] Default balancing values
  - [x] Toggle flags for modules
  - [x] Debug mode toggle
  - [x] Per-world enable/disable support
- [x] Reload-safe initialization
  - [x] Startup sanity checks
  - [x] Missing variable recovery
  - [x] Version migration placeholder

## 2) Custom Item System (Vanilla-Based)

- [x] Item registry system
  - [x] Item ID format and parser
  - [x] Display name + lore formatting standard
  - [x] Rarity/tier formatting standard
- [x] Item creation utilities
  - [x] Give item by ID
  - [x] Validate item by ID
  - [x] Convert/normalize legacy item metadata
- [x] Item categories
  - [x] Raw resources
  - [x] Intermediate materials (dusts/crushed/chunks)
  - [x] Components (plates/gears/rods/wires)
  - [x] Machine parts (casings/coils/frames)
  - [x] Upgrade items
  - [x] Utility tools (wrench/linker/meter)

## 3) Recipe System

- [x] Recipe registry
  - [x] Recipe IDs and lookup index
  - [x] Recipe type tagging
  - [x] Validation for malformed recipe data
- [x] Crafting recipes
  - [x] Shaped-style custom checks
  - [x] Shapeless-style custom checks
  - [x] Unlock requirements by tier
- [x] Machine recipes
  - [x] Single input -> output
  - [x] Multi-input processing
  - [x] Timed recipe handling
  - [x] Fuel/heat/energy cost support
  - [x] Byproduct output chances
- [x] Recipe UX
  - [x] Human-readable recipe descriptions
  - [x] Recipe search/filter hooks
  - [x] Missing requirement explanation

## 4) GUI Framework

- [x] Generic GUI framework
  - [x] Reusable border template
  - [x] Reusable navigation row
  - [x] Back/close conventions
- [x] Main Tech menu
  - [x] Category buttons
  - [x] Progression summary panel
  - [x] Quick links to machine help
- [x] Recipe browser GUI
  - [x] Pagination
  - [x] Search query input flow
  - [x] Filter by tier/category
  - [x] View recipe details page
- [x] Machine GUIs
  - [x] Input/output slot guide
  - [x] Progress indicator
  - [x] Fuel/heat/energy indicator
  - [x] Mode toggle buttons
- [x] Admin GUIs
  - [x] Balance settings menu
  - [x] Machine inspector menu
  - [x] Debug actions menu

## 5) Progression Tiers

- [x] Tier 0: Primitive tech
  - [x] Manual processing tools
  - [x] Intro materials and starter components
  - [x] Tutorial-style first recipes
- [x] Tier 1: Mechanical
  - [x] Basic machines unlocked
  - [x] Fuel-powered processing
  - [x] First automation hooks
- [x] Tier 2: Industrial
  - [x] Multi-step production chains
  - [x] New machine upgrades
  - [x] Byproducts and recycling loops
- [x] Tier 3: Advanced automation
  - [x] High-throughput processing
  - [x] Routing/filter logic
  - [x] Efficiency optimization systems

## 6) Basic Machines

- [x] Crusher
  - [x] Ore -> crushed ore recipes
  - [x] Progress timer
  - [x] Sound/feedback
- [x] Press
  - [x] Ingot -> plate recipes
  - [x] Component compression recipes
  - [x] Speed upgrade support
- [x] Mixer
  - [x] Two-input recipes
  - [x] Three-input advanced recipes
  - [x] Batch mode support
- [x] Smelter+
  - [x] Enhanced smelting recipes
  - [x] Optional bonus output chance
  - [x] Fuel efficiency modifier

## 7) Advanced Machines

- [x] Assembler
  - [x] Component-based crafted outputs
  - [x] Pattern memory slot
  - [x] Queue processing
- [x] Refinery
  - [x] Multi-stage material refinement
  - [x] Fluid-like abstraction via item tokens
  - [x] Byproduct capture
- [x] Electrolyzer (abstracted)
  - [x] Energy-gated recipes
  - [x] Split outputs
  - [x] Heat/efficiency interaction
- [x] Fabricator
  - [x] Late-game complex parts
  - [x] Long-duration processes
  - [x] Quality tier bonus system

## 8) Heat / Power / Fuel Systems

- [x] Unified machine power API
  - [x] Consume heat/fuel points
  - [x] Passive drain behavior
  - [x] Pause when unfueled
- [x] Heat system
  - [x] Heat generation from burners
  - [x] Heat buffers on machines
  - [x] Heat loss over time
- [x] Fuel handling
  - [x] Fuel value table
  - [x] Fuel byproduct behavior (ash/slag)
  - [x] Auto-refuel mode support
- [x] Power progression
  - [x] Primitive fuel stage
  - [x] Mid-game efficient fuels
  - [x] Late-game high-output fuel items

## 9) Logistics & Automation

- [x] Item transport abstraction
  - [x] Pull/push logic between machines
  - [x] Directional IO config
  - [x] Transfer rate limits
- [x] Filter system
  - [x] Whitelist mode
  - [x] Blacklist mode
  - [x] Tag/category filtering
- [x] Priority routing
  - [x] Preferred destination setting
  - [x] Overflow fallback behavior
  - [x] Loop prevention logic
- [x] Buffer blocks (virtual machine buffers)
  - [x] Input cache behavior
  - [x] Output cache behavior
  - [x] Throughput upgrades

## 10) Machine Upgrades

- [x] Upgrade item framework
  - [x] Speed upgrade
  - [x] Efficiency upgrade
  - [x] Yield/fortune upgrade
  - [x] Capacity upgrade
- [x] Upgrade slot validation
  - [x] Max stack per slot
  - [x] Tier requirements
  - [x] Incompatibility rules
- [x] Upgrade UI feedback
  - [x] Applied effects display
  - [x] Effective machine stats

## 11) World Interactions

- [x] Environmental modifiers
  - [x] Rain bonus/penalty for selected machines
  - [x] Biome-based efficiency modifiers (optional)
  - [x] Height/depth modifiers (optional)
- [x] Interaction recipes
  - [x] Washing via water interactions
  - [x] Heating via nearby fire/lava checks
  - [x] Cooling logic with water/snow
- [x] Chunk safety
  - [x] Behavior in unloaded chunks
  - [x] Resume behavior after chunk load

## 12) Player Experience & UX

- [x] In-game onboarding
  - [x] `/st help`
  - [x] First-use tutorial prompts
  - [x] Starter objective hints
  - [x] Completion-first objective notifications
  - [x] Next-objective lookup command
  - [x] Step-by-step objective instructions
  - [x] Full walkthrough command
- [x] Feedback systems
  - [x] Actionbar status updates
  - [x] Optional sound cues
  - [x] Chat notifications with concise wording
- [x] Accessibility/usability
  - [x] Consistent icon language in GUIs
  - [x] Clear error messages
  - [x] Confirmation for destructive actions

## 13) Economy & Balance Integration

- [x] Economy hooks (optional)
  - [x] Cost to craft/activate advanced machines
  - [x] Sell-value balancing for outputs
  - [x] Cooldown/maintenance costs
- [x] Throughput balancing
  - [x] Baseline processing times
  - [x] Tier multipliers
  - [x] Upgrade cap limits
- [x] Anti-exploit balance rules
  - [x] No free loops with byproducts
  - [x] No machine duplication exploits
  - [x] No item copy exploits in GUIs

## 14) Multiplayer Safety

- [x] Ownership and access rules
  - [x] Owner-only machine config
  - [x] Team/shared access support
  - [x] Public mode toggle
- [x] Concurrency safety
  - [x] Lock machine while processing state changes
  - [x] Prevent double-click race conditions
  - [x] Isolated GUI sessions per player
- [x] Grief prevention hooks
  - [x] Respect claim plugins if present
  - [x] Break protection for active machines
  - [x] Optional admin override command

## 15) Admin & Debug Tooling

- [x] Admin command suite
  - [x] Reload module state
  - [x] Give item by ID
  - [x] Inspect machine at target block
  - [x] Force-complete machine process (debug)
- [x] Debug dashboards
  - [x] Active machine count
  - [x] Processing queue stats
  - [x] Tick/load monitoring snapshot
- [x] Audit logs (optional)
  - [x] Machine placement logs
  - [x] Admin action logs
  - [x] Error event logs

## 16) Persistence & Migrations

- [x] Machine state persistence
  - [x] Save processing progress
  - [x] Save upgrade/loadout state
  - [x] Save mode/config state
- [x] Versioned data migration
  - [x] Data schema version key
  - [x] Migration handler skeleton
  - [x] Rollback fallback plan
- [x] Recovery tools
  - [x] Cleanup orphan machine entries
  - [x] Repair invalid metadata entries

## 17) Performance Optimization

- [x] Processing scheduler improvements
  - [x] Active-machine list instead of world scan
  - [x] Bucketed processing intervals
  - [x] Idle machine sleep mode
- [x] Recipe lookup optimization
  - [x] Cached lookup table
  - [x] Fast path for common recipes
  - [x] Invalidation on reload
- [x] Memory cleanup
  - [x] Remove stale GUI session vars
  - [x] Remove stale machine references
  - [x] Periodic cleanup task

## 18) QA & Test Coverage

- [x] Manual test plans
  - [x] Item creation tests
  - [x] Recipe validity tests
  - [x] Machine chain tests
  - [x] GUI interaction tests
- [x] Edge case tests
  - [x] Full inventory outputs
  - [x] Machine broken mid-process
  - [x] Reload during active processing
  - [x] Multiple users same machine
- [x] Regression checklist
  - [x] No dupe bugs
  - [x] No item deletion bugs
  - [x] No stuck machine states

## 19) Feature Sets / Milestones

- [x] **Feature Set A - Core Tech Loop (MVP)**
  - [x] Item registry
  - [x] Recipe registry
  - [x] Main GUI + recipe browser
  - [x] Crusher + Press + Mixer
  - [x] Basic fuel system
- [x] **Feature Set B - Industrial Expansion (Beta)**
  - [x] Assembler + Refinery
  - [x] Upgrade framework
  - [x] Basic logistics/filtering
  - [x] Advanced recipe chains
- [x] **Feature Set C - Automation Depth (RC)**
  - [x] Priority routing
  - [x] Throughput balancing
  - [x] Ownership/access controls
  - [x] Admin diagnostics
- [x] **Feature Set D - Polish & Stability (v1.0)**
  - [x] Full balancing pass
  - [x] Documentation complete
  - [x] Performance pass complete
  - [x] QA regression checklist complete
- [x] **Feature Set E - Onboarding UX Refresh**
  - [x] Passive objective reminders disabled by default
  - [x] Objective-complete -> next-objective messaging
  - [x] `/st objective next` support
  - [x] Tutorial command/status wording cleanup
  - [x] Clear step-by-step primitive loop guidance
  - [x] Primitive hammer onboarding step

## 20) Documentation

- [x] Keep README architecture section current
- [x] Add module-level comments/headers in every script
- [x] Add command reference page
- [x] Add item and recipe index docs
- [x] Add changelog for each feature set completion

---

## Notes

- Keep this file updated as the single source of truth for build progress.
- When a subfeature is complete, check it off immediately.
- If scope changes, add new items under the correct section and date-tag major additions.
