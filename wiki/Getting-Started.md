# Getting Started

This page explains the early Simple Tech experience for players.

## First-Time Flow

When a player joins for the first time, Simple Tech:

- welcomes them
- points them to `/st help`
- initializes their starter objective track
- shows the current objective once

The onboarding flow is intentionally low-noise.

## Starter Objectives

Use these commands at any time:

- `/st objective`
- `/st objective current`
- `/st objective next`
- `/st objective walkthrough`
- `/st objective status`

### Objective Track

1. Collect `raw_iron`
2. Find and hold your `primitive_hammer`
3. Use `primitive_hammer` on a grindstone to obtain `crushed_iron`
4. Use `primitive_hammer` on an anvil with 2 `crushed_iron` to create `iron_plate`
5. Run `/st progress`

After each completed objective, the system announces completion and tells the player the next step.

The objective command now includes clear step-by-step instructions instead of only naming the target item.

If a player wants the full sequence in one place, `/st objective walkthrough` prints the entire primitive tutorial from start to finish.

## Starter Tool

On first join, players receive a starter `primitive_hammer` to avoid a dead-end in the tutorial.

The tutorial now explicitly stops and asks the player to locate and hold that hammer before the first grindstone interaction.

If it is lost, a replacement can be crafted from:

- `raw_iron`
- `stick`

## Exactly How to Get a Primitive Hammer

There are two normal ways to get one.

### Method 1: First join starter kit

When a player joins for the first time, Simple Tech gives them:

- `primitive_hammer` x1

So the first thing to do is:

1. check your hotbar
2. if it is not there, check the rest of your inventory
3. put `primitive_hammer` in your hand

### Method 2: Replacement craft

The replacement recipe is:

- `raw_iron`
- `stick`

Recipe ID:

- `primitive_hammer_recipe`

Important note:

- this uses the Simple Tech manual crafting flow, not the vanilla crafting table grid
- hold `raw_iron` in your hand
- keep `stick` somewhere in your inventory
- sneak-right-click a crafting table
- because it is `crafting_shaped`, the documented order matters: `raw_iron` first, `stick` second

If you are unsure, use:

- `/strecipe view crafting_shaped primitive_hammer_recipe`

to inspect the exact registered recipe.

## Exactly How to Use the Primitive Hammer

### To make `crushed_iron`

1. keep at least 1 `raw_iron` anywhere in your inventory
2. hold `primitive_hammer` in your hand
3. sneak-right-click a grindstone
4. you should receive `crushed_iron`

### To make `iron_plate`

1. keep at least 2 `crushed_iron` anywhere in your inventory
2. hold `primitive_hammer` in your hand
3. sneak-right-click an anvil
4. you should receive `iron_plate`

## If You Still Cannot Get One

Check these in order:

1. did you already receive the starter one on first join?
2. are you looking for the item ID `primitive_hammer` specifically?
3. did you lose it and need a replacement?
4. did you inspect the recipe with `/strecipe view crafting_shaped primitive_hammer_recipe`?
5. are you using the Simple Tech manual crafting flow instead of the vanilla crafting-table UI?

If you are testing as admin and just want one immediately:

- `/stitem give primitive_hammer 1`

## Important UX Change

Passive reminder spam is disabled by default.

That means players are not repeatedly pinged in chat to do the same objective. Instead, they are told:

- when an objective is completed
- what the next objective is
- how to check status manually

## First Useful Commands

- `/st help` - main entry point
- `/st status` - quick system summary
- `/st progress` - progression overview
- `/st objective next` - see the upcoming task
- `/st recipes` - browse available recipes
- `/strecipe search <query>` - search recipes directly

## Early Primitive Loop

The intended first loop is:

- collect raw iron
- find or craft `primitive_hammer`
- sneak-right-click a grindstone while raw iron is in your inventory
- sneak-right-click an anvil while 2 crushed iron are in your inventory
- create `iron_plate`
- review progress

## Early Goals After Tutorial

Once the starter objectives are done, the player should move toward:

- placing a crusher, press, mixer, or smelter
- creating `machine_casing`
- learning fuel and heat buffers
- building the first mechanical processing chain

## Tips for Server Owners

If you want the old reminder behavior back, objective reminders can be re-enabled in data by setting:

- `{st.config::objective::reminders}` to `true`

Default behavior is `false`.
