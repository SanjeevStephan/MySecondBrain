![[index-of-linux-basics-for-hacker]]

## Create Your First Script : Hello World

### SCRIPT-01 | Hello-World.sh ( Your 1st Script )

| STEPS   | COMMAND               | WHAT DOES IT DO ?                                           |
| ------- | --------------------- | ----------------------------------------------------------- |
| Step-01 | touch `helloworld.sh` | Creates a new Bash Script.                                  |
| Step-02 | nano `helloworld.sh`  | Open the Text-File in Terminal Text-Editor                  |
| Step-03 | Type `#! /bin/bash`   | Add this line to let the bash compiler that it is a script. |
| Step-04 | Type `# Comment`      | Anything Typed After `#` will not be executed by shell.     |
| Step-05 | Type `echo type-msg`  | `echo` will print message on the Screen.                    |


```bash
#! /bin/bash
# This is a Comment 

echo "Hello,World!"

```

## Setting Execute Permissions
By default, a newly created bash script is not executable even by you,even the owner.

| Step-06 | ls -l | List the Files and their permissions |
| ------- | ----- | ------------------------------------ |
You should see something like this below.
```bash
┌──(cipher㉿watchdog)-[/tmp/TEST]
└─$ ls -l
total 0
-rw-r--r-- 1 cipher cipher 0 Jun 21 13:20 helloworld.sh

```

> As you can see, our new file has rw-r--r-- (644) permissions. As you learned in Chapter 5, this means the owner of this file only has read (r) and write (w) permissions, but no execute (x) permissions. The group and all other users have only read permissions. We need to give ourselves exe- cute permissions in order to run this script. 


| Step-07 | chmod u+x `helloworld.sh` | This gives the owner executable permissions |
| ------- | ------------------------- | ------------------------------------------- |
Now when we do a long listing on the file, like so, we can see that we have execute permissions
```bash
┌──(cipher㉿watchdog)-[/tmp/TEST]
└─$ ls -l
total 0
-rwxr--r-- 1 cipher cipher 61 Jun 21 13:22 helloworld.sh

```

The file will also be in green, another indicator of its execute permissions. The script is now ready to run.

| Step-08 | `./helloworld.sh` | This will execute the Script that you just created |
| ------- | ----------------- | -------------------------------------------------- |
```bash
./helloworld.sh
Hello WOrld
```
> Success! You just Completed your first shell script!


## Adding Functionality with Variable & User-Input
So, now we have a simple script. All it does is echo back a message to stan- dard output. If we want to create more advanced scripts, we will likely need to add some variables.


| _Variable_ | A variable is an area of storage that can hold something in memory |
| ---------- | ------------------------------------------------------------------ |
* That “something” might be some letters or words (strings) or numbers. 
* It’s known as a variable because the values held within it are changeable; this is an extremely useful feature for adding functionality to a script.

### SCRIPT-02 | welcome-script.sh (Display Input on the Screen)

| TASKS   | WHAT TO DO ?                                        |
| ------- | --------------------------------------------------- |
| Task-01 | add functionality to prompt the user for their name |
| Task-02 | place whatever they input into a variable           |
| Task-03 |  echo a welcome message that includes their name    |
Create a new file in your text editor and follow the Steps as below.

| STEPS   | COMMAND                      | WHAT DOES IT DO ?                                                                                |
| ------- | ---------------------------- | ------------------------------------------------------------------------------------------------ |
| Step-01 | touch `hellouser.sh`         | Creates a new Bash Script named ( `"hellouser.sh"`)                                              |
| Step-02 | nano `helloworld.sh`         | Open the Text-File in Terminal Text-Editor                                                       |
| Step-03 | `#! /bin/bash`               | Add this line to let the system to know that we want to use the bash interpreter for this script |
| Step-04 | `# Comment`                  | Anything Typed After `#` will not be executed by shell.                                          |
| Step-05 | `echo "What is Your Name ?"` | This `echo` will ask the user for the name                                                       |
| Step-06 | `read name`                  | Type Your-Name and Hit Enter-Key                                                                 |
| Step-07 | `echo "Welcome $name !`      | This Line will Welcome you along with your-name                                                  |

> Here is the Complete Script.
```bash
#! /bin/bash
# This is your second bash script.
# In this one, you prompt the user for input,place the input in a variable, and
# Display the variable contetns in a String.

echo "What is your name! User ? : "
read name

echo "Welcome User!, $name"

```

