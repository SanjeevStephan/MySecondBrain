#os/linux/basics 
![[index-of-linux-basics-for-hacker]]
### One of the most fundamental tasks in Linux—or any operating system—is adding and removing software.

| Command                | Description                                                                                                                                            |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| apt-get update         | search through all the packages on your system and check whether updates are available. If so, the updates are downloaded                              |
| apt-get upgrade -y     | upgrade every package on your system                                                                                                                   |
| apt-cache search snort | The apt tool has a search function that can check whether the package is available.                                                                    |
| apt-get install snort  | install a piece of software from your operating system’s default repository in the terminal                                                            |
| apt-get remove snort   | The remove command doesn’t remove the configuration files, which means you can reinstall the same package in the future without reconfiguring          |
| apt-get purge snort    | remove the configuration files at the same time as the package, you can use the purge option,                                                          |
| apt autoremove snort   | Now that you’re removing Snort, those other libraries or dependencies are<br><br>no longer required, so they can be removed by running apt autoremove. |