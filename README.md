# Portable power station specs and appliance wattages

This is the data behind [OutageMath](https://www.outagemath.com/): specs for 54 portable power stations from Anker SOLIX, BLUETTI, DJI, EcoFlow, Goal Zero and Jackery (37 still sold new, 17 older ones that people still own), plus the wattages of 48 common appliances.

I took every number from the manufacturer's own product pages, manuals or help center, and each row links to where it came from. If a maker doesn't publish a value, the cell is empty. I didn't fill gaps from reviews or guesses.

License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Use it however you like; just credit OutageMath and link to https://www.outagemath.com/.

## Files

| File | What's in it |
|---|---|
| `data/power-stations.csv` | One row per model: capacity, chemistry, continuous and surge output, solar input, weight, UPS switchover, cycle life, warranty, source and OutageMath page |
| `data/power-stations.json` | Same models, with every field and every source URL |
| `data/appliances.csv` | Running, starting and average watts for household and medical devices, with sources |
| `data/appliances.json` | Same, as JSON |

## Power station columns

| Column | Meaning |
|---|---|
| `status` | `current` if the maker still sells it, `legacy` if it was replaced or discontinued |
| `capacity_wh` | Rated battery capacity in watt-hours |
| `chemistry` | `LFP` (lithium iron phosphate) or `NMC` |
| `ac_continuous_w` / `ac_surge_w` | Continuous and peak AC output in watts |
| `max_solar_input_w`, `solar_v_min`, `solar_v_max` | Solar input limits as published |
| `max_ac_input_w` | Wall-charging input in watts, where published |
| `ups_switch_ms` | UPS/EPS switchover time; empty if the model has no UPS mode |
| `cycle_life`, `cycle_life_to_pct` | Rated cycles, and the capacity left at the end of them (usually 70% or 80%) |
| `source` | Manufacturer page the row was checked against |
| `page` | The model's page on OutageMath, with runtimes for common appliances |

## Appliance columns

`running_w` is the typical draw while running and `starting_w` is the short surge at startup. `avg_w` is the average over a day, which for things that cycle on and off (fridges, freezers, pumps) is much lower than the running draw. `note` explains the assumption.

The CPAP and oxygen concentrator figures come from the makers' own documents and WHO specs. They're fine for planning, but check the label on your own device, and don't count on a single battery for equipment someone's life depends on.

## Related

- Charts and medians: [statistics page](https://www.outagemath.com/power-stations/statistics/)
- [Runtime calculator](https://www.outagemath.com/tools/runtime-calculator/) built on this data (you can [embed it](https://www.outagemath.com/tools/embed/) on your own site)

Spotted a wrong number? Open an issue with a link to the manufacturer's page and I'll fix it.

## Citing

> OutageMath, *Portable power station specifications and appliance wattages*, https://www.outagemath.com/, updated 2026-10-11. CC BY 4.0.

Last updated 2026-10-11.
