# Objects to Data
### Group Proposal
Martin Roger Ze Schneider, Lars Mangel, Dominique Brouwer, Cassandra Sijtsma, Dianne Ocampo

##### Question
How often are Hillary Clinton Donald Trump mentioned on The New York Times as the Presidential Election nears its end? Who is mentioned more and is a higher number consistent with substantial coverage or tabloid coverage?

##### Method
The method we will be using is scraping. Our search terms will include "Donald Trump" and "Hillary Clinton." Since these two are already prominent American figures prior to this election, we will limit the timeline from August 1, 2016 to October 1, 2016; beginning shortly after the Republican National Convention (July 18-21, 2016) and Democratic National Conventions (July 25-28, 2016) and ending shortly after the first Presidential Debate (Sept. 27, 2016). We believe that this timeline allows us to avoid any spikes in frequency of mentions for either candidate due to an event coinciding with their party and allows space for coverage on both candidates following their first debate. We hope to delve deeper into our analysis following our initial scraping of frequency by looking into spike areas to see whether the event can be tied to a particular instance. These instances will hopefully reveal whether the majority of mentions of either candidate is critical, substantial, or simply tabloid coverage.


##### Visualisation
+ How often are Clinton and Trump mentioned between August 1, 2016 - October 1, 2016?
    + We plan to create a visual using a timeline on the x-axis of the daily dates between August 1, 2016 and October 1, 2016. The y-axis will show the frequency of mentions starting from 0 to the closest 10th. We will plot Clinton and Trump's results on individual graphs and follow with a third containing both results for comparison.

##### Data
The dataset we plan to scrape from is The New York Times API. To filter our queries we will first use the timeline mentioned above. Additionally, we will filter further by including parameters such as the filter query and field limit. We plan to filter and obtain data from only the "Presidential Election of 2016" section of the NYT. The field limit will allow us to view the keywords, intro snippet of the articles as well as the web url for each piece. This will give us a glimpse into the data and help us decide what information to look into after seeing frequency results. It will also show what section each article falls under, allowing us to distinguish between news, op-eds, and videos for example.
