# Minimal Inventory Manager

A single‑file, zero‑dependency inventory and equipment assignment tool that runs entirely in your browser using LocalStorage.

- Tech: HTML + CSS + vanilla JS (no build step)
- Data: saved to LocalStorage; import/export JSON
- Look & feel: clean brutalist UI with consistent action buttons and custom dropdowns

## Features
- Employees
  - Add/remove employees
  - Edit employee name (✎)
  - Per‑equipment unassign (⊗)
- Inventory
  - Categories: laptop, headset, mouse, other
  - Add items with quantity; edit name/quantity (✎) with validation
  - Remove item (🗑) with safety checks if assigned
- Assign
  - Custom dropdowns to select employee and equipment
  - Assign multiple categories at once
  - See a table of assigned equipment and unassign per category
- Customization
  - Customize (sidebar): accent/background/card/muted colors + compact mode
  - Theme persisted to LocalStorage
- Utilities
  - Export JSON; Import JSON; Clear All
  - Favicon included (base64)

## Quick start
1. Open `INDEX.HTML` in any modern browser (Chrome, Edge, Firefox, Safari).
2. Start by adding employees and inventory.
3. Use the Assign tab to link equipment to employees.

Tip: Data is stored in your browser’s LocalStorage—no server required.

## Import / Export
- Export: Click “Export JSON” to download `inventory.json`.
- Import: Click “Import JSON” and select a previously exported file.
- Clear: “Clear All” resets both employees and inventory (and keeps your theme).

## Editing & Actions
- Tables use consistent action buttons across Employees, Inventory, and Assign:
  - ✎ Edit
  - ⊗ Unassign (per category)
  - 🗑 Remove/Delete
- Buttons are always visible (not just on row hover) for clarity.

## Customization (Theme)
- Click “Customize” in the sidebar.
- Change: Accent, Background, Card, Muted text colors; toggle Compact mode.
- Settings persist via LocalStorage.

## Data model
The exported JSON has this shape:

```json
{
  "employees": [
    {
      "id": "emp_xxx",
      "name": "Jane Doe",
      "equipment": {
        "laptop": "laptop_xxx" | null,
        "headset": "headset_xxx" | null,
        "mouse": "mouse_xxx" | null,
        "other": "other_xxx" | null
      }
    }
  ],
  "inventory": {
    "laptop": [
      { "id": "laptop_xxx", "name": "Dell 5410", "model": "Dell 5410", "qty": 5, "assigned": 2 }
    ],
    "headset": [],
    "mouse": [],
    "other": []
  }
}
```

Notes:
- You can’t reduce an item’s quantity below the number already assigned.
- Removing an item that’s assigned will prompt and unassign it from employees.

## Troubleshooting
- Favicon not changing: hard refresh (Ctrl/Cmd + Shift + R) to bypass cache.
- Nothing saves: ensure your browser allows LocalStorage (disable private/incognito restrictions).
- UI glitches after updates: hard refresh to reload the latest single‑file assets.

## Development
- No build tools; just edit `INDEX.HTML`.
- Custom dropdowns are implemented with simple JS and CSS; no external libs.

## Credits
- Developer: Abdul Manan — https://github.com/abdulmanan69

## License
This project is provided as‑is with no warranty.
