# Exercise 1 - Viewing and modifying file access permissions

1.
```
theia@theia-quyduong106:/home/project$ wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/usdoi.txt
--2023-09-10 22:59:29--  https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/module%201/usdoi.txt
Resolving cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)... 169.63.118.104
Connecting to cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud (cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud)|169.63.118.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8121 (7.9K) [text/plain]
Saving to: ‘usdoi.txt.1’

usdoi.txt.1                     100%[====================================================>]   7.93K  --.-KB/s    in 0s      

2023-09-10 22:59:29 (851 MB/s) - ‘usdoi.txt.1’ saved [8121/8121]

theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt
theia@theia-quyduong106:/home/project$ 
```

```
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ chmod -r usdoi.txt       
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
--w------- 1 theia users 8121 Sep 28  2022 usdoi.txt
theia@theia-quyduong106:/home/project$ chmod +r usdoi.txt                
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt
theia@theia-quyduong106:/home/project$ chmod o-r usdoi.txt
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
```