# Balmorel

Balmorel is an open-source energy system model, written in GAMS. It finds the least-cost investment in and operation of electricity, heat and other energy commodities across interconnected regions.

## Project structure

**Base**:
The `base` folder, which holds the reference model, addons and data that every scenario falls back on.
_Avoid_: master model, default folder

**Scenario**:
A folder next to `base` with its own `model`, `data` and `simex` folders. It contains only the files that differ from base.
_Avoid_: case, run folder, project

**Addon**:
An optional module of equations and data that extends the core model and is switched on or off per scenario, e.g. the hydrogen addon.
_Avoid_: extension, plugin, module

**Simex**:
The folder in a scenario that holds results one run exports for a later run to read.
_Avoid_: export folder

## Geography

**Country**:
The coarsest geographical level, made up of regions.

**Region**:
A part of a country where electricity supply must equal demand. Electricity is transmitted between regions, and a region often matches a bidding zone.
_Avoid_: node, zone

**Area**:
The finest geographical level, inside a region, where technologies are located and heat supply must equal demand.
_Avoid_: district, zone

## Time

**Year**:
A model year, such as 2030, that the energy system is optimised for.

**Season**:
A subdivision of a year. In the standard data, a season is one week.
_Avoid_: week, period

**Time period**:
A subdivision of a season. In the standard data, a time period is one hour.
_Avoid_: hour, time step, term

## Modelling

**Technology**:
A type of generation, conversion or storage unit, such as a wind turbine, a combined heat and power plant or a heat storage.
_Avoid_: plant, unit, generator

**Fuel**:
An energy input that technologies use, including non-combustible resources such as wind, sun and water.
_Avoid_: energy source, resource

**Investment run**:
A run in which Balmorel decides new capacity as well as how to operate it.
_Avoid_: expansion run, capacity run

**Operational run**:
A run with capacities fixed from an earlier investment run, in which Balmorel decides only how to operate them, often over more time periods or other weather years.
_Avoid_: dispatch run, simulation run

**Vintage**:
The year in which a unit of capacity is built. Its costs and efficiencies stay at that year's values for its whole lifetime.
_Avoid_: cohort, build year

## Emission policy

**National emission cap**:
An annual limit on the net CO2 emissions of a group of countries, covering all sectors in the model.
_Avoid_: CO2 budget, emission target

**Maritime carbon budget**:
A separate annual limit on the CO2 emissions from ship fuel use.
_Avoid_: maritime cap, IMO cap

**Maritime fuel demand**:
The fuel energy required by ships calling at modelled ports, given per fleet segment.
_Avoid_: shipping demand, bunker demand

## CO2 capture, transport and storage

**Point-source capture**:
Capture of CO2 from the exhaust of a technology that burns fuel or converts biomass, such as a combined heat and power plant, a boiler or a steam reformer.
_Avoid_: CCS plant, flue-gas CCS

**Onboard carbon capture (OCC)**:
Capture of CO2 from a ship's exhaust, kept on board and unloaded at port.
_Avoid_: shipboard CCS

**Direct air capture (DAC)**:
Capture of CO2 from ambient air, independent of any fuel use.
_Avoid_: air capture, CDR (CDR also covers biogenic capture)

**Solid sorbent DAC**:
DAC that binds CO2 to a solid sorbent and releases it with low-temperature heat.
_Avoid_: low-temperature DAC, LT-DAC

**Liquid solvent DAC**:
DAC that absorbs CO2 in an alkaline solution and releases it in a high-temperature calciner.
_Avoid_: high-temperature DAC, HT-DAC

**RepAir**:
An electrochemical DAC technology that separates CO2 from air using electricity only.
_Avoid_: electrochemical DAC (when RepAir specifically is meant)

**Storage site**:
A geological reservoir, onshore or offshore, where captured CO2 is injected permanently.
_Avoid_: sink, sequestration area

**Injection limit**:
The highest rate, in tonnes per year, at which a storage site can accept CO2.
_Avoid_: storage capacity (the total volume a site can hold)
