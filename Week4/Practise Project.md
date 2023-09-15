# Practice Project: Historical Weather Forecast Comparison to Actuals

## Initialize your weather report log file
1.  Create a text file called rx_poc.log 
```
theia@theia-quyduong106:/home/project$ touch rx_poc.log
```
2. Add a header to your weather report
```
theia@theia-quyduong106:/home/project$ header=$(echo -e "year\tmonth\tday\tobs_tmp\tfc_temp")
theia@theia-quyduong106:/home/project$ echo $header>rx_poc.log
theia@theia-quyduong106:/home/project$ echo -e "year\tmonth\tday\thour\tobs_tmp\tfc_temp">rx_poc.log
```

## Download the raw weather data
1. Create a text file called rx_poc.sh and make it an executable Bash script
```
theia@theia-quyduong106:/home/project$ touch rx_poc.sh
theia@theia-quyduong106:/home/project$ #! /bin/bash
theia@theia-quyduong106:/home/project$ chmod u+x rx_poc.sh
theia@theia-quyduong106:/home/project$ ls rx_poc.sh
rx_poc.sh
theia@theia-quyduong106:/home/project$ 
```

2. Edit rx_poc.sh to download today's weather report from wttr.in
2.1 Create the filename for today's wttr.in weather report
```
theia@theia-quyduong106:/home/project$ today=$(date +%Y%m%d)
theia@theia-quyduong106:/home/project$ weather_report=raw_data_$today
theia@theia-quyduong106:/home/project$ weather_report=raw_data_$(date +%Y%m%d)
```

2.2 Download the wttr.in weather report for Casablanca and save it with the filename you created
```
theia@theia-quyduong106:/home/project$ city=Casablanca
theia@theia-quyduong106:/home/project$ curl wttr.in/$city --output $weather_report
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  9195  100  9195    0     0  15717      0 --:--:-- --:--:-- --:--:-- 15744
```

## Extract and load the required data
1. Edit rx_poc.sh to extract the required data from the raw data file and assign them to variables obs_tmp and fc_temp
```
theia@theia-quyduong106:/home/project$ grep °C $weather_report > temperatures.txt
```
1.1 Extract the current temperature, and store it in a shell variable called
```
theia@theia-quyduong106:/home/project$ obs_tmp=$(cat -A temperatures.txt | head -1 | cut -d "+" -f2 | cut -d "^" -f1 )
theia@theia-quyduong106:/home/project$ echo "observed temperature = $obs_tmp"
observed temperature = 26
```

1.2 Extract tomorrow's temperature forecast for noon, and store it in a shell variable called fc_tmp
```
theia@theia-quyduong106:/home/project$ fc_temp=$(cat -A temperatures.txt | head -3 | tail -1 | cut -d "+" -f2 | cut -d "(" -f1 | cut -d "^" -f1 )
```

2. Store the current hour, day, month, and year in corresponding shell variables
```
theia@theia-quyduong106:/home/project$ hour=$(TZ='Morocco/Casablanca' date -u +%H) 
theia@theia-quyduong106:/home/project$ day=$(TZ='Morocco/Casablanca' date -u +%d) 
theia@theia-quyduong106:/home/project$ month=$(TZ='Morocco/Casablanca' date +%m)
theia@theia-quyduong106:/home/project$ year=$(TZ='Morocco/Casablanca' date +%Y)
```

3. Merge the fields into a tab-delimited record, corresponding to a single row in Table 1
```
theia@theia-quyduong106:/home/project$ record=$(echo -e "$year\t$month\t$day\t$obs_tmp\t$fc_temp")
theia@theia-quyduong106:/home/project$ echo $record>>rx_poc.log
```

## Schedule your Bash script rx_poc.sh to run every day at noon local time
1. Determine what time of day to run your script
```
theia@theia-quyduong106:/home/project$ date
Fri Sep 15 12:50:00 EDT 2023

theia@theia-quyduong106:/home/project$ date -u
Fri Sep 15 16:50:30 UTC 2023
```

2. Create a cron job that runs your script
```
theia@theia-quyduong106:/home/project$ crontab -e
crontab: installing new crontab
```

3. Final Solution
```
theia@theia-quyduong106:/home/project$ #! /bin/bash
theia@theia-quyduong106:/home/project$ today=$(date +%Y%m%d)
theia@theia-quyduong106:/home/project$ weather_report=raw_data_$today
theia@theia-quyduong106:/home/project$ city=Casablanca
theia@theia-quyduong106:/home/project$ curl wttr.in/$city --output $weather_report
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  9195  100  9195    0     0  19076      0 --:--:-- --:--:-- --:--:-- 19116
theia@theia-quyduong106:/home/project$ hour=$(TZ='Morocco/Casablanca' date -u +%H) 
theia@theia-quyduong106:/home/project$ day=$(TZ='Morocco/Casablanca' date -u +%d) 
theia@theia-quyduong106:/home/project$ month=$(TZ='Morocco/Casablanca' date +%m)
theia@theia-quyduong106:/home/project$ year=$(TZ='Morocco/Casablanca' date +%Y)
theia@theia-quyduong106:/home/project$ grep °C $weather_report > temperatures.txt
theia@theia-quyduong106:/home/project$ obs_tmp=$(cat -A temperatures.txt | head -1 | cut -d "+" -f2 | cut -d "^" -f1 )
theia@theia-quyduong106:/home/project$ echo "observed = $obs_tmp"
observed = 26
theia@theia-quyduong106:/home/project$ fc_temp=$(cat -A temperatures.txt | head -3 | tail -1 | cut -d "+" -f2 | cut -d "(" -f1 | cut -d "^" -f1 )
theia@theia-quyduong106:/home/project$ echo "fc temp = $fc_temp"
fc temp = 23
theia@theia-quyduong106:/home/project$ record=$(echo -e "$year\t$month\t$day\t$obs_tmp\t$fc_temp")
theia@theia-quyduong106:/home/project$ echo $record>>rx_poc.log
theia@theia-quyduong106:/home/project$ 
```

## Create a script to report historical forecasting accuracy
To begin, create a tab-delimited file called historical_fc_accuracy.tsv using the following code to insert a header of column names:
```
theia@theia-quyduong106:/home/project$ echo -e "year\tmonth\tday\tobs_tmp\tfc_temp\taccuracy\taccuracy_range" > historical_fc_accuracy.tsv
```
1.  Determine the difference between today's forecasted and actual temperatures
```
heia@theia-quyduong106:/home/project$ yesterday_fc=$(tail -2 rx_poc.log | head -1 | cut -d " " -f5)
theia@theia-quyduong106:/home/project$ today_temp=$(tail -1 rx_poc.log | cut -d " " -f4)
theia@theia-quyduong106:/home/project$ accuracy=$(($yesterday_fc-$today_temp))
```

2. Assign a label to each forecast based on its accuracy
```
theia@theia-quyduong106:/home/project$ if [ -1 -le $accuracy ] && [ $accuracy -le 1 ]
> then
>    accuracy_range=excellent
> elif [ -2 -le $accuracy ] && [ $accuracy -le 2 ]
> then
>     accuracy_range=good
> elif [ -3 -le $accuracy ] && [ $accuracy -le 3 ]
> then
>     accuracy_range=fair
> else
>     accuracy_range=poor
> fi
theia@theia-quyduong106:/home/project$ echo "Forecast accuracy is $accuracy"
Forecast accuracy is -3
```

3. Append a record to your historical forecast accuracy file.
```
theia@theia-quyduong106:/home/project$ row=$(tail -1 rx_poc.log)
theia@theia-quyduong106:/home/project$ year=$( echo $row | cut -d " " -f1)
theia@theia-quyduong106:/home/project$ month=$( echo $row | cut -d " " -f2)
theia@theia-quyduong106:/home/project$ day=$( echo $row | cut -d " " -f3)
theia@theia-quyduong106:/home/project$ echo -e "$year\t$month\t$day\t$today_temp\t$yesterday_fc\t$accuracy\t$accuracy_range" >> historical_fc_accuracy.tsv
```

4. Full solution for handling a single day
```
theia@theia-quyduong106:/home/project$ #! /bin/bash
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ yesterday_fc=$(tail -2 rx_poc.log | head -1 | cut -d " " -f5)
theia@theia-quyduong106:/home/project$ today_temp=$(tail -1 rx_poc.log | cut -d " " -f4)
theia@theia-quyduong106:/home/project$ accuracy=$(($yesterday_fc-$today_temp))
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ echo "accuracy is $accuracy"
accuracy is -3
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ if [ -1 -le $accuracy ] && [ $accuracy -le 1 ]
> then
>            accuracy_range=excellent
> elif [ -2 -le $accuracy ] && [ $accuracy -le 2 ]
>    then
>                accuracy_range=good
>        elif [ -3 -le $accuracy ] && [ $accuracy -le 3 ]
>        then
>                    accuracy_range=fair
>            else
>                        accuracy_range=poor
> fi
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ echo "Forecast accuracy is $accuracy_range"
Forecast accuracy is fair
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ row=$(tail -1 rx_poc.log)
theia@theia-quyduong106:/home/project$ year=$( echo $row | cut -d " " -f1)
theia@theia-quyduong106:/home/project$ month=$( echo $row | cut -d " " -f2)
theia@theia-quyduong106:/home/project$ day=$( echo $row | cut -d " " -f3)
theia@theia-quyduong106:/home/project$ echo -e "$year\t$month\t$day\t$today_temp\t$yesterday_fc\t$accuracy\t$accuracy_range" >> historical_fc_accuracy.tsv
```

## Create a script to report weekly statistics of historical forecasting accuracy
1.  Download the synthetic historical forecasting accuracy dataset
```
theia@theia-quyduong106:/home/project$ wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-LX0117EN-Coursera/labs/synthetic_historical_fc_accuracy.tsv
--2023-09-15 13:01:21--  https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-LX0117EN-Coursera/labs/synthetic_historical_fc_accuracy.tsv
Resolving cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)... 169.63.118.104
Connecting to cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)|169.63.118.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 263 [text/tab-separated-values]
Saving to: ‘synthetic_historical_fc_accuracy.tsv’

synthetic_historical_fc_accurac 100%[====================================================>]     263  --.-KB/s    in 0s      

2023-09-15 13:01:21 (28.3 MB/s) - ‘synthetic_historical_fc_accuracy.tsv’ saved [263/263]

```
2. Load the historical accuracies into an array covering the last week of data
```
theia@theia-quyduong106:/home/project$ #!/bin/bash
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ echo $(tail -7 synthetic_historical_fc_accuracy.tsv  | cut -f6) > scratch.txt
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ week_fc=($(echo $(cat scratch.txt)))
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ # validate result:
theia@theia-quyduong106:/home/project$ for i in {0..6}; do
>     echo ${week_fc[$i]}
> done
-5
-1
-2
4
-2
0
1
```

3. Display the minimum and maximum absolute forecasting errors for the week
```
theia@theia-quyduong106:/home/project$ #!/bin/bash
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ echo $(tail -7 synthetic_historical_fc_accuracy.tsv  | cut -f6) > scratch.txt
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ week_fc=($(echo $(cat scratch.txt)))
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ # validate result:
theia@theia-quyduong106:/home/project$ for i in {0..6}; do
>     echo ${week_fc[$i]}
> done
-5
-1
-2
4
-2
0
1
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ for i in {0..6}; do
>   if [[ ${week_fc[$i]} < 0 ]]
>   then
>     week_fc[$i]=$(((-1)*week_fc[$i]))
>   fi
>   # validate result:
>   echo ${week_fc[$i]}
> done
-5
-1
-2
4
-2
0
1
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ minimum=${week_fc[1]}
theia@theia-quyduong106:/home/project$ maximum=${week_fc[1]}
theia@theia-quyduong106:/home/project$ for item in ${week_fc[@]}; do
>    if [[ $minimum > $item ]]
>    then
>      minimum=$item
>    fi
>    if [[ $maximum < $item ]]
>    then
>      maximum=$item
>    fi
> done
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ echo "minimum ebsolute error = $minimum"
minimum ebsolute error = 0
theia@theia-quyduong106:/home/project$ echo "maximum absolute error = $maximum"
maximum absolute error = -5
theia@theia-quyduong106:/home/project$ 
```