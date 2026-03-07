# Simple Tech Command Reference

## Player Commands

- `/st`
  - Opens main Simple Tech menu/help panel.
- `/st help`
  - Shows main menu/help panel.
- `/st status`
  - Shows progression and registry summary.
- `/st progress`
  - Shows progression summary panel (tier, recipe/item counts, machine counts).
- `/st objective [current|next|walkthrough|status]`
  - Shows your current starter objective, previews the next one, displays the full walkthrough, or shows onboarding status.
- `/st machine`
  - Opens a command-driven machine panel for the targeted machine block.
- `/st admin <balance|inspect|debug>`
  - Opens command-driven admin panels for balance shortcuts, machine inspection, or debug actions.
- `/st recipes [query]`
  - Opens paged recipe browser (command-driven view).
- `/st recipes tier <0-3>`
  - Filters recipe browser by unlock tier.
- `/st recipes type <recipe_type>`
  - Filters recipe browser by recipe type (for example `machine_press`).
- `/stnext`
  - Next page in current paged view.
- `/stprev`
  - Previous page in current paged view.
- `/strecipe list [type]`
  - Lists recipe types or recipes under a type.
- `/strecipe view <type> <id>`
  - Displays detailed recipe information.
- `/strecipe search <query>`
  - Searches recipes by key/description.
- `/stwallet`
  - Shows your current Simple Tech credit balance when economy hooks are enabled.
- `/stvalue`
  - Shows the sell value of the item currently held in your hand.
- `/stsell [amount]`
  - Sells the held item stack, or part of it, for configured credits.

## Item Commands

- `/stitem list`
  - Lists registered custom item IDs.
  - Permission: `simpletech.items`
- `/stitem give <id> [amount]`
  - Gives a registered custom item.
  - Permission: `simpletech.admin`
- `/stitem normalize`
  - Rebuilds the held Simple Tech item to the current metadata format.
  - Permission: `simpletech.items`

## Basic Machine Commands

- `/stmachine set <crusher|press|mixer|smelter>`
  - Registers target block as a basic machine.
  - Permission: `simpletech.admin`
- `/stmachine remove`
  - Removes target basic machine.
  - Permission: `simpletech.admin`
- `/stmachine info`
  - Shows target basic machine state.
- `/stmachine autofuel <on|off|status>`
  - Toggles or inspects buffer-backed auto-refuel mode for the targeted basic machine.
- `/stmachine list`
  - Lists registered basic machines.

Mixer note:
- Sneak-right-click a mixer with `tech_wrench` to toggle between `single` and `batch` mode.

## Advanced Machine Commands

- `/stadvanced set <assembler|refinery|electrolyzer|fabricator>`
  - Registers target block as an advanced machine.
  - Permission: `simpletech.admin`
- `/stadvanced remove`
  - Removes target advanced machine.
  - Permission: `simpletech.admin`
- `/stadvanced info`
  - Shows target advanced machine state.
- `/stadvanced autofuel <on|off|status>`
  - Toggles or inspects buffer-backed auto-refuel mode for the targeted advanced machine.
- `/stadvanced list`
  - Lists registered advanced machines.

## Logistics Commands

- `/stlogistics setlink <x,y,z[,priority]>`
  - Replaces existing routes and links target source machine to destination coordinates.
- `/stlogistics addlink <x,y,z[,priority]>`
  - Adds an additional destination route for priority-based routing.
- `/stlogistics clear`
  - Clears source logistics link.
- `/stlogistics mode <whitelist|blacklist>`
  - Sets filter mode.
- `/stlogistics io <any|north|south|east|west|up|down>`
  - Sets directional IO constraint for dispatch links.
- `/stlogistics allow <itemId>`
  - Adds item ID to allow filter list.
- `/stlogistics deny <itemId>`
  - Adds item ID to deny filter list.
- `/stlogistics allowtag <tag>`
  - Adds a category tag allow filter.
- `/stlogistics denytag <tag>`
  - Adds a category tag deny filter.
- `/stlogistics filters`
  - Clears allow/deny filter lists.
- `/stlogistics rate <itemsPerTransfer>`
  - Sets per-transfer throughput limit.
- `/stlogistics info`
  - Shows mode, rate, route count, filter counts, and primary link target.

## Buffer Commands

- `/stbuffer set`
  - Registers the targeted block as a virtual machine buffer.
- `/stbuffer remove`
  - Removes the targeted virtual buffer.
- `/stbuffer info`
  - Shows cached-item and link info for the targeted buffer.
- `/stbuffer list`
  - Lists registered virtual buffers.

Automation note:
- Machine outputs can cache into linked buffers.
- Linked buffers can automatically feed compatible single-input basic machines.
- Auto-refuel enabled machines can also draw their preferred fuel item from linked buffers.
- Sneak-right-click a buffer with `throughput_upgrade_1` to increase its transfer rate.

All logistics commands require permission: `simpletech.admin`.

## Admin & Debug Commands

- `/stdebug stats`
  - Shows machine counts, active counts, queue totals, loaded chunk snapshot.
  - Permission: `simpletech.debug`
- `/stdebug inspect`
  - Inspects target machine state.
  - Permission: `simpletech.debug`
- `/stdebug forcefinish`
  - Forces active target machine to finish on next tick.
  - Permission: `simpletech.admin`
- `/stdebug audit`
  - Shows recent audit entries and recent error entries.
  - Permission: `simpletech.debug`

- `/stadmin reload-state [all|items|recipes]`
  - Rebuilds in-memory registries.
- `/stadmin module <moduleId> <on|off>`
  - Toggles module enabled state flag.
- `/stadmin audit <on|off|clear>`
  - Controls audit log behavior.
- `/stadmin recover <status|cleanup|repair|migrate>`
  - Shows or runs persistence recovery and migration helpers.
- `/stadmin claimhook <info|use|break|block|clear> [reason]`
  - Tests or configures the optional claim-hook bridge on the targeted machine.
- `/stadmin economy <on|off|status>`
  - Toggles or inspects optional economy-hook behavior.

All `/stadmin` commands require permission: `simpletech.admin`.

- `/stbalance`
  - Shows the current balance summary and the most important default tuning values.
- `/stbalance <key>`
  - Shows the current value of a specific balance/config key.
- `/stbalance <key> <value>`
  - Sets a numeric config balance key.
  - Permission: `simpletech.admin`

## Access Commands

- `/staccess info`
  - Shows owner/public/shared-access info for the targeted machine.
- `/staccess claim`
  - Claims ownership of an unowned machine, or your own/admin-managed machine.
- `/staccess public <on|off>`
  - Toggles public access for the targeted machine.
- `/staccess share <playerName>`
  - Grants shared access to the targeted machine.
- `/staccess unshare <playerName>`
  - Removes shared access from the targeted machine.
- `/staccess overridebreak`
  - Admin-only. Arms a one-time break override for an active targeted machine.
- `/staccess takeover`
  - Admin-only. Transfers targeted machine ownership to yourself.

Confirmation note:
- Destructive actions like removing machines/buffers, clearing audit logs, and admin ownership takeover require repeating the command within 10 seconds.
