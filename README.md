# CPSC456 Assignment 2: Python Worm

#### Programmer(s): Anthony Berton
#### Python version: 3.7
#### Extra Credit Implemented: Yes
#### Important note: When I ran the code, I had to change the code to remove the index '[0]' on sshInfo in the spreadAndeExecute() and CleanUp() function calls in line 314 and line 322 of my code. When I ran it as it was initially, I recieved an error message stating that SSHClient does not accept indexing
<br>

---
<br>

## How to Implement:
First, select a Linux VM to run worm.py on. Then open a terminal on the VM. </br>

Once you open your terminal, copy the worm.py file to the /tmp directory

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*cp <worm.py_path> /tmp*

Next, go to the directory of your worm.py file and execute the infection by running the file

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*python /tmp/worm.py*

If the program executes correctly, the hosts of the other two VMs should recieve the infection.</br>
Open the other VMs and open terminals in both of them. </br>
Check to see if the hosts are infected by entering the following command in both terminals

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*hostname -I; ls /tmp*

If the worm.py program executed correctly in the first VM, then all the infected hosts should have the /tmp/infected.txt and /tmp/worm.py in the hostname list.

**Note:** If you want to execute a cleanup process on the infected hosts, run the worm.py file and include either "-c" or "--clean"

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*python /tmp/worm.py -c &nbsp;&nbsp;&nbsp; OR &nbsp;&nbsp;&nbsp; python /tmp/worm.py --clean*

**Note:** If you want to spread the worm infection to hosts outside of your current network domain, run the worm.py file and include either "-m" or "--multi"

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*python /tmp/worm.py -m &nbsp;&nbsp;&nbsp; OR &nbsp;&nbsp;&nbsp; python /tmp/worm.py --multi*

## Extra Credit:

### EC1: Cleaner function
I implemented a function for cleaning the worm infection off of the hosts called CleanUp(sshClient). The function operates similarly to the SpreadAndExecute(sshClient) function in that they both pass an sshClient parameter and use it to initiate a file transfer object for either sending or removing files from the hosts. The clean up function removes the "/tmp/worm.py" and "/tmp/infected.txt" files from infected hosts.

### EC2: Multi-spreading operation
The multi-spread will spread the worm infection to hosts in the other network domain in the GNS3 topology. The multi-spread will operate in the getHostsOnTheSameNetwork() function where the port scanning takes place. If the user requests a multi-spread, then the program will scan for hosts in the "10.0.1.0/24" network like it does for the "10.0.0.0/24 network. The program will then add the scanned hosts from both networks onto the liveHosts list.
