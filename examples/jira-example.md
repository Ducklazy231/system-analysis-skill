# Jira example — Filter Stock by Warehouse

> **Illustrative only.** This ticket is not associated with a live system.

## Title

Add Warehouse Filter to Inventory Stock List

## As-Is

The stock list does not offer a warehouse filter. A staff user must open item details to check stock in a specific warehouse.

## To-Be

Add a Warehouse filter above the stock list. When a warehouse is selected, the list should show only the stock records associated with that warehouse.

## Acceptance Criteria

- Given a staff user selects Warehouse A, when the list refreshes, then only stock records from Warehouse A are shown.
- Given no records match the selected warehouse, when the list refreshes, then the system shows an empty state.
- Warehouse visibility and default selection must follow confirmed role and data-access rules.

## Need Confirmation

Confirm whether the warehouse list is role-restricted and which warehouse is selected by default.
