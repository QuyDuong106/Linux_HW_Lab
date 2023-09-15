# Using conditional statements and logical operators
## 1.1. Create a new Bash script
```
theia@theia-quyduong106:/home/project$ echo '#!/bin/bash' > conditional_script.sh
theia@theia-quyduong106:/home/project$ chmod u+x conditional_script.sh
```

```
![Alt text](image.png)
```

```
theia@theia-quyduong106:/home/project$ ./conditional_script.sh 
Are you enjoying this course so far?
Enter "y" for yes, "n" for no.y
I'm pleased to hear you are enjoying the course!
Your feedback regarding what you have been enjoying would be most welcome!

theia@theia-quyduong106:/home/project$ ./conditional_script.sh 
Are you enjoying this course so far?
Enter "y" for yes, "n" for no.n
I'm sorry to hear you are not enjoying the course.
Your feedback regarding what we can do to improve the learning experience
for this course would be greatly appreciated!
```