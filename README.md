# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11) in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

## How will this changed be analized?

To analise the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# Graph analyzes
Over the years there has been an incresed number of airports and flights going to the different airports in the USA and this is no difference for the period from 1999 - 2003. Even with the the terror attack in 2001 there was mutiple new airports that opened from 2002-2003 and the flights increased aslo substantially. From 1999 - 2000 there was 208 airports and this number incresed to 285 in the period 2002-2003, already here there is an indication that traveling nationally becomes more and more popular one reson the this rising popularity of travelling natianally with plains in the USA is becaouse the also has become much more efficient. In the period from 2002 - 2003 there has been a substantially decrease in the number of delayed flights and canceled flights, while the travel time is much shorter than driving across the states. This can be observed in the two tabels belows that shows the airports network from 1999-2000 and 2002 - 2003: 

| IATA | Region    | Strength | Avg Airtime | Avg Distance | Avg Dep Delay | Avg Arr Delay | Cancelled Origin Count | Diverted Origin Count |
|------|-----------|----------|-------------|--------------|---------------|---------------|------------------------|-----------------------|
| ORD  | Midwest   | 1190170  | 116.69      | 1370.14      | 14.56         | 14.24         | 35303                  | 1447                  |
| ATL  | Southeast | 1058168  | 93.49       | 1068.41      | 11.23         | 8.19          | 16137                  | 1057                  |
| DFW  | Southwest | 984122   | 122.35      | 1475.36      | 10.69         | 5.85          | 15963                  | 1410                  |
| LAX  | West      | 807862   | 140.57      | 1818.60      | 11.56         | 10.53         | 13715                  | 755                   |
| PHX  | Southwest | 733226   | 108.87      | 1332.34      | 13.22         | 10.38         | 7701                   | 681                   |
| STL  | Midwest   | 690592   | 94.63       | 1068.31      | 10.97         | 7.41          | 7392                   | 789                   |
| DTW  | Midwest   | 615381   | 92.20       | 1008.31      | 10.95         | 5.13          | 9546                   | 816                   |
| MSP  | Midwest   | 581397   | 109.05      | 1268.48      | 8.40          | 3.13          | 7808                   | 806                   |
| DEN  | Mountain  | 546186   | 114.88      | 1435.99      | 12.28         | 10.52         | 6657                   | 641                   |
| SFO  | West      | 544031   | 146.24      | 1912.95      | 13.61         | 15.80         | 12387                  | 621                   |

| IATA | Region    | Strength | Avg Airtime | Avg Distance | Avg Dep Delay | Avg Arr Delay | Cancelled Origin Count | Diverted Origin Count |
|------|-----------|----------|-------------|--------------|---------------|---------------|------------------------|-----------------------|
| ORD  | Midwest   | 1388214  | 105.26      | 1216.27      | 7.84          | 5.53          | 15285                  | 1104                  |
| DFW  | Southwest | 1228058  | 108.28      | 1235.17      | 5.61          | 1.01          | 8413                   | 884                   |
| ATL  | Southeast | 1201228  | 84.20       | 1029.34      | 7.90          | 5.82          | 6794                   | 950                   |
| LAX  | West      | 812923   | 131.84      | 1617.66      | 4.29          | 0.75          | 4480                   | 510                   |
| PHX  | Southwest | 687674   | 118.53      | 1453.29      | 6.93          | 1.57          | 3444                   | 569                   |
| IAH  | Southwest | 609715   | 113.04      | 1347.36      | 3.25          | 2.37          | 1801                   | 353                   |
| MSP  | Midwest   | 572741   | 112.53      | 1310.30      | 4.31          | 0.91          | 3469                   | 488                   |
| DTW  | Midwest   | 561032   | 92.66       | 1006.10      | 6.76          | 1.17          | 4261                   | 502                   |
| LAS  | West      | 547541   | 113.76      | 1409.50      | 6.89          | 3.65          | 1880                   | 480                   |
| DEN  | Mountain  | 524394   | 125.50      | 1415.76      | 4.34          | 1.35          | 2417                   | 386                   |

The two tabels shows the top 10 most visited airports in the USA, where "IATA" is the International Air Transport Association codes that is used to identify the different airports, "Strength" is the number of flights that visited that giving airport in the period, "Avg Airtime, "Avg Distance", "Avg Dep Delay" and "Avg Arr Delay" are all messured in hours. 



## Visualization of the graph

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

<img width="1346" height="717" alt="billede" src="https://github.com/user-attachments/assets/0db016f8-3eec-4bae-8f4d-d2df790c5138" />
<img width="1318" height="711" alt="billede" src="https://github.com/user-attachments/assets/0e0833af-1b3d-4c68-9eb6-550c6efea110" />

In the two figures it can be observed that the security and safty related words are not dominant at all, but it can be observed that in 2003 one of the frequent terms that got repeated a lot was "crashed". However because word cloud doesn't provide context to the terms is is not possible to determine from the visualitation that the term "chrashed" directly have a correlation to safty such as investigating airplane chrashes to prevent it for happeningn again. 

Similar, for 2010 word cloud contains the frequent terms such as "World War" and "War". But because of the missing context of the use of these specefic terms it is not possible to determine if they have a correlation to safty for the airports, but the terms might reflect military usech of the airports.





# Discussion

# Konlusion
