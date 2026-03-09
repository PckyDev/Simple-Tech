# Water Wheel

## Summary
- **Tier:** Mechanical
- **Base item:** Barrel
- **Purpose:** Generates mechanical power from nearby water

## Crafting Recipe
```text
[Empty]         [Iron Shaft] [Empty]
[Spruce Stairs] [Barrel]     [Spruce Trapdoor]
[Empty]         [Iron Frame] [Empty]
```

## Placement
1. Place the Water Wheel on a block beside a shoreline.
2. The block below the placed piece becomes the support block.
3. The machine searches for adjacent water.
4. If placement is valid, it builds a 3-part structure:
   - spruce stairs at the placed block
   - barrel facing the water
   - spruce trapdoor on the far side

## Power Output
- Produces power only while valid adjacent water is present.
- Sends `1` power every `10` ticks through a connected [Cable](../items/cable.md).
- Currently outputs to the [Press](press.md).

## Connection Setup
1. Craft a [Cable](../items/cable.md).
2. Right-click the Water Wheel.
3. Right-click a [Press](press.md) within `10` blocks, or route the connection through a [Cable Utility Pole](cable-utility-pole.md).

## Notes
- If any part of the multiblock is broken, the whole Water Wheel breaks.
- Breaking the machine returns the Water Wheel item.
- Connected Cables are dropped back if the machine is removed.
- The machine shows status text when looked at in-game.
- Water Wheels are commonly paired with a [Press](press.md), [Belt](belt.md), and [Cable Utility Pole](cable-utility-pole.md) for cleaner automation layouts.
