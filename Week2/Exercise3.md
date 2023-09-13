# Understanding directory access permissions
 ```
 theia@theia-quyduong106:/home/project$ mkdir test
theia@theia-quyduong106:/home/project$ ls -l
total 32
-rw-r--r-- 1 theia users   24 Sep 10 22:01 done.txt
-rw-r--r-- 1 theia users   39 Sep 10 21:55 hello_world_2.txt
-rw-r--r-- 1 theia users  122 Sep 10 21:58 hello_world.txt
drwxr-sr-x 2 theia users 4096 Sep 10 23:03 test
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt.1
 ```

 ```
 theia@theia-quyduong106:/home/project$ cd test
theia@theia-quyduong106:/home/project/test$ mkdir test2
theia@theia-quyduong106:/home/project/test$ cd ../
 ```

 ```
 theia@theia-quyduong106:/home/project$ cd test
theia@theia-quyduong106:/home/project/test$ mkdir test2
theia@theia-quyduong106:/home/project/test$ cd ../
theia@theia-quyduong106:/home/project$ chmod u-x test
theia@theia-quyduong106:/home/project$ cd test
bash: cd: test: Permission denied
theia@theia-quyduong106:/home/project$ ls -l
total 32
-rw-r--r-- 1 theia users   24 Sep 10 22:01 done.txt
-rw-r--r-- 1 theia users   39 Sep 10 21:55 hello_world_2.txt
-rw-r--r-- 1 theia users  122 Sep 10 21:58 hello_world.txt
drw-r-sr-x 3 theia users 4096 Sep 10 23:05 test
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt.1
theia@theia-quyduong106:/home/project$ mdkir test/test3
bash: mdkir: command not found
theia@theia-quyduong106:/home/project$ mkdir test/test3
mkdir: cannot create directory ‘test/test3’: Permission denied
theia@theia-quyduong106:/home/project$ chmod u+x test
theia@theia-quyduong106:/home/project$ chmod u-w test
theia@theia-quyduong106:/home/project$ ls -l
total 32
-rw-r--r-- 1 theia users   24 Sep 10 22:01 done.txt
-rw-r--r-- 1 theia users   39 Sep 10 21:55 hello_world_2.txt
-rw-r--r-- 1 theia users  122 Sep 10 21:58 hello_world.txt
dr-xr-sr-x 3 theia users 4096 Sep 10 23:05 test
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
-rw-r--r-- 1 theia users 8121 Sep 28  2022 usdoi.txt.1
theia@theia-quyduong106:/home/project$ cd test
theia@theia-quyduong106:/home/project/test$ mkdir test_again
mkdir: cannot create directory ‘test_again’: Permission denied
 ```

 ```
 
 ```