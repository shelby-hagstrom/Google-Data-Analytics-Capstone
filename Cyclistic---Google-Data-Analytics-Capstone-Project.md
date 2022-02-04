Cyclistic - Google Data Analytics Capstone Project
================
Shelby Hagstrom
02/04/2022

## Setting up my environment

Setting up my R environment by installing and loading the ‘tidyverse’
packages

``` r
install.packages("tidyverse", repos = "http://cran.us.r-project.org")
```

    ## 
    ##   There is a binary version available but the source version is later:
    ##           binary source needs_compilation
    ## tidyverse  1.3.0  1.3.1             FALSE

    ## installing the source package 'tidyverse'

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.6     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.4     ✓ stringr 1.4.0
    ## ✓ readr   2.1.2     ✓ forcats 0.5.1

    ## Warning: package 'stringr' was built under R version 3.5.2

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(lubridate)
```

    ## 
    ## Attaching package: 'lubridate'

    ## The following objects are masked from 'package:base':
    ## 
    ##     date, intersect, setdiff, union

``` r
library(readr)
library(knitr)
```

## Collect the data

Uploading csv files from divvy-tripdata

``` r
january_2021 <- read_csv("202101-divvy-tripdata.csv")
```

    ## Rows: 96834 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
february_2021 <- read_csv("202102-divvy-tripdata.csv")
```

    ## Rows: 49622 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
march_2021 <- read_csv("202103-divvy-tripdata.csv")
```

    ## Rows: 228496 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
april_2021 <- read_csv("202104-divvy-tripdata.csv")
```

    ## Rows: 337230 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
may_2021 <- read_csv("202105-divvy-tripdata.csv")
```

    ## Rows: 531633 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
june_2021 <- read_csv("202106-divvy-tripdata.csv")
```

    ## Rows: 729595 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
july_2021 <- read_csv("202107-divvy-tripdata.csv")
```

    ## Rows: 822410 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
august_2021 <- read_csv("202108-divvy-tripdata.csv")
```

    ## Rows: 804352 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
september_2021 <- read_csv("202109-divvy-tripdata.csv")
```

    ## Rows: 756147 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
october_2021 <- read_csv("202110-divvy-tripdata.csv")
```

    ## Rows: 631226 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
november_2021 <- read_csv("202111-divvy-tripdata.csv")
```

    ## Rows: 359978 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
december_2021 <- read_csv("202112-divvy-tripdata.csv")
```

    ## Rows: 247540 Columns: 13

    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (7): ride_id, rideable_type, start_station_name, start_station_id, end_...
    ## dbl  (4): start_lat, start_lng, end_lat, end_lng
    ## dttm (2): started_at, ended_at

    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
all_trips <- rbind(january_2021, february_2021, march_2021, april_2021, may_2021, june_2021, july_2021,
                   august_2021, september_2021, october_2021, november_2021, december_2021)
```

## Clean up and add data for analysis

``` r
colnames(all_trips)  #List of column names
```

    ##  [1] "ride_id"            "rideable_type"      "started_at"        
    ##  [4] "ended_at"           "start_station_name" "start_station_id"  
    ##  [7] "end_station_name"   "end_station_id"     "start_lat"         
    ## [10] "start_lng"          "end_lat"            "end_lng"           
    ## [13] "member_casual"

``` r
nrow(all_trips)  #Number of rows in the data frame
```

    ## [1] 5595063

``` r
dim(all_trips)  #Dimensions of the data frame
```

    ## [1] 5595063      13

``` r
head(all_trips)  #First 6 rows of data frame
```

    ## # A tibble: 6 × 13
    ##   ride_id rideable_type started_at          ended_at            start_station_n…
    ##   <chr>   <chr>         <dttm>              <dttm>              <chr>           
    ## 1 E19E6F… electric_bike 2021-01-23 16:14:19 2021-01-23 16:24:44 California Ave …
    ## 2 DC88F2… electric_bike 2021-01-27 18:43:08 2021-01-27 18:47:12 California Ave …
    ## 3 EC45C9… electric_bike 2021-01-21 22:35:54 2021-01-21 22:37:14 California Ave …
    ## 4 4FA453… electric_bike 2021-01-07 13:31:13 2021-01-07 13:42:55 California Ave …
    ## 5 BE5E8E… electric_bike 2021-01-23 02:24:02 2021-01-23 02:24:45 California Ave …
    ## 6 5D8969… electric_bike 2021-01-09 14:24:07 2021-01-09 15:17:54 California Ave …
    ## # … with 8 more variables: start_station_id <chr>, end_station_name <chr>,
    ## #   end_station_id <chr>, start_lat <dbl>, start_lng <dbl>, end_lat <dbl>,
    ## #   end_lng <dbl>, member_casual <chr>

``` r
tail(all_trips) #Last 6 rows of data frame
```

    ## # A tibble: 6 × 13
    ##   ride_id rideable_type started_at          ended_at            start_station_n…
    ##   <chr>   <chr>         <dttm>              <dttm>              <chr>           
    ## 1 92BBAB… electric_bike 2021-12-24 15:42:09 2021-12-24 19:29:35 Canal St & Madi…
    ## 2 847431… electric_bike 2021-12-12 13:36:55 2021-12-12 13:56:08 Canal St & Madi…
    ## 3 CF407B… electric_bike 2021-12-06 19:37:50 2021-12-06 19:44:51 Canal St & Madi…
    ## 4 60BB69… electric_bike 2021-12-02 08:57:04 2021-12-02 09:05:21 Canal St & Madi…
    ## 5 C414F6… electric_bike 2021-12-13 09:00:26 2021-12-13 09:14:39 Lawndale Ave & …
    ## 6 37AC57… classic_bike  2021-12-13 08:45:32 2021-12-13 08:49:09 Michigan Ave & …
    ## # … with 8 more variables: start_station_id <chr>, end_station_name <chr>,
    ## #   end_station_id <chr>, start_lat <dbl>, start_lng <dbl>, end_lat <dbl>,
    ## #   end_lng <dbl>, member_casual <chr>

``` r
str(all_trips)  #List of columns and data types (numeric, character, etc)
```

    ## spec_tbl_df [5,595,063 × 13] (S3: spec_tbl_df/tbl_df/tbl/data.frame)
    ##  $ ride_id           : chr [1:5595063] "E19E6F1B8D4C42ED" "DC88F20C2C55F27F" "EC45C94683FE3F27" "4FA453A75AE377DB" ...
    ##  $ rideable_type     : chr [1:5595063] "electric_bike" "electric_bike" "electric_bike" "electric_bike" ...
    ##  $ started_at        : POSIXct[1:5595063], format: "2021-01-23 16:14:19" "2021-01-27 18:43:08" ...
    ##  $ ended_at          : POSIXct[1:5595063], format: "2021-01-23 16:24:44" "2021-01-27 18:47:12" ...
    ##  $ start_station_name: chr [1:5595063] "California Ave & Cortez St" "California Ave & Cortez St" "California Ave & Cortez St" "California Ave & Cortez St" ...
    ##  $ start_station_id  : chr [1:5595063] "17660" "17660" "17660" "17660" ...
    ##  $ end_station_name  : chr [1:5595063] NA NA NA NA ...
    ##  $ end_station_id    : chr [1:5595063] NA NA NA NA ...
    ##  $ start_lat         : num [1:5595063] 41.9 41.9 41.9 41.9 41.9 ...
    ##  $ start_lng         : num [1:5595063] -87.7 -87.7 -87.7 -87.7 -87.7 ...
    ##  $ end_lat           : num [1:5595063] 41.9 41.9 41.9 41.9 41.9 ...
    ##  $ end_lng           : num [1:5595063] -87.7 -87.7 -87.7 -87.7 -87.7 ...
    ##  $ member_casual     : chr [1:5595063] "member" "member" "member" "member" ...
    ##  - attr(*, "spec")=
    ##   .. cols(
    ##   ..   ride_id = col_character(),
    ##   ..   rideable_type = col_character(),
    ##   ..   started_at = col_datetime(format = ""),
    ##   ..   ended_at = col_datetime(format = ""),
    ##   ..   start_station_name = col_character(),
    ##   ..   start_station_id = col_character(),
    ##   ..   end_station_name = col_character(),
    ##   ..   end_station_id = col_character(),
    ##   ..   start_lat = col_double(),
    ##   ..   start_lng = col_double(),
    ##   ..   end_lat = col_double(),
    ##   ..   end_lng = col_double(),
    ##   ..   member_casual = col_character()
    ##   .. )
    ##  - attr(*, "problems")=<externalptr>

``` r
summary(all_trips)  #Statistical summary of data
```

    ##    ride_id          rideable_type        started_at                 
    ##  Length:5595063     Length:5595063     Min.   :2021-01-01 00:02:05  
    ##  Class :character   Class :character   1st Qu.:2021-06-06 23:52:40  
    ##  Mode  :character   Mode  :character   Median :2021-08-01 01:52:11  
    ##                                        Mean   :2021-07-29 07:41:02  
    ##                                        3rd Qu.:2021-09-24 16:36:16  
    ##                                        Max.   :2021-12-31 23:59:48  
    ##                                                                     
    ##     ended_at                   start_station_name start_station_id  
    ##  Min.   :2021-01-01 00:08:39   Length:5595063     Length:5595063    
    ##  1st Qu.:2021-06-07 00:44:21   Class :character   Class :character  
    ##  Median :2021-08-01 02:21:55   Mode  :character   Mode  :character  
    ##  Mean   :2021-07-29 08:02:58                                        
    ##  3rd Qu.:2021-09-24 16:54:05                                        
    ##  Max.   :2022-01-03 17:32:18                                        
    ##                                                                     
    ##  end_station_name   end_station_id       start_lat       start_lng     
    ##  Length:5595063     Length:5595063     Min.   :41.64   Min.   :-87.84  
    ##  Class :character   Class :character   1st Qu.:41.88   1st Qu.:-87.66  
    ##  Mode  :character   Mode  :character   Median :41.90   Median :-87.64  
    ##                                        Mean   :41.90   Mean   :-87.65  
    ##                                        3rd Qu.:41.93   3rd Qu.:-87.63  
    ##                                        Max.   :42.07   Max.   :-87.52  
    ##                                                                        
    ##     end_lat         end_lng       member_casual     
    ##  Min.   :41.39   Min.   :-88.97   Length:5595063    
    ##  1st Qu.:41.88   1st Qu.:-87.66   Class :character  
    ##  Median :41.90   Median :-87.64   Mode  :character  
    ##  Mean   :41.90   Mean   :-87.65                     
    ##  3rd Qu.:41.93   3rd Qu.:-87.63                     
    ##  Max.   :42.17   Max.   :-87.49                     
    ##  NA's   :4771    NA's   :4771

``` r
# This will allow us to aggregate ride data for each month, day, or year ... before completing these operations we could only aggregate at the ride level
# https://www.statmethods.net/input/dates.html more on date formats in R found at that link
all_trips$date <- as.Date(all_trips$started_at) #The default format is yyyy-mm-dd
all_trips$month <- format(as.Date(all_trips$date), "%m") ##Adds the month of the ride
all_trips$day <- format(as.Date(all_trips$date), "%d") ##Adds the date of the ride
all_trips$year <- format(as.Date(all_trips$date), "%Y") ##Adds the year of the ride
all_trips$day_of_week <- format(as.Date(all_trips$date), "%A")  ##Adds the day of week of the ride
```

``` r
# https://stat.ethz.ch/R-manual/R-devel/library/base/html/difftime.html
all_trips <- all_trips %>% 
  mutate(ride_length = ended_at - started_at) ##Time in seconds
```

``` r
# The dataframe includes a few hundred entries when bikes were taken out of docks and checked for quality by Divvy or ride_length was negative
# We will create a new version of the dataframe (v2) since data is being removed
# https://www.datasciencemadesimple.com/delete-or-drop-rows-in-r-with-conditions-2/
all_trips_v2 <- all_trips[!(all_trips$ride_length<0),]
```

## Conduct descriptive analysis

``` r
table(all_trips_v2['member_casual'])
```

    ## 
    ##  casual  member 
    ## 2528946 3065970

``` r
mean(all_trips_v2$ride_length) #straight average (total ride length / rides)
```

    ## Time difference of 1316.18 secs

``` r
median(all_trips_v2$ride_length) #midpoint number in the ascending array of ride lengths
```

    ## Time difference of 720 secs

``` r
max(all_trips_v2$ride_length) #longest ride
```

    ## Time difference of 3356649 secs

``` r
min(all_trips_v2$ride_length) #shortest ride
```

    ## Time difference of 0 secs

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = mean)
```

    ##   all_trips_v2$member_casual all_trips_v2$ride_length
    ## 1                     casual               1920.1327 
    ## 2                     member                818.0129

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = median)
```

    ##   all_trips_v2$member_casual all_trips_v2$ride_length
    ## 1                     casual                     958 
    ## 2                     member                     576

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = max)
```

    ##   all_trips_v2$member_casual all_trips_v2$ride_length
    ## 1                     casual                 3356649 
    ## 2                     member                   93596

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual, FUN = min)
```

    ##   all_trips_v2$member_casual all_trips_v2$ride_length
    ## 1                     casual                       0 
    ## 2                     member                       0

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
```

    ##    all_trips_v2$member_casual all_trips_v2$day_of_week all_trips_v2$ride_length
    ## 1                      casual                   Friday               1820.9160 
    ## 2                      member                   Friday                799.4950 
    ## 3                      casual                   Monday               1912.5269 
    ## 4                      member                   Monday                794.8517 
    ## 5                      casual                 Saturday               2082.3740 
    ## 6                      member                 Saturday                915.8742 
    ## 7                      casual                   Sunday               2253.9949 
    ## 8                      member                   Sunday                939.4763 
    ## 9                      casual                 Thursday               1662.1955 
    ## 10                     member                 Thursday                766.5710 
    ## 11                     casual                  Tuesday               1678.3396 
    ## 12                     member                  Tuesday                767.2874 
    ## 13                     casual                Wednesday               1659.4383 
    ## 14                     member                Wednesday                769.1496

``` r
all_trips_v2$day_of_week <- ordered(all_trips_v2$day_of_week, levels=c("Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"))
```

``` r
aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
```

    ##    all_trips_v2$member_casual all_trips_v2$day_of_week all_trips_v2$ride_length
    ## 1                      casual                   Sunday               2253.9949 
    ## 2                      member                   Sunday                939.4763 
    ## 3                      casual                   Monday               1912.5269 
    ## 4                      member                   Monday                794.8517 
    ## 5                      casual                  Tuesday               1678.3396 
    ## 6                      member                  Tuesday                767.2874 
    ## 7                      casual                Wednesday               1659.4383 
    ## 8                      member                Wednesday                769.1496 
    ## 9                      casual                 Thursday               1662.1955 
    ## 10                     member                 Thursday                766.5710 
    ## 11                     casual                   Friday               1820.9160 
    ## 12                     member                   Friday                799.4950 
    ## 13                     casual                 Saturday               2082.3740 
    ## 14                     member                 Saturday                915.8742

``` r
all_trips_v2 %>% 
  mutate(weekday = wday(started_at, label = TRUE)) %>%  #creates weekday field using wday()
  group_by(member_casual, weekday) %>%  #groups by usertype and weekday
  summarise(number_of_rides = n()                           #calculates the number of rides and average duration 
  ,average_duration = mean(ride_length)) %>%        # calculates the average duration
  arrange(member_casual, weekday)                               # sorts
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

    ## # A tibble: 14 × 4
    ## # Groups:   member_casual [2]
    ##    member_casual weekday number_of_rides average_duration
    ##    <chr>         <ord>             <int> <drtn>          
    ##  1 casual        Sun              481104 2253.9949 secs  
    ##  2 casual        Mon              286373 1912.5269 secs  
    ##  3 casual        Tue              274388 1678.3396 secs  
    ##  4 casual        Wed              278948 1659.4383 secs  
    ##  5 casual        Thu              286064 1662.1955 secs  
    ##  6 casual        Fri              364075 1820.9160 secs  
    ##  7 casual        Sat              557994 2082.3740 secs  
    ##  8 member        Sun              376117  939.4763 secs  
    ##  9 member        Mon              416204  794.8517 secs  
    ## 10 member        Tue              465509  767.2874 secs  
    ## 11 member        Wed              477156  769.1496 secs  
    ## 12 member        Thu              451520  766.5710 secs  
    ## 13 member        Fri              446423  799.4950 secs  
    ## 14 member        Sat              433041  915.8742 secs

``` r
all_trips_v2 %>% 
  group_by(member_casual, month) %>%  #groups by usertype and weekday
  summarise(number_of_rides = n()                           #calculates the number of rides and average duration 
  ,average_duration = mean(ride_length)) %>%        # calculates the average duration
  arrange(member_casual, month)                             # sorts
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

    ## # A tibble: 24 × 4
    ## # Groups:   member_casual [2]
    ##    member_casual month number_of_rides average_duration
    ##    <chr>         <chr>           <int> <drtn>          
    ##  1 casual        01              18117 1541.075 secs   
    ##  2 casual        02              10131 2962.394 secs   
    ##  3 casual        03              84032 2289.551 secs   
    ##  4 casual        04             136601 2281.379 secs   
    ##  5 casual        05             256916 2293.858 secs   
    ##  6 casual        06             370678 2227.304 secs   
    ##  7 casual        07             442048 1967.446 secs   
    ##  8 casual        08             412662 1727.221 secs   
    ##  9 casual        09             363883 1668.932 secs   
    ## 10 casual        10             257242 1720.438 secs   
    ## # … with 14 more rows

## Create visualizations

``` r
all_trips_v2 %>% 
  mutate(weekday = wday(started_at, label = TRUE)) %>% 
  group_by(member_casual, weekday) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, weekday)  %>% 
  ggplot(aes(x = weekday, y = number_of_rides, fill = member_casual)) +
  geom_col(position = "dodge")
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

![](Cyclistic---Google-Data-Analytics-Capstone-Project_files/figure-gfm/visualize%20the%20number%20of%20rides%20by%20rider%20type-1.png)<!-- -->

``` r
all_trips_v2 %>% 
  mutate(weekday = wday(started_at, label = TRUE)) %>% 
  group_by(member_casual, weekday) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, weekday)  %>% 
  ggplot(aes(x = weekday, y = average_duration, fill = member_casual)) +
  geom_col(position = "dodge")
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

    ## Don't know how to automatically pick scale for object of type difftime. Defaulting to continuous.

![](Cyclistic---Google-Data-Analytics-Capstone-Project_files/figure-gfm/create%20a%20visualization%20for%20average%20duration-1.png)<!-- -->

``` r
all_trips_v2 %>% 
  group_by(member_casual, month) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, month)  %>% 
  ggplot(aes(x = month, y = number_of_rides, fill = member_casual)) +
  geom_col(position = "dodge")
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

![](Cyclistic---Google-Data-Analytics-Capstone-Project_files/figure-gfm/visualize%20the%20number%20of%20rides%20by%20rider%20type%20by%20month-1.png)<!-- -->

``` r
all_trips_v2 %>% 
  group_by(member_casual, month) %>% 
  summarise(number_of_rides = n()
            ,average_duration = mean(ride_length)) %>% 
  arrange(member_casual, month)  %>% 
  ggplot(aes(x = month, y = average_duration, fill = member_casual)) +
  geom_col(position = "dodge")
```

    ## `summarise()` has grouped output by 'member_casual'. You can override using the `.groups` argument.

    ## Don't know how to automatically pick scale for object of type difftime. Defaulting to continuous.

![](Cyclistic---Google-Data-Analytics-Capstone-Project_files/figure-gfm/create%20a%20visualization%20for%20average%20duration%20by%20month-1.png)<!-- -->

## Export summary file for further analysis

``` r
# Create a csv file that we will visualize in Excel, Tableau, or my presentation software
# N.B.: This file location is for a Mac. If you are working on a PC, change the file location accordingly (most likely "C:\Users\YOUR_USERNAME\Desktop\...") to export the data. You can read more here: https://datatofish.com/export-dataframe-to-csv-in-r/
counts <- aggregate(all_trips_v2$ride_length ~ all_trips_v2$member_casual + all_trips_v2$day_of_week, FUN = mean)
write.csv(counts, file = '~/Desktop/avg_ride_length.csv')
```
