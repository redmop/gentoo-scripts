# gentoo-scripts
These are  unmaintained as I've not used Gentoo in about 10 years.

# Dynamic DISTCC_HOSTS & MAKEOPTS Generation for Portage
This script will reside in /etc/portage/bashrc and will try to detect which computers are up (and with nmap installed, which are running distccd) 

This script does the following: 

Checks to see if distcc (and not -distcc) is in your features 
Reads in your /etc/distcc/hosts file 
Auto validates your localhost 
Pings any non-localhost in your /etc/distcc/hosts file 
If it gets a response and you have nmap installed, it checks to see if distccd is running on that computer (port 3632 default) 
Any validated host has it's /limit added to the MAKEOPTS=-j (it understands the defaults) 
Writes the valid hosts to your DISTCC_HOSTS variable 
Displays the variables DISTCC_HOSTS and MAKEOPTS 
Will run once each for each package right before it compiles. 
Automaticly finding of active DISTCC hosts (NEW)
