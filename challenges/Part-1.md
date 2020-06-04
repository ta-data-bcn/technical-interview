![Ironhack logo](https://i.imgur.com/1QgrNNw.png)


##  Data Science Challenge - Part 1

All the strategy here will be planned considering I have full access to Airbnb data base and the metrics of its website/app.

I'll provide not a solution but two; a simple (cheaper, easier and probably less accurate) and a hard solution (more expensive, more difficult but more accurate).

## Simple solution

### Database

I'll create a data set from Airbnb database. I'll consider each row being a Airbnb reservation.
The parameter studied will be:

- Owner of the place.
- City where the place is located.
- Area of the city where the place is located.
- Professional photos: yes/no.
- Date of booking.
- The Daily Price the place had during that reservation.

With this dataframe created and considering all the cleaning stuff is done and there is nothing wrong, like NaN or strange values:

### Analysis and Visualization

The data will be grouped my cities/area and then the time-line will be studied.
This time-line will be consider in months, so high and low seasons will be taken in mind.

A plot will be created. X axis: Time; Y axis: Mean earning/month.

3 lines will be shown:
*Places which had professional photos since the beginning.
*Places which never used proffessional photos.

Since each neigbourhood in a city has different mean prices, this approach should reduce the bias in our data caused by each place having a different price. Places that didnt have proffessional photos but at some point used proffesional photos will change category in that month. Also, for these owners who had amateur photos and then changed, it will be calculated after how long they did this change.


## Hard Solution

Would include the previous analysis but also would study how users navigate throught the website/app.
This study would classify each search in 2 categories: if the user booked a place or not.

In both cases, positive or negative, the percentage of proffessional/amateur photos will be calculated.
I will be able to know if there was a direct correlation between this percentage and the percentage of visits/bookings.

Also, it will be important the order of the possible options a user watched. It would be interesting if a person goes first to the places with proffessional photos or not.

## To conclude

No matter what solution we use, I will show how this proffessional photos affects sales. Also, according to this date, in case it improves the sale I will estimate how many month takes for an owner to amortize the investment. Being clear about this will allow the company not only to know proffessional photos are good but also to be more pedagogical with their clients.











