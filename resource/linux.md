 # Here are some useful commands and tips for a new user to the Linux system
 * List hardware information: lshw -short -c device, for example,
   - CPU: lshw -short -c processor
   - Hard Drive: lshw -short -c disk
 * List contents of a folder: ls -option file/folder: 
   - show permission of items in current folder: ls -l
   - show file size: ls -lh
   
 
 ; step into a folder: cd folder; see the size of a file/folder: du -sh file/folder
 * Transfer files from windows to your server folder: a) install putty (https://www.putty.org/) on you local windows computer (ubuntu or Mac does not require it); b) start transferring: pscp "D:\myfile.xyz" accountname@202.120.37.176:~/  (replace pscp with scp if your local computer is Ubuntu or Mac)
  * Run your python algorithm: a) activate base environment by: conda activate base; b)step into the folder containing your algorithm coder; c) run your algorithm by: python main.py
  * The base conda environment has installed tensorflow-gpu 2.1 and pytorch 1.4 (gpu enabled). If you need to use other version tensorflow or pytorch, you can tell me to install for you; or, alternatively, you can also install by yourself: a) create an environment in conda by: conda create --name myenv; b) conda activate myenv; c) conda install mypackage -y
  * Most data and code could be downloaded from internet, so you don't have to transfer everything from you local computer. You can download them by the command: wget http://xyz.com/file or git clone https://github.com/xyz/myrepo.git
  * If your algorithm runs for a long time and you want to monitor it status frequently, you can write algorithm intermediate resuls to a file and check it each time after you login. Alternatively, you may use the "screen" command (search for a tutorial on internet).
  * Before running your algorithm, use "nvidia-smi" to check if both GPU are occupied by others (right most column: 0% means free; otherwise busy).
  * To quit this vim file and return to the command input terminal, Press "Esc" and type ":q", then pressing "Enter"
