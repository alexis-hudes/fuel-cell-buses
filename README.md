# fuel-cell-buses
A cost comparison of transitioning Vermont's public bus fleet to battery electric buses, hydrogen fuel cell buses, and a combination.

This analysis was completed as part of a final project for the course ENGS 173: Energy Conversions at Dartmouth College by Alexis Hudes and Allison Trapani.

**Background**:

Vermont has commited to transitioning their public bus fleet to net-zero propulsion by 2050. Their current plan is to use all battery electric buses to do so. However, some of the current routes covered exceed the range of battery electric buses. In this project, we compared the following costs for three scenarios of all battery electric buses, all hydrogen fuel cell buses, and a combinations:

- Upfront costs: vehicles and infrastructure
- Ongoing costs: fuel/electricity per mile

We did not account for ongoing operation costs.

The information we gathered came from a wide range of sources, which are listed below. There is a lot of uncertainty associated with each input variable we used. To deal with this uncertainty, we assigned probability distribution functions to each input and ran a Monte Carlo Simulation.

Some of our inputs were discrete. For example, the public transportation program manager from VTrans told us that VTrans typically purchases 11 or 12 chargers for every 10 battery electric buses. For this input, we assigned a 50-50 chance of 11 vs. 12. Another discrete input was the electricity rate, depending on whether the buses were being charged at off-peak, mid-peak, or on-peak. Based on our knowledge that VTrans tries to maximize off-peak charging overnight, but can't always achieve this due to charger failures and the need for mid-day charging for long routes, we assigned the probabilities of 70%, 20%, and 10% to off-peak, mid-peak, and on-peak respectively.

For all other inputs, we assigned a normal distribution to the range found from sources. For example, based on an academic study, the cost of liquefaction is $2.5 - $3 / kg. We assigned a normal distribution to that range, which assumes that 95% of values will fall within the range and the average is in the middle.

With more time and expert elicitation, probability distribution functions should be tailored more specifically to each input.

**How to run**:

The Jupyter notebook titled vtrans_hydrogen is self-contained. 

It was built using Python 3.9.13 and uses the packages numpy, matplotlib, scipy, random, and math.


**Data sources**:

LCOH: [DOE Hydrogen Program Record](https://www.hydrogen.energy.gov/docs/hydrogenprogramlibraries/pdfs/24005-clean-hydrogen-production-cost-pem-electrolyzer.pdf?sfvrsn=8cb10889_1#:~:text=Collectively%2C%20these%20show%20that%20electrolyzer,Initial%20Liftoff%20Report%20%5B4%5D.)

LCOT: [Paths to low-cost hydrogen energy at a scale for transportation applications in the USA and China](http://dx.doi.org/10.1093/ce/zkz033)

Fuel economy: [AC Transit Fuel Cell Electric Bus Progress Report](https://www.osti.gov/servlets/purl/1963241)

Liquefaction: [Hydrogen liquefaction: a review of the fundamental physics, engineering practice and future opportunities](https://doi.org/10.1039/D2EE00099G)

Tax credit: [Clean Hydrogen Production Tax Credit (45V) Resources](https://www.energy.gov/articles/clean-hydrogen-production-tax-credit-45v-resources)

Electricity rates: [Vermont Electric Cooperative](https://vermontelectric.coop/client_media/files/Rate_Summary_Effective_01_01_2024.pdf)

Electric Bus Efficiency: [Blog Post](https://www.sustainable-bus.com/news/electric-bus-range-electricity-consumption/)

Diesel Price: [EIA: Petroleum and Other Liquids](https://www.eia.gov/dnav/pet/hist/LeafHandler.ashx?n=pet&s=emd_epd2d_pte_r1x_dpg&f=m)

Diesel Efficiency: [Blog Post](https://www.pfleet.com/blog/comparing-types-of-buses-and-their-mpg)
