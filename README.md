## Ubuntu
List package
```
$ dpkg -l | grep nvidia
```
Modify percentage critical
```
$ sudo gedit /etc/UPower/UPower.conf
```
Find package version
```
$ apt-cache madison <package-name>
```
Remove package
```
$ sudo apt-get purge 'nvidia.*'
$ sudo apt-get purge nvidia-*
```
Remove package on certain date
https://askubuntu.com/questions/548683/how-can-one-remove-all-packages-installed-after-a-certain-date-time
```
$ grep "2020-12-09.*.install " /var/log/dpkg.log | awk '{ print $4 }' | cut -d: -f1 | xargs sudo apt-get --yes purge
```
Remove permission
```
$ sudo chmod o+rx <filename>
```
Increase permission of hard-drive
```
$ sudo chown -R username:username /media/username/nameofdrive
```
Increase permission of folder
```
$ sudo chown -R 1000:1000 /home/username/folder
```
Change alias python to python3 (bashrc)
```
alias python=python3
```
7zip zip and split
```
$ 7z -v100m a my_zip.7z my_folder/
```
7zip extract (not flattened)
```
$ 7z x my_zip.7z.001
```
Change to English language
```
$ export LC_ALL=C 
```
Keyboard or mouse malfunction
```
$ sudo apt-get install xserver-xorg-input-all
```
## NVIDIA
Install nVidia driver
```
$ sudo add-apt-repository ppa:graphics-drivers/ppa
$ sudo apt update
$ sudo apt install nvidia-driver-440
```
Symlink CUDA
```
$ sudo ln -s /usr/local/cuda-10.0 /usr/local/cuda
```
NVIDIA activity
```
$ sudo pip3 install gpustat
$ watch -c gpustat -cp --color
```
or
```
$ watch -c nvidia-smi
```
Check CUDNN version
```
$ cat /usr/include/cudnn.h | grep CUDNN_MAJOR -A 2
```
## Darknet
Train
```
$ ./darknet detector train /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg ./darknet53.conv.74 -gpus 0,1 > /home/jeff/DARKNET/dataset/train.log
```
Test
```
$ ./darknet detector test /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg /home/jeff/DARKNET/dataset/darknet-yolov3_1000.weights /home/jeff/DARKNET/dataset/001.png
```
Resume
```
$ ./darknet detector train /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg /home/jeff/DARKNET/dataset/darknet-yolov3.backup > /home/jeff/DARKNET/dataset/train.log
```
## Jupyter
Install jupyter
```
$ sudo python3 -m pip install -U jupyter ipython
$ sudo reboot
```
Uninstall jupyter
```
$ python3 -m pip uninstall -y jupyter jupyter_core jupyter-client jupyter-console notebook qtconsole nbconvert nbformat ipython
```
## Github
View log
```
$ git log --oneline
```
Rebase (https://www.internalpointers.com/post/squash-commits-into-one-git)
```
$ git rebase --interactive 6394dc
Change pick to s, except the first one
$ git push origin HEAD -f
```
Checkout to a new branch
```
$ git checkout -b <branch-name>
```
Use a checkout
```
$ git checkout <commit-id-sha> 
```
Push to a branch
```
$ git push -u origin <branch-name>
```
Clone recursive
```
$ git clone --recursive ssh://XXXXXXXXXXXXXXXX
```
## Anaconda
View environment list
```
$ conda env list
```
Create environment based on .yml
```
$ conda env create -f environment.yml
```
Export to .yml
```
$ conda update ---all
$ conda env export --no-builds > env.yml
$ conda env create -f env.yml
```
Instal conda package
```
$ conda install <package-name>
$ conda install jpeg=9b
```
Uninstall conda
```
$ rm -rf ~/anaconda3
```
Add channel conda-forge
```
$ conda config --add channels conda-forge
$ conda config --set channel_priority strict
```
Install older Anaconda
```
$ conda install conda=4.6.14
```
Install older Python version
```
$ conda install python=3.6
```
## COCO
Install pycocotools
```
$ sudo python3 -m pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
```
## Docker
List active container
```
$ docker ps
```
List all container
```
$ docker ps -a-
```
Start container
```
$ docker start <name>
```
Stop container
```
$ docker stop <name>
```
Remove container
```
$ docker rm <name>
```
Remove all stopped container, images, and unused networks
```
$ docker system prune
```
Suicide
```
$ docker system prune -a
```
Commit to image
```
$ docker commit -m "<Message>" -a "<Author Name>" <container-id> <repository/image_name>
$ docker commit -m "added Node.js" -a "sammy" d9b100f2f636 sammy/ubuntu-nodejs 
```
Rename image
```
$ docker tag <container-id> <repository>/<image_name>
$ docker tag d583c3ac45fd myname/server:latest
```
Run bash
```
$ docker exec -it <container-id> bash
```
