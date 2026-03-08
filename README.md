<p align="center">
	<img src="https://github.com/PckyDev/Simple-Tech/blob/main/src/branding/logo.png?raw=true" />
</p>

A modular Skript-based tech ecosystem for vanilla Minecraft servers.

Simple Tech adds automation, processing chains, power-like progression, and utility systems based on vanilla redstone mechanics **without custom textures or custom blocks**. It uses vanilla blocks/items plus custom names, lore, recipes, metadata, and GUIs to create a scalable tech experience.

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
- Everything must be representable with vanilla items/blocks, holograms, block displays, and Skript logic.

### Design inspirations
- Create mod: approachable mechanical progression and transport/processing feel.

---

## 2) Design Philosophy

Simple Tech should feel like “what vanilla might look like with light industrial gameplay.”

### Principles
- **Readable:** every machine/item has clear purpose and in-game description.
- **Composable:** outputs from one machine become inputs to others.
- **Tiered:** early game is cheap and simple, late game is efficient and complex.
- **Consistent:** same naming, GUI patterns, and recipe language everywhere.
- **Safe:** no irreversible actions without confirmation/feedback.
- **Low-noise onboarding:** tutorial guidance appears at meaningful milestones.

---

## 3) Technical Approach (Skript)

Because we are not adding real custom blocks, “machines” are represented by:
- A placed vanilla block (machine base).
- Look at the block to show a hologram above it with the machine name, progress, and status.
- Right click the block to open a custom GUI with input/output slots, progress bars, and action buttons.
- Optional marker item in the block name/lore or linked variable data.
- Interaction handlers (right-click, inventory click, break/place, hopper events).
- Per-machine state in variables (progress, buffers, upgrades, owner, mode).

### Data model patterns
- Global settings: `{st.config::*}`
- Per-player: `{st.player::%uuid of player%::*}`
- Per-machine by location: `{st.machine::%world%:%x%:%y%:%z%::*}`
- Recipe cache/indexes: `{st.recipe::<type>::<id>::*}`
- GUI session state: `{st.gui::%uuid of player%::*}`

### Naming and audio/visual conventions
- Prefix all options/variables/functions with `st`.
- Use lowercase snake-like keys for IDs: `crushed_iron`.
- Use Title Case for display names: `Crushed Iron`.
- Items have enchant glint to distinguish them from vanilla items, but no custom textures.
- GUIs have consistent color schemes and slot patterns.
- Use satisfying sound effects for interactions (e.g. anvil sounds for pressing, furnace sounds for smelting).
- Use particle effects for interactions (e.g. smoke for burning, sparks for pressing).

---

## 4) Planned Folder Structure

```text
simple tech/
	wiki/
		... (documentation and guides for players and admins)
	apis/
		... (reusable systems for all scripts, like power/heat/fuel management, logistics routing, etc.)
	items/
		... (item definition scripts, one skript per item, includes recipe definitions that produce the item)
	machines/
		... (machine logic scripts, one skript per machine, includes recipe definitions that create the machine, processing logic, GUI handling, interaction handlers, upgrade logic, etc.)
	
	README.md
	core.sk (core utilities, common options, message formatting, permission checks)
```

---

## 5) Progression Model

### Tier 0: Primitive Tech
- Manual processing.
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
- Enchant glow/glint (hidden enchants)
- Persistent ID in lore or stored identification strategy

### Rules
- Every custom item must have:
    - `id`
	- human-readable `name`
	- `tier`
	- short `description`
- No two items share the same `id`.

---

## 7) Current Prototype Content

### Primitive crushing
- `Hammer`
	- Uses the vanilla mace appearance.
	- Crafted from iron ingots and sticks.
	- Cannot be used as a weapon.
	- Used in an anvil to crush raw ores and flatten ingots.
- `Crushed Iron`
	- Made by combining a hammer with `Raw Iron` in an anvil.
	- Produces `2x Crushed Iron`.
	- Can be smelted into `Iron Ingot` with custom furnace progress and flame behavior.
- `Crushed Gold`
	- Made by combining a hammer with `Raw Gold` in an anvil.
	- Produces `2x Crushed Gold`.
	- Can be smelted into `Gold Ingot` with custom furnace progress and flame behavior.
- `Crushed Copper`
	- Made by combining a hammer with `Raw Copper` in an anvil.
	- Produces `2x Crushed Copper`.
	- Can be smelted into `Copper Ingot` with custom furnace progress and flame behavior.

### Primitive plates
- `Iron Plate`
	- Made by combining a hammer with an `Iron Ingot` in an anvil.
	- Uses the vanilla iron pressure plate appearance.
- `Gold Plate`
	- Made by combining a hammer with a `Gold Ingot` in an anvil.
	- Uses the vanilla gold pressure plate appearance.
- `Copper Plate`
	- Made by combining a hammer with a `Copper Ingot` in an anvil.
	- Uses the vanilla acacia pressure plate appearance.

### Mechanical components
- `Hand Crank`
	- Crafted from `1x Iron Plate` and `1x Stick`.
	- Attaches to machines to provide manual stored power.
	- Uses the vanilla lever appearance.
- `Iron Frame`
	- Crafted from 8 `Iron Ingots` in a ring.
	- Uses the vanilla iron bars appearance.
- `Copper Frame`
	- Crafted from 8 `Copper Ingots` in a ring.
	- Uses the vanilla copper grate appearance.
- `Iron Shaft`
	- Crafted from 3 `Iron Plates` in a vertical line.
	- Uses the vanilla chain appearance.
- `Copper Shaft`
	- Crafted from 3 `Copper Plates` in a vertical line.
	- Uses the vanilla copper chain appearance.

### First machine
- `Press`
	- Crafted from `Iron Plates`, `Iron Frames`, `Iron Shafts`, and a `Piston`.
	- Placeable machine based on the vanilla piston block.
	- Can have a `Hand Crank` attached to store up to 32 power.
	- When supplied with enough stored power, it processes dropped items in front of the machine.
	- `Iron / Gold / Copper Ingots` become `2x Plates`.
	- `Raw Iron / Raw Gold / Raw Copper` become `4x Crushed Ore`.
