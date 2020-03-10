Switching from Windows to Linux, especially to the command terminal in a local or remote server, is propabily a painful experience for most people! But as long as you get familiar with some basic commands and skills, you'll find that Linux is actually easy to deal with and efficient for productivity.  Here I summarize some useful commands and tips that are frequently used in Ubuntu Linux. Hopefully, they could help you to quickly adapt to the new interaction method:
# Frequent commands for basic operations
 * List hardware information: lshw -short -c device, for example,
   - CPU: lshw -short -c processor
   - Hard Drive: lshw -short -c disk
   - Similarly, -c memory, -c display, -class network
 * Step into a folder: cd folder
   - Parental folder: cd ..
   - Your home folder: cd ~ 
   - Root folder: cd /
   - Show where am I: pwd
 * List contents of a folder: ls -option file/folder: 
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
   - For both commands, add -R option to for whole folder copy/move
  * Download a file from the Internet: wget http://www.xyz.com/file
  * Show CPU/RAM usage of each process: top (press q to exit)
  * Show network flow: iftop (q to exit)
  * Show disk space: df -Th
  * Install/uninstall a application: sudo apt install/remove appname

# Tips for operating a sever remotely
 * Transfer files from windows to your server folder: a) install putty (https://www.putty.org/) on you local windows computer (ubuntu or Mac does not require it); b) start transferring: pscp "D:\myfile.xyz" accountname@202.120.37.176:~/  (replace pscp with scp if your local computer is Ubuntu or Mac)
  * Run your python algorithm: a) activate base environment by: conda activate base; b)step into the folder containing your algorithm coder; c) run your algorithm by: python main.py
  * The base conda environment has installed tensorflow-gpu 2.1 and pytorch 1.4 (gpu enabled). If you need to use other version tensorflow or pytorch, you can tell me to install for you; or, alternatively, you can also install by yourself: a) create an environment in conda by: conda create --name myenv; b) conda activate myenv; c) conda install mypackage -y
  * Most data and code could be downloaded from internet, so you don't have to transfer everything from you local computer. You can download them by the command: wget http://xyz.com/file or git clone https://github.com/xyz/myrepo.git
  * If your algorithm runs for a long time and you want to monitor it status frequently, you can write algorithm intermediate resuls to a file and check it each time after you login. Alternatively, you may use the "screen" command (search for a tutorial on internet).
  * Before running your algorithm, use "nvidia-smi" to check if both GPU are occupied by others (right most column: 0% means free; otherwise busy).
  * To quit this vim file and return to the command input terminal, Press "Esc" and type ":q", then pressing "Enter"
  
# Skills for machine learners

