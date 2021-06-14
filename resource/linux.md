**Preface:** This note is not a complete tutorial about Linux system. Rather, it is just a short reference for the lab students to run their algorithms on the MLKD-Server with a minimal requirement of Linux knowledge. An elegant tutorial of Unix/Linux system given by _Sean Kross_ can be found [HERE](https://github.com/hellotem/the-unix-workbench)

## Frequently used Linux commands
(Note: **bold** words mean commands and _italic_ words mean user specified terms)

 * List hardware information: **lshw -short -c** _device_, e.g.
   - CPU: lshw -short -c processor
   - Hard Drive: lshw -short -c disk
   - Similarly, -c memory, -c display, -class network
   - devices could be combined to show together, e.g. lshw -short -c processor -c memory
 * Step into a folder: **cd** _folder_, e.g.
   - Parental folder: cd ..
   - Your home folder: cd ~ or cd /home/_username_
   - Root folder: cd /
   - Show current path: pwd
 * List contents of a folder: **ls** -option _folder_, e.g.
   - List all by name: ls 
   - Show permission of items in current folder: ls -l
   - Show file size in human readable unit (KB, MB, GB): ls -lh
   - Sort files by size: ls -lS
 * Create/Delete a file/folder: 
   - Create a folder: **mkdir** _foldername_
   - Remove a file: **rm** _filename_
   - Remove a folder: **rm -rf** _foldername_
 * Copy/move a file/folder (src) to another place (dest): **cp/mv** -options _src dest_, e.g.
   - Copy a file to current folder: cp _/folder/file_ . (don't miss the dot ".")
   - Move a file in current folder to another folder: mv _file folder_
   - For both commands, add -i option to show confirmation for existing file replacement
   - For both commands, add -R option for whole folder copy/move
  * Show overall size of a folder or file: **du -sh** _file/folder_
  * Download a file from the Internet: **wget** _http://www.xyz.com/file_
  * Show CPU and RAM usage of each process: **top** (press shift+i to show percentage; press q to exit)
  * Show network flow: **iftop** (q to exit)
  * Show disk space: **df -Th**
  * Install/uninstall a application: sudo apt install/remove _appname_

## Run and debug Python codes
* Run a Python code file (e.g. main.py): python main.py
* Create/Edit a Python code file with Vim Editor:
  - Open/create a Python code file: vim main.py (install vim first by the command **sudo apt install vim**)
  - Use left, right, up and down arrows (or page up and page down) to navigate through you code file
  - To input/change code: first press button "i" to enter edit mode, so the vim will accept keyboard inputs normally.
  - To save changes and quit Vim: first press "Esc" to quit edit mode, then type :wq and press "Enter" (":" means command, "w" means write and "q" means quit)
* Debug a Python code file:
  - Import the python debugging package in your python code file by "import pdb"
  - Insert a new line "pdb.set_trace()" just before the line where you want to stop to debug
  - Run your python file and it will stop executing at the line you just added.
  - Check you variables' value and state by inputing their name, input "q" and press "Enter" to quit debugging mode
 
  
## Python packages/environments management
"Conda is an open-source, cross-platform, language-agnostic package manager and environment management system. " -- from Wikipedia. 

With conda, you can quickly create a virtual environment and install specific version packages for your different python algorithms. A virtual environment is an isolated configuration that is usually not visible in system scope. So, you can safely install/manage different versions of a python package (e.g. python 2.x and python 3.x) and make them co-exist in a system without interfering with each other (e.g. you want to run several python algorithms simultaneously but each of them needs a different version of python).

* Install miniconda: [https://conda.io/projects/conda/en/latest/user-guide/install/linux.html](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html)

* Environment management:
  - a) Create an environment: **conda create --name** _envname_
  - b) Activate (to enter) an environment: **conda activate** _envname_
  - c) List all existing environments: **conda env list**
  - d) Delete an environment: **conda env remove --name** _envname_

* Package management: 
  - a) Install a package: **conda install** _pkgname==version_
  - b) List installed packages: **conda list** 
  - c) Remove a package: **conda remove** _pkgname_
  - d) Search all available versions of a package: **conda search** _pkgname_
  

## Remote Linux server connection and data transferring
* Connect to your remote sever via ssh: 
  - a) Install openssh on your server and start it;
  - b) Check your server IP by **ip -a** and write it down;
  - c) Open a terminal in you local machine and input the command: **ssh** _username@ip_, press "Enter" and input your password (you may need to set forward rules if your sever is behind a router). 
  - d) If login correctly, you should see the command prompt in the format "username@servername:~$"
* Transfer files between local computer and remote server: 
  - a) Install [putty] (https://www.putty.org/) on you local Windows computer (local Linux or Mac does not require it); 
  - b) Local -> server: **pscp** -option _local_file_path username@ip:server_file_path_
  - c) Server -> local: **pscp** -option _usename@ip:server_file_path local_file_path_
  - c) Replace **pscp** with **scp** if your local computer is Linux or Mac (be aware of the path name difference! Windows uses '\' while Linux and Mac use '/')
  - d) Use -r option for whole a folder transfer
* Most data and code could be downloaded from the Internet, so you really don't have to transfer everything from you local computer to the remote server. Instead, you can obtain them by: 
  - a) Downloading a file: **wget** _https://www.xyz.com/file_ 
  - b) Cloning a git repository: **git clone** _https://github.com/xyz/myrepo.git_ 
  

## Run/debug Python code on a remote server
* Run your Python code in a conda environment: 
  - a) Log into your remote server via ssh (see the above section for howto)
  - b) Activate your conda environment by: **conda activate** _envname_; 
  - c) Step into the folder containing your algorithm code; 
  - d) Run your algorithm by: **python** _main.py_.
* If your algorithm runs for a long time and you want to monitor it status frequently, you can write algorithm intermediate resuls to a file and check it each time after you login. Alternatively, you may use the friendly **_screen_** command (search on the Internet for a tutorial, pls!).
* Before running your algorithm, you can use **nvidia-smi** to check GPU ocupation (right most column: 0% means free; otherwise being busy); use **top** to check CPU usage (press q to quit). Make sure no GPU/CPU usage conflict.
* To debug your Python code remotely:
  - a) Open your source file with vi/vim by: **vim** _file.py_;
  - b) Navigate to target line and setup a break point by **pdb.set_trace()**. Save and Exit (Press "Esc"; type ":wq"; press "Enter");
  - c) Run the algorithm again. Execution will stop at the break point;
  - d) Check variable value using print;run the target expression to find out errors; other debugging techniques...
  - e) Input "n" for one step execution; "c" to continue running; "q" to terminate debug process
 
Finally, you are welcome to contact me if you have any question.

