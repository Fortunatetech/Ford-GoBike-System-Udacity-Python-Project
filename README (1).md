# (Ford GoBike System Data Exploration)
## by (Ayodele Ayodeji Fortunate)

## Background Information on the Ford GoBike System Dataset

This dataset includes information about individual rides made in a bike-sharing system covering the greater San Francisco Bay area.
The data consists of information regarding 183,412 member's individual trip, including duration in seconds, start time, end time, start station_id and bike share for all trip among others as we see in the variable description bellow. 
The dataset can be found in the [here](https://github.com/BetaNYC/Bike-Share-Data-Best-Practices/wiki/Bike-Share-Data-Systems).

**Features Decription**

The dataset consists of almost 183,412 rows and 16 columns:

- Duration_sec: This is the duration of trip per member in seconds.
- start_time: This include the information about the start time and date for each trip.
- end_time: This include the information about the end time and date for each trip.
- start_station_id: Take-off station identification number.
- start_station_name: Take-off station name.
- start_station_latitude: Location of start station in terms of latitude.
- start_station_longitude: Location of start station in terms of longitude.
- end_station_id: Identification number of station where members ends their trips.
- end_station_name: Name of stations where members ends their trips.
- end_station_latitude: Location of end station in terms of latitude.
- end_station_longitude: Location of end station in terms of longitude.
- bike_id: This is the identification number of Bike used for each trip.
- user_type: Types of members engaging with the bike trips. whether customer or suscribers.
- member_birth_year: Birth year of members.
- member_gender: Sex of members engaging with the bike trips. We have Male, Female and Others.
- bike_share_for_all_trip: This tells wether members share their ride or not throughout their entire trip. 

**Little modification done on the dataset to suit my analysis and exploration.**

1. Null values were removed from the dataset
2. start_time and end_time was changed to datetime
3. start_time and the end_time splitted into time of the day, day of the week and month of the year. This is necessary for my analysis
4. Datatype of member_birth_year was changed to integer 
5. Actual age of members were extracted from member_birth_year provided and assign it to age groups
6. duration_min was added to the dataframe
7. Drop the columns that are not needed for the analysis 

##### After the modification  

After the whole cleaning process, Ford GoBike System Data having **183412** rows of trip and  **16** columns of features reduced to **174952** rows of trip and the columns of features increased to **18** features.

For this project, I carried out exploratory analysis through visualization on **When are most trips taken in terms of time of day, day of the week**. Although frequency of trips by Month was not considered because the data provided only covers a single month (**February**) for start month  just that most of the trips ended in early March (**the first week**). 


For the visualizations, I started with univariate visualizations, moving through bivariate visualizations, and finally multivariate visualizations.

For the case study, we will concentrate only on the variables in the top ten bullet points: start day time, end day time, start weekday, end_weekday and the independent variables. 

- start day time - Morning, Afternoon, Evening and Night.
- end day time - Morning, Afternoon, Evening and Night.
- start weekday: - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday and Sunday.
- end_weekday: - Monday, Tuesday, Wednesday, Thursday, Friday, Saturday and Sunday.
- Member_age: Exact age of members engaging with the bike trip system
- Duration_min: Duration of trip converted to minutes
- member_gender: Sex of members engaging with the bike trips - Male, Female and Others.
- user_type: Types of members engaging with the bike trips - customer or suscribers.
- start_station_name: Take-off station name.
- end_station_name: Name of stations where members ends their trips. 

* start day time, end day time, start weekday and end_weekday are the dependent variables
* Others - are the independent variables

Our focus will be on answering the question about the effect of these independent variables on the frequency of trips taken in terms of time of day, day of the week.


## Summary of Findings

> I started up with univariate exploration where I found out that Morning for time of the day and Thursday for weekdays happens to be the most frequent period when members are engaging with the Bike sharing system. 

> I also found that more of the bike trips bike-sharing system covering the greater San Francisco Bay area starts in the morning follow by the evening time then afternoon while members do not really start their trips in the night. Same goes for end time of the day. Also, members whose ride starts and ends at same time of the day are total of  **169086** while those members whose ride starts and end in the different times of the day are **5866**. This implies that most of the members engaging with bike-sharing system covering the greater San Francisco Bay starts and ends their trips at same time of the day of which Morning is the most frequent.

> Moving down to bivariate, where I comparing other independent variables with my dependent variable for futher investigation.  Observing the relationship between log transformation of member age in both time of the day and weeek, I observe that for the start time of the day, Morning time is still the most frequent time of the day. I also discovered that young adult, matured, middle age and the elderly are mostly having their trips in the morning. while Afternoon is the most frequent in teenager and old members. This is Same for the end day time. But for both start and end days of the week, Thursday is the most frequent day of the week in all the specified age groups. 

> Comparing the effect of user type on the frequency of trips by time of the day, Morning time still seems to stand out in suscribers but Afternoon seens to be the most frequent in customers and this applies for both start and end imes of the day. But for start and end day of the week, Interestingly Thursday seems to stand out in both customers and suscribers.

> It is suprising to know that while comparing the efect of member gender on the freuency of trips for both time of the day and weekdays, morning and Thursday are the most frequent periods when most trips were taken respectively as suggested by the distribution time of day and days of the week.

> Finanly, compairing more independent variables for more investigation. Now looking at the effect of stations and gender on when most trips were taken. I found out that, in male, it was still same Thursday except for **San Francisco Caltrain (Townsend St at 4th St)** where Tuesday is the most frequent.

> In female, it was still same Thursday except for **San Francisco Caltrain Station 2 (Townsend St at 4th St)**, **Steuart St at Market St** and **San Francisco Caltrain (Townsend St at 4th St)** where Tuesday is the most frequent

> While a huge exception is noticed in Others gender, **Market St at 10th St** where Tuesday is the most frequent.
**Powell St BART Station (Market St at 4th St)** where Sunday is the most frequent. Friday and Saturday are equal in terms of frequency in **Steuart St at Market St**. **Howard St at Beale St**, **San Francisco Ferry Building (Harry Bridges Plaza)** Wednessday is the most frequent. Tuesday equals with Thurday in **Powell St BART Station (Market St at 5th St)**. Finally, in **San Francisco Caltrain (Townsend St at 4th St)** Friday is the most frequent.

> Looking at the effect of stations and customers on when most trips were taken, it is only in 3 stations out of the 10 most used stations that Thursday is the most frequent while other 7 station are distributed over other days of the week. For Suscribers, Thursday is most frequent in 7 stations and equal in two stations while Tuesday is the most frequent in one station. For time of the day, it is only in 4 stations out of the 10 most used stations that Morning time is the most frequent while other 6 stations are distributed Afternoon and Evening. For Suscribers, Thursday is most frequent in 7 stations while Evening is the most frequent in the other 3 stations.

> Finally, in multivariate, I compared duration in minutes and time of the day and weekdays by user type, I found out that, Morning time of the day still happens to be the most frequent time of the day that members are engaging with bike sharing system in San Francisco Bay area. For weekdays, Members who are Subscribers are more engaging with the bike trip and most interestingly, Fridays happens to be the most frequent time of the day that members are engaging with bike sharing system in San Francisco Bay area. Compared duration in minutes and time of the day and weekdays by member age groups, **Afternoon** time of the day happens to be the most frequent time of the day that members who are Adults, Young Adults are engaging with bike sharing system in San Francisco Bay area. While it seems to be Morning time for senior citizens though almost equal with the Afternoon time. which implies that senior citizens prefer to make their trips in the morning time and Afternoon time of the day. For Weekdays, Most interestingly, having compared duration and time of the day by member age groups, **Sunday** time of the day seems to be the most frequent time of the day that members who are Young Adults and Senior Citizens except for members who are Adults where **Saturday** seems to be the most frequent, are engaging with bike sharing system in San Francisco Bay area. Compared duration in minutes and time of the day and weekdays by member gender, **Afternoon** time of the day seems to be the most frequent time of the day that members who are Male, Female and Others are engaging with bike sharing system in longer duration in San Francisco Bay area. For Weekdays, **Saturday** seems to be the most frequent time of the day that members who are Male. **Friday** for Female members while it is **Thursday** for Others are engaging with bike sharing system in longer duration in San Francisco Bay area.

#### For bike-sharing system covering the greater San Francisco Bay area. On average,  Morning time is period of the day when most trips were taken and for the days of the week it is on Thursday.

## Key Insights for Presentation

For the presentation, I focus on just the influence of member age groups, member gender, user type, start and end stations and leave out most of the intermediate derivations. I start by introducing the distribution of start and end time of the day also the start and end day of the week.

Afterwards, I introduce each of the independent variables one by one. To start, I use the bar plots of start and end time of the day across member age groups. The other 3 independent variables, member gender, user type, start and end stations are covered afterwards using cluster bar chart, stripplot and scatter using facetgrid.