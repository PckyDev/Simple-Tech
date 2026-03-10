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
- One Cable connects exactly two endpoints.
- Maximum link range is `10` blocks.
- Most machine endpoints can only be part of one Cable link at a time.
- A [Cable Utility Pole](../machines/cable-utility-pole.md) can hold up to `3` Cable connections, one on each top port.
- Machines placed directly next to each other automatically chain into the same power network.
- Because of that, only one machine in a touching group needs a direct Cable connection.
- Breaking a connected machine drops the Cable back.

## Current Machine Support
- **Power source:** [Water Wheel](../machines/water-wheel.md)
- **Power receiver:** [Press](../machines/press.md)
- **Power receiver:** [Encased Fan](../machines/encased-fan.md)
- **Relay / routing:** [Cable Utility Pole](../machines/cable-utility-pole.md)

## Notes
- The Cable uses the vanilla lead appearance.
- A visual lead line appears between connected machines.
- Cable Utility Poles can be used to reroute and organize Cable lines.
- Touching machines can share power without additional Cable links between each machine.
- If either end becomes invalid, the connection is removed.
