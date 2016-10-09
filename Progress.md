# Progress
### NYT API Experimenting
+ I searched ‘Presidential Debate’
+ timeline: Sept 26 - 28 (one day before debate to day after debate)
+ fl: keywords 
+ hl: true
+ ranked the keywords
+ facet field: type_of_material
+ facet filter: true
+ facet field will show the frequency of ‘Presidential Debate’ in different sections of NY Times

### Problems
+ not sure how to filter more through the data to find specific info to Presidential Election
  + Solved in next lab: fq: section_name (?)
  
### Intended query
+ Search 'Hillary Clinton' and 'Donald Trump'
+ Timeline: Aug 1 2016 - Oct 1 2016
  + Just after RNC and DNC to just after first Presidential Debate
+ Observe frequency of the appearance of Clinton and Trump and compare
+ Visualize a comparison, dive deeper into information to observe context within high spikes of frequency
  + This will allow us to answer a second question of whether the NYT coverage is substantial
 
### Problems
+ Not sure how to extract data from API to enter into R or visualisation
+ Alan showed how to enter into browser address and view as CSV but results are confusing and not sure how to read them
