## 1. Get basic information about the operating system.
```
theia@theia-quyduong106:/home/project$ uname
Linux
```
## 2. View all running processes on the system.
```
theia@theia-quyduong106:/home/project$ ps -e
   PID TTY          TIME CMD
     1 ?        00:00:00 sh
     7 ?        00:00:00 entrypoint.sh
    35 ?        00:00:00 cron
    36 ?        00:00:02 node
    47 ?        00:00:00 sh
    48 ?        00:00:00 node
    59 ?        00:00:18 node
    76 ?        00:00:27 node
    98 pts/0    00:00:00 bash
   421 pts/1    00:00:00 bash
 15954 pts/1    00:00:00 nano
 16021 ?        00:00:01 node
 16037 ?        00:00:00 node
 16217 pts/1    00:00:00 ps
```

## 3. Get the table of processes and sort by memory usage.
```
theia@theia-quyduong106:/home/project$ top
top - 22:26:10 up 11 days,  6:53,  0 users,  load average: 0.98, 0.57, 0.58
Tasks:  14 total,   1 running,  12 sleeping,   1 stopped,   0 zombie
%Cpu(s):  2.6 us,  2.0 sy,  0.0 ni, 95.4 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
KiB Mem : 32722504 total,  3560388 free,  2988428 used, 26173688 buff/cache
KiB Swap:        0 total,        0 free,        0 used. 29262004 avail Mem 

   PID USER      PR  NI    VIRT    RES    SHR S  %CPU %MEM     TIME+ COMMAND                                                 
    76 theia     20   0 1223780  67768  32772 S   0.7  0.2   0:28.14 node                                                    
    59 theia     20   0 1048012 106260  37620 S   0.3  0.3   0:18.52 node                                                    
     1 theia     20   0    4632    876    808 S   0.0  0.0   0:00.02 sh                                                      
     7 theia     20   0   12888   3288   2996 S   0.0  0.0   0:00.01 entrypoint.sh                                           
    35 root      20   0   31320   2860   2576 S   0.0  0.0   0:00.01 cron                                                    
    36 theia     20   0  864152  75208  32984 S   0.0  0.2   0:02.24 node                                                    
    47 theia     20   0    4640    896    820 S   0.0  0.0   0:00.00 sh                                                      
    48 theia     20   0  716392  98596  33036 S   0.0  0.3   0:00.90 node                                                    
    98 theia     20   0   25444   7744   3360 S   0.0  0.0   0:00.50 bash                                                    
   421 theia     20   0   25444   7728   3344 S   0.0  0.0   0:00.67 bash                                                    
 15954 theia     20   0   23772   4412   3112 T   0.0  0.0   0:00.06 nano                                                    
 16021 theia     20   0  869180  67792  34520 S   0.0  0.2   0:01.21 node                                                    
 16037 theia     20   0  605276  43568  32612 S   0.0  0.1   0:00.20 node                                                    
 16225 theia     20   0   41664   3668   3176 R   0.0  0.0   0:00.00 top                                                     

```

## 4. Display the current time.
```
theia@theia-quyduong106:/home/project$ date "+%T"
22:26:34
```

## 5. Using one command, display the messages "Hello!" and "Goodbye!" separated by a new line.
```
theia@theia-quyduong106:/home/project$ echo -e "Hello! \nGoodbye!"
Hello! 
Goodbye!
```