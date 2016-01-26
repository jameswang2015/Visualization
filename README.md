# Visualization
Udacity Final Project: Make Effective Data Visualization

##Summary
I preprocessed the given US airport information from 1987 to 2008 and generated “flight_US.json” which include top 20 busiest airports in the given years, then this json file is used as an input for this visualization project. The visualization follows martini glass theory. Note that in the given data if there is no information (“NaN”) for ArrDelay or DepDelay then that record is not included in this analysis.

##Design
The base of the martini glass shows the busiest airports (which has the most flights) each year. Notice that in the given year from 1987 to 2008 the busiest airports are either Chicago Ohare Intl or Hartsfield Jackson Atlanta Int, so in this base map only these two circles show up. This is followed with the animation which shows top 20 busiest airports starting from 1987 and ended with 2008; once at that point the year buttons are listed at the left of page to allow readers to select their desired year to check the detail. Also at this stage readers can hover mouse over each circles (representing the airports) which triggered a pop-up box showing detailed information such as airport name, total flight#, arrival delay information and departure delay information.

The US map is selected to show the geographic impact on airport delay. The northeast airports in general get more delay than all rest of areas while the west region is overall better than average. This may be because the northeast airports were developed much earlier than the rest of areas and the designed infrastructures are not sufficient to meet today’s traffic requirement. 

Going through each year readers can easily tell the traffic grows and flight delay gets worse; when closely comparing year 2000, 2001, 2002 and 2003, readers can see the traffic drops a bit and delay get lighted around 2001 and then increase gradually again after 2003, which shows the impact of 911 on airline industry.

Also notice the circle area instead of radius is encoded to represent the number of flights to avoid overrepresentation.

##Feedback
1. From the first feedback of matthew_240343, I changed the title and added the narrative to make the story clearer to readers. This is showed in GitHub commit *fbee756*:“Update title and add description”.

2. From the second feedback of my wife, I added legend to show the relationship of the circle size and the corresponding flight number – a larger circle represents busier airport with more flights. Note that here I use circle area (not circle radius) to correctly show the difference of airport traffic proportionally. This is showed at GitHub commit *575a8e5*:“version3: add legend for size of flight number”

3. In commit *e3392f1*:“Final version4:diverse color coding airport delay and create legend”, I applied diverse color coding to each airport (circle) based on the delay index defined in following formula: ArrDelay%* ArrDelayAverage+DepDelay%* DepDelayAverage. Corresponding legends are added as well. The airports with minimum delay is colored with “lime” and then gradually changed to “red” which represents the worst delay airport. Using diverse color coding can make the transition from light to heavy delay more smoothly and intuitively.

4. From the third feedback of ucaiado, I moved the legend of color and size to the beginning of the animation so that users can follow up with what is happening throughout the animation. Also, some bullet notes are added to show the story to readers. These changes are all reflected in the final GitHub commit *63c1c6f*:“moved legend, add bullet notes”.

5. From the fourth feedback of my colleague, I applied different color (red) for each individual year in the title and added more story in the bullet notes. This is final commit showed in *8e68cdc*:”update title and bullet notes”. 


##Resource
* [GEOJSON AND KML DATA FOR THE UNITED STATES](http://eric.clst.org/Stuff/USGeoJSON)
* [Airport, airline and route data](http://openflights.org/data.html)
* [Selection.data([values[, key]])](https://github.com/mbostock/d3/wiki/Selections#data)
* [SVG Color specification](http://www.w3.org/TR/SVG/types.html#DataTypeColor)
* [Diverse color coding by using d3.scale.linear()](https://github.com/mbostock/d3/wiki/Quantitative-Scales)
