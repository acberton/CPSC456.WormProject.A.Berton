# CPSC456 Assignment 2: Python Worm

#### Programmer(s): Anthony Berton
<br>

---
<br>

## How to Implement:
First, select a Linux VM to run worm.py on. Then open a terminal on the VM. </br>

In the terminal, go to the directory of your worm.py file and execute the infection by running the file

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*python worm.py*

If the program executes correctly, the hosts of the other two VMs should recieve the infection.</br>
Open the other two VMs and open terminals in both of them. </br>
Check to see if the hosts are infected by entering the following command in both terminals

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*hostname -I; ls /tmp*

If the worm.py program executed correctly in the first VM, then all the infected hosts should have the /tmp/infected.txt and /tmp/worm.py in the hostname list. 

## Extra Credit?:
