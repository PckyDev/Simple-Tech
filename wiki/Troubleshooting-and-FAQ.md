# Troubleshooting and FAQ

This page answers the most common confusion points in the current Simple Tech experience.

## I can't figure out how to get `primitive_hammer`

Start here:

1. check your hotbar
2. check the rest of your inventory
3. first-time players should receive one automatically

If it is missing and you need a replacement:

- hold `raw_iron` in your hand
- keep `stick` in your inventory
- sneak-right-click a crafting table
- recipe ID: `primitive_hammer_recipe`
- inspect it with `/strecipe view crafting_shaped primitive_hammer_recipe`

If you are testing as admin:

- `/stitem give primitive_hammer 1`

## I have the hammer, but step 3 still makes no sense

To make `crushed_iron`:

1. hold `primitive_hammer`
2. keep `raw_iron` in your inventory
3. sneak-right-click a grindstone

To make `iron_plate`:

1. hold `primitive_hammer`
2. keep `2 crushed_iron` in your inventory
3. sneak-right-click an anvil

## How do I inspect an exact recipe?

Use:

- `/strecipe list`
- `/strecipe list <type>`
- `/strecipe view <type> <id>`
- `/strecipe search <query>`

Examples:

- `/strecipe view crafting_shaped primitive_hammer_recipe`
- `/strecipe view crafting_shapeless iron_plate_manual`

## What does `crafting_shaped` mean here?

In the recipe registry, `crafting_shaped` means the ingredient order matters.

Example:

- `primitive_hammer_recipe` = hold `raw_iron`, carry `stick`, then sneak-right-click a crafting table

## What does `crafting_shapeless` mean here?

It means the ingredients only need to be present together. Order does not matter.

Example:

- `iron_plate_manual` = `crushed_iron` + `crushed_iron`

## Which pages should I read first?

- [Getting Started](Getting-Started.md)
- [Recipes and Processing](Recipes-and-Processing.md)
- [Machines](Machines.md)
- [Commands and Administration](Commands-and-Administration.md)