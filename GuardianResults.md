#Results from The Guardian (UK)
### Donald Trump
+ Using the Guardian API we filtered the search to our timeline of Aug 1, 2016 - Oct 1, 2016
+ Important to our search was that we filter to only the U.S. section of the website
+ To collect the data, we found that the Guardian only returned 10 results per page. We changed the url to return 200 results to make it easier to collect the data into a CSV
+ Hits returned 533 results
+ **content.guardianapis.com/search?section=us-news&from-date=2016-08-01&to-date=2016-10-01&order-by=oldest&page=3&page-size=200&q=Donald Trump&api-key=d36cb96b-2722-46aa-adf6-f4af2a5ae259**

####Command in R and Plot
+ We collected each page of data into a CSV and cleaned it up because the publication dates included times in addition to the dates. We then wrote a command to read the CSV and count the number of times each date appeared and to read the plot.
+ Our variables were the daily dates on the x-axis and the number of mentions or frequency per day on the y-axis.

#### Script
library(plyr)
guardianTrump = read.csv("~/Desktop/ObjectsToData/guardianTrump1.csv");
count(guardianTrump, "webPublicationDate")
table(guardianTrump$webPublicationDate)
plot(table(guardianTrump$webPublicationDate), 
     xlab='Date', ylab='Number of mentions', main='Guardian: Donald Trump', type="l")

![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/guardiantrumpBAR.png)
+ Our first graph was a bar graph. Before adding "type="l"" to the script this bar graph was produced however it was a little difficult to see the overall frequency within the two month timeline. It was good to see each days results however we wanted to see the overall effect.
![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/guardiantrumpLINE.png)
+ After adding type="l" this graph was produced and it gave us a bigger picture of frequency within the timeline.

### Hillary Clinton
+ Using the Guardian API we filtered the search to our timeline of Aug 1, 2016 - Oct 1, 2016
+ Important to our search was that we filter to only the U.S. section of the website
+ To collect the data, we found that the Guardian only returned 10 results per page. We changed the url to return 200 results to make it easier to collect the data into a CSV
+ Hits returned 533 results
+ **content.guardianapis.com/search?section=us-news&from-date=2016-08-01&to-date=2016-10-01&order-by=oldest&page=3&page-size=200&q=Hillary Clinton&api-key=d36cb96b-2722-46aa-adf6-f4af2a5ae259**

####Command in R and Plot
+ Identical to the Trump analysis, we collected each page of data into a CSV and cleaned it up because the publication dates included times in addition to the dates. We then wrote a command to read the CSV and count the number of times each date appeared and to read the plot.
+ Our variables were the daily dates on the x-axis and the number of mentions or frequency per day on the y-axis.

#### Script
guardianTrump = read.csv("~/Desktop/ObjectsToData/guardianTrump1.csv");
count(guardianTrump, "webPublicationDate")
table(guardianTrump$webPublicationDate)
plot(table(guardianTrump$webPublicationDate), 
     xlab='Date', ylab='Number of mentions', main='Guardian: Donald Trump', type="l")

![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/guardianclintonBAR.png)
![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/hillaryguardianplotLINE.png)
