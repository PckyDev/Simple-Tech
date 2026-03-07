# Architecture and Data Model

This page is intended for maintainers and advanced server operators.

## Script Modules

- `st_00_core.sk` - shared utilities, config, onboarding, access helpers, balance defaults
- `st_01_items.sk` - item definitions and metadata helpers
- `st_02_recipes.sk` - recipe definitions, lookup, search, and metadata
- `st_03_gui.sk` - command-driven GUI and panel outputs
- `st_04_machines_basic.sk` - basic machine runtime
- `st_05_machines_advanced.sk` - advanced machine runtime
- `st_06_power_and_heat.sk` - fuel, heat, auto-refuel helpers
- `st_07_logistics.sk` - links, filters, routes, and buffers
- `st_08_world_interactions.sk` - environmental modifiers and chunk-safe behavior
- `st_09_balance_and_debug.sk` - recovery, migration, persistence, balance reporting, diagnostics

## Core Data Patterns

### Global Config

- `{st.config::*}`

Examples:

- feedback toggles
- economy toggles
- objective reminder settings
- balance values

### Player Data

- `{st.player::%uuid of player%::*}`

Examples:

- tier
- onboarding state
- objective stage
- tutorial completion

### Machine Data

- `{st.machine::%key%::*}`

Examples:

- type
- location
- active state
- progress
- remaining time
- output state
- upgrades
- access and ownership

### Recipe Data

- `{st.recipe::<type>::<id>::*}`

Examples:

- inputs
- outputs
- duration
- fuel cost
- byproduct info
- quality bonus info

### GUI Sessions

- `{st.gui::%uuid of player%::*}`

## Persistence and Recovery

Simple Tech supports:

- machine snapshots
- restore-on-load behavior
- schema version tracking
- migration checkpoints
- orphan cleanup
- metadata repair helpers

## Migration Model

The migration system includes:

- a target schema version
- recorded rollback checkpoint values
- applied migration step tracking
- legacy item normalization placeholder support

## Performance Model

Optimization features include:

- active machine lists instead of full-world scans
- bucketed processing intervals
- sleeping idle machines
- cached recipe lookup
- stale GUI cleanup
- periodic orphan cleanup

## Design Priorities

- parser-safe Skript structure
- conservative compatibility choices
- explicit logic over overly clever abstractions
- reload-safe state repair
