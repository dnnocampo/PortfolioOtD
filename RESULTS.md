# Final Findings

Martin Roger Ze Schneider, Lars Mangel, Dominique Brouwer, Cassandra Sijtsma, Dianne Ocampo

###Group Proposal
####Question

How often are Hillary Clinton Donald Trump mentioned on The New York Times as the Presidential Election nears its end? Who is mentioned more and is a higher number consistent with substantial coverage or tabloid coverage?

#####Method

The method we will be using is scraping. Our search terms will include "Donald Trump" and "Hillary Clinton." Since these two are already prominent American figures prior to this election, we will limit the timeline from August 1, 2016 to October 1, 2016; beginning shortly after the Republican National Convention (July 18-21, 2016) and Democratic National Conventions (July 25-28, 2016) and ending shortly after the first Presidential Debate (Sept. 27, 2016). We believe that this timeline allows us to avoid any spikes in frequency of mentions for either candidate due to an event coinciding with their party and allows space for coverage on both candidates following their first debate. We hope to delve deeper into our analysis following our initial scraping of frequency by looking into spike areas to see whether the event can be tied to a particular instance. These instances will hopefully reveal whether the majority of mentions of either candidate is critical, substantial, or simply tabloid coverage.

####Visualisation

How often are Clinton and Trump mentioned between August 1, 2016 - October 1, 2016?
We plan to create a visual using a timeline on the x-axis of the daily dates between August 1, 2016 and October 1, 2016. The y-axis will show the frequency of mentions starting from 0 to the closest 10th. We will plot Clinton and Trump's results on individual graphs and follow with a third containing both results for comparison.
Data

The dataset we plan to scrape from is The New York Times API. To filter our queries we will first use the timeline mentioned above. Additionally, we will filter further by including parameters such as the filter query and field limit. We plan to filter and obtain data from only the "Presidential Election of 2016" section of the NYT. The field limit will allow us to view the keywords, intro snippet of the articles as well as the web url for each piece. This will give us a glimpse into the data and help us decide what information to look into after seeing frequency results. It will also show what section each article falls under, allowing us to distinguish between news, op-eds, and videos for example.

## Results

To use the New York Times API we first obtained a key. From there we used the API to search our terms "Donald Trump" and "Hillary Clinton" within the timeline of August 1, 2016 - October 1, 2016. Initially, we began searching 
these terms within the query (q) parameter on the API. We also entered the facet_field parameter to section_name and the facet_filter to the value 'true'. This allowed us to see which sections involved the highest amount of articles that included our search terms. However, we ran into issues as this returned many results and all the parameters gave us a very messy CSV file to look through. After experimentation we finally found the simplest way to obtain the information we were looking for (publication dates and headline) was to search our terms within the filter query (fq) parameter with the label 'headline'. Therefore our searches looked like "headline: Trump" and "headline: Clinton". Additionally, we shortened our terms to the candidates' last names as we found that the timeline deduced the results enough to only pertain to the candidates as opposed to other issues regarding Trump or perhaps Bill Clinton instead of Hillary.

Our final query involved searching headlines only that included "Trump" or "Clinton" within the dates August 1 - October 1, 2016. The search was further filtered to only include the publication date, full headline, and web url. The url for this search appeared as: 

**http://api.nytimes.com/svc/search/v2/articlesearch.json?fq=headline:%22Trump%22&begin_date=20160801&end_date=20161001&sort=oldest&fl=headline,pub_date,web_url&hl=true&page=__**

AND

**http://api.nytimes.com/svc/search/v2/articlesearch.json?fq=headline:%22Clinton%22&begin_date=20160801&end_date=20161001&sort=oldest&fl=headline,pub_date,web_url&hl=true&page=__**

An issue we came across was that the NYT API only returned 10 results per page. Therefore we split up the process amongst the five of us to go through a set of pages. We took the data, put it through a json to CSV converter and compiled all the results into a CSV. 
We then took the CSV, cleaned it up to line up all the publication dates, and put it through R Studio to plot the results. We originally produced a bar graph to show the number of articles published each day involving headlines with "Trump" or "Clinton", but also decided to produce a line graph to create an easier overview of the frequency over the two months. 

The scripts we produced are as follows: 

**library(plyr)
NYTtrump = read.csv("~/Desktop/ObjectsToData/CSVTrump/trump1.csv");
count(NYTtrump, "pub_date")
table(NYTtrump$pub_date)
plot(table(NYTtrump$pub_date), 
     xlab='Date', ylab='Number of mentions', main='NYT: Trump', type="l")**
     
To create the line graph we simply added the "type="l"" to the end of the script.

![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/NYTTrumpBAR.png)
![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/NYTTrumpLINE.png)
![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/NYTClintonBAR.png)
![image](https://github.com/dnnocampo/PortfolioOtD/blob/master/NYTClintonLINE.png)

Our "Trump" search returned **1291** results, while "Clinton" returned **757** results. 
This confirmed our belief that Trump would be making more headlines due to his controversial campaign. 
However, it did not reveal our originally hypothesis that coverage of either candidate would increase as Election Day nears, both candidates have similar frequencies near the end of the timeline. Perhaps this shows that rather than focusing on each candidate, news articles are rather focusing on the election as a whole and looking at the real policy issues and campaigns.
Additionally, by including headlines and web urls in our CSV, we are able to refer to it when investigating the spikes in frequency. For example, Trump returned more than 40 results on Aug. 2. Our CSV shows that Trump had quite a busy time in the news during that time as he had casued rifts in the Republican party when he refused to endorse Paul Ryan and John McCain, was being criticized by Obama for his candidacy, and making controversial remarks about Korea, Russia, and Mexico.  
On the other hand, Clinton's busiest day in NYT headlines was Sept. 27 the day of the first presidential debate. 
