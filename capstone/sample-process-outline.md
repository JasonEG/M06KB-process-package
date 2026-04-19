# Sample Process Outline — Filament Change and Test Print
**Printer:** Prusa MK3S+
**Material:** PLA
**Role:** Print Operator
**Prepared by:** Jason Geanuracos
**Date:** 2026-04-05

---

## Overview

**Trigger:** A finished print is on the bed and a filament swap is required before the next job.

**End State:** New filament loaded, first layer calibration confirmed, printer ready for next job.

---

## Inputs / Materials Required

- Prusa MK3S+ printer (powered on, print complete)
- New spool of PLA filament
- Spring steel PEI sheet (already on bed)
- LCD control knob (built into printer)

---

## Phase 1 — Remove Finished Print

1. Confirm print is complete and nozzle is parked at home position.
2. Wait for bed to cool to ~50°C (monitor on LCD display).
3. Remove the spring steel PEI sheet from the magnetic bed.
4. Bend each end of the sheet ~30 degrees to pop the print free.
5. Set print aside; replace sheet flat on the bed.

## Phase 2 — Unload Filament

1. On the LCD, navigate to **Load/Unload > Unload Filament**.
2. Select material: **PLA** (printer heats nozzle to 215°C automatically).
3. When prompted, press the knob — printer retracts filament automatically.
4. Gently pull the filament out of the extruder and PTFE tube.
5. Coil and clip the filament to the spool to prevent tangling.

## Phase 3 — Load New Filament

1. Mount new spool on the spool holder.
2. LCD: **Load/Unload > Load Filament > PLA**.
3. Insert filament tip into the extruder opening; push until the gear grabs.
4. Printer feeds filament through and purges — watch for consistent color exiting the nozzle.
5. Confirm clean color, then press the knob to accept.

## Phase 4 — First Layer Calibration Test

1. LCD: **Calibration > First Layer Calibration**.
2. Printer prints a single-layer test pattern across the bed.
3. Observe layer adhesion and width — adjust Live Adjust Z if needed *(turn the knob during print to raise or lower nozzle height)*.
4. Accept result if layer is flat and consistent.
5. If layer fails after 2 attempts, note the current Z offset value, reset to default, and re-run calibration from step 1.

