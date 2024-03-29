---
title: "02 Selection"
author: '35762384'
date: "17/02/2021"
output: 
  html_document: 
    keep_md: yes
    code_folding: show  
---  

  
#### Introduction
The availability of health facility data, such as location, capacity and resources present, is an important factor needed for decision-making processes, especially in the ongoing COVID-19 pandemic. Examples of uses include planning of interventions, disease surveillance, information for insurance companies and health management information systems (HMIS) (WHO, 2018). It is also often used for research purposes, with many studies utilising facility data to determine accessibility to healthcare or travel times (Hulland et al., 2019). However, availability is often not the issue but the fact that there are multiple sources and the discrepancies between them (Makinde et al., 2018). It is common for different organisations, e.g. non-governmental organisations (NGOs), government departments and other non-profit organisations, to produce their own lists and a need to further investigate differences is noted in studies using this data (Hulland, 2020). The aim of this paper is to do address this point; to analyse and highlight the differences between sources of facility data using Malawi as a case study and mark areas for improvement in the quality of the data.

One source for Malawi is a list compiled by the Kenyan Wellcome Trust Research Programme (KWTRP) for 50 sub-Saharan African countries and was released in 2019 (Maina et al., 2019). It focused on public health facilities, those run by the government, faith-based organisations (FBOs) and NGOs and also removed facilities that only provide specialised care such as psychiatry. It’s availability as open-access data as well as the thorough cleaning and validation processes implemented, meant it is often cited in other studies (Falchetta et al., 2020) (Judson et al., 2020) (Dowhaniuk, 2021) (Wariri et al., 2021). Several sources of information for facilities were combined to produce one list and in the case of Malawi, personal communication with health related organisations, data from The Humanitarian Data Exchange (HDX) and The Christian Health Association of Malawi (CHAM) were used (Maina et al., 2019). An important note is that the years of when the information was acquired from these sources vary, with the most recent being 2017 and the personal communication being conducted in 2013. The list is now being hosted by the World Health Organisation (WHO) Global Malaria Programme with the aim to update (WHO, 2019). However, since the publication of this study, there have been no updates or changes. Therefore, there is a need to compare with other sources, especially as the age of this data might mean new developments are not captured which could affect the study’s popularity. 

A newer source is the Master Facility List (MFL) from and managed by the Malawi Ministry of Health (MOH, 2021). The WHO recommends that every country produces a MFL with the aim of it being the primary source and describes how to develop it in (WHO, 2019). It must be accessible, regularly updated and validated. Although many African countries have made steps towards formulating a MFL under these guidelines, issues of access and missing elements are often 
encountered, making its usage more difficult (South et al., 2021). With Malawi, the MFL is openly available.However, its validation methods are not made clear and information on the most recent update is only available when selecting a specific facility and is not part of the dataset that can be downloaded. Despite this, the fact that is maintained by the Ministry of Health and so has the potential to be incorporated into the health system and that it is a more recent source, it is worth investigating how this list compares to others. 

Other sources are mostly dependent on information contributed by volunteers, of which healthsites.io is a global project aiming to map every health facility running (Healthsites, 2021). It works with OpenStreetMap, which provides the baseline map as well as the methods to input data, and since its establishment in 2016 has recorded over 900,000 facilities. Anyone can contribute and effort has been put into validation processes, which includes a Location Validation Index, a score that reflects other users verifying that facility exists. The data is freely available and access to the most recent version can be gained through several formats such as an API. Other lists can also be incorporated into healthsites.io and there is a process outlined for the import of facility lists from national ministries of health. However, similarly with other lists, it struggles with completeness and it has been shown that less than 2% of healthsites.io data for sub-Saharan Africa contains attributes describing capacity (South et al., 2021). It seems that the quality or functionality of these lists is limited across all of these sources. 

Quality data is important but this is often neglected or not investigated. There are several issues that are prominent with facility data from sub-Saharan Africa. Lists are often missing key elements such as capacity, equipment and services they provide. Not only this, problems with missing coordinates can also occur, with the WHO-KWTRP data reporting 9 missing coordinates for Malawi (Maina et al., 2019). These issues are present but there is not much research highlighting this, especially when comparing between sources, but this is important for studies that go on to utilise these lists. The outbreak of COVID-19 brought a greater emphasis on the need for this. Several countries have allowed open access to their facility data, encouraging external research to aid the response to the pandemic and improvement of the data itself . For example, research investigating the ability of health facilities to increase capacity and the identification of people vulnerable due to various factors in Kenya were performed with open facility data (Barasa et al., 2020) (Macharia et al., 2020). Therefore, maintenance and quality control of facility lists are essential in providing accurate data and contributing to valid research. 

The aim for this paper is to provide a reproducible summary of facility data for Malawi, discuss differences that are relevant to potential stakeholders and make apparent areas for improvement. The following hypotheses have been developed to address this: 

1.	The same number of health facility locations are recorded for Malawi across healthsites.io, WHO-KWTRP and their MFL
2.	The health facility locations and proportion of facility types recorded in the Malawi MFL are similar to those being used in current global analyses
3.	Hospital locations stored in healthsites.io are currently not a good representation of those available from the Malawi MFL


##### Methods  
- Websites from where I downloaded  
- What was done to the data pre-analysis, e.g. removing NAs  
- Software used (packages?)  

##### Results  

##### Data quality  

  ... the MFL contains some missing coordinates. Upon inspection, there are 181 missing values, which also contains 62 coordinates that are not in Malawi and were either inputted incorrectly or not known. The missing values were omitted before analysis. However, if these 62 coordinates are also removed, there are 1365 facilities in the MFL. In the WHO-KWTRP, there are 9 missing coordinates and this was stated in (Maina et al., 2019). Healthsites.io carries some missing attributes but all coordinates are present and reside within Malawi. The WHO-KWTRP contains the least attribute data, only describing ownership and admin 1 regions the facilities are in besides the core information of name, type and location. The MFL adds to this by including admin 2 regions, which are the districts, functionality, date opened and another version for facility names under the column 'Common name'. However, their website for the MFL gives the option of obtaining more information on capacity and resources by selecting an individual facility. Unfortunately this aspect is not available as part of the MFL data to download. Healthsites.io by far provides a greater variety of attributes out of the 3 sources. However for Malawi, 13.7% of facilities have no names assigned, which is one of the basic elements needed. Other attributes are also sparse.  


  
  Analysis into duplicates within lists shows that names for 5 facilities in the MFL appear more than once that also have same coordinates up to at least 2 decimal places. Of these 5 facilities, 3 share same entries in the other attribute columns while the remaining 2 differ in type. In the WHO-KWTRP, one health centre appears twice with the same attributes and coordinates. With healthsites.io, there are 17 names that appeared more than once and all apart from 2 have similar coordinates up to at least 2 decimal places. Searching for duplicate coordinates rather than names also gave matches. In healthsites.io, 3 facilities that were also part of the previous 17 have identical coordinates. The timestamp on these facilities indicate that their duplicates were inputted at the exact same time. The WHO-KWTRP list does not have duplicates while the MFL returned 44 distinct coordinates that were repeated at least more than once. One of these cases is repetition of one location for 24 facilities, of different types and names, in Blantyre. However, some results are due to no coordinates being available and for example, (-1,1) was inputted instead.  
  
  Figure 1 shows method and number of duplicate data points that have been removed. As discussed, duplicates are found by identical names or coordinates. If the coordinates and other attributes match, the duplicate is removed. Assessing the distribution of the missing coordinates in the MFL using the district column, Lilongwe, Blantyre and Mangochi have 16%, 14% and 15% of their facilities with missing locations. Both Lilongwe and Blantyre also host the largest number of facilities in Malawi. The duplicates that were removed in the MFL are in Mwanza and Mangochi. From the WHO-KWTRP, only the regions of the 9 facilites can be determined from the data with 7 present in the Southern and 2 in the Northern regions and the duplicate that was removed, also present in the south. Healthsites map out ones removed... . The duplicate coordinates in the MFL have facilities with different names and so have not been removed. Three do have the same names, however, 2 facilities are part of the ones removed and the remaining were of different types.  






##### Hypothesis 1  

The MFL contains more than 2 and 5 times as many facilities compared to the WHO-KWTRP and healthsites.io respectively. In total, there are 638 facilities recorded in the WHO-KWTRP data, 1424 in the MFL and 234 in healthsites.io (figure 1). These numbers have been derived after the removal of missing coordinates and duplicates.  

![](02-Selection_files/figure-html/Number of facilities-1.png)<!-- -->
  
##### Hypothesis 2  

With the WHO-KWTRP list often used in research, a comparison to the MFL is made here. Setting aside the classifications of unclassified and private in the MFL, both the MFL and WHO-KWTRP have similar numbers of classification types (figure 2). However, there is a difference in the amount of specificity. The WHO-KWTRP provides 5 categories for hospitals while the MFL only provides 3. In contrast, the MFL separates health posts and dispensaries while WHO-KWTRP combines these facilities. The private and unclassified groups not present in WHO-KWTRP only make up 0.4% of the number of facilities in the MFL. Much of the variation between these two sources is accounted for by the number of each type of facilities. Hospitals constitute 8% of the total in the MFL and 13% in WHO-KWTRP. Health centres form most of the facilities in the WHO-KWTRP list, 71%, while the closely related clinics only form 3%. In the MFL, there is more of an even spread of clinics and health centres, which constitute 39% and 35% respectively.  

![](02-Selection_files/figure-html/Types of facilities-1.png)<!-- -->![](02-Selection_files/figure-html/Types of facilities-2.png)<!-- -->
  
Figure 3 shows the point locations of each facility from both sources and an interactive version can be viewed online. By viewing this map, it appears that the same central hospitals are recorded in both lists and majority of district hospitals, apart from 2, are also matching. Distribution of the 3 other hospital categories in WHO-KWTRP is similar to that of 'hospital' in the MFL (figure 3). However, it also confirms the MFL has a significant number of clinics that are not accounted for in the WHO-KWRTP list, which only reports a small number in the central and southern regions.  
![](02-Selection_files/figure-html/Maps-1.png)<!-- -->
  
  Comparison between private faciltiies is made here, as the WHO-KWTRP data does not include this. In the MFL, 30% of all facilities are privately owned and majority of these consist of 356 clinics, 45 dispensaries and 16 hospitals. Distribution across the country indicates many are present in Blantyre and Lilongwe, with 95 and 67 respectively (figure ..).  
  
![](02-Selection_files/figure-html/Private MFL-1.png)<!-- -->
  
##### Hypothesis 3  

Within healthsites.io, 157 hospitals are recorded which is greater than both the MFL and WHO-KWTRP, with 117 and 82 hospitals respectively (figure 4). Healthsites.io does not provide a breakdown of hospitals into groups. A look into the distribution by district shows majority of the difference in hospital number is concentrated around 3 districts in the south (figure 5). Blantyre district has 39 hospitals in healthsites.io compared to 14 in the MFL and both its neighbouring Mwanza and Thyolo districts have 9 and 7 additional hospitals in healthsites.io respectively. Instances where the MFL has more hospitals in a district, the number does not exceed more than 4 facilities. A note here is that 4 hospitals in the MFL did not have accurate coordinates and so were dropped from the total of 117 in this analysis. 
  
![](02-Selection_files/figure-html/Hospital comparison-1.png)<!-- -->![](02-Selection_files/figure-html/Hospital comparison-2.png)<!-- -->
 
##### Blantyre  
(23 private facilities did not intersect)  
talk about private in blantyre  
talk about hospitals in blantyre  

![](02-Selection_files/figure-html/Blantyre-1.png)<!-- -->![](02-Selection_files/figure-html/Blantyre-2.png)<!-- -->
  


  
























