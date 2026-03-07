# Power, Heat, and Logistics

This page covers the runtime systems that keep Simple Tech automation moving.

## Fuel and Pseudo-Power

Simple Tech uses fuel points rather than a true cable network.

Core behaviors:

- recipes can cost fuel points
- active machines can consume upkeep over time
- machines pause when unfueled
- machines can resume after refueling

## Heat System

Heat affects selected machines and recipes.

Included features:

- heat generation from nearby burners
- heat buffers on machines
- heat loss over time
- heat-aware fuel efficiency on some processes

## Fuel Progression

### Early Game

- vanilla basic fuels

### Mid Game

- `heat_briquette`

### Late Game

- `thermal_cell`

## Auto-Refuel

Auto-refuel can pull a remembered preferred fuel from linked buffers.

How it works:

1. enable auto-refuel on a machine
2. manually add one fuel item to teach the preferred fuel ID
3. link a buffer route supplying that fuel
4. the machine pulls fuel automatically when needed

Commands:

- `/stmachine autofuel <on|off|status>`
- `/stadvanced autofuel <on|off|status>`

## Logistics System

The logistics layer supports machine-to-machine and machine-to-buffer flows.

### Core Features

- pull/push abstraction
- directional IO controls
- transfer rate limits
- whitelist and blacklist filters
- tag/category filters
- priority routes
- overflow fallback behavior
- loop prevention

## Virtual Buffers

Buffers act as virtual storage/transfer endpoints.

Features:

- input caching
- output caching
- throughput upgrades
- machine output staging
- auto-feeding compatible machines
- auto-refuel source role

## Logistics Commands

- `/stlogistics setlink <x,y,z[,priority]>`
- `/stlogistics addlink <x,y,z[,priority]>`
- `/stlogistics clear`
- `/stlogistics mode <whitelist|blacklist>`
- `/stlogistics io <any|north|south|east|west|up|down>`
- `/stlogistics allow <itemId>`
- `/stlogistics deny <itemId>`
- `/stlogistics allowtag <tag>`
- `/stlogistics denytag <tag>`
- `/stlogistics filters`
- `/stlogistics rate <itemsPerTransfer>`
- `/stlogistics info`

## Buffer Commands

- `/stbuffer set`
- `/stbuffer remove`
- `/stbuffer info`
- `/stbuffer list`

## Optimization Notes

The ecosystem includes:

- active-machine lists
- bucketed machine processing
- idle machine sleep mode
- cached recipe lookups
- periodic cleanup of stale state
