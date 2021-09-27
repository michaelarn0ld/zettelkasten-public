# Configuring Intel 6E AX210 WiFi Card (Ubuntu 20.04 Kernel 5.11.0)

After building my machine this week, I was having trouble getting the MOBO's
on-board wifi to function with Linux. I ran the following commands to debug:
```
lshw -C network
```
The output here clearly showed the hardware was recognized and the drivers came
installed already. This was confusing, however, because I was getting the 
infamous "No WiFi adapter detected!" message from ubuntu. Further troubleshooting
led me to run this command:
```
dmesg | grep iwlwifi
```
Reading the log uncovered the error "Timeout waiting for PNVM load!". I
investigated and found a very helpful form [here](https://bugzilla.kernel.org/show_bug.cgi?id=212371). 
The solution turned out to be a temporary fix, but it will have to work until a
better option comes around:
```
mv ~/lib/firmware/iwlwifi-ty-a0-gf-a0.pnvm ~/lib/firmware/iwlwifi-ty-a0-gf-a0_rename.pnvm
```
Simply, just rename the file. Restoring to its original brings back the bug. 
Apparently, the current firmare is not compatible with this PNVM. Removing the 
file was also an option; however, I kept it in case a future solution demands that
I have the file.
#### TEST
## Tags
#linux #firmware
