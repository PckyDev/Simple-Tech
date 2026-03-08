# Press

## Summary
- **Tier:** Mechanical
- **Base block:** Piston
- **Purpose:** Uses stored manual power to process dropped items placed in front of it

## Crafting Recipe
```text
[Iron Plate] [Iron Shaft] [Iron Plate]
[Iron Frame] [Piston]     [Iron Frame]
[Iron Plate] [Iron Shaft] [Iron Plate]
```

## Setup
1. Place the Press.
2. Right-click it with a [Hand Crank](../items/hand-crank.md) to attach the crank.
3. Drop the input item on the ground in front of the Press.
4. Right-click the Press to add power.
5. When enough power is stored, the Press will process one input.

## Automation
- The Press can also receive power from a [Water Wheel](water-wheel.md) through a [Cable](../items/cable.md).
- Automatic power is transferred in small increments over time instead of by manual clicks.
- Only one Cable can be connected to a Press at once.

## Power
- Stores up to `32` power.
- Uses `4` power per completed press.

## Recipes
### Ingot Pressing
- `Iron Ingot` → `2x Iron Plate`
- `Gold Ingot` → `2x Gold Plate`
- `Copper Ingot` → `2x Copper Plate`

### Ore Crushing
- `Raw Iron` → `4x Crushed Iron`
- `Raw Gold` → `4x Crushed Gold`
- `Raw Copper` → `4x Crushed Copper`

## Notes
- The Press doubles the manual Hammer output for supported recipes.
- It currently processes dropped items directly in front of the machine.
- Breaking the Press returns the Press item, and also returns the attached Hand Crank if one is installed.
- If the Press is connected by Cable, breaking it also returns the Cable.
