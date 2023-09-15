# Using arrays for storing and accessing data within for loops
## 1. Download a CSV file to your current working directory
```
theia@theia-quyduong106:/home/project$ csv_file="https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/M3/L2/arrays_table.csv"
theia@theia-quyduong106:/home/project$ wget $csv_file
--2023-09-15 05:17:13--  https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/M3/L2/arrays_table.csv
Resolving cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)... 169.63.118.104
Connecting to cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)|169.63.118.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [text/csv]
Saving to: ‘arrays_table.csv’

arrays_table.csv                100%[====================================================>]      54  --.-KB/s    in 0s      

2023-09-15 05:17:13 (9.89 MB/s) - ‘arrays_table.csv’ saved [54/54]

```
## 2. Display the CSV file to understand what it looks like
```
theia@theia-quyduong106:/home/project$ cat arrays_table.csv
column_0,column_1,column_2
1,2,3
4,5,6
7,8,9
10,11,12
```

## 3. Create a Bash script that parses table columns into 3 arrays\
```
theia@theia-quyduong106:/home/project$ chmod +x arrays_table.csv
theia@theia-quyduong106:/home/project$ nano arrays_table.csv
theia@theia-quyduong106:/home/project$ nano parses_table.sh
theia@theia-quyduong106:/home/project$ chmod +x parses_table.sh
theia@theia-quyduong106:/home/project$ ./parses_table.sh 
Displaying the first column:
column_0 1 4 7 10
```

## 4. Create a new array as the difference of the third and second columns.
```
theia@theia-quyduong106:/home/project$ nano parses_table.sh
theia@theia-quyduong106:/home/project$ chmod +x parses_table.sh
theia@theia-quyduong106:/home/project$ ./parses_table.sh 
Displaying the first column:
column_0 1 4 7 10
There are 5 lines in the file
column_3 1 1 1 1
```

## 5. Create a report by combining your new column with the source table
```
theia@theia-quyduong106:/home/project$ nano parses_table.sh
theia@theia-quyduong106:/home/project$ chmod +x parses_table.sh
theia@theia-quyduong106:/home/project$ ./parses_table.sh 
Displaying the first column:
column_0 1 4 7 10
There are 5 lines in the file
column_3 1 1 1 1
theia@theia-quyduong106:/home/project$ nano parses_table.sh
theia@theia-quyduong106:/home/project$ chmod +x parses_table.sh
theia@theia-quyduong106:/home/project$ ./parses_table.sh 
Displaying the first column:
column_0 1 4 7 10
There are 5 lines in the file
column_3 1 1 1 1

theia@theia-quyduong106:/home/project$ cat arrays_table.csv
column_0,column_1,column_2
1,2,3
4,5,6
7,8,9
10,11,12
```

```
![Alt text](image-3.png)
```