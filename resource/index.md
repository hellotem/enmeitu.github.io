---
layout: default
---
## Announcements
*  For SJTU students who want to participate researches on machine learning and artificial intelligence, please contact me directly with an email titled "SJTU Student Research".
* I am very happy to write a recommandation letter for students who attend my classes or take part into research activities in our lab. Please send me a copy of your transcript and CV (if you have one). 

## Major AI related conferences

Conference Name  | Submission Deadline | Conference Date |Conference Location 
----------------- | -------------| -------------|-------------
[ECCV-20](https://eccv2020.eu/)|Mar 05, 2020|Aug 23-28, 2020|Glasgow, UK
[NeurIPS-20](https://nips.cc/Conferences/2020)| May 05, 2020 (abstract)| Dec 2-8, 2020|Vancouver, Canada
[ICCV-21](https://www.thecvf.com/?page_id=100)|Mar, 2021(TBD)|Oct, 2021 (TBD)|Montreal, Canada
[SIGKDD-20](https://www.kdd.org/kdd2020/#!) | ~~Feb 13, 2020~~ | Aug 22, 2020 | San Diego, CA, USA
[ICML-20](https://icml.cc/Conferences/2020)| ~~Jan 30, 2020~~| Jul 12-18, 2020|Vienna, Austria
[IJCAI-20](http://www.ijcai20.org) | ~~Jan 21, 2020~~|Jul 11-17, 2020|Yokohama, Japan
[ACL-20](https://acl2020.org/)|~~Dec 09, 2019~~|Jul 5-10, 2020|Seattle, USA
[CVPR-20](http://cvpr2020.thecvf.com/) | ~~Nov 15, 2019~~|Jun 14-19, 2020|Seattle, USA
[ICLR-20](https://iclr.cc/) | ~~Sep 25,2019~~| Apr 26-30, 2020|Addis Ababa, Ethiopia
[AAAI-20](https://aaai.org/Conferences/AAAI-20/)| ~~Sep 05, 2019~~| Feb 07-12, 2020| New York, USA


## Best universities in China ([full ARWU ranking list](http://www.shanghairanking.com/Chinese_Universities_Rankings/Overall-Ranking-2019.html))

Rank | University Name | Location | Province
----- | ------------ | --------- | ----------
1	|Tsinghua University |	Beijing | Beijing
2	|Peking University	|Beijing | Beijing
3	|Zhejiang University	|Hangzhou | Zhejiang
4	|Shanghai Jiao Tong University|	Shanghai | Shanghai
5	|Fudan University	|Shanghai | Shanghai
6	|University of Science and Technology of China|	Hefei |Anhui
7	|Huazhong University of Science and Technology|	Wuhan | Hubei
7	|Nanjing University	|Nanjing | Jiangsu
9	|Sun Yat-Sen University	|Guangzhou | Guangdong
10	|Harbin Institute of Technology	|Harbin | Heilongjiang

#### Here is a [Map of China](https://www.chinadiscovery.com/china-maps/china-provincial-map.html) and a good [overview of China](https://www.chinadiscovery.com/travel-guide/facts.html)

## Useful commands/skills for linux 
  * List files in current folder: ls; step into a folder: cd folder; see the size of a file/folder: du -sh file/folder
  * Transfer files from windows to your server folder: a) install putty (https://www.putty.org/) on you local windows computer (ubuntu or Mac does not require it); b) start transferring: pscp "D:\myfile.xyz" accountname@202.120.37.176:~/  (replace pscp with scp if your local computer is Ubuntu or Mac)
  * Run your python algorithm: a) activate base environment by: conda activate base; b)step into the folder containing your algorithm coder; c) run your algorithm by: python main.py
  * The base conda environment has installed tensorflow-gpu 2.1 and pytorch 1.4 (gpu enabled). If you need to use other version tensorflow or pytorch, you can tell me to install for you; or, alternatively, you can also install by yourself: a) create an environment in conda by: conda create --name myenv; b) conda activate myenv; c) conda install mypackage -y
  * Most data and code could be downloaded from internet, so you don't have to transfer everything from you local computer. You can download them by the command: wget http://xyz.com/file or git clone https://github.com/xyz/myrepo.git
  * If your algorithm runs for a long time and you want to monitor it status frequently, you can write algorithm intermediate resuls to a file and check it each time after you login. Alternatively, you may use the "screen" command (search for a tutorial on internet).
  * Before running your algorithm, use "nvidia-smi" to check if both GPU are occupied by others (right most column: 0% means free; otherwise busy).
  * To quit this vim file and return to the command input terminal, Press "Esc" and type ":q", then pressing "Enter"

###### Updated on Mar 9, 2020

