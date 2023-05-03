# J296 Final Project: Data analysis + visualization + documentation

## By Nadia Lathan
### Story summarization

Motor vehicle collisions are on the rise in California and across the country – a trend that has accelerated since the pandemic begun in 2020. However, the opposite is true in Richmond, Calif. where collisions have steadily declined over the last four years. Through careful data analysis and with the power of Google Sheets, I examine how Richmond compares to the rest of the state on traffic safety.

### Where high speeds meet open roadways
Speeding is the number one cause of roadway collisions in California, according to the Transportation Injury Mappying System from the Safe Transportation Research and Education Center at Unversity of California, Berkeley. The same is true nationally, where [speeding accounts for about one-third of all motor vehicle collisions](https://www.nhtsa.gov/risky-driving/speeding)and has been the case for two decades.

This trend is [well supported by academic research](https://safety.fhwa.dot.gov/speedmgt/ref_mats/fhwasa1304/Resources3/08%20-%20The%20Relation%20Between%20Speed%20and%20Crashes.pdf) that shows the likelihood for collision increases as speed increases, in addition to the severity of injury.

The same is true in Richmond where 1,134 collisons occured due to unsafe speeding from 2018 to Janurary 2023.

<img width="713" alt="Screen Shot 2023-05-03 at 5 26 21 AM" src="https://user-images.githubusercontent.com/123508219/235915163-dacf6846-d802-40bf-b6e6-be0d234b1625.png">


Of the four most common reaons for collision – unsafe speed, improper turning, traffic signals and signs, and failure to yield – 20% were due to drivers exceeding the speed limit. Although not quite as high as the national average (29%), speeding plays a significant role in disrupting traffic safety.

Why the sense of urgency?

According to the National Highway Traffic Safety Administration, traffic congestion and tardiness are common reasons for why drivers begin to maneuver at dangerous speeds. As people sit in traffic, they become agitated when the speed they were traveling at gets interrupted. Running late for, say, an appointment or interview, also causes drivers to push against the flow of traffic. Although Richmond has, in general, seen a steady decline in unsafe speeding collisions, more and more motorists are hitting the roadways as [Alameda County slowly returns to pre-pandemic levels of vehicle mileage](https://tims.berkeley.edu/covid19.php), which, in part, fosters conditions for unsafe driving.

### Car collisions have fallen every year in Richmond since 2018

Motor vehicle collisions hit a high point of 72 incidents in March 2018 with a total of nearly 700 crashes that year, and haven't reached the same level since.

<img width="716" alt="Screen Shot 2023-05-03 at 1 48 34 AM" src="https://user-images.githubusercontent.com/123508219/235870941-ff7c75af-84fb-4b74-807e-cae3c5a42ba2.png">

There's a sharp drop from February through April in 2020 because of the pandemic, and incidents reached a historic low of 23 collisions in April. The same time last year had about two and half times more motor vehicle collisions. However, likely due to significantly less roadway traffic, crashes decreased overall by 6% from 2019 to 2020.

This decline is even steeper between 2021 and 2022, **where annual crashes fell by 20%.**, denoting a pattern that's in stark contrast with the rest of state, as total crashes fell by roughly 6% within the same time frame across California per the [UC Berkeley Transportation Injury Mapping System](https://tims.berkeley.edu/covid19.php).

Although there aren't clear explanations for why this is the case – and is something I would like to further explore with the sources I have identified – the city has allocated numerous resources towards alternative modes of transportation in the last four years which may partially explain the consistent fall in crashes.

The Department of Transportation has introduced bike share and EV carshare services (both to varying degress of success – the former which was phased out in 2021 but has since returned) all within the last four years, and expansive projects to improve high-injury corridors such as San Pablo Avenue have been in development for even longer. The precise driving force behind these trends remains to be further investigated.

## Data analysis

I acquired my data from the city of Richmond's open data base, [Transparent Richmond](https://www.transparentrichmond.org/). It contained information for traffic collisions from 2017 that was updated on a daily basis. I downloaded the data set sometime in late January and restricted my data analysis to 2022. I filtered out data from 2017 due to concerning discrepancies in the data, such as some categories (like pedestrian collisions, for example) not being tabulated until April of 2017.

All traffic data was gathered by Richmond Police, which comes with its own limitations. Incidents that were not reported or discovered by Richmond PD are ommitted in this data set, which likely disservice's Richmond's Black community the most who – for historical and systematic reasons – are less prone to report incidents to the police.

Very little cleaning was needed for this data set. Transparent Richmond accomplishes much of this with their own toggling features for data analysis and contract external firms to help publish these data sets. 

## Into the weeds

The majority of my analysis involved making pivot tables that detailed the parties involved in a collision (other cars, pedestrians, bicyclists), the date, and count of involvement for every single from 2018 to 2020. The steps looked something like below:

pivot table: 2018 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2018"
  * filter – involved_with
    * status: showing 1 item (other motor vehicles)

I then categorized the date of each incident by month by right-clicking the collision_date column > create pivot date group > month. My final pivot table for years 2018, 2019, 2020, 2021, and 2022 looked something like this:

<img width="365" alt="Screen Shot 2023-05-03 at 7 18 15 AM" src="https://user-images.githubusercontent.com/123508219/235943544-bf77f458-497d-408c-a8ee-b7f391e0a867.png">

This helped me determine the number of collisions per month for every single year with each given party (cars, pedestrians, and bicyclists).

I conducted roughly the same process to determine primary collision factor which helped me determine the popular causes for crashes:

primary collision factor
  * row – primary collision factor
    * sort by: countA
  * value – primary collision factor
    * summarize by: countA

<img width="369" alt="Screen Shot 2023-05-03 at 7 22 32 AM" src="https://user-images.githubusercontent.com/123508219/235944726-af736290-85ec-4793-8dbe-a19001f6e8b6.png">

I did the same process to create a pivot table for types of collision and what day of the week they occurred, parties involved in a collision, and count of collision types.

Collision day and type:

<img width="283" alt="Screen Shot 2023-05-03 at 7 27 46 AM" src="https://user-images.githubusercontent.com/123508219/235946269-6181a6a6-da71-4c89-84d7-ccb0777f8616.png">

(not full pivot table)


Parties involved:

<img width="328" alt="Screen Shot 2023-05-03 at 7 28 30 AM" src="https://user-images.githubusercontent.com/123508219/235946475-b9a47387-a3e2-4bcf-ab49-b27400311181.png">

Count of collision types:

<img width="277" alt="Screen Shot 2023-05-03 at 7 29 26 AM" src="https://user-images.githubusercontent.com/123508219/235946724-7930dcaa-4d71-4377-85fa-6270d3279bc0.png">

(not full pivot table)

### Questions

1. How have pedestrian collisions changed over time?
 * Pedestrian collisions have generally decreased over time, totaling 5.82% of all collisions in 2018 to 3.94% in 2022.

 * For my analysis, I had to piece together each pivot table I made for collision involvement and copied over the values in a new sheet to create a four-year timeline.

<img width="280" alt="Screen Shot 2023-05-03 at 7 36 08 AM" src="https://user-images.githubusercontent.com/123508219/235948807-bdb2e1cf-2e93-40a0-b110-840b63a5d0a8.png">
(not full pivot table)

2. Which days have the highest collision rates?
  * Wednesday had the highest amount of collisions, 895 total across four years, just barely beating out Saturday which had 891. Friday was third, with 862 total collisions.

<img width="244" alt="Screen Shot 2023-05-03 at 7 42 09 AM" src="https://user-images.githubusercontent.com/123508219/235950595-05ec55a5-25c8-420e-b1f2-4bf1f6d13eb2.png">

3. What's the most common cause for a collision?
  * As mentioned in my story summation, unsafe speeding is the number one cause of all roadway collisions (1,134 incidents), meanwhile improper turning is second on the list (1,015 incidents)

<img width="409" alt="Screen Shot 2023-05-03 at 7 44 50 AM" src="https://user-images.githubusercontent.com/123508219/235951369-6e0fe72f-bfeb-4081-8b98-d91d3bb1270f.png">

4. What day experienced the highest number of people involved in a single incident?
  * To answer this question, I returned to the main data table and filtered for "number of parties involved."

<img width="960" alt="Screen Shot 2023-05-03 at 7 50 00 AM" src="https://user-images.githubusercontent.com/123508219/235952843-990b478a-357d-4cc8-b181-9b8e80abc5da.png">

There were threee incidents total – all of which 7 people were affected. However, the crash on October 27, 2019 was the only one within the alloted time frame (2018 - 2022), and inolved two key characteristics of the majority of collisions: speeding and colliding with another vehicle.

5. Where do most accidents occur?
* Although I wasn't able to acquire precise location information from this data set (the columns alloted for the road location were left blank), I was able to gather something about the general geographic area of where most crashes happened.

Police denoted which "reporting districts" collisions took place, of which Richmond has three of them – Northern, Central, and Southern. 35% of all collisions took place in the Northern district, and roughly 33% in the Central district. 

<img width="309" alt="Screen Shot 2023-05-03 at 8 03 37 AM" src="https://user-images.githubusercontent.com/123508219/235956993-85be65a1-cce8-4ccc-82d7-9c1c4306a368.png">

For reference, here is a map of Richmond's reporting districts. [Source: City of Richmond](https://www.ci.richmond.ca.us/DocumentCenter/View/443/District--Beat-Map?bidId=).

<img width="835" alt="Screen Shot 2023-05-03 at 8 09 58 AM" src="https://user-images.githubusercontent.com/123508219/235958746-538e8334-1b33-45cd-a6a4-a8dc4f91bc5a.png">

### Complete Data Diary

1. created pivot table: primary collision factor
  * row – primary collision factor
    * sort by: countA
  * value – primary collision factor
    * summarize by: countA

2. created pivot table: collision day and type
  * row – collision day of week
    * sort by: countA of primary collision factor
  * row – primary collision factor
    * sort by: countA of primary collision factor
  * value – primary collision factor
    * summarize by: countA

3. pivot table: collision type
  * row – collision day of week
    * sort by: countA of collison type
  * row – collision type
    * sort by: countA of collision type
  * value – collision type
    * summarize by: countA

4. pivot table: parties involved
  * row – involved with
    * sort by: countA of involved with
  * value – involved with
    * summarize by: countA
    * summarize by: show as % of column

5. pivot table: 2017 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2017"

6. pivot table: 2018 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2018"

7. pivot table: 2019 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2019"

8. pivot table: 2020 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2020"

9. pivot table: 2021 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2021"

10. pivot table: 2022 collision involvement
  * row – involved with
    * order: descending
    * sort by: involved with
  * row – collision date
    * order: ascending
    * sort by: collision date
  * value – involved with
    * summarize by: countA
    * show as: default
  * filter – collision date
    * status: text contains "2022"

11. right click > create pivot date group >
  * applied to 2017, 2018, 2019, 2020, 2021, and 2022 collision involvement tables

### Sources

**Daniel Chavarria**

Daniel is the Public Works Director for the City of Richmond. He can provide insight as to why collisions overall are down in Richmond because public works manages traffic safety and road management. Although he is relatively new to the position (~one year in I believe), he can provide information about any traffic calming projects or other safety measures that have been installed within the last few years.

Contact info: daniel_chavarria@ci.richmond.ca.us

**Jill Cooper***

Jill is the co-director of the Safe Transportation Research and Education Center at UC Berkeley. She specializes in traffic safety and injury prevention planning. She can provide insight into Richmond's roadway collision trends and other potential improvements can make with respect to pedestrian and cylists' safety.

Contact info: cooperj@berkeley.edu

### Links

Data vizalizations: 

https://www.datawrapper.de/_/M6aE7/

https://www.datawrapper.de/_/1pbFh/

Google sheet data set:

https://docs.google.com/spreadsheets/d/1jx7cJITCztwr29iFvRJZ8Fp17JetpayG8Lycw7Yk-Ak/edit?usp=sharing

Cited information:
https://www.nhtsa.gov/risky-driving/speeding

https://safety.fhwa.dot.gov/speedmgt/ref_mats/fhwasa1304/Resources3/08%20-%20The%20Relation%20Between%20Speed%20and%20Crashes.pdf

https://tims.berkeley.edu/covid19.php

