# Example BRD — Warehouse stock filter

> **Hypothetical scenario.** This example is not linked to any real company or product.

## Problem

In this example Inventory module, staff cannot filter the stock list by warehouse. Checking stock for a selected warehouse requires opening each item's detail page.

## Objective

Allow staff to view stock for a selected warehouse without reviewing item details one by one.

## Scope

**In scope:** warehouse selection, stock list filtering, and empty state.

**Out of scope:** stock transfer, quantity adjustment, and approval workflow.

## As-Is / To-Be

| As-Is | Proposed To-Be |
|---|---|
| The stock list has no warehouse filter | Staff can select a warehouse |
| Staff opens item detail to see stock by warehouse | The list displays stock associated with the selected warehouse |

## Business Requirements

| ID | Actor | Requirement | Expected Result | Status |
|---|---|---|---|---|
| INV-001 | Staff | Select a warehouse from the allowed options | The selected warehouse becomes the active filter | Proposed |
| INV-002 | System | Filter stock records based on the selected warehouse | Records for other warehouses are hidden | Proposed |
| INV-003 | System | Display an empty state when no data matches | Staff sees a clear empty result instead of a generic error | Proposed |

## Acceptance Criteria

- Given Staff selects Warehouse A, when the stock list loads, then only records belonging to Warehouse A are displayed.
- Given no items match the selected warehouse, when the filter is applied, then the system displays an empty state.

## Open Questions

| Question | Impact | Status |
|---|---|---|
| Are warehouse options restricted by the user's role? | Permission and data visibility | Need Confirmation |
| Should the initial selection be All Warehouses or the user's default warehouse? | Initial filter behavior | Need Confirmation |

Use this as a writing example only. Do not copy its hypothetical requirements into a real project without validation.
