#skills/scripting/python/get-started-with-python
## 1 | How to Install Python

To make sure that our versions are up-to-date, let’s update and upgrade the system with apt-get:

| sudo apt-get update     |
| ----------------------- |
| sudo apt-get -y upgrade |
> The -y flag will confirm that w
> e are agreeing for all items to be installed.

Once the process is complete, we can check the version of Python 3 that is installed in the system by typing:

| python3 -V |
| ---------- |
You will receive output in the terminal window that will let you know the version number.
```
# OUTPUT

┌──(cipher㉿watchdog)-[~]
└─$
python3 -V
Python 3.11.8

```



There are a few more packages and development tools to install to ensure that we have a robust set-up for our programming environment:

| `sudo apt-get install build-essential libssl-dev libffi-dev python-dev-is-python3` |
| ---------------------------------------------------------------------------------- |


| `pip install --upgrade pip` |
| --------------------------- |


Once Python is set up, and pip and other tools are installed, we can set up a virtual environment for our development projects on the next step .


## 2 | How to Install Python Packages 

To manage software packages for Python, let’s install pip

| sudo apt-get install -y python3-pip |
| ----------------------------------- |
You can install Python packages by typing:

| Syntax  | `pip3 install <package-name>` |
| ------- | ----------------------------- |
| Example | `pip3 install numpy`          |
Here, package_name can refer to any Python package or library, such as
* Django for web development
* NumPy for scientific computing

Once Python is set up, and pip and other tools are installed, we can set up a virtual environment for our development projects.

## 3 | How to Setup Virtual Environment



Virtual environments enable you to have an isolated space on your computer for Python projects, ensuring that each of your projects can have its own set of dependencies that won’t disrupt any of your other projects.

We need to first install the `venv` module, part of the standard Python 3 library, so that we can create virtual environments. Let’s install `venv` by typing:

| sudo apt-get install -y python3-venv |
| ------------------------------------ |
With this installed, we are ready to create environments


| STEPS   | WHAT TO DO                        | COMMAND                    |
| ------- | --------------------------------- | -------------------------- |
| STEP-01 | create a new directory with mkdir | `mkdir environment_test`   |
| STEP-02 | go inside the directory           | `cd environment_test`      |
| STEP-03 | create an environment by running  | `python3 -m venv <my_env>` |
| STEP-04 |                                   |                            |


```
                                                                                ┌──(cipher㉿watchdog)-[~/TEST/python101/test_env]
└─$ python3 -m venv first_python_env

┌──(cipher㉿watchdog)-[~/TEST/python101/test_env]
└─$ cd first_python_env    
```

Essentially, this sets up a new directory that contains a few items which we  # can view with the ls command
```
                                                                                ┌──(cipher㉿watchdog)-[~/TEST/python101/test_env/first_python_env]
└─$ ls   
bin  include  lib  lib64  pyvenv.cfg 
```

To use this environment, you need to activate it, which you can do by typing the following command that calls the `/bin/activate script.
[[how-to-code-in-python.pdf#page=25&selection=493,0,622,0|how-to-code-in-python, page 25]]

| STEP-04 | activate the environment | `source my_env/bin/activate` |
| ------- | ------------------------ | ---------------------------- |
|         |                          |                              |

> Your prompt will now be prefixed with the name of your environment, in this case it is called my_env. Your prefix may look somewhat different, but the name of your environment in parentheses should be the first thing you see on your line:.

```
                                            
┌──(first_python_env)─(cipher㉿watchdog)[~/python101/test_env/first_python_env]
└─$ 

```
This prefix lets us know that the environment `first_python_env` is currently active, meaning that when we create programs here they will use only this particular environment’s settings and packages.

[[how-to-code-in-python.pdf#page=25&selection=1111,0,1441,1|how-to-code-in-python, page 25]]
Note: Within the virtual environment, you can use the command python instead of python3, and pip instead of pip3 if you would prefer.
After following these steps, your virtual environment is ready to use.
## 4 | Understand Python Interactive Console


## 5 | Execute Your First Python Script

Now that we have our virtual environment set up, if you haven't then follow the steps from [[03-how-to-setup-virtual-environment]].
 let’s create a simple “Hello, World!” program. 

> STEP-01
> To do this, we’ll open up a command-line text editor such as nano and create a new file
```
                                            
┌──(first_python_env)─(cipher㉿watchdog)[~/python101/test_env/first_python_env]
└─$  nano helloworld.py

```
> STEP-02
> Once the text file opens up in the terminal window we’ll type out our program:
```
print("Hello, World!")
```
>STEP-03
>Exit nano by typing the `control` and `x` keys, and when prompted to save the file press `y`.


| STEP-04 | Execute the Python Code | `python helloworld.py` |
| ------- | ----------------------- | ---------------------- |
```                                           
┌──(first_python_env)─(cipher㉿watchdog)-[~/…/python101/first_python_env/script]
└─$ python helloworld.py 
Hello World,Python Programmer

```

To leave the environment, simply type the command deactivate and you will return to your original directory.


Let’s go over what the program did in more detail
* Python executed the line `print("Hello, World!") `by calling the print() function.
* The string value of `Hello, World! `was passed to the function.
* the string `Hello, World! `is also called an argument since it is a value that is passed to a function.


Congratulations! You have written the “Hello, World!” program in Python 3.

## 6 | List All Python Packages
# 

List all python packages installed in the linux os

To list all Python packages installed in the Linux OS, you can use the following methods:

**Method 1: Using pip list command**

You can use the `pip list` command to list all Python packages installed in the Linux OS. This command will list all packages installed globally.

```
pip list
```

**Method 2: Using pip list --local command**

If you want to list packages installed in a specific virtual environment, you can use the `pip list --local` command.

```
pip list --local
```

**Method 3: Using pip freeze command**

The `pip freeze` command can be used to list all packages installed in the Python environment, including those installed using pip and those installed using other package managers.

```
pip freeze
```

**Method 4: Using pip show command**

The `pip show` command can be used to list information about a specific package, including its version and location.

```
pip show <package_name>
```

**Method 5: Using Anaconda Navigator**

If you are using Anaconda, you can use the Anaconda Navigator to list all packages installed in your environment.

**Method 6: Using ActiveState Platform**

The ActiveState Platform provides a command-line interface (CLI) called the State Tool that can be used to list all installed packages.

```
state packages
```

**Method 7: Using Osquery and Kolide**

Osquery and Kolide can be used to enumerate Python packages across your fleet of devices.

**Note:** The above methods may list different packages depending on the Python environment and package manager used.
