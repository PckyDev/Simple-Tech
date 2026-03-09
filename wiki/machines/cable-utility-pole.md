# Cable Utility Pole

## Summary
- **Tier:** Mechanical
- **Base block:** Mud Brick Wall
- **Purpose:** Routes Cable connections through a tall pole with up to `3` connection points

## Crafting Recipe
```text
[Spruce Fence]    [Copper Shaft] [Spruce Fence]
[Spruce Trapdoor] [Copper Frame] [Spruce Trapdoor]
[Empty]           [Mud Brick Wall] [Empty]
```

## Placement
1. Place the Cable Utility Pole on the ground.
2. The pole builds upward from its base.
3. The top crossbar is rotated to match the direction you are looking when placing it.

## Height Control
1. Look directly at the pole base.
2. Scroll the hotbar to change the pole height.
3. The top section moves up or down without rebuilding the entire pole.

## Rules
- The pole can be resized from height `1` up to height `5`.
- Placement fails if there is not enough empty space for the full structure.
- Resizing also fails if the new height would overlap other blocks.
- The pole can keep attached Cable connections while being resized.

## Cable Routing
- The pole provides `3` top fence connection points.
- Each top fence can hold `1` Cable connection.
- Cables can connect machines through the pole instead of only directly machine-to-machine.
- This is useful for routing power from a [Water Wheel](water-wheel.md) to one or more nearby machines.

## Breaking Behavior
- Breaking the base breaks the entire pole and drops the Cable Utility Pole item.
- Breaking a top fence only disconnects the Cable on that port.
- Breaking connected machines still returns their attached Cable items.

## Notes
- The top uses spruce fences and spruce trapdoors as the crossbar.
- The structure builds with a short animation.
- The Cable visual line moves with the pole when the height changes.