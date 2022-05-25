# Bash: Special Workflows

## Change Directory to the Path of Executable Easily
Sometimes, you want to inspect some executable. Instead of the normal way to
navigate the file system, here is the easy way to navigate to its directory:
```
cd $(which [EXECUTABLE_ON_PATH] | sed 's|\(.*\)/.*|\1|')
```
Alternatively, if you just want to edit the file, you can do so like this:
```
vi $(which [EXECUTABLE_ON_PATH])
```

## Running Background Process on SSH Machine + Leaving SSH W/O Killing Process
I have found that sometimes you want to run a process in the background on a
machine you are ssh'd into but then later you end up wanting to exit the ssh
session and want to keep the process running. Other cases might be that you are
AFK for some time and if your local machine goes "to sleep" then you might 
encounter a broken pipe, thus killing whatever process you were running on the
ssh machine.

To avoid this, we can do the following!
* SSH into the machine where the process will be run
* Start a tmux session
```
tmux
```
* Start the process
```
./foo > out.log &    #start foo in the background and redirect stdout to out.log
```
* Detach the tmux session `CTRL+A, d` or within tmux session run
```
tmux detach
```
* Exit SSH
* SSH back into the host machine and attach the tmux session
```
tmux attach
```
* Notice that the job is running inside of tmux, look with
```
jobs
```


## Related
[202110090443](../202110090443) - Shell Tips: Use 'bc' as a Calculator
[202111031844](../202111031844) - Working with Delimited Data
[202111011559](../202111011559) - ANSI Escapes and Colors


## Tags
#bash
