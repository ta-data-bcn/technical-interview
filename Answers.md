![Ironhack logo](https://i.imgur.com/1QgrNNw.png)

## Data Science Challenge

### Tips
- Include code, graphics and text in a combined output. Tell a story, and let us know very clearly about your thoughts and analytical process.

### Part 1: Experiment design

- Provide full details about how you will run experiments to assess the impact of this service on both hosts and guests. How will you ensure that the experiments are valid and not biased? 

The experiment will be an A/B testing with the following considerations:

* Select a percentage to deviate the traffic, let's assume 50% (to maximize the time to reach statistical significance).
* We must assure that the distribution of ages in the samples have the same proportion in both experiments to avoid age bias (e.g: millenials preferences).
* To avoid biasing in the quality of the shown photos, also those taken by smartphones should be taken by photographers. Thus, the impact of smartphone vs professional cameras can be analyzed at the same level of photography compositions.
* We have to consider that hosts might be skeptical about the changes so we should offer them some Airbnb rewards for those joining the campaing.
* From the point of view of guests, we would analyze the conversion rates comparing websites showing apartments with smartphone photography against professional photo cameras.
* The final analysis would asses for hosts which strategy of photography to follow.
* Actions to implement if professional photographer service is cancelled: make guidelines for users to take their photos with smartphones

<!---
* Does the analysis only for millenials make sense? If complete analysis, avoid bias considering ages!
* We would target millenials, thus the modifications on the website photos would be directed to people below 35 years.
* Measure not only conversion rates but also a comparison between hosts sales (think more about a possible bias introduced by long stays, not to measure exclusively on money)
-->


### Part 2: Result analysis

The analysis is presented in `distance_challenge` Jupyter Notebook.

#### Challenge
Try to answer the following questions:

1. Should the company move towards *road* distance? What's the max price it would make sense to pay per query? (make all the  assumptions you need, and make them explicit)
2. How would you improve the experimental design? Would you collect any additional data? 

After the analysis these are the concluding remarks:

* Neither the distributions of travel distances nor the distributions of travel durations obtained for the two systems of measurement show that there is statistical significance between the two.
* However, it is true that in particular cities, the status of the traffic is a key element to decide how to assign vehicles.
* Thus, the `road` distance would make a big different not for the average calls but in case of particular traffic events.
* A proposition would be to use a system of calls that instead of asking always the API uses instead the `linear` system and checks it every certain amount of time for traffic incidents and only switch in those cases.
* The price of the API calls can be costed using a percentage of the commission that we are gaining for each travel. We could take the median of these commissions and decide within the company which percentage is a proper value to assign for this cost.
* The experimental design could be improved considering each city as a particular case, adding more data to capture different traffic accidents for a longer period than 5 days and targeting the rush hours and analyzing them as special cases.

