


## Commands to List Packages 
 #os/linux/commands/list-packages

| Command                                               | What does it do ?                                                                   |
| ----------------------------------------------------- | ----------------------------------------------------------------------------------- |
| sudo apt list <br>                                    | List all the packages from the sources.list                                         |
| sudo apt list \| grep installed                       | List only those packages that are Installed                                         |
| `apt list --installed \| grep -F \[installed\]`       | get a list of packages that resulted from user commands and their dependencies only |
| sudo apt remove packagename -y                        | Remove Package Name without confirmation                                            |
| `apt list --installed \| grep -F \[installed,local\]` |                                                                                     |
|                                                       |                                                                                     |
|                                                       |                                                                                     |
|                                                       |                                                                                     |
> List Only Local Installed Pkgs
```bash
apt list --installed | grep -F \[installed,local\]
```

---