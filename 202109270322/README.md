# Exploring the Differences between *.bashrc* and *.profile*

### .bashrc
This file is used to load bash specific settings. All functions, aliases, and
prompt configurations exist in this file. Keep in mind that this is excecuted
for interactive non-login shells; it happens when a new terminal window is 
opened or a new bash instance occurs.

### .profile
This file is used to configure enivorment variables, including ```$PATH``` and
others. This is executed for login shells, or when you first login to the
machine (either via ssh or from the desktop). The purpose of this file is to
configure the shell before the initial command prompt. The *.bashrc* file is
sourced from *.profile*.

## Tags
#linux #bash
