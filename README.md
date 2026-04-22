# How did the airport traffic and security evolve after the terror incedint on the 11/09-2001 also known as (9/11) in the United Stated of America?

This project explores how the airport traffic look a few years before 9/11 and then compares to how it look a couple years later, this an interresting comparison because over the few decades, the security in airports has been substantially increased but the amount of people who are travelling on plane also have been substially increse. It is expected that there can be observed a substatially more media covered text on the secruity in the airports after 9/11 and fewer flights the year later but in the later years it is expected that the traffic has increased substantially than it was before 9/11 but still with increasing secruity in the airports.

## How will this changed be analized?

To analise the change of airport traffic before and after 9/11 we will make a graph where all the airpots will be the nodes in the graph and the flights connecting to the airpots will be the edges. When we are making the graph we will make it as a wighted edge. The weight to the nodes will be the number of flights going to the specifik airport, this will be useful to see which airports is most frequently visited and it will give an indication on the changes of the traffic in the airports.

The way we will analise the security improvement in the airports is with textuel analyse and here we are going to webscrabe relevent texts on weekipidia where we will gather all the scrabed texts into documents. With all the text in the documents we can start on tokenizing the words so it will be possible for us to find the most frequent used words. When all this is done we will visualised all the most frequent used words that was found with TF-IDF and visualize them with using word clouds.

# Graph analyzes

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

These 

These TF-IDF scores needs to be intepretated cautiosly because of the amount of available text have changed alot over the years which can be absorved in the table above. As mentioned the table below shows the TF-IDF scores of specifc terms that correlated to the securyity in the aiports, the reason for this table is interresting is because the TF-IDF scores messure how important a word is in a giving document, this means it will show an indication of how often a geving word is mentioned in the text from 2003 and 2010.

| TERM      | TF-IDF SCORE (2003) | TF-IDF SCORE (2010) | PERCENT CHANGE (2003→2010) |
|-----------|---------------------|---------------------|----------------------------|
| SECURITY  | 0.0087              | 0.0180              | +106.9%                    |
| SAFETY    | 0.0000              | 0.0221              | NEW                        |
| TSA       | 0.0000              | 0.0036              | NEW                        |
| SCREENING | 0.0000              | 0.0054              | NEW                        |
| SEPTEMBER | 0.0087              | 0.0281              | +223.0%                    |
| ATTACK    | 0.0000              | 0.0049              | NEW                        |

In the table it can be observed that from 2003 and 2010, there has been an increase of the use of these specic words in the documents contributes more, which also indicates that the safte and security in airports has become a lager topic. But it can also be abserved that the "secuirty" term from 2003 only contributed 0.087% but it 2010 it increased to 1.8% which is a substantially increase. But there can be mutiple reasons for this, first of all the number of words that was scrabed from 2003 was only 182 and in 2010 there was 3387 words. This has a huge inpact in what the TF-IDF scores will be, because the proportion of the texts from these two years is far from each other. But none the less there has been an increase airport security detail over the years, but it is not ass noticable as we ennetially thorght, this can also be observed in the word cloud visualization:

## Word clouds visualization

The figure below shows the word cloud visualization where there has been used a lot of stop words to filter out unwanted words, this was also mentioned earlier.

<img width="647" height="716" alt="billede" src="https://github.com/user-attachments/assets/711eef04-3b91-4375-a1cd-25b184b30b87" />


In the figure it can be observed that there is none to little frequently words that mentions security in airports and airplanes, the closet it comes is in 2010 it can be seen that on of the more frequent words is army which is a type of security it only depends on the context.

# Discussion

# Konlusion
