# Cable

## Summary
- **Tier:** Mechanical
- **Base item:** Lead
- **Purpose:** Connects a power source to a compatible machine

## Crafting Recipe
```text
[Empty]  [String]     [Empty]
[String] [Iron Shaft] [String]
[Empty]  [String]     [Empty]
```

## Uses
1. Hold the Cable.
2. Right-click the first machine to mark the start.
3. Right-click the second machine to complete the link.

## Current Rules
- One Cable connects exactly two machines.
- Maximum link range is `10` blocks.
- A machine can only be part of one Cable link at a time.
- Breaking a connected machine drops the Cable back.

## Current Machine Support
- **Power source:** [Water Wheel](../machines/water-wheel.md)
- **Power receiver:** [Press](../machines/press.md)

## Notes
- The Cable uses the vanilla lead appearance.
- A visual lead line appears between connected machines.
- If either end becomes invalid, the connection is removed.
