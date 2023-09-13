# Hands-on Lab: Access Control Commands
## 1. List the permissions set for the file usdoi.txt that you downloaded to your project directory at the beginning of the lab.
```
theia@theia-quyduong106:/home/project/test$ cd /home/project
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-rw-r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
```

## 2. Revoke the write permission on usdoi.txt for the user, and verify your result.
```
theia@theia-quyduong106:/home/project$ chmod u-w  usdoi.txt
theia@theia-quyduong106:/home/project$ ls -l usdoi.txt
-r--r----- 1 theia users 8121 Sep 28  2022 usdoi.txt
```

## 3. What happens if you try to delete usdoi.txt after revoking write permissions for the user?
```
theia@theia-quyduong106:/home/project$ rm usdoi.txt
rm: remove write-protected regular file 'usdoi.txt'? y
theia@theia-quyduong106:/home/project$ ls usdoi.txt
ls: cannot access 'usdoi.txt': No such file or directory
```

## 4. Create a new directory called tmp_dir in your home directory.
```
theia@theia-quyduong106:/home/project$ mkdir tmp_dir
```

## 5. View the permissions of the newly created directory, tmp_dir.
```
theia@theia-quyduong106:/home/project$ ls -ld tmp_dir
drwxr-sr-x 2 theia users 4096 Sep 10 23:19 tmp_dir
```

## 6. Revoke the user write permission for tmp_dir.
```
theia@theia-quyduong106:/home/project$ chmod u-w tmp_dir
```

## 7. Check whether you can create a subdirectory of tmp_dir called sub_dir
```
theia@theia-quyduong106:/home/project$ mkdir tmp_dir/sub_dir
mkdir: cannot create directory ‘tmp_dir/sub_dir’: Permission denied
```