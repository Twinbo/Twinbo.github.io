
# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11), aswell as across 1988-2007 in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

/\ skal erstatte det ovenover, men rettes lige til først. 

This projects explortes how airport traffic got affected by 9/11, and in general how airport routes evolved from late 80'ties to early 2000's. The project will also look into how different wording and topics evolves on each airports wikipedia page. The change in evation secutiry and in general is especialy intereting in this time period as major overhauls was done after the terrorist attack.  1. cite. The period which the text analysis will cover, is around 2003-2025, this is because wikipidia was founded in 2001, and only took off a couple of years later. TSA (Transportation Security Administration) was also created after the attack as a way to ensure proper security and rules for travel. 2. cite. This is also a direct result of the attact, which we hopely also can see in the data, aswell as how number of flights developed. 

1. cite: https://www.tsa.gov/about/employee-stories/day-tsa-history-november-19-2001
2. cite: https://www.gao.gov/products/gao-03-1150t

## Analysing Aviation Development Through Route Networks and Textual Change

To analyse the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# US airport flight dataset
The airline dataset is from RITA which was a unit within the U.S. Department of Transportation (USDOT). The unit manageed Bureau of Transportations Statistics (BTS), which collects data on airline on-time performace, traffic and finances. RITA was dissolved in 2015, but that years after our dataset was created. We downloaded the dataset from dataverse.hardvard.edu under the name "Data Expo 2009: Airline on time data" from American Statistical Association (ASA). The airline dataset has around 120 milion flights records in total, taking up around 12 GB of space. Each flight row has numarous features as date, depature time, arrival time, Carrier, Flightnum, Arrival delay / Depature delay, airtime, cancellation and ect. More detailed descriptions of the features can be seen on dataverse.hardvard.edu. 

The graph below shows that the total number of US domestic flights generally increased from 1988 to 2007. Flight numbers were fairly stable until the late 1990s, before increasing around 2000 and 2001. After 9/11, the number of flights dropped sharply in 2002 by nearly half a million flights, which is consistent with the major disruption in the aviation system after the terrorist attacks. However, air traffic began to recover in 2003 and continued to increase strongly in the following years.

Cancelled flights were much more unstable than total flights. The graph shows a clear peak around 2001, where cancellations increased dramatically, likely because of the security measures and disruption caused by 9/11. In 2002, cancellations dropped sharply as the aviation system reopened, but after that they started to increase again as more flight in general also increased. Diverted flights stayed much lower than cancelled flights and were quite stable across the years.

Overall, the graph shows long-term growth in US domestic air traffic, but it also shows that cancellations fluctuated significantly. This means that even though some short-term comparisons may show improvements in airport performance, these improvements were not necessarily permanent across the full time period.

<figure>
  <img width="100%" alt="US Domestic Flights 1988–2007" src="https://github.com/user-attachments/assets/b11416cc-4c07-410b-b04a-78f794675722" />

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
    <th colspan="6" align="center">Change from 2001 Pre 9/11 to 2001 Post 9/11</th>
  </tr>
  <tr>
    <th>Compared Airports</th>
    <th>Category</th>
    <th>2001 Pre 911</th>
    <th>2001 Post 911</th>
    <th>Change</th>
    <th>Interpretation</th>
  </tr>

  <tr>
    <td rowspan="7">All airports appearing in both periods<br><b>217 airports/nodes</b></td>
    <td><b>Total Flights</b></td>
    <td>534,460</td>
    <td>469,162</td>
    <td>-65,298 (-12.22%)</td>
    <td>Fewer total flights post-911 ↓</td>
  </tr>

  <tr>
    <td><b>Avg Airtime</b></td>
    <td>103.86</td>
    <td>101.08</td>
    <td>-2.78 (-2.68%)</td>
    <td>Slight decrease ↓</td>
  </tr>

  <tr>
    <td><b>Avg Distance</b></td>
    <td>1,197.65</td>
    <td>1,162.74</td>
    <td>-34.90 (-2.91%)</td>
    <td>Slight decrease ↓</td>
  </tr>

  <tr>
    <td><b>Avg Dep Delay</b></td>
    <td>8.82</td>
    <td>5.85</td>
    <td>-2.97 (-33.64%)</td>
    <td>Departure delays decreased ↓</td>
  </tr>

  <tr>
    <td><b>Avg Arr Delay</b></td>
    <td>7.18</td>
    <td>-0.07</td>
    <td>-7.25 (-101.02%)</td>
    <td>Arrival delays decreased strongly ↓</td>
  </tr>

  <tr>
    <td><b>Cancelled Origin Count</b></td>
    <td>12,694</td>
    <td>98,681</td>
    <td>+85,987 (+677.38%)</td>
    <td>Far more cancellations ↑</td>
  </tr>

  <tr>
    <td><b>Diverted Origin Count</b></td>
    <td>1,402</td>
    <td>1,205</td>
    <td>-197 (-14.05%)</td>
    <td>Fewer diversions ↓</td>
  </tr>
</table>

The cancelled flights network graph compares the airport network in August 2001 with September 2001. Each node represents an airport, and the lines between airports represent routes where cancelled flights occurred. The color of the routes show how many cancelled flights occurred on that route, using a log scale. This means that stronger/brighter routes indicate routes with many more cancellations.

The graph shows a clear difference between August and September. In August, the network had 204 airports and 1,060 weighted edges, with 13,318 cancelled flights. In September, the number of total flights decreased from 544,351 to 490,698, but the number of cancellations increased sharply to 99,324 as the table above showed. This means that even though fewer flights were operated in September, cancellations became much more common.

The September network is also visibly denser than the August network. There are more airports included in the cancellation network, increasing from 204 to 217, and the number of weighted edges increased from 1,060 to 1,582. This suggests that cancellations were not limited to only a few airports or routes, but spread across a larger part of the US domestic flight network.

Major airports such as LAX, DFW, ORD, ATL, DCA, LGA, and BOS are amoung the top 10 nodes in the network, with highest cancelled fligts. In September, many of these airports are connected by stronger and more visible cancellation routes, showing that large hubs were strongly affected. The graph therefore supports the idea that the disruption in September 2001 affected the national airport network broadly, rather than only individual airports.

It is also important to note that the average departure delay and average arrival delay decreased in September. However, this does not necessarily mean that the system performed better. Since many flights were cancelled, they were not included in the delay averages. Therefore, the most important result in this graph is the large increase in cancellations and the wider spread of cancelled routes across the airport network.


<figure>
  <img width="1775" height="646" alt="image" src="https://github.com/user-attachments/assets/b8a1e0ee-3c10-4dde-8dd3-3d80e7ff7ce7" />

  <figcaption>
    Figure: Pre vs Post 9/11 comparison network graph - Cancelled weigted edges.
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

<img width="1471" height="1047" alt="image" src="https://github.com/user-attachments/assets/c7318640-0708-4758-92b5-7bf6a7bc600f" />


The table shows that the middle periods had fewer weighted edges, but more flights per edge. This suggests that traffic became more concentrated, with more flights being operated on fewer airport-to-airport connections. The highest cancellation rate was in 1998–2002, which is expected because this period includes 2001 and the disruption after 9/11. In the final period, 2003–2007, the network expanded strongly again, with more airports and route connections, while the cancellation rate decreased compared with 1998–2002.

| Period | Total flights | Weighted edges | Flights per edge | Cancellations | Cancellation rate |
|---|---:|---:|---:|---:|---:|
| 1988–1992 | 25.7 million | 2,491 | ~10,300 | 273,127 | ~1.1% |
| 1993–1997 | 26.3 million | 2,107 | ~12,500 | 444,789 | ~1.7% |
| 1998–2002 | 27.8 million | 2,066 | ~13,500 | 782,651 | ~2.8% |
| 2003–2007 | 35.4 million | 3,949 | ~9,000 | 645,638 | ~1.8% |


# Text analyzes
The text analysis investigates the development of the descriptive language used to describe the airports in the Unites States of America (USA) has changed over time, especially in relation to security, terrorism, TSA, screening, and 9/11. This analysis is based on the historical text from Wikipedia from the airport pages withing the USA in the period from 2003-2025. For each year, the pages were scrabbed and stored in documents so it could be process for this analysis. 

The reason this analysis starts from 2003 and not 2001 or before where it really is interesting so it could be more in death on how 9/11 impacted the whole aviation system withing the airports itself, is because Wikipedia was lunched in 2001. In the first years of Wikipedia there was none, to very little, text available on many airport pages. Before Wikipedia became widely used, information about the many airports was commonly found through newsletters, newspapers, television, radio, or the official airports sources. Therefore, it was not possible to gather any meaningful text before 2003 on Wikipedia that could be used in a comparison.

This limitation of available text is important when interpreting the results. Such as in 2003 we were only able to gather around 15273 meaningful tokens, and this number of tokens has substantially increased over the years which also can be observed in the figure below. Already in 2025, we were able to gather 905719 tokens. One token describes one word, so the available meaningful words grows from 15273 words to 905719 words.

<figure>
  <img width="877" height="468" alt="billede" src="https://github.com/user-attachments/assets/38e5ace2-5c10-449a-933e-1c927e231ca5" />
  <figcaption>
    Figure: Shows the increasing available tokens on Wikipedia 
  </figcaption>
</figure>


Because of the growth of available meaningful words, later years has a naturally higher change of containing specific words such as security, TSA, screening, terror, or attack. Therefore, an increase in these terms necessary doesn’t mean that airport security became proportionately more important over the years in the text. Part of the increase may simply be caused by the fact of the more available text over the years. 


## Word clouds visualization
The word clouds shows the most important TF-IDF terms in the collected airports texts. The TF-IDF words highlights the words that is relative importen for a document compared to the full collections of documents. THis makes it useful to identify words that charactirase specifik periods. In the follwoing word clouds visualization there can be observed how the language was used in the hole poriode from 2003-2025 and after this there can be observed an comparison on how the language used by the airorts have changed over time. There will here be look upon a period from 2003-2014 that will be compared to 2015-2025. To make these word cloud visualization it was needed to have a lot of filtering, because some words such as "airport", destination location and city names was really generic for all the periods and because of this it would not be interresting to look upon the genaric most frequent words, because this wouldn't give an insigt of how the periods have changed over time.
<figure>
  <img width="1019" alt="billede" src="https://github.com/user-attachments/assets/5236cddf-5351-49b7-b3bd-96a9f33acf9a" />
  <figcaption>
    Figure: Shows the TF-IDF wordcloud for the whole periode 2003-2025
  </figcaption>
</figure>
In the word cloud visualization above it can be observed that many of the largest words are related to airport descriptions and functionality, such as administration, federal, united states, eneral and runway. This suggest that much of the Wikipidea text descripes the overall infrastructure, ownership, some location that failed to be filtered out but also the operations details of the aviation system.

The same goes for the periods from 2003-2014 and 2015-2025, in those periods it was also primaerly the administration of the airports and the avaition that is most frequent.

<figure>
  <img width="790" height="431" alt="billede" src="https://github.com/user-attachments/assets/ef0315fe-e9b0-477c-9360-b060f49e8ad0" />
  <figcaption>
    Figure: Shows the TF-IDF wordcloud fro the peiod 2003-2014
  </figcaption>
</figure>

<figure>
 <img width="790" height="431" alt="billede" src="https://github.com/user-attachments/assets/f9d1c964-8ca4-4b71-aae9-4efc763d6e22" />
  <figcaption>
    Figure: Shows the TF-IDF wordcloud fro the peiod 2015-2025
  </figcaption>
</figure>

In the two word clouds visualizations above there can be observed, that there have not been a big change of the language used on discribing the airports and avaition systems over time, but if we look at the big courpus for the hole period from 2003-2025 and then campare to the seperate two periods 2003-2014 and 2015-2025. It can be observed that secruaty for both the period 2003-2014 and 2015-2025 is much more frequent than the hole courpus combined, this indicates that the security in the airports and the avation industry always have been prioitised, but it is not a word that is not frequint enough to be noticiable. But this not the oly thing that can be observed, because in the earlier period from 2003-2014 some of the words that are slighty more frequent used than in the later periods from 2015-2025, is such as "accident" and "safty". This is an indication that in the earlier periods the safte of the planes was more important and written more about and the same goes for the accidents, but here it indicates that there might have been more accidents either regardin the planes or in the airports also had a higher focus point. But these interepetation also needs to be intepetated carefully, because in the later periods of the weekipidea texts contains much more text than the earlier. This means that because the words such as "safty" and "accident" seems to be more frequent in the ealier years, then it can be because of the limited text and there are therefore not as a big divertion use of words in the earlier years than the later years.  

## Development of secuirty-related terms
The figure below shows the TF-IDF scores for selected security-relates terms over time. The terms incluide security, TSA, screening, teroor, terrorsim, attack, September Elven and safety. The reason 9/11 is written as september eleven was because it prevented 9/11 to be filtered out of the documents and therefore september eleven replaced every place where 9/11 was written. These terms were chosen because they are related to airport secuirty and the broader consequences of 9/11.

<figure>
  <img width="1019" height="545" alt="billede" src="https://github.com/user-attachments/assets/2b0cf4fa-70e5-4d93-93a2-c18501698b05" />
  <figcaption>
    Figure: Shows the development of the term specific TF-IDF 
  </figcaption>
</figure>

The tesult from the observation above needs to be intepretaded carefully because of the amount of aviliable Wikipedia text increases strongly over time, as menchiened earlier the later years may contain more mentions of the security-level words simply because the documents are longer and more detailed. So these results from the TF-IDF score should not be interpretaded as direct evidence that airport secruity became more important over time, but rather as an indication of how the langauge in the aiprot pages shifts is focus on using these specifc word.

It can be observed in the figure is that the graph maximum TF-IDF score is around 0.02. This means that the selceted security-related terms do not dominate the airport texts. In other words, even though such terms as security, safety, TSA, and screening are relevant to the topic the Wikipidea airport pages are still mainly focused on general airport descriptions and infrastructures. 

In the TF-IDF score figure it can be observed that the mentioning of 9/11 was most frequent between 2003-2005 where it eversince have been slightly decresing aport in the middel of 2005-2010. This is not the only thing that is notiacible such as attack peaked around 2004 and 2010 which indicates that in this periods there was some insececurity regarding the avation, but ever since it has be fequently low. The terms such as security and safety increases stronlgy around 2008-2011 and still remains one of the important selected terms in later years, which also indicates that the safty and secruety in the aviation industry still remains important. 

But a surprigsengly observations that can be made is that the term TSA is not mentioned at all and the reason it is interesting is because that TSA stands for Transportation Security Administration, the reason this is an really important term when analyzing the direct impact 9/11 had for the avation system and the overall secrutity in the airports, is because the TSA was founded and signed because of 9/11 and here was established the 19'th November 2001. TSA is designed to prevent similar attacks in the future, where it driven by the disre to help the USA. TSA is responsible for screening passengers and baggage in the airpots and this is to strengthen the overall secruity and the safety in the airports. 
Source: https://www.tsa.gov/history

One possible explantion is that individuel Wikipedia pages often describe local airport infrastructure and historical developments, rather than national security agencies. Even though TSA is important for the airport security and the transporttation secruity as a hole, it may not be mentioned direclt on the aiport pages. This shows an important limitation of the text analysis because the Wikipedea airport pages may not fully capture broader institutional changes in avation security after 9/11. Another explination of this could also be related to the filtering of words and this could potentionelly lead TSA to be filtered out. 

# Discussion
The analysis of both the Newwork of US domestic flight and the textual history of airpot Wikipedia webpages reveals a complex story of disruption, adaption, and long-term structural evolution int he aviation setcor. 

The Immediate vs. Long-term impact of 9/11.

The immediate impact of the Sept. 11 Terrorist attack clearly show up in the flight network data from August to September 2001. The system responded
with a massiv surge in cancellations, actually freezing the network. The network graph of cancelattions demonstrates that this distruption was not isolated only to the easst coast - it densely affected major hubs nationwide like LAX, ORD, ATL, DFW etc. When we looking at a broader timeline from 1988-2007, the data shows remarkable resilience. By 2003, domestic flight volumes had recovered and continued to grwo, showing that the fear of terrorism did not permanently suppress the motivation for the public to fly. 

Network Topology and the Hub and Spoke Centralization.

A major finding from our network analysis is the structural evolution of the flight routes. Between the 1988-1992 period and the 1998-2002 period, the number of active airports and unique route connections (edges) decreased, yet the total number of flights increased. This visual observation is mathematically confirmed by the network's advanced metrics. The network exhibits negative assortativity (a disassortative network), meaning that highly connected major hubs predominantly connect to smaller regional airports, rather than small airports connecting to each other.
Coupled with a consistently short average path length despite a sparse edge density, these metrics prove that the US aviation industry successfully transitioned into a highly optimized "hub-and-spoke" model. While 9/11 caused a massive temporary disruption, this long-term centralization trend shows that operational efficiency and regional clustering (as confirmed by high Louvain modularity) were prioritized alongside new security measures.

The Textual evolution of airport security. 

The text analysis provides insights into how the narrative and identity of airports changed alongside the physical network. A huge limmitation to note is the abnormal growth of wikipedia itself - as the platform matured the sheer volume of available tokens grew from about 15.000 to 900.000 tokens.
Despite the limitiation, the TF-TDF analysis successfully highlights qualitative shifts in language. 
Interestingly, our hypothesis—that post-9/11 security terms would completely dominate modern airport descriptions - was not entirely supported by the data. As the word clouds illustrate, both the early (2003-2014) and later (2015-2025) periods remained heavily focused on basic physical infrastructure, administration, and geographical location (highlighted by terms like "runway", "terminal", and "federal").
While terms like "safety" and "security" did show sustained importance in the timeline analysis, highly specific institutional terms like "TSA" were surprisingly absent. This absence reveals a fascinating dynamic: Wikipedia pages are locally focused. They describe the physical construction of terminals and runways rather than the national federal agencies operating inside them. Furthermore, it highlights a classic NLP challenge, as crucial short-form acronyms like "TSA" can often be overshadowed by standard vocabulary or removed by data-filtering algorithms. Ultimately, the text data shows that while aviation safety remains a steady topic, the fundamental public description of an airport remains rooted in its physical infrastructure.
# Conclusion
This project set to explore how US airport traffic and security evolved surrounding the crucial events of September 11, 2001. By combining advanced network science with NLP, we conclude that the aviation secotr went through a dual tranformation - a mathematical  optimization of its phyisical routes and a fundamental shift in its operational identity.

The network data confirms that 9/11 caused an unpecedented, immidiate halt to domestic travl, charaterized by a massive, nationwide spike in flight cancellations. However, this disruotion was temporary. Our toptlogical matrics - specially the negative assortativity and short path lenghts from 1998 - 2007 - proves a long-term structual consolidation into a higly efficient, resilient hub-and-spoke system. 

Simultaneously, the text analysis of Wikipedia articles from 2003-2025 demonstrates how public documentation of these airports evolved. While the physical network recovered and optimized, the textual narrative remained heavily focused on physical infrastructure rather than national security policy. Although the direct institutional impacts of 9/11 (such as the TSA) reshaped the actual travel experience, local Wikipedia pages reflect a continued focus on geographical and operational facts. Ultimately, the data proves that while the US aviation network rapidly modernized its physical connections, the public identity of the airport remained firmly tied to its physical foundations.
