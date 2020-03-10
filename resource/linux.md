# Some information for new Linux users

Switching from Windows to Linux, especially to the command terminal in a local or remote server, is propabily a painful experience for most people! But as long as you get familiar with some basic commands and skills, you'll find that Linux is actually easy to deal with and efficient for productivity.  Here I summarize some useful commands and tricks that are frequently used in Ubuntu Linux. Hopefully, they could help you to quickly adapt to the new interaction method.

<div style="text-align:center"><img src="1111.png" alt="Markdown Monster icon" align="center" width="500" /></div>

## Frequent commands for basic operations
 * List hardware information: lshw -short -c device, for example,
   - CPU: lshw -short -c processor
   - Hard Drive: lshw -short -c disk
   - Similarly, -c memory, -c display, -class network
   - devices could be combined to show together, e.g. lshw -short -c processor -c memory
 * Step into a folder: cd folder
   - Parental folder: cd ..
   - Your home folder: cd ~ 
   - Root folder: cd /
   - Show where am I: pwd
 * List contents of a folder: ls -option folder: 
   - Show permission of items in current folder: ls -l
   - Show file size in human readable unit (KB, MB, GB): ls -lh
   - Sort files according to size: ls -lS
 * Show size of a folder or file: du -sh file/folder
 * Create/Delete a file/folder: 
   - Create a folder: sudo mkdir foldername
   - Remove a file/folder: sudo rm -rf filename/foldername
 * Copy/move a file/folder to another place: cp/mv -options src dest 
   - Copy file to current folder: cp /foler/file .
   - Move file in current folder to other folder: mv file folder
   - For both commands, add -i option to show confirmation for existing file replacement
   - For both commands, add -R option for whole folder copy/move
  * Download a file from the Internet: wget http://www.xyz.com/file
  * Show CPU and RAM usage of each process: top (press shift+i to show percentage; press q to exit)
  * Show network flow: iftop (q to exit)
  * Show disk space: df -Th
  * Install/uninstall a application: sudo apt install/remove appname

## Tips for operating a sever remotely
* Connect to your remote sever: 
  - a) Install openssh on your server and start it;
  - b) Check your server IP by *ip -a* and write it down;
  - c) Open a terminal in you local machine and input the command: _ssh username@ip_, press _Enter_ and input your password. 
  - d) If login correctly, you should see the command prompt in the format _username@servername:~$_
* Transfer files from local windows to remote server: 
  - a) Install putty (https://www.putty.org/) on you local windows computer (ubuntu or Mac does not require it); 
  - b) Start transferring: pscp "D:\myfile.xyz" accountname@202.120.37.176:~/;
  - c) Replace pscp with scp if your local computer is Ubuntu or Mac
* Most data and code could be downloaded from the Internet, so you really don't have to transfer everything from you local computer to a remote server. Instead, you can obtain them by the command: 
  - a) Download a file: wget http://xyz.com/file 
  - b) Clone a git repository: git clone https://github.com/xyz/myrepo.git 
  
## Run/debug Python code on a remote server
* Run your python algorithm: 
  - a) Activate your conda environment by: conda activate base; 
  - b) Step into the folder containing your algorithm code; 
  - c) Run your algorithm by: python main.py.
* If your algorithm runs for a long time and you want to monitor it status frequently, you can write algorithm intermediate resuls to a file and check it each time after you login. Alternatively, you may use the "screen" command (search for a tutorial on internet).
* Before running your algorithm, you can use "nvidia-smi" (if with a GPU) to check GPU ocupation (right most column: 0% means free; otherwise busy); use "top" to check CPU usage.
* To debug your code remotely:
  - a) Open your source file with vi/vim by: vi file.py;
  - b) Set a break point by pdb.set_trace() (import the pdb package in your code file)
  - c) Run the algorithm and the execution will stop at the break point;
  - d) You can check variable value using print and other techniques;
  - e) Input n for one step execution; c for continue running; q to terminate debug process
  - f) To quit vim and return to the command input terminal, Press "Esc" and type ":q", then pressing "Enter".
 
Finally, you are welcome to contact me if you have any question.

