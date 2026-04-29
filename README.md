<style>
  .container {
    max-width: 1400px;
    margin: auto;
  }
</style>

<div class="container">

# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11) in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

## How will this changed be analized?

To analise the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# Graph analyzes
Over the years there has been an incresed number of airports and flights going to the different airports in the USA and this is no difference for the period from 1999-2003. Even with the the terror attack in 2001 there was mutiple new airports that appered from 2002-2003 and the flights increased aslo substantially. From 1999-2000 there was 208 airports and this number incresed to 285 in the period 2002-2003. There is a substantially decrease in the number of delayed flights and cancled flights in the period from 2002-2003 then from 1999-2000. The overall distance also changed between these two time periods, in the period from 1999-2000 the average distance was longer than the average distance from 2002-2003. This can be observed in the two tabels belows that shows the airports network from 1999-2000 and 2002 - 2003: 

<table>
  <tr>
    <th colspan="9" align="center">Time period: 1999–2000</th>
  </tr>
  <tr>
    <th>IATA</th>
    <th>Region</th>
    <th>Strength</th>
    <th>Avg Airtime</th>
    <th>Avg Distance</th>
    <th>Avg Dep Delay</th>
    <th>Avg Arr Delay</th>
    <th>Cancelled Origin Count</th>
    <th>Diverted Origin Count</th>
  </tr>
  <tr>
    <td>ORD</td>
    <td>Midwest</td>
    <td>1190170</td>
    <td>116.69</td>
    <td>1370.14</td>
    <td>14.56</td>
    <td>14.24</td>
    <td>35303</td>
    <td>1447</td>
  </tr>
  <tr>
    <td>ATL</td>
    <td>Southeast</td>
    <td>1058168</td>
    <td>93.49</td>
    <td>1068.41</td>
    <td>11.23</td>
    <td>8.19</td>
    <td>16137</td>
    <td>1057</td>
  </tr>
  <tr>
    <td>DFW</td>
    <td>Southwest</td>
    <td>984122</td>
    <td>122.35</td>
    <td>1475.36</td>
    <td>10.69</td>
    <td>5.85</td>
    <td>15963</td>
    <td>1410</td>
  </tr>
  <tr>
    <td>LAX</td>
    <td>West</td>
    <td>807862</td>
    <td>140.57</td>
    <td>1818.60</td>
    <td>11.56</td>
    <td>10.53</td>
    <td>13715</td>
    <td>755</td>
  </tr>
  <tr>
    <td>PHX</td>
    <td>Southwest</td>
    <td>733226</td>
    <td>108.87</td>
    <td>1332.34</td>
    <td>13.22</td>
    <td>10.38</td>
    <td>7701</td>
    <td>681</td>
  </tr>
  <tr>
    <td>STL</td>
    <td>Midwest</td>
    <td>690592</td>
    <td>94.63</td>
    <td>1068.31</td>
    <td>10.97</td>
    <td>7.41</td>
    <td>7392</td>
    <td>789</td>
  </tr>
  <tr>
    <td>DTW</td>
    <td>Midwest</td>
    <td>615381</td>
    <td>92.20</td>
    <td>1008.31</td>
    <td>10.95</td>
    <td>5.13</td>
    <td>9546</td>
    <td>816</td>
  </tr>
  <tr>
    <td>MSP</td>
    <td>Midwest</td>
    <td>581397</td>
    <td>109.05</td>
    <td>1268.48</td>
    <td>8.40</td>
    <td>3.13</td>
    <td>7808</td>
    <td>806</td>
  </tr>
  <tr>
    <td>DEN</td>
    <td>Mountain</td>
    <td>546186</td>
    <td>114.88</td>
    <td>1435.99</td>
    <td>12.28</td>
    <td>10.52</td>
    <td>6657</td>
    <td>641</td>
  </tr>
  <tr>
    <td>SFO</td>
    <td>West</td>
    <td>544031</td>
    <td>146.24</td>
    <td>1912.95</td>
    <td>13.61</td>
    <td>15.80</td>
    <td>12387</td>
    <td>621</td>
  </tr>
</table>

<table>
  <tr>
    <th colspan="9" align="center">Time period: 2002–2003</th>
  </tr>
  <tr>
    <th>IATA</th>
    <th>Region</th>
    <th>Strength</th>
    <th>Avg Airtime</th>
    <th>Avg Distance</th>
    <th>Avg Dep Delay</th>
    <th>Avg Arr Delay</th>
    <th>Cancelled Origin Count</th>
    <th>Diverted Origin Count</th>
  </tr>
  <tr>
    <td>ORD</td>
    <td>Midwest</td>
    <td>1388214</td>
    <td>105.26</td>
    <td>1216.27</td>
    <td>7.84</td>
    <td>5.53</td>
    <td>15285</td>
    <td>1104</td>
  </tr>
  <tr>
    <td>DFW</td>
    <td>Southwest</td>
    <td>1228058</td>
    <td>108.28</td>
    <td>1235.17</td>
    <td>5.61</td>
    <td>1.01</td>
    <td>8413</td>
    <td>884</td>
  </tr>
  <tr>
    <td>ATL</td>
    <td>Southeast</td>
    <td>1201228</td>
    <td>84.20</td>
    <td>1029.34</td>
    <td>7.90</td>
    <td>5.82</td>
    <td>6794</td>
    <td>950</td>
  </tr>
  <tr>
    <td>LAX</td>
    <td>West</td>
    <td>812923</td>
    <td>131.84</td>
    <td>1617.66</td>
    <td>4.29</td>
    <td>0.75</td>
    <td>4480</td>
    <td>510</td>
  </tr>
  <tr>
    <td>PHX</td>
    <td>Southwest</td>
    <td>687674</td>
    <td>118.53</td>
    <td>1453.29</td>
    <td>6.93</td>
    <td>1.57</td>
    <td>3444</td>
    <td>569</td>
  </tr>
  <tr>
    <td>IAH</td>
    <td>Southwest</td>
    <td>609715</td>
    <td>113.04</td>
    <td>1347.36</td>
    <td>3.25</td>
    <td>2.37</td>
    <td>1801</td>
    <td>353</td>
  </tr>
  <tr>
    <td>MSP</td>
    <td>Midwest</td>
    <td>572741</td>
    <td>112.53</td>
    <td>1310.30</td>
    <td>4.31</td>
    <td>0.91</td>
    <td>3469</td>
    <td>488</td>
  </tr>
  <tr>
    <td>DTW</td>
    <td>Midwest</td>
    <td>561032</td>
    <td>92.66</td>
    <td>1006.10</td>
    <td>6.76</td>
    <td>1.17</td>
    <td>4261</td>
    <td>502</td>
  </tr>
  <tr>
    <td>LAS</td>
    <td>West</td>
    <td>547541</td>
    <td>113.76</td>
    <td>1409.50</td>
    <td>6.89</td>
    <td>3.65</td>
    <td>1880</td>
    <td>480</td>
  </tr>
  <tr>
    <td>DEN</td>
    <td>Mountain</td>
    <td>524394</td>
    <td>125.50</td>
    <td>1415.76</td>
    <td>4.34</td>
    <td>1.35</td>
    <td>2417</td>
    <td>386</td>
  </tr>
</table>

The two tabels shows the top 10 most visited airports in the USA, where "IATA" is the International Air Transport Association codes that is used to identify the different airports, "Strength" is the number of flights that visited that giving airport in the period, "Avg Airtime, "Avg Dep Delay" and "Avg Arr Delay" are all messured in minutes, "Avg Distance" is messured in kilometers (km). Because the top 10 most visitet airports are not axactly the same in the two time periods, the direct comparison only includes the 8 airports that appear in both top-10 lists. This means the comparison of major recurring hubs, but not as a comparison of the entire US domestic airport system. 

<table>
  <tr>
    <th colspan="6" align="center">Change from 1999–2000 to 2002–2003</th>
  </tr>
  <tr>
    <th>Compared Airports</th>
    <th>Category</th>
    <th>1999–2000</th>
    <th>2002–2003</th>
    <th>Change</th>
    <th>Interpretation</th>
  </tr>
  <tr>
    <td rowspan="7">ORD, DFW, ATL, LAX, PHX, MSP, DTW, DEN</td>
    <td><b>Strength</b></td>
    <td>6,516,512</td>
    <td>6,976,264</td>
    <td>+459,752 (+7.06%)</td>
    <td>More flights in 2002–2003 ↑</td>
  </tr>
  <tr>
    <td><b>Avg Airtime</b></td>
    <td>112.26</td>
    <td>109.85</td>
    <td>-2.41 (-2.15%)</td>
    <td>Slight decrease ↓</td>
  </tr>
  <tr>
    <td><b>Avg Distance</b></td>
    <td>1347.20</td>
    <td>1285.49</td>
    <td>-61.72 (-4.58%)</td>
    <td>Slight decrease ↓</td>
  </tr>
  <tr>
    <td><b>Avg Dep Delay</b></td>
    <td>11.61</td>
    <td>6.00</td>
    <td>-5.61 (-48.35%)</td>
    <td>Departure delays decreased a lot ↓</td>
  </tr>
  <tr>
    <td><b>Avg Arr Delay</b></td>
    <td>8.50</td>
    <td>2.26</td>
    <td>-6.23 (-73.36%)</td>
    <td>Arrival delays decreased strongly ↓</td>
  </tr>
  <tr>
    <td><b>Cancelled Origin Count</b></td>
    <td>112,830</td>
    <td>48,563</td>
    <td>-64,267 (-56.96%)</td>
    <td>Far fewer cancellations ↓</td>
  </tr>
  <tr>
    <td><b>Diverted Origin Count</b></td>
    <td>7,613</td>
    <td>5,393</td>
    <td>-2,220 (-29.16%)</td>
    <td>Fewer diversions ↓</td>
  </tr>
</table>

The comparison shows that the 8 comman major airports had more flights in 2002-2003 than in 1999-2000, but their combined strength increased with 7% which corresponds to an increase with 459,752 flights. At the same time it can be seen seen that the average depature delay, average arrival delay, cancelled origin count and dicerted origin count all decreased. 

This suggests that, for these selceted major airports, operational performance was better in 2002-2003 than in 1999-2000. Howecer, these results can not be intepreted as evidence that the entire aviation system has become more efficient. THe reason for this is because if the avaitation traffic is look upon a longer period from 1988-2007 it can be observed that there is an increase of canceled flights and general flights. This is demonstrated in the graph below:

<img width="2085" height="889" alt="billede" src="https://github.com/user-attachments/assets/08299700-7a7a-41e4-8453-fe46a3dd7621" />


In the graph at can be observed that the number of flights drops with nerly halv a million flights which is an extrordinory drop and it is consistent with the aviation disruption after 9/11. The year after in 2003 it can be observed that the avaition traffic returns to normal and starts to climb again. In the graph it can also be observed that a tromendunce amount of flights around 250k got cancelled when 9/11 happened, this was also done for security messures, but when the aviation oppened up again in 2002 the number of cancled flights dropped a lot and ever since it has been climbing. So even though the change table showed a decreassed in canceled flights the over all tendency of the cancelations is increasing and climbing to oversee the peak of canceled flights before 9/11. This hows the improvement observed in the selsected-airport comparison was not permanent across the full time period.  


## Visualization of the graph

The two graph visualitations from 1999-2000 and 2002-2003 is shown as a headmap wher the warmer the cennections too the nodes which is the airports, the more flights travelled to that designatad airport. The IATA codes of the most 10 visited airports are also shown on the nodes, this makes it also possible to see which communities the 10 most visted airports belongs to. 
The colour of the nodes shows the graphical communites of the airports, so the airports that is located in the same regian will have the same colour to show they are one community.

<img width="4245" height="3594" alt="billede" src="https://github.com/user-attachments/assets/98bf377d-4a32-4f08-ab35-c1338c2fe1dc" /> 

<img width="4245" height="3594" alt="billede" src="https://github.com/user-attachments/assets/987338ec-e62c-49da-aabf-463a3fa7948a" />

Between the two grapth there can be observed that a lot have changed in the way people travels, first of all from 1999-2000 it can be seen the most travelled airports are more spread out than from 2002-2003 where the most traveled airports are more centrulized, but ther can also be seen that there have been an increase of nodes which mean that there have been established more airports around the communities and this is because of the general higher demand of travelling via planes. 

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

</div>
