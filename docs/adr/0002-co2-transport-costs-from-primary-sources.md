# CO2 and fuel transport costs from primary sources

The ship, liquefaction, port and tanker costs in the OptiFlow transport data were rebuilt from the primary sources instead of taken from the processed raw-data workbook, because the workbook applied its price-year factor twice in some cells and used a CO2 ship energy use far below the DEA value (26 vs 180 MWh per day). CO2 shipping follows the DEA carbon capture, transport and storage catalogue (ship sheet 423, liquefaction notes in sheets 401 and 411) and the CO2 pipeline fixed cost follows sheet 421. Liquid hydrocarbon, methanol and ammonia tankers follow the DEA energy transport catalogue, with trips and distances from Korberg et al. (2021). All values are in EUR2015 at a 4 % rate of return, and the DEA 2050 values are used for every model year because transport costs are not indexed by year.

## Consequences

- The electricity price behind the liquefaction cost (67 EUR/MWh) is the one input without a source.
- The CO2 port fee borrows the ammonia carrier port cost, as no CO2-specific value was available.
