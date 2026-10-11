# OutageMath open data: portable power stations and appliance wattages

Published specifications of **54 portable power stations** (37 sold new today, 17 older models still in use) from Anker SOLIX, BLUETTI, DJI, EcoFlow, Goal Zero, Jackery, and the **48 appliance wattages** behind every runtime estimate on [OutageMath](https://www.outagemath.com/).

Every value comes from the manufacturer: product pages, user manuals or official help centers. Each row lists its sources. Nothing is estimated from reviews, and missing values are left blank rather than guessed.

Free to use under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit "OutageMath" with a link to https://www.outagemath.com/.

## Files

| File | What it holds |
|---|---|
| `data/power-stations.csv` | One row per model: capacity, chemistry, continuous and surge output, solar input, weight, UPS switchover, cycle life, warranty, source and OutageMath page |
| `data/power-stations.json` | The same models with every field we track and every source URL |
| `data/appliances.csv` | Running, starting and average watts for common household and medical devices, with the assumptions and sources |
| `data/appliances.json` | The same, as JSON |

## Power station columns

| Column | Meaning |
|---|---|
| `status` | `current` if the maker sells it new, `legacy` if it has been replaced or discontinued |
| `capacity_wh` | Rated battery capacity in watt-hours |
| `chemistry` | `LFP` (lithium iron phosphate) or `NMC` |
| `ac_continuous_w` / `ac_surge_w` | Continuous and peak AC output in watts |
| `max_solar_input_w`, `solar_v_min`, `solar_v_max` | Solar input limits as published |
| `max_ac_input_w` | Wall-charging input in watts, where published |
| `ups_switch_ms` | Switchover time in UPS or EPS mode, blank if the model has none |
| `cycle_life`, `cycle_life_to_pct` | Rated cycles, and the remaining capacity they are rated to (often 70% or 80%) |
| `source` | The manufacturer page the row was checked against |
| `page` | The model's OutageMath page, with runtimes for common appliances |

## Appliance columns

`running_w` is the typical draw while running and `starting_w` the brief startup surge. `avg_w` is the average over time: for devices that cycle on and off, such as fridges and pumps, it is well below the running draw. `note` gives the assumption behind it.

The medical entries (CPAP, home and portable oxygen concentrators) come from the device makers' manuals and WHO specifications. They are for planning only. Check your own device's label, and don't rely on a battery alone for life-sustaining equipment.

## Use it

- **Charts and stories:** medians and distributions are on the [statistics page](https://www.outagemath.com/power-stations/statistics/).
- **Runtime for any setup:** the [runtime calculator](https://www.outagemath.com/tools/runtime-calculator/) uses this data, and it can be [embedded on your site](https://www.outagemath.com/tools/embed/).
- **Corrections:** open an issue with the manufacturer source, and we'll fix the row.

## Cite

> OutageMath. *Portable power station specifications and appliance wattages.* https://www.outagemath.com/ (data updated 2026-10-11). CC BY 4.0.

Data updated 2026-10-11. Maintained by Hicham M., a developer.
