# Linux: File Descriptors, Memory, and More!

## Awesome Commands and the TLDR
* `lsof [option] [args]` - gives the information to find out the files which are
   opened by which process
* `ps [options]` - ps command is used to list the currently running processes
   and their PIDs along with some other information depends on different options.
* `pmap [options] pid [...]` - gets the memory map of a process
* `grep MemTotal /proc/meminfo` - gets the total amount of memory on your system
* `top` - command is used to show the Linux processes. It provides a dynamic
   real-time view of the running system
* `docker stats [options] [container...]` - command returns a live data stream for
   running containers. To limit data to one or more specific containers, specify
   a list of container names or ids separated by a space. 


## Useful & Specific Examples
* `ps aux` - great way to view processes
* `pmap <PID> | tail -n 1` - get total memory consumed by a process
* `lsof -p <PID> | wc -l` - number of all files for a specific process
* `lsof -a -K -p <PID> | wc -l` - number of all files (including child processes)
* `ps -p 17 -o pid,user,vsz,rss,...` - display these columns only for pid 17


## Difference between RSS and VSZ
RSS is the Resident Set Size and is used to show how much memory is allocated to
that process and is in RAM. It does not include memory that is swapped out. It
does include memory from shared libraries as long as the pages from those
libraries are actually in memory. It does include all stack and heap memory.

VSZ is the Virtual Memory Size. It includes all memory that the process can
access, including memory that is swapped out, memory that is allocated, but not
used, and memory that is from shared libraries.


## Related
[202109270322](../202109270322) - Exploring the Differences between *.bashrc* and *.profile* \
[202110050353](../202110050353) - Exploring Links (ln) in Linux \
[202110050602](../202110050602) - Understanding Stdin, Stdout, Stderr \
[202110051756](../202110051756) - Create and Manage Users and Groups \
[202110052020](../202110052020) - Changing File Permissions \
[202110062225](../202110062225) - Shell Scripting, Interpretting, and Running Processes


## Tags
#linux
