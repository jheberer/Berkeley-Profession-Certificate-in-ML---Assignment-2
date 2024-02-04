# Berkeley-Profession-Certificate-in-ML---Assignment-2
### What drives the price of a car?

The following notebook was used to produce these findings: 
https://github.com/jheberer/Berkeley-Profession-Certificate-in-ML---Assignment-2/blob/main/car_price.ipynb

## Deployment
Now that we've settled on our models and findings, it is time to deliver the information to the client. You should organize your work as a basic report that details your primary findings. Keep in mind that your audience is a group of used car dealers interested in fine tuning their inventory.

### Problem Statement
The business goal here is to understand pricing for cars, discern the major attributes of a car that influence the pricing, and then build a model that helps us predict the pricing. A used car dealership is a very cash starved business, and the flow of inventory is very important. It's important to help dealers with this pricing model so that they can:
  1. Pay the appropriate price for new inventory
  2. Set profitable, yet competitive prices for consumers

If a dealer understands pricing then they can maximize margins and target certain stock.

### Modeling Process
A standard CRISP-DM model was followed in executing this analysis.

CRISP-DM is an industry standard and it entails Understanding the Problem, Understanding the Data, Preparing the Data, Modelling the Data, Evaluating Findings, and lastly, sharing findings such as providing a report like this one.

Of these, preparing the data was the most complex and risk heavy portion of the analysis, because inappropriate data preparation could cause unknown deleterious affects on the model.
It is necessary here to disclose what changes were made to the data, so that it is known what data was in--and not in--the model.
  1. ID
  2. VIN
  3. State
  4. Model
  5. Manufacturer
  6. Region
  7. Paint Color

These values were either meaningless in this context (ID, VIN), or too complex or specific to suit the model (State, Model, Manufacturer, Region, Paint Color).
For the latter group, remodeling based on subsets of these data points (like a pricing model specific to Manufacturer) might benefit some dealers.

Without being too technical, cylinders was dropped after additional data exploration, as it was determined to be too highly correlated to other variables like size and certain (larger) vehicle types.

It's clear that some of the data was junky, as there were odometer readings as high as 10,000,000, and prices as high as $3,736,929,000. These outliers were addressed appropriately.

### Findings
The model is generally effective, with its accuracy decreasing for vehicles that are priced at roughly $20,000 and up, where it tends to underestimate price. Please bear this in mind when reviewing these results.
A follow-up for a pricing model specifically for more expensive vehicles, or an even more extensive modeling process like this would be a good follow-up.

![image](https://github.com/jheberer/Berkeley-Profession-Certificate-in-ML---Assignment-2/assets/7217117/ae16ce62-f8d8-4ed9-8a38-b2ad258205ee)


Several models were tested, scored, and optimized. Our final model predicts that consumers value the following attributes highest:
* Newer
* Trucks, pickups (as opposed to sedans or coupes)
* Better condition
* Less mileage
* Secured title

Year was the greatest determination in price. For every additional year (newer), a vehicle increases by $573 dollars ($3300 for every 5.75 years to adhere more strongly to the model).
On the flip side, for every 49,000 miles on the odometer, a vehicle loses $2550 in value.

### Business Recommendation(s)
The recommendation is clear: If dealers want to maximize prices, they should stock larger vehicles, especially trucks and pickups.
Vehicles with less mileage are highly preferred.
When possible, the dealer should be willing to invest significant money into improving the condition of the vehicle.
Also, dealers avoid complicated lien statuses.

### Next Steps
As previously mentioned, there are some improvements that could be made to this model. Specifically, it would be useful to run region based or manufacturer based analyses to help dealers in specific regions and stocking exclusively for certain manufacturers.
I recommend we also invest in getting better model information, as the data we acquired initially is not at all useful; model data needs to be standardized.
