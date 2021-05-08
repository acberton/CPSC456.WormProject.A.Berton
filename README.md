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

**Note:** If you want to execute a cleanup process on the infected hosts, run the worm.py file and include either "-c" or "--clean"

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*python worm.py -c &nbsp;&nbsp;&nbsp; OR &nbsp;&nbsp;&nbsp; python worm.py --clean*

## Extra Credit:

### EC1: Cleaner function
I implemented a function for cleaning the worm infection off of the hosts called CleanUp(sshClient). The function operates similarly to the SpreadAndExecute(sshClient)
function in that they both pass an sshClient parameter and use it to initiate a file transfer object for either sending or removing files from the hosts. The clean up
function removes the "/tmp/worm.py" and "/tmp/infected.txt" files from infected hosts.
