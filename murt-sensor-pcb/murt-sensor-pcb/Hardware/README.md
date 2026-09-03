# Hardware — Altium Source Files

This folder holds the raw Altium Designer source for the sensor interface board.

- `Project/` — the `.PrjPcb` project file and any project-level workspace files. Open this first; it links the schematic and PCB documents.
- `Schematic/` — `.SchDoc` schematic sheet(s).
- `PCB/` — `.PcbDoc` PCB layout file(s).

## Opening the project
1. Install Altium Designer (a matching or newer version to the one used originally, if known).
2. Open the `.PrjPcb` file in `Project/`.
3. Compile the project (Project → Compile PCB Project) to validate the schematic-to-layout link before making changes.

## Notes
- Keep the `Project/`, `Schematic/`, and `PCB/` files together — Altium project files reference relative paths to the schematic and PCB documents.
- If you add or rename sheets, update the `.PrjPcb` file references accordingly.
