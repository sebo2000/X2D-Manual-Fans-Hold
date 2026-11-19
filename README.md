# X2D Manual Fans Hold

Printer preset for Bambu Studio 2.9 (Bambu Lab X2D, 0.4 mm nozzle) for printing PLA and PETG with the auxiliary and chamber fans at fixed speeds that you control.

## What it does

The preset inherits the stock "Bambu Lab X2D 0.4 nozzle" profile. It changes only the start, layer-change and filament-change G-code, and only in cooling mode (chamber below 40 °C). Heated-chamber prints (ABS, ASA and so on) are not changed.

- **Print start**: sets the left aux fan (`P2`) to 30%, the right aux fan (`P10`) to 30% and the chamber exhaust fan (`P3`) to 70%. Firmware chamber autocooling (`M142`) is not turned on.
- **Layer changes**: the per-filament aux-fan ramps and the `M142` autocooling updates are removed.
- **Filament / hotend changes**: no fan commands at all. Speeds you change on the printer or in the Device tab during the print are not overwritten by the G-code.
- **End of print**: the stock end G-code turns the fans off as usual.

To use other speeds, edit the `M106 P2/P10/P3` lines under `; MANUAL FANS` in the printer's start G-code (S value = percent × 2.55).

## Files

- `Bambu Lab X2D 0.4 nozzle - Manual Fans Hold.json`: the printer preset. In Bambu Studio: *File → Import → Import Configs…*, then select "Bambu Lab X2D 0.4 nozzle - Manual Fans Hold" as the printer.
- `Bambu Lab X2D 0.4 nozzle - Manual Fans Hold.3mf`: an example project (a cube, PETG + PLA) with the preset already selected.

## Note

This is a test preset. The firmware may still reset the fans when it switches hotends. If it does, use a variant that sends the fixed speeds again after every filament change. Use at your own risk.
