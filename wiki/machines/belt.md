# Belt

## Summary
- **Tier:** Mechanical
- **Base block:** Deepslate Tile Slab
- **Held item appearance:** Netherite Nautilus Armor
- **Purpose:** Moves dropped items horizontally in a straight line

## Crafting Recipe
```text
[Dried Kelp] [Dried Kelp]   [Dried Kelp]
[Dried Kelp] [Copper Shaft] [Dried Kelp]
[Empty]      [Empty]        [Empty]
```

## Placement
1. Hold the Belt item.
2. Right-click a ground block to set the first position.
3. Right-click another ground block to set the second position.
4. The Belt builds in the air blocks above those positions.

## Placement Rules
- Belts currently only build in a straight horizontal line.
- Diagonal placement is not supported.
- Both points must be on the same `Y` level.
- The path must be clear.
- Each Belt segment needs solid ground underneath.
- Belts cannot be built over water.
- Building costs `1 Belt` item per placed block.

## Transport
- Dropped items placed on the Belt are carried along its direction.
- Straight runs move items continuously along the line.
- Turns are supported by changing the direction of the next Belt segment.
- The Belt can feed items directly into nearby processing setups such as the [Press](press.md).

## Direction Control
- Look at a Belt segment to see an arrow on top of it.
- Right-click a Belt segment to reverse its direction.
- Each segment stores a direction used for item movement.

## Notes
- Belt segments break individually and return the Belt item.
- The build animation places segments one by one.
- Belt arrows are shown with flat text displays on top of the segments.
