# Create and Manage Users and Groups
See ```man``` for any questions on these system admin tools.


## Pure Basics
```bash
adduser or useradd [USERNAME]                # to create user
su - [USERNAME]                              # to "login" as user
deluser or userdel [USERNAME]                # to delete user
usermod [OPTIONS] [ARGS...] [USERNAME]       # to modify user settings
chown [OPTIONS] [OWNER:GROUP] [ARGS...]      # to change file owner/group
```


## Common Things
```bash
usermod -s /path/to/shell [USERNAME]         # changes default shell of user
chown -r [OWNER:GROUP] [ARGS...]             # changes owner/group recursively
usermod -a -G [GROUP] [USERNAME]             # adds a user to a group
ls -l                                        # see permissions of files
```

* ```adduser``` makes adding users much simpler than ```useradd```
* ```userdel``` makes deleting users much simpler than ```deluser```


## Related
[202110050353](../202110050353) - Exploring Links (ln) in Linux
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr


## Tags
#linux #sysadmin
