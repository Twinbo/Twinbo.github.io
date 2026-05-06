
# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11) in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

## How will this changed be analized :)?

To analise the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# US airport flight dataset
The airline dataset is from RITA which was a unit within the U.S. Department of Transportation (USDOT). The unit manageed Bureau of Transportations Statistics (BTS), which collects data on airline on-time performace, traffic and finances. RITA was dissolved in 2015, but that years after our dataset was created. We downloaded the dataset from dataverse.hardvard.edu under the name "Data Expo 2009: Airline on time data" from American Statistical Association (ASA). The airline dataset has around 120 milion flights records in total, taking up around 12 GB of space. Each flight row has numarous features as date, depature time, arrival time, Carrier, Flightnum, Arrival delay / Depature delay, airtime, cancellation and ect. More detailed descriptions of the features can be seen on dataverse.hardvard.edu. 

The graph below shows that the total number of US domestic flights generally increased from 1988 to 2007. Flight numbers were fairly stable until the late 1990s, before increasing around 2000 and 2001. After 9/11, the number of flights dropped sharply in 2002 by nearly half a million flights, which is consistent with the major disruption in the aviation system after the terrorist attacks. However, air traffic began to recover in 2003 and continued to increase strongly in the following years.

Cancelled flights were much more unstable than total flights. The graph shows a clear peak around 2001, where cancellations increased dramatically, likely because of the security measures and disruption caused by 9/11. In 2002, cancellations dropped sharply as the aviation system reopened, but after that they started to increase again. Diverted flights stayed much lower than cancelled flights and were quite stable across the years.

Overall, the graph shows long-term growth in US domestic air traffic, but it also shows that cancellations fluctuated significantly. This means that even though some short-term comparisons may show improvements in airport performance, these improvements were not necessarily permanent across the full time period.

<figure>
  <img src="https://github.com/user-attachments/assets/08299700-7a7a-41e4-8453-fe46a3dd7621"
       alt="US Domestic Flights 1988–2007" width="100%">
  <figcaption>
    Figure: Trends in total, canceled, and diverted US domestic flights from 1988 to 2007.
  </figcaption>
</figure>

# Graph analyzes
For further analyse we will first take a closer look into the flight records one month before and the month of the terrorist attack. Before analysing the changes, it is important to understand that the categories in the table are measured in different ways. Some variables are measured in minutes, such as average airtime, average departure delay, and average arrival delay. Average distance is measured in kilometers, while total flights, cancelled origin count, and diverted origin count are flight counts. Therefore, the table should be read by comparing each category between August and September, rather than comparing the raw values across different categories.

The table gives a more detailed view of how air traffic changed from August 2001 to September 2001. The most noticeable change is the large increase in cancelled flights. Although total flights decreased by almost 10%, cancelled origin counts increased by more than 645%. This suggests that the September 11 attacks had a major immediate impact on the airline system, with many planned flights being cancelled rather than delayed.

An interesting observation is that both average departure delay and average arrival delay decreased in September. At first, this could make it look like flight performance improved. However, this result should be interpreted carefully. Since many flights were cancelled, they would not be included in the delay averages. Therefore, the lower delay values do not necessarily mean that airports operated more efficiently. Instead, it may show that fewer delayed flights actually took place because many flights were removed from the schedule.

The diverted origin count also decreased slightly, but this may be connected to the lower total number of flights in September. Since there were fewer flights overall, there were also fewer opportunities for diversions. Therefore, the decrease in diversions is less important than the large increase in cancellations.

Overall, the table shows that September 2001 was not mainly characterized by longer delays, but by a sharp reduction in flights and a major increase in cancellations. This supports the idea that the terrorist attack caused a sudden disruption to US domestic air traffic.

This means that cancellation count is the most important indicator in this comparison, because it captures the disruption more clearly than average delay or diversion count.

<table>
  <tr>
    <th colspan="6" align="center">Change from 2001 Aug to 2001 Sep</th>
  </tr>
  <tr>
    <th>Compared Airports</th>
    <th>Category</th>
    <th>2001 Aug</th>
    <th>2001 Sep</th>
    <th>Change</th>
    <th>Interpretation</th>
  </tr>

  <tr>
    <td rowspan="7">All airports appearing in both periods</td>
    <td><b>Total Flights</b></td>
    <td>544,335</td>
    <td>490,698</td>
    <td>-53,637 (-9.85%)</td>
    <td>Fewer total flights in Sep ↓</td>
  </tr>

  <tr>
    <td><b>Avg Airtime</b></td>
    <td>72.48</td>
    <td>71.28</td>
    <td>-1.20 (-1.66%)</td>
    <td>Slight decrease ↓</td>
  </tr>

  <tr>
    <td><b>Avg Distance</b></td>
    <td>752.21</td>
    <td>741.35</td>
    <td>-10.86 (-1.44%)</td>
    <td>Slight decrease ↓</td>
  </tr>

  <tr>
    <td><b>Avg Dep Delay</b></td>
    <td>6.96</td>
    <td>4.64</td>
    <td>-2.31 (-33.27%)</td>
    <td>Departure delays decreased a lot ↓</td>
  </tr>

  <tr>
    <td><b>Avg Arr Delay</b></td>
    <td>8.93</td>
    <td>3.27</td>
    <td>-5.66 (-63.39%)</td>
    <td>Arrival delays decreased strongly ↓</td>
  </tr>

  <tr>
    <td><b>Cancelled Origin Count</b></td>
    <td>13,318</td>
    <td>99,324</td>
    <td>+86,006 (+645.79%)</td>
    <td>Far more cancellations ↑</td>
  </tr>

  <tr>
    <td><b>Diverted Origin Count</b></td>
    <td>1,574</td>
    <td>1,386</td>
    <td>-188 (-11.94%)</td>
    <td>Fewer diversions ↓</td>
  </tr>
</table>

The cancelled flights network graph compares the airport network in August 2001 with September 2001. Each node represents an airport, and the lines between airports represent routes where cancelled flights occurred. The color of the routes show how many cancelled flights occurred on that route, using a log scale. This means that stronger/brighter routes indicate routes with many more cancellations.

The graph shows a clear difference between August and September. In August, the network had 204 airports and 1,060 weighted edges, with 13,318 cancelled flights. In September, the number of total flights decreased from 544,351 to 490,698, but the number of cancellations increased sharply to 99,324 as the table above showed. This means that even though fewer flights were operated in September, cancellations became much more common.

The September network is also visibly denser than the August network. There are more airports included in the cancellation network, increasing from 204 to 217, and the number of weighted edges increased from 1,060 to 1,582. This suggests that cancellations were not limited to only a few airports or routes, but spread across a larger part of the US domestic flight network.

Major airports such as LAX, DFW, ORD, ATL, DCA, LGA, and BOS are amoung the top 10 nodes in the network, with highest cancelled fligts. In September, many of these airports are connected by stronger and more visible cancellation routes, showing that large hubs were strongly affected. The graph therefore supports the idea that the disruption in September 2001 affected the national airport network broadly, rather than only individual airports.

It is also important to note that the average departure delay and average arrival delay decreased in September. However, this does not necessarily mean that the system performed better. Since many flights were cancelled, they were not included in the delay averages. Therefore, the most important result in this graph is the large increase in cancellations and the wider spread of cancelled routes across the airport network.


<figure>
  <img src="https://github.com/user-attachments/assets/379e2b7b-917b-4b00-8017-099e1269f7d1" 
       alt="US Domestic Flights 1988–2007" width="100%">
  <figcaption>
    Figure: Septemper 2001 vs August 2001 comparison network graph - Cancelled weigted edges.
  </figcaption>
</figure>

## General aviations developments graphs
The below graph is a 5 year split of the entire dataset. The first and last year of the dataset are excluded as they were not whole years, just some parts of the months. So each period the totel flights are summed, and so on for each feature. Now the edges are just the weigdes flight between two airports IATA. So for example LAX to JFK will have one edge, but its color will be depending on the weigth on a log scaled shown on each graph. A small statistics box is also attached for each period, which the most nodes in the last period from 2003-2007. 

The airports are split into communities by Louvain, which clearly split the nodes into its seprate region when looking at the map. We wanted top 5 communites, but for some of the perioed louvain created less. In general the nodes communities are split into EAST, WEST, SOUTH and MID/NORTH region. Where the top communies are located changes from period to period, but where it creates the communites seems to be consistant across all periods. 

From the 1. period 1988–1992 to 2. period 1993–1997, the number of airports decreased from 260 to 234, and the number of weighted edges decreased from 2,491 to 2,107. This means that the network had fewer airport-to-airport connections, even though the total number of flights increased from about 25.7 million to 26.3 million. The same pattern continues in 1998-2002, where the number of airports remained lower than in the 1. period and the number of weighted edges decreased further to 2,066, while total flights increased to about 27.8 million.

This suggests that the US domestic flight network became more concentrated. In other words, airlines may have operated more flights on fewer routes, instead of spreading flights across many different airport connections. Therefore, the missing airports should not automatically be interpreted as airports closing permanently. It is more likely that some airports or routes became less active in this dataset, while larger hub airports and important routes handled more traffic. We definatively don't have the data for these removed airports. 

This development fits with changes in US aviation after deregulation, where airlines increasingly organized their routes around hub-and-spoke systems. In this type of system, traffic is concentrated through major hub airports, while smaller airports may have fewer direct connections. GAO also found that although many airports gained service after deregulation, some small- and medium-sized communities experienced decreases in service. Therefore, the decrease in airports and edges can be interpreted as a sign of network centralization rather than an overall decline in air traffic.

https://www.gao.gov/products/t-rced-96-126?utm_source=

https://transportgeography.org/contents/chapter5/air-transport/hub-spoke-deregulation/

<img width="1512" height="1062" alt="image" src="https://github.com/user-attachments/assets/0aa8af3e-a059-40fc-90a6-d9f535857d7f" />


The table shows that the middle periods had fewer weighted edges, but more flights per edge. This suggests that traffic became more concentrated, with more flights being operated on fewer airport-to-airport connections. The highest cancellation rate was in 1998–2002, which is expected because this period includes 2001 and the disruption after 9/11. In the final period, 2003–2007, the network expanded strongly again, with more airports and route connections, while the cancellation rate decreased compared with 1998–2002.

| Period | Total flights | Weighted edges | Flights per edge | Cancellations | Cancellation rate |
|---|---:|---:|---:|---:|---:|
| 1988–1992 | 25.7 million | 2,491 | ~10,300 | 273,127 | ~1.1% |
| 1993–1997 | 26.3 million | 2,107 | ~12,500 | 444,789 | ~1.7% |
| 1998–2002 | 27.8 million | 2,066 | ~13,500 | 782,651 | ~2.8% |
| 2003–2007 | 35.4 million | 3,949 | ~9,000 | 645,638 | ~1.8% |


# Text analyzes
Because Wikipedia was lunched in 2001 it was not feasiable to find text documents that the described the security in the airports and for this reason we are analysing some texts from 2003 and compare those with texts from 2010. There was used webscrabing with weekipidias own API'S for all the airports in the USA to gather all the aviable texts from 2003 to 2025. The table below describes how many words we scrabed through the years from every airprot, it can be observed that the newer the year is the more text was avaible:

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

The table above illustrate the number of words gathered from the airports in the USA from weekpidea over the years, but it can be observed that the number of words has been substancually increased over the years and this is a problem for analyzing how the security in the aiprots has become more strict and increased. The reason for this is because the later years contains more secruety-related language than the sparse early-years. As a result of this, the later documents are more likely to contain security-related language simply because the documents are longer and more detialed.

These issues is also important to take into consideration when interpretating the TF-IDF scores shown in the following table. TF-IDF scores messure how important a term is within a document relative to the full collection of documents. In this case the TF-IDF scores shows an indication of how promenent selected security-related words are in the airport texts from 2003 and 2010. But because of the massive difference of availe text between 2003 and 2010 the TF-IDF values needs to be intepretaed cautiously. 

| TERM      | TF-IDF SCORE (2003) | TF-IDF SCORE (2010) | PERCENT CHANGE (2003→2010) |
|-----------|---------------------|---------------------|----------------------------|
| SECURITY  | 0.0087              | 0.0180              | +106.9%                    |
| SAFETY    | 0.0000              | 0.0221              | NEW                        |
| TSA       | 0.0000              | 0.0036              | NEW                        |
| SCREENING | 0.0000              | 0.0054              | NEW                        |
| SEPTEMBER | 0.0087              | 0.0281              | +223.0%                    |
| ATTACK    | 0.0000              | 0.0049              | NEW                        |

It can be observed in the table above that several security-related terms appear with higher TF-IDF scores in 2010 than in 2003. This suggest that security-language became more visuable in the airport texts over time. However, this is not a direct proof that the airport security itself became stricter after 9/11, the major reason for this is because the size difference of the text from 2003 and 2010. The 2003 text only contains 183 words and the 2010 text contains 3387 words which means there is much more room for mentioning security-related words more in deepth and detail. This means these resutls are better understood as an indication that the security is more promenant in the recent years. Because of the security-related words is such a small part of the combined words used in all the texts, they will not be as dominent in the word cloud visualition as expected. 
## Word clouds visualization

The two figures below shows the word cloud visualization with the most frequent used words with in the documents from 2003 and 2010. The bigger the terms are in the word cloud visualitation the more frequent that specific word is.

<img width="900" alt="billede" src="https://github.com/user-attachments/assets/0db016f8-3eec-4bae-8f4d-d2df790c5138" />
<img width="900" alt="billede" src="https://github.com/user-attachments/assets/0e0833af-1b3d-4c68-9eb6-550c6efea110" />

In the two figures it can be observed that the security and safty related words are not dominant at all, but it can be observed that in 2003 one of the frequent terms that got repeated a lot was "crashed". However because word cloud doesn't provide context to the terms is is not possible to determine from the visualitation that the term "chrashed" directly have a correlation to safty such as investigating airplane chrashes to prevent it for happeningn again. 

Similar, for 2010 word cloud contains the frequent terms such as "World War" and "War". But because of the missing context of the use of these specefic terms it is not possible to determine if they have a correlation to safty for the airports, but the terms might reflect military usech of the airports.





# Discussion

# Konlusion
