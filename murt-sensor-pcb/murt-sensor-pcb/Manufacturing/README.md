# Manufacturing Files

Everything needed to fabricate and assemble the board.

- `Gerbers/` — RS-274X Gerber files exported from Altium (File → Fabrication Outputs → Gerber Files).
- `Drill/` — Excellon drill files (NC Drill) exported alongside the Gerbers.
- `BOM/` — Bill of materials (`.xlsx`/`.csv`) listing every part, reference designator, manufacturer part number, and supplier link.
- `PickAndPlace/` — Centroid / pick-and-place file for automated assembly (File → Assembly Outputs → Generates pick and place files), if the board will be machine-assembled.

## Export checklist (Altium)
1. Run DRC (Design Rule Check) and clear all violations before exporting.
2. `File → Fabrication Outputs → Gerber Files` → export to `Gerbers/`.
3. `File → Fabrication Outputs → NC Drill Files` → export to `Drill/`.
4. `File → Assembly Outputs → Bill of Materials` → export to `BOM/`.
5. `File → Assembly Outputs → Generates pick and place files` → export to `PickAndPlace/`.
6. Zip the `Gerbers/` + `Drill/` folders together when submitting to a fab house (e.g. JLCPCB, PCBWay, OSH Park).

## Fab notes
*(Add board thickness, copper weight, surface finish, min trace/space, and stack-up notes here once finalized.)*
