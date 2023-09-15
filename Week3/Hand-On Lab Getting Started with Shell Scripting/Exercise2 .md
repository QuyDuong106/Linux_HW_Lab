# Using a shebang line
## 2.1. Find the path to the interpreter
```
theia@theia-quyduong106:/home/project$ which bash
/bin/bash

```

## 2.2. Edit the script greet.sh and add the shebang line to the script
Open the file and add the following line at the beginning of the script:
```
#! /bin/bash

```

## 2.3 Check the permissions of the script
```
theia@theia-quyduong106:/home/project$ chmod +x greet.sh
theia@theia-quyduong106:/home/project$ chmod u+x greet.sh
theia@theia-quyduong106:/home/project$ 
theia@theia-quyduong106:/home/project$ ls -l greet.sh
-rwxr-xr-x 1 theia users 530 Sep 11 22:26 greet.sh
theia@theia-quyduong106:/home/project$ chmod +x greet.sh
theia@theia-quyduong106:/home/project$ ls -l greet.sh
-rwxr-xr-x 1 theia users 530 Sep 11 22:26 greet.sh
```

## 2.4. Execute the script.
```
theia@theia-quyduong106:/home/project$ ./greet.sh
Enter your name :QDuong
Welcome QDuong
Congratulations! You just created and ran your first shell script using Bash on IBM Skills Network
```