This is a collection of BadUSB scripts for Flipper Zero/Rubber Ducky(maybe) that are meant to automize the process of setting up ssh connection with root preveligies. Tested on ROSA-Fresh, in theory should work with all Fedora based distros.

INSTRUCTIONS

It's dead simple : 

1. Go into Grub (Hold shift while booting if it doesn't show up automagically)

2. Press E after you select your OS you want to hack.. I mean the one you forgot root password for.

3. In "linux" line change "ro" to "rw", and add "init=/bin/bash" after whatever options come after (quiet, splash, etc.)
eg. should look something like this : 
linux   /boot/vmlinuz-3.13.0-24-generic rw quiet splash init=/bin/bash root=UUID...

4. Now boot with Ctrl+X and dump "Hello_world!" payload

5. reboot and login as root user into DE. previous payload changed password to "pwnd"

6. open terminal and dump "Hello_world!_2" payload

7. exfiltrate ip address of the target. Pro tip : it is saved to "/ip_address.md" (Push the file onto a usb stick or something), if you are not familliar with linux, search for "inet" line under interface that has "state" "UP" in that file. Ignore backslash and everething after it on that line

8. Run "ssh root@<ip address>" on a remote machine in the same network (Shouldn't be a problem if target machine is on a school network or something like that)

9. Use your imagination! You've got remote root level access to a school computer!!! It *is* persistant between reboots, btw
