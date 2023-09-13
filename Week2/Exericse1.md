# Exercise 1 - Informational Commands
```
theia@theia-quyduong106:/home/project$ whoami
theia
```

```
theia@theia-quyduong106:/home/project$ uname
Linux
theia@theia-quyduong106:/home/project$ uname -a
Linux theia-quyduong106 5.4.0-156-generic #173-Ubuntu SMP Tue Jul 11 07:25:22 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
```

```
theia@theia-quyduong106:/home/project$ id
uid=1000(theia) gid=1000(theia) groups=1000(theia),27(sudo),100(users)
```

```
theia@theia-quyduong106:/home/project$ df
Filesystem     1K-blocks     Used Available Use% Mounted on
overlay        101986876 74910312  22656328  77% /
tmpfs              65536        0     65536   0% /dev
tmpfs           16361252        0  16361252   0% /sys/fs/cgroup
/dev/vda2      101986876 74910312  22656328  77% /etc/hosts
shm                65536        0     65536   0% /dev/shm
tmpfs           28937800       16  28937784   1% /run/secrets/kubernetes.io/serviceaccount
tmpfs           16361252        0  16361252   0% /proc/acpi
tmpfs           16361252        0  16361252   0% /proc/scsi
tmpfs           16361252        0  16361252   0% /sys/firmware
theia@theia-quyduong106:/home/project$ df -h
Filesystem      Size  Used Avail Use% Mounted on
overlay          98G   72G   22G  77% /
tmpfs            64M     0   64M   0% /dev
tmpfs            16G     0   16G   0% /sys/fs/cgroup
/dev/vda2        98G   72G   22G  77% /etc/hosts
shm              64M     0   64M   0% /dev/shm
tmpfs            28G   16K   28G   1% /run/secrets/kubernetes.io/serviceaccount
tmpfs            16G     0   16G   0% /proc/acpi
tmpfs            16G     0   16G   0% /proc/scsi
tmpfs            16G     0   16G   0% /sys/firmware
```

```
theia@theia-quyduong106:/home/project$ ps
   PID TTY          TIME CMD
   421 pts/1    00:00:00 bash
 15954 pts/1    00:00:00 nano
 16136 pts/1    00:00:00 ps
theia@theia-quyduong106:/home/project$ ps -e
   PID TTY          TIME CMD
     1 ?        00:00:00 sh
     7 ?        00:00:00 entrypoint.sh
    35 ?        00:00:00 cron
    36 ?        00:00:02 node
    47 ?        00:00:00 sh
    48 ?        00:00:00 node
    59 ?        00:00:16 node
    76 ?        00:00:23 node
    98 pts/0    00:00:00 bash
   421 pts/1    00:00:00 bash
 15954 pts/1    00:00:00 nano
 16021 ?        00:00:00 node
 16037 ?        00:00:00 node
 16137 pts/1    00:00:00 ps
```

```
Filesystem     1K-blocks     Used Available Use% Mounted on
top - 22:13:07 up 11 days,  6:40,  0 users,  load average: 0.70, 0.68, 0.68
Tasks:  14 total,   1 running,  12 sleeping,   1 stopped,   0 zombie
%Cpu(s):  3.3 us,  2.1 sy,  0.0 ni, 94.4 id,  0.0 wa,  0.0 hi,  0.2 si,  0.0 st
KiB Mem : 32722504 total,  3029140 free,  3410872 used, 26282492 buff/cache
top - 22:13:26 up 11 days,  6:41,  0 users,  load average: 0.57, 0.65, 0.67
Tasks:  14 total,   2 running,  11 sleeping,   1 stopped,   0 zombie
%Cpu(s):  3.5 us,  2.3 sy,  0.0 ni, 93.9 id,  0.1 wa,  0.0 hi,  0.2 si,  0.0 st
KiB Mem : 32722504 total,  3025564 free,  3413684 used, 26283256 buff/cache
KiB Swap:        0 total,        0 free,        0 used. 28836004 avail Mem 

   PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                                                 
    76 theia     20   0 1212516  56332  32772 S   0.5  0.2   0:23.60 node                                                    
     1 theia     20   0    4632    876    808 S   0.0  0.0   0:00.02 sh                                                      
     7 theia     20   0   12888   3288   2996 S   0.0  0.0   0:00.01 entrypoint.sh                                           
    35 root      20   0   31320   2860   2576 S   0.0  0.0   0:00.01 cron                                                    
    36 theia     20   0  864152  75620  32920 S   0.0  0.2   0:02.06 node                                                    
    47 theia     20   0    4640    896    820 S   0.0  0.0   0:00.00 sh                                                      
    48 theia     20   0  716392  98596  33036 S   0.0  0.3   0:00.90 node                                                    
    59 theia     20   0 1048012 106332  37620 R   0.0  0.3   0:16.26 node                                                    
    98 theia     20   0   25444   7744   3360 S   0.0  0.0   0:00.50 bash                                                    
   421 theia     20   0   25444   7728   3344 S   0.0  0.0   0:00.54 bash                                                    
 15954 theia     20   0   23772   4412   3112 T   0.0  0.0   0:00.06 nano                                                    
 16021 theia     20   0  869180  67208  34520 S   0.0  0.2   0:00.91 node                                                    
 16037 theia     20   0  605276  43568  32612 S   0.0  0.1   0:00.16 node                                                    
 16140 theia     20   0   41664   3668   3176 R   0.0  0.0   0:00.00 top     
```

```
theia@theia-quyduong106:/home/project$ echo"Welcome to the linux lab"
bash: echoWelcome to the linux lab: command not found
theia@theia-quyduong106:/home/project$ echo "Welcome to the linux lab"
Welcome to the linux lab
```

```
theia@theia-quyduong106:/home/project$ echo -e "This will printed \nin two lines"
This will printed 
in two lines
```

```
theia@theia-quyduong106:/home/project$ date
Sun Sep 10 22:17:47 EDT 2023
theia@theia-quyduong106:/home/project$ date "+%D"
09/10/23
```

```
theia@theia-quyduong106:/home/project$ man ls
theia@theia-quyduong106:/home/project$ man -k
apropos what?
```