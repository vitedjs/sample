---
title: Tables
order: 32
---

# Tables

Markdown tables can present structured information with column alignment and
inline formatting.

| Theme     |  Framework  |    Status | Version |
| :-------- | :---------: | --------: | ------: |
| Bootstrap | Bootstrap 6 |     Ready |   0.1.2 |
| Mantine   |  Mantine 9  | **Ready** |   0.5.2 |
| Material  | Material UI |   `Ready` |   0.1.1 |

Tables remain readable on narrow screens: when a table is wider than its
container, scroll horizontally to see the remaining columns.

## Wide table

This table has many columns to exercise horizontal scrolling in a narrow
viewport.

|  ID | Project | Owner     | Status      | Priority | Region        | Updated    | Issues | Release |
| --: | :------ | :-------- | :---------- | :------: | :------------ | :--------- | -----: | :------ |
| 101 | Atlas   | A. Chen   | In progress |   High   | Europe        | 2026-10-28 |     12 | 2.4.0   |
| 102 | Beacon  | M. Patel  | Ready       |  Normal  | Asia Pacific  | 2026-10-30 |      3 | 1.8.2   |
| 103 | Compass | J. Rivera | Planned     |   Low    | North America | 2026-11-01 |      0 | 0.9.0   |

## Long rows

Long cell values should remain readable without pushing the whole document
outside its content area. Text with spaces can wrap, while an unbroken value
can be reached by scrolling horizontally.

| Case             | Description                                                                                                                                                                                                                      | Example value                                                                                 |
| :--------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------- |
| Long description | This row contains a deliberately long explanation to check that a table cell with ordinary prose wraps naturally over multiple lines, keeps the row readable, and does not overlap adjacent columns when the viewport is narrow. | A paragraph with spaces can wrap inside the cell.                                             |
| Long identifier  | A long unbroken identifier tests the table's horizontal overflow behavior when the content cannot wrap at spaces.                                                                                                                | `artifact-build-2026-11-03-region-asia-pacific-release-candidate-04-7d9c2a61e5b843109f18d4ca` |
