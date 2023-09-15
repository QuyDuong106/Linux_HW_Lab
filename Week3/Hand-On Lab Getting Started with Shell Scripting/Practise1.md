## 1. Create a script named greetnew.sh that takes the first and last names of the user, saves them in corresponding variables firstname and lastname, and prints a welcome message, such as "Hello <firstname> <lastname>".

1. Create a new file named greetnew.sh
2. Add to the file 
```
#! /bin/bash

# This script accepts the user\'s name and prints 
# a message greeting the user

# Print the prompt message on screen
echo -n "Enter your firstname :"	  	

# Wait for user to enter a name, and save the entered name into the variable \'name\'
read firstname				

# Print the prompt message on screen
echo -n "Enter your lastname :"	  	

# Wait for user to enter a name, and save the entered name into the variable \'name\'
read lastname	

# Print the welcome message followed by the name	
echo "Hello $firstname $lastname."
```
3. Save the file
4. Add execute permision 
```
theia@theia-quyduong106:/home/project$ chmod u+x greetnew.sh
```
5. Execute the file 
```
theia@theia-quyduong106:/home/project$ ./greetnew.sh
Enter your firstname :Quy
Enter your lastname :Duong
Hello Quy Duong.
```