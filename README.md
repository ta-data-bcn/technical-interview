![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

## Data Science Challenge

The purpose of this challenge is to assist us in evaluating candidates for a role in our Product team. We only pass this challenge to candidates that we feel have a solid background and could be a good fit for our team. We appreciate you taking this time to help ensure we’re a good fit for each other.

### Tips
- Include code, graphics and text in a combined output. Tell a story, and let us know very clearly about your thoughts and analytical process.

### Part 1: Experiment design
#### Background
In 2011 AirBnB ran some experiments which showed that when a property featured professional photography, users were much more likely to trust the property and consequently make a booking. So, AirBnB a launched [free professional photography service](https://www.airbnb.com/professional_photography) for all hosts. From inside the listing page, hosts were able to click a link to view more about the service, request a professional photographer, and subsequently (after the photo shoot) have their property profile updated with professional photos. 

The project initially proved to be a success:
- Guests were more likely to book a property that had professional photography.
- Hosts were able to charge more for listings with professional photos.

However, over time this also became a multimillion dollar operation and a challenge to manage across over 200 countries. 

Fast forward to 2016, and some new developments have also helped with building trust:

- 2013: Launch of identity verification for hosts and guests.
- 2014: Launch of double blind reviews (neither host nor guest can see the other’s review), ensuring more honest reviews of properties and hosts. 
- 2015: Huge global PR lift for AirBnB, raising the profile of the company.

An additional interesting development has also been the proliferation of smartphones with powerful and high-quality cameras (+apps) over the last few years, which has made it more possible for hosts to take good quality photos of their property. There is also the opinion that perhaps millennials have come to expect smartphone photos as the norm and are less likely to expect professional photography. 

#### Challenge

Since the professional photography service consumes so many operational and financial resources, AirBnB management are unsure if they should continue. AirBnB management have asked the Data Science team to analyse the impact of the professional photography service in order to determine whether or not they should continue funding the service. 

- Provide full details about how you will run experiments to assess the impact of this service on both hosts and guests. How will you ensure that the experiments are valid and not biased? 

### Part 2: Result analysis

#### Background
A ride hailing app currently assigns new incoming trips to the _closest_ available vehicle. To compute such distance, the app currently computes haversine distance between the pickup point and each of the available vehicles. We refer to this distance as *linear*. 

However, the expected time to reach A from B in a city is not 100% defined by Haversine distance:
cities are known to be places where huge amount of transport infrastructure (roads, highways, bridges, tunnels) is deployed to increase capacity and reduce average travel time. Interestingly, this heavy investment in infrastructure also implies that bird distance does not work so well as proxy, so the isochrones for travel time from certain location drastically differ from the perfect circle defined by bird distance, as we can see in this example from CDMX where the blue area represents that it is reachable within a 10 min drive. 

![Imgur](https://i.imgur.com/hYXhpiM.png)
 
In addition to this, travel times can be drastically affected by traffic, accidents, road work...So that even if a driver is only 300m away, he might need to drive for 10 min because of road work in a bridge.

#### Proposal
In order to optimise operations, engineering team has suggested they could query an external real time maps API that not only has roads, but also knows realtime traffic information. We refer to this distance as *road* distance.

In principle this assignment is more efficient and should outperform *linear*. However, the queries to the maps API have a certain cost (per query) and increase the complexity and reliability of a critical system within the company. So Data Science team has designed an experiment to help engineering to decide.

#### Experimental design

The designed experiment is very simple. For a period of 5 days, all trips in 3 cities (Bravos, Pentos and Volantis) have been randomly assigned using *linear* or *road* distance:

* Trips whose *trip_id* starts with digits 0-8 were assigned using *road* distance.
* Trips whose *trip_id* starts with digits 9-f were assigned using *linear* distance.

#### Data description
The collected data is available in [this link](https://www.dropbox.com/s/e3j1pybfz5o3vq9/intervals_challenge.json.gz?dl=0). Each object represent a `vehicle_interval` that contains the following attributes:

* `type`: can be `going_to_pickup`, `waiting_for_rider` or `driving_to_destination`. 
* `trip_id`: uniquely identifies the trip.
* `duration`: how long the interval last, in seconds.
* `distance`: how far the vehicle moved in this interval, in meters.
* `city_id`: either bravos, pentos and volantis.
* `started_at`: when the interval started, UTC Time.
* `vehicle_id`: uniquely identifies the vehicle.
* `rider_id`: uniquely identifies the rider.

#### Example
```
{
  "duration": 857,
  "distance": 5384,
  "started_at": 1475499600.287,
  "trip_id": "c00cee6963e0dc66e50e271239426914",
  "vehicle_id": "52d38cf1a3240d5cbdcf730f2d9a47d6",
  "city_id": "pentos",
  "type": "driving_to_destination"
}
```

#### Challenge
Try to answer the following questions:

1. Should the company move towards *road* distance? What's the max price it would make sense to pay per query? (make all the  assumptions you need, and make them explicit)
2. How would you improve the experimental design? Would you collect any additional data? 

### Special thanks
Thanks to davidmyths and gusy for the challenge.
