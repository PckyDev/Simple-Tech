# Balance, QA, and Roadmap

This page summarizes balancing, test coverage, and the project roadmap state.

## Balance Areas

Simple Tech includes configurable balance values for:

- machine duration multipliers
- tier multipliers
- fuel upkeep
- economy maintenance
- advanced activation costs
- sell values
- upgrade caps

## Balance Commands

- `/stbalance`
- `/stbalance <key>`
- `/stbalance <key> <value>`
- `/stadmin economy status`

## Economy Hooks

Optional economy support includes:

- player balances
- item sell values
- maintenance costs
- advanced activation charges

Commands:

- `/stwallet`
- `/stvalue`
- `/stsell [amount]`

## QA Coverage

The project includes a manual test plan covering:

- item creation tests
- recipe validity tests
- machine chain tests
- GUI interaction tests
- edge cases
- regression checks
- recovery and admin validation
- balance validation
- auto-refuel validation

## Stability and Safety Features

- lock-based concurrency protection
- confirmation flow for destructive actions
- ownership and access control
- break protection for active machines
- claim-hook bridge support
- audit and error logs
- persistence snapshots
- recovery cleanup and repair tools

## Roadmap State

All tracked technical features are complete.

The only unchecked tracker items are the broad release-goal labels:

- MVP Goal Reached
- Beta Goal Reached
- Release Candidate Goal Reached
- v1.0 Goal Reached

Those are milestone labels rather than missing implementation work.

## Feature Set Timeline

- Feature Set A - Core Tech Loop
- Feature Set B - Industrial Expansion
- Feature Set C - Automation Depth
- Feature Set D - Polish & Stability
- Feature Set E - Onboarding UX Refresh

## Suggested Future Expansion Areas

If the project grows beyond the current tracker, likely future areas are:

- new item families and machine chains
- additional advanced machine types
- expanded GUI presentation
- more economy integrations
- world-specific balance presets
- deeper late-game routing challenges
