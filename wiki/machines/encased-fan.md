````markdown
# Encased Fan

## Summary
- **Tier:** Mechanical
- **Base item:** Copper Bulb
- **Purpose:** Produces directional air when powered

## Crafting Recipe
```text
[Empty]           [Spruce Trapdoor] [Empty]
[Spruce Trapdoor] [Copper Frame]    [Spruce Trapdoor]
[Empty]           [Spruce Trapdoor] [Empty]
```

## Placement
1. Place the Encased Fan on a block.
2. The machine uses the direction you are looking to choose its output face.
3. Looking up or down while placing can make the fan blow vertically.
# Encased Fan

## Summary
- **Tier:** Mechanical
- **Base item:** Copper Bulb
- **Purpose:** Produces directional air when powered

## Crafting Recipe
```text
[Empty]           [Spruce Trapdoor] [Empty]
[Spruce Trapdoor] [Copper Frame]    [Spruce Trapdoor]
[Empty]           [Spruce Trapdoor] [Empty]
```

## Placement
1. Place the Encased Fan on a block.
2. The machine uses the direction you are looking to choose its output face.
3. Looking up or down while placing can make the fan blow vertically.

## Structure
- The center block is the machine core.
- The output face uses a **Waxed Copper Trapdoor**.
- The other faces use **Spruce Trapdoors**.
- Adjacent fans can be placed directly beside each other.

## Power
- The fan must be connected to mechanical power through a [Cable](../items/cable.md).
- Power can come from a [Water Wheel](water-wheel.md).
- Machines placed directly next to each other automatically share the same cable network.
- This means a row of touching fans only needs one direct cable connection.

## Air Modes
Open the fan GUI and place one of these in the center slot:

- **Empty:** normal air
- **Water Bucket:** wet air
- **Lava Bucket:** hot air

The core block changes to match the selected mode.

## Normal Air
- Pushes dropped items in the output direction.
- Higher available power increases the effective range.
- The current range is shown in the machine hologram.

## Wet Air
- Produces wet airflow particles.
- Useful for alternate fan setups and future processing behavior.

## Hot Air
- Produces hot airflow particles.
- Can smelt dropped items placed in front of the fan.
- Smelting speed increases with fan strength.
- Entire dropped stacks are processed at once when the cook time is reached.
- Items can keep heating progress while traveling through multiple hot-air fans, such as across a [Belt](belt.md).
- Supports vanilla furnace-style outputs plus Simple Tech crushed ore smelting.

## Smelting Support
Examples include:
- raw ores into ingots
- food into cooked food
- sand into glass
- cactus into green dye
- crushed iron, gold, and copper into ingots

## Notes
- Trapdoor sides cannot be opened normally.
- Full blocks can replace side trapdoors if needed for compact builds.
- Breaking any fan part breaks the full machine and drops the Encased Fan item.
- Stored water or lava is also returned when the machine is broken.