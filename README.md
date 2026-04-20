# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11) in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

## How will this changed be analized?

To analise the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# Graph analyzes

## Visualization of the graph

# Text analyzes
Because Wikipedia was lunched in 2001 it was not feasiable to find text documents that the described the security in the airports and for this reason we are analysing some texts from 2003 and compare those with texts from 2010. There was used webscrabing technices to gather all the texts from the weekipidia from 2001 to 2025 with searching for the hearders that contain "airport security". Through the webscrabing there aere already an indication in the different documents with the titel "Aiport Security" becomes lager and larger, this can also be seen in the following table:

| Year | Status | Cleaned Words Found |
|------|--------|---------------------|
| 2001 | Too short / not found | - |
| 2002 | Too short / not found | - |
| 2003 | Found | 182 |
| 2004 | Found | 390 |
| 2005 | Found | 1056 |
| 2006 | Found | 1424 |
| 2007 | Found | 2175 |
| 2008 | Found | 2919 |
| 2009 | Found | 3148 |
| 2010 | Found | 3387 |
| 2011 | Found | 3372 |
| 2012 | Found | 3595 |
| 2013 | Found | 3915 |
| 2014 | Found | 4012 |
| 2015 | Found | 4033 |
| 2016 | Found | 4035 |
| 2017 | Found | 4111 |
| 2018 | Found | 3863 |
| 2019 | Found | 3894 |
| 2020 | Found | 4276 |
| 2021 | Found | 4318 |
| 2022 | Found | 4351 |
| 2023 | Found | 4500 |
| 2024 | Found | 4515 |
| 2025 | Found | 4599 |

But these found words in the documents which has been tokinized, they do not indicate if it is only the airport secruety that is mentioned in the documents. If there are multiple topics with a lot of filler words in the documents with the header "Airport Security" then it will lead for the specific workds ass "airport security, torrerism, war ect.." will become a very small procent of the most frequent words. But even if the documents is only about "Aiport Security" and they don't use those words frquently, then it will be hard to observe any changes over the year. Because of these issues, there was used a lot of different stopper words when making the TF-IDF scores and the words cloud visualizer. Some of the stopper words there was used is such ass "gate, concourse, airlink, pinnacle, ect...". The comparison of the TF-IDF scores from 2003 vs 2010 can be seen in the following table:



## Word clouds visualization

# Discussion

# Konlusion
