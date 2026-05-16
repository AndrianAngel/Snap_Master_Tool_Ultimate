# 🪟 SnapMaster Tool — Ultimate Release

**SnapMaster** is a portable Windows utility that gives you full control over window snapping, layout management, and session restoration — with a live preview grid, hotkeys, and a clean dark-mode settings panel. No installation required.

---

## 📦 Download

| File | Description |
|---|---|
| `Snap_Master_Tool_Ultimate_Release_26_16_05_Stable_X86.exe` | Standalone portable executable |
| `Snap_Master_Tool_Ultimate_Release_26_16_05_Stable_X86.zip` | Same executable, zipped for easy sharing |

> Both files are identical — the ZIP is provided for convenience (e.g. sharing or downloading on restricted networks).

### Why 32-bit (x86)?

SnapMaster is compiled as a **32-bit application** intentionally. A 32-bit binary runs natively on **both 32-bit and 64-bit versions of Windows** without any compatibility layer or additional runtime. Since SnapMaster is a window management utility — not a CPU-intensive application — there is zero performance benefit to 64-bit, and shipping x86 guarantees the widest possible compatibility out of the box, on any modern Windows machine.

---

## 🚀 Getting Started

1. Drop the `.exe` anywhere — it's fully portable.
2. A `SnapMaster.ini` config file will be created next to the exe on first save.
3. The app runs in the system tray. Right-click the tray icon to access all features.
4. Open **Settings** with `Ctrl+Alt+S` (default) or via the tray menu.

---

## ⚙️ Settings Sections

The Settings window is organized into four sections accessible from the left navigation panel.

---

### 🟩 Layouts

Enable or disable any of the **12 built-in snap layouts**. Disabled layouts never appear in the selector grid.

Available layouts:

| # | Name | Description |
|---|---|---|
| 1 | Wide Center | 3 columns — narrow left, wide center, narrow right |
| 2 | Dual Vertical | 2 equal side-by-side columns |
| 3 | Dual Horizontal | 2 equal stacked rows |
| 4 | Triple Vertical | 3 equal vertical columns |
| 5 | Triple Horizontal | 3 equal horizontal rows |
| 6 | Four Quadrants | 2×2 grid |
| 7 | Six Grid (2×3) | 6-cell grid (2 columns × 3 rows) |
| 8 | Left 2/3 + Right Split | Large left pane + 2 stacked right panes |
| 9 | Right 2/3 + Left Split | Large right pane + 2 stacked left panes |
| 10 | Top 2/3 + Bottom Split | Large top area + 2 side-by-side bottom panes |
| 11 | Tiles – Big Top Left | Large top-left + small top-right + full bottom strip |
| 12 | Tiles – Big Bottom Right | Full top strip + small bottom-left + large bottom-right |

**How to snap a window:**

- Hold your **trigger key** (`Ctrl` or `Shift`) + **left-click and drag** a window from its **title bar**.
- The layout selector grid appears — hover a slot to see a **live preview** of where the window will land.
- **Release the mouse** inside a slot to snap the window there.
- **Release the trigger key first** to cancel without snapping.
- While hovering a slot, **right-click** to swap with a window already occupying that zone.
- The preview turns **red** when a zone is already occupied (swap candidate).

---

### 🟦 Hotkeys

All hotkeys are fully customizable in this section. The trigger key for dragging (`Ctrl` or `Shift`) is also set here.

| Default | Action |
|---|---|
| `Ctrl+Alt+R` | **Restore ALL** snapped windows to their pre-snap positions, then clears snap memory |
| `Ctrl+Shift+R` | **Restore ACTIVE** window only — restores the focused window to its pre-snap position |
| `Ctrl+Alt+C` | **Cycle layouts** — rotates through layouts matching your current snapped window count |
| `Ctrl+Shift+U` | **Restore last closed snapped window** (LIFO — see details below) |
| `Ctrl+Alt+I` | **Clear closed snap history** — empties the restore stack with a confirmation dialog |
| `Ctrl+Alt+S` | **Open / close Settings** |

#### 🔄 Restore Last Closed Snapped Window — Two-Press Flow

This hotkey uses a **two-press sequence** — do not press both too quickly:

- **Press 1 — Reopen:** Reopens the most recently closed snapped window from the LIFO stack. The app launches in the background without stealing focus.
- **Press 2 — Reposition:** After the restored window has loaded and you have **clicked on it to give it focus**, press the hotkey again to apply its saved size and position.

> ⚠️ Focus matters — make sure the restored window is the **active (focused) window** before pressing the second time, otherwise the size/position will be applied to the wrong window.

**Behavior by window type:**
- **Explorer windows** — restores both **size and position** to the exact snap zone it was in.
- **Regular apps** — restores **size only** (position is not stored, as apps may open at different locations depending on their own logic).

> 💡 If the window reappears in the same location it was snapped to, you won't notice a visual change on the second press — but it is still needed to correctly apply the stored dimensions.

**Important note about Cycle + Restore:**

After using the **Cycle Layouts** hotkey, restoring closed snapped windows remains possible, but the **LIFO order may shift** for some windows — the exact sequence can change.

> 💡 **Suggestion:** If you need to restore windows to their exact positions after cycling, use **Re-snap** before closing them. And if you're starting a new project or a new snapping session, **clear the history first** (`Ctrl+Alt+I`) so your restore stack stays clean and predictable. 🙂

#### 🔁 Cycle Layouts

Rotates through all enabled layouts whose **slot count exactly matches** your current number of snapped windows.

- Example: 2 snapped windows → cycles between *Dual Vertical* and *Dual Horizontal*.
- Requires at least one prior snap in the current session. Unsnapped windows are ignored.

---

### 🟨 Options

#### Gap Size (0–50 px)

Adds spacing between snapped window zones.

- **0 px (Green):** Windows extend slightly beyond screen edges to hide the resize border — zones fill cleanly with no visible gap.
- **1–20 px (Yellow):** Moderate visible gaps between all zones.
- **21–50 px (Red):** Large gaps — useful for wallpaper visibility or ultra-wide setups.

#### Swap Apps

When you drop a window onto a zone **already occupied** by another snapped window, the occupying window automatically moves to the dragged window's original position instead of stacking. Disable this if you prefer manual placement only.

#### Track & Restore Closed Snapped Windows

Watches for snapped windows being closed and saves their path and size to a **LIFO stack** for later restoration via the restore hotkey. Disable this option if you never use the restore-closed feature to reduce background tracking overhead.

#### Hotkey — Restore Last Closed Snap

Allows you to customize the hotkey used for the two-press restore-closed sequence directly from this section.

#### Disable Tooltips

Hides most tray notification popups. Useful if you find them distracting once you know the workflow.

**Hidden when disabled:**
- Window restored / All windows restored
- Opened app / Restore size hint (2nd press prompt)
- Position restored / Size & position restored
- Cycle layout name
- No snapped windows to cycle / No pre-snap found
- Config reloaded

**Always shown regardless of this setting:**
- Clear snap history confirmation (requires your input)
- No closed windows in memory (actionable feedback)
- No layouts match N snapped windows (cycle cannot proceed)

---

### 🩷 Exceptions

List any apps that SnapMaster should **completely ignore** — one entry per line.

You can enter:
- A **process name:** `notepad.exe`, `chrome.exe`, `vlc.exe`
- A **window title** (or part of it): `Task Manager`, `Picture-in-Picture`

SnapMaster checks both the process name and the window title for each entry. A partial title match is enough — `Picture` will match `Picture-in-Picture`.

Excepted windows:
- Cannot be dragged into the layout selector
- Will not be tracked for restore-on-close
- Are excluded from cycle and swap logic

Use **Browse...** to pick an `.exe` directly from disk, or **Paste** to paste from clipboard. Changes take effect after clicking **SAVE**.

---

## 🗂️ Tray Menu

Right-click the tray icon for quick access to:

- Settings
- Restore All Windows
- Restore Active Window
- Clear Snap History
- Cycle Layouts
- Reload Config
- Exit

---

## 📁 Configuration

Settings are saved to `SnapMaster.ini` in the same folder as the executable. You can reload the config at any time via the tray menu without restarting.

---

## 👤 Author

**AndrianAngel** — [github.com/AndrianAngel](https://github.com/AndrianAngel)

*All rights reserved.*
