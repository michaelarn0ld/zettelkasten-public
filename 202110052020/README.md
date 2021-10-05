# Changing File Permissions
```bash
chmod [ugoa] [+-] [rwx]
```
|    Option     |    Summary                                                   |
|    :-:        |    -                                                         |
|    u          |    access changed for user who owns the file                 |
|    g          |    access changed for other users in the file's group        |
|    o          |    access changed for users outside the file's group         |
|    a          |    access changed for all users (default in no option given) |

|    Mode       |    Summary                                                   |
|    :-:        |    -                                                         |
|    +          |    adds the specified permissions                            |
|    -          |    removes the specified permissions                         |

|    Permission |    Summary                                                   |
|    :-:        |    -                                                         |
|    r          |    reading permissions                                       |
|    w          |    writing permissions                                       |
|    x          |    excecutable permissions                                   |


## Related
[202110051756](../202110051756) - Create and Manage Users and Groups


## Tags
#linux #sysadmin
