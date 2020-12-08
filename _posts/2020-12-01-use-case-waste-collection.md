---
layout: post
title:  "Waste collection"
categories: [ Research, Use Cases ]
image: http://senseable.mit.edu:60080/uploads/eb3cdb3342824ef1b24fc796e0dca016.jpg
---

Almost 23 million kilos of household waste alone is produced in Amsterdam’s city centre each year; that’s aside from any commercial, industrial or green waste [[ref](https://www.ust-media.com/ust-magazine/UST031/76/)].

Roboat units can collect waste for the Centrum district of Amsterdam, where residents currently deposit trash on the curb for collection. To alleviate the many problems caused by large trash trucks on historic streets - congestion, pollution, noise, etc. - Roboat can serve as floating dumpsters that autonomously transfer waste.

Beyond Amsterdam, the proposed fleet of waste-collecting vehicles has the potential to provide infrastructural improvements in other water-based cities, where the need for a nimble waste collection system is even more dire.

<img src="http://senseable.mit.edu:60080/uploads/eb3cdb3342824ef1b24fc796e0dca016.jpg" alt="waste" width="500"/>

### Why?

**1) Avoid damage to fragile Amsterdam quay walls**

*Problem:* Waste is transported mainly by heavy, diesel-powered trucks on congested city roads, which not only worsen traffic and pollution but can damage quay walls and pavements, causing further disruption, safety risks, and costing taxpayers’ money to fix [[ref](https://www.ust-media.com/ust-magazine/UST031/76/)].
Kilometres of quay walls in the city are in poor condition due to years of neglect (e.g.,  [Quay wall Grimburgwal in the City of Amsterdam collapsed](https://www.linkedin.com/company/amsterdam-institute-for-advanced-metropolitan-solutions/videos/native/urn:li:ugcPost:6706588026425888770/?isInternal=true&lipi=urn%3Ali%3Apage%3Acompanies_company_videos_index%3BVkmIVbHMSyyinIqJ81OjNA%3D%3D), [sinkhole Marnixstraat](https://www.at5.nl/artikelen/174805/tramverkeer-plat-door-sinkhole-aan-marnixstraat)).

*Solution:* The Roboat is being developed for a range of uses, with autonomous waste collection being touted strongly as an alternative to road-based refuse handling.

**2) Decrease traffic**

*Problem:* The city center of Amsterdam is relatively small but busy.

*Solution:* As 25% of the city of Amsterdam consists of water surface, Amsterdam offers the ideal environment to expand its current infrastructure with the deployment of autonomous vessels, alleviating pressure from the streets.
Amsterdam is ideally suited to moving waste collection off its road network and onto its canals.
For example, by using Roboat to collect waste from Amsterdam’s city center, the number of traffic movements within the city center can be reduced. 

**3) Improve waste separation**

*Problem:* The current paradigm requires that residents take different types of trash to distinct locations, the inconvenience and complexity frequently result in lower recovery rates for recyclables and environmentally harmful waste. In response, Amsterdam is keen on significantly improving waste separation rates by 2020 [[ref](https://www.ams-institute.org/urban-challenges/smart-urban-mobility/roboat/)].

*Solution:* Roboat offers enormous possibilities in terms of environmental exploration and sensing. Roboats could also clear the canals from waste. The floating dumpsters can play a key role in source separation when other types of waste are added to the equation.

**4) Decrease visual pollution**

*Problem:* waste is currently placed at the curbs of the canals, distorting the view on the canals, taking up a lot of space and attracting rodents.

*Solution:* For the scenic views on the Amsterdam canals Roboat offers a more attractive way of collecting household waste.

* By placing the containers in the water, Roboat offers an alternative to the current built-in underground containers used throughout the city, which are unsuitable to be placed within the fragile quays of the canals. 
* Assuming that residents are willing to walk a maximum of 110 meters to dispose of household waste – the average distance Amsterdammers need to walk in other neighborhoods to bring their waste to the underground containers – approximately 48 floating containers need to be deployed in the canals to offer sufficient capacity.
* When the containers are full, a Roboat tug boat navigating autonomously will take the floating containers to the waste processing platform. With one vessel, the household waste of about 1100 households can be collected in a flexible and quiet way, without taking up space on the street.

### Questions on the status-quo

* What is the route of the trucks?
* What is the cost of the current system (trucks, labor, maintenance, quay wall reparations, etc.)?
* Are there areas only accessible by trucks? Where can Roboats successfully replace trucks?
* *"Our research shows that such a system could serve 70% of the Centrum district."* How to calculate this number?

### Current research

* [An Adaptive Large Neighbourhood Search for Real-Time Waste Collection Inventory Routing with Autonomous Vessels *T. Gast, B. Atasoy, F. Duarte, D. Rus*](http://senseable.mit.edu/papers/pdf/20200903_Gast-etal_WasteHotelRoboat_hEart.pdf) - Considers waste generated by hotels.
Investigates different waste generating scenarios and multiple re-optimisation strategies. Future research:
    * Heterogeneous set of containers with different sizes, to reduce the number of late picks.
    * Smarter, more complex operators can be investigated to enable the ALNS converge to a better solution.
    * Stochastic version.

* [Waste Collection in Amsterdam Centrum Using Autonomous Vessels: Optimization of container type selection and location for household waste collection in Amsterdam Centrum with Autonomous Vessels (Roboats) *H.J. van Toor*](https://repository.tudelft.nl/islandora/object/uuid:8d5e0ef2-63d1-42ea-a69e-1f8fc89f4b10/datastream/OBJ/download) - Considers a facility location problem with different facility types in order to maximize the coverage with a minimum number of containers.
    * Comparison: (1) Roboats,trucks, and EVs Vs. (2) Roboats and EVs.
        * EVs take filled containers to a barge which can carry multiple EcoCassetes.
        * Roboats take filled containers to a barge.
        * Trucks lift underground containers.
        * Barge sails to the AEB (Waste Energy Company).

    * Recommendations:
        * Assigning a few households to a specific container with a slightly larger walking distance than 150 meters, it could save some extra located containers.

