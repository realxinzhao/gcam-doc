---
layout: index
title: Energy for Water
prev: supply_water.html
next: outputs_quantity.html
gcam-version: v5.3 
---

# Table of Contents

- [Inputs to the Model](#inputs-to-the-model)
- [Description](#description)
- [Equations](#equations)
- [Insights and intuition](#insights-and-intuition)
- [Policy options](#policy-options)
- [IAMC Reference Card](#iamc-reference-card)
- [References](#references)

## Inputs to the Model
**Table 1: Input data required for energy-for-water (EFW)**

| Name | Resolution | Unit | Source |
| :--- | :--- | :--- | :--- |
| Energy intensities of EFW processes (desalination, abstraction, treatment, distribution, wastewater treatment) | Global | GJ per $$m^3$$ | Liu et al. 2016 |
| Irrigation water withdrawals | By region, GLU, crop | $$km^3$$ per year | [GCAM water demand](demand_water.html) |
| Municipal water withdrawals | By nation | $$km^3$$ per year | [GCAM water demand](demand_water.html) |
| Industrial water withdrawals | By nation | $$km^3$$ per year | [GCAM water demand](demand_water.html) |
| Desalinated water production | By nation | $$km^3$$ per year | FAO Aquastat |
| Shares of wastewater treated | By nation | Unitless | Liu et al. 2016 |
| Non-renewable groundwater supply curves - electricity inputs | 20 grades per geopolitical region and GLU | GJ per $$m^3$$ | <a href="https://github.com/JGCRI/superwell">Superwell</a> |


## Description

### System boundaries
The specific system boundaries are explained in Kyle et al. (2016), and are set so as to include all energy for activities whose primary output is water, and to exclude from this domain production technologies that use both energy and water as inputs to produce some other good. For example, in thermoelectric power generation, energy is applied to water, and several studies of energy-for-water (e.g., Sanders and Webber 2012) have included it. This is not represented in GCAM as an "energy-for-water" process; rather, GCAM's representation of thermoelectric power generation consists of technologies that consume inputs of energy and water, and produce electricity as an output. The system boundaries of "energy-for-water" (EFW) consist of the following activities:

* Water abstraction
* Water treatment
* Water distribution
* Wastewater treatment

Within the following sectors:

* Desalinated water supply
* Irrigated crop production
* Industrial manufacturing
* Municipal water supply

### Modeling energy-for-water
The modeling approach is documented in Kyle et al. (2021), and consists of the following steps:

* Estimation of water flow volumes of EFW processes and sectors
* Multiplication of water flow volumes by assumed energy intensities
* Adjustment of historical energy consumption in the commercial and industrial sectors to accommodate explicitly represented EFW

As indicated in Table 1, the historical water flow volumes for several of the sectors and processes are estimated in the [GCAM water demand](demand_water.html) part of the model, but even still several modifications are made. Table 2 shows the specific methods of estimation of each modeled water sector and process in the model, as well as the sectors from which base-year energy is re-allocated, and how the demands for each of these water flow volumes are driven in the future time periods.

**Table 2: Methods of estimation of water flow volumes by EFW sectors and processes**

| Sector | Process | Historical data source | Energy deducted from | Future demand driver |
| :--- | :--- | :--- | :--- | :--- |
| Desalinated water | Treatment | FAO Aquastat | Industry Sector; Commercial and Public Services | Municipal water demand; manufacturing water demand |
| Irrigation water | Abstraction | [Irrigation water withdrawals](demand_water.html), plus upstream distribution losses <sup>[1](#table2_footnote1)</sup> | Agriculture; Commercial and Public Services | Irrigation water demand |
| Industry | Abstraction | [Industrial water withdrawals](demand_water.html), minus desalinated water use <sup>[2](#table2_footnote2)</sup> | Industry Sector | Industrial Output |
| Industry | Treatment | [Industrial water withdrawals](demand_water.html), minus desalinated water use <sup>[2](#table2_footnote2)</sup> | Industry Sector | Industrial Output |
| Industry | Wastewater Treatment | [Industrial water withdrawals](demand_water.html), times wastewater treatment share <sup>[3](#table2_footnote3)</sup> | Industry Sector | Industrial Output |
| Municipal | Abstraction | [Municipal water withdrawals](demand_water.html), minus desalinated water use <sup>[2](#table2_footnote2)</sup> | Commercial and Public Services | Municipal water demand |
| Municipal | Treatment | [Municipal water withdrawals](demand_water.html), minus desalinated water use <sup>[2](#table2_footnote2)</sup> | Commercial and Public Services | Municipal water demand |
| Municipal | Distribution | [Municipal water withdrawals](demand_water.html) | Commercial and Public Services | Municipal water demand |
| Municipal | Wastewater Treatment | [Municipal water withdrawals](demand_water.html), times wastewater treatment share <sup>[3](#table2_footnote3)</sup> | Commercial and Public Services | Municipal water demand |

<a name="table2_footnote1">1</a>: Upstream conveyance losses are from the nation-level estimates of Rohwer et al. (2007).

<a name="table2_footnote2">2</a>: Historical desalinated water production is assigned to municipal and industrial consumers on the basis of the relative shares of each sector's water withdrawal volumes

<a name="table2_footnote3">3</a>: Historical shares of wastewater treatment are estimated as the respective sector's withdrawal volume, minus consumptive uses, times the region's wastewater treatment shares, estimated by nation in Liu et al. (2016). In the future these shares increase with per-capita GDP, similar to the representation of pollutant emissions abatement in the [Emissions module](emissions.html).


## Equations 
The equations that determine water supply are described here.

#### Variable #1

{Insert equations used to calculate variable #1}

See `method name` in [code_file.cpp](link to code on GitHub).

## Policy options 
This section summarizes some of the energy-based policy options available in GCAM. 

### Policy type #1

{<}Insert paragraph describing a type of policy for this sector. Include links to xml input files on GitHub and/or the policies.html or policies_examples.html pages}

## Insights and intuition

### Paper/Topic #1

{One paragraph summary of a key insight from one or more papers}

## IAMC Reference Card

<Add relevant parts of IAMC reference card>


## References


