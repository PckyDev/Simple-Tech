# Commands and Administration

This page summarizes the command surface of Simple Tech.

## Player Commands

- `/st`
- `/st help`
- `/st status`
- `/st progress`
- `/st objective [current|next|status]`
- `/st machine`
- `/st admin <balance|inspect|debug>`
- `/st recipes [query]`
- `/st recipes tier <0-3>`
- `/st recipes type <recipe_type>`
- `/stnext`
- `/stprev`
- `/strecipe list [type]`
- `/strecipe view <type> <id>`
- `/strecipe search <query>`
- `/stwallet`
- `/stvalue`
- `/stsell [amount]`

## Item Commands

- `/stitem list`
- `/stitem give <id> [amount]`
- `/stitem normalize`

## Machine Commands

### Basic Machines
- `/stmachine set <crusher|press|mixer|smelter>`
- `/stmachine remove`
- `/stmachine info`
- `/stmachine autofuel <on|off|status>`
- `/stmachine list`

### Advanced Machines
- `/stadvanced set <assembler|refinery|electrolyzer|fabricator>`
- `/stadvanced remove`
- `/stadvanced info`
- `/stadvanced autofuel <on|off|status>`
- `/stadvanced list`

## Logistics and Buffer Commands

- `/stlogistics ...`
- `/stbuffer ...`

See [Power, Heat, and Logistics](Power-Heat-and-Logistics.md) for the system-level explanation.

## Access Commands

- `/staccess info`
- `/staccess claim`
- `/staccess public <on|off>`
- `/staccess share <playerName>`
- `/staccess unshare <playerName>`
- `/staccess overridebreak`
- `/staccess takeover`

## Debug Commands

- `/stdebug stats`
- `/stdebug inspect`
- `/stdebug forcefinish`
- `/stdebug audit`

## Admin Commands

- `/stadmin reload-state [all|items|recipes]`
- `/stadmin module <moduleId> <on|off>`
- `/stadmin audit <on|off|clear>`
- `/stadmin recover <status|cleanup|repair|migrate>`
- `/stadmin claimhook <info|use|break|block|clear> [reason]`
- `/stadmin economy <on|off|status>`
- `/stbalance`
- `/stbalance <key>`
- `/stbalance <key> <value>`

## Permission Notes

Typical permission nodes:

- `simpletech.use`
- `simpletech.items`
- `simpletech.debug`
- `simpletech.admin`

## Administration Areas

### Balance and Economy

Use:

- `/stbalance`
- `/stadmin economy status`
- `/stwallet`
- `/stvalue`
- `/stsell`

### Recovery and Migration

Use:

- `/stadmin recover status`
- `/stadmin recover cleanup`
- `/stadmin recover repair`
- `/stadmin recover migrate`

### Claim Hook Compatibility

Use:

- `/stadmin claimhook ...`

### Command-Driven Admin Panels

Use:

- `/st admin balance`
- `/st admin inspect`
- `/st admin debug`
