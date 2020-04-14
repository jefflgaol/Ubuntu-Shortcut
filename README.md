## Ubuntu
List package
```
$ dpkg -l | grep nvidia
```
Remove package
```
$ sudo apt-get purge 'nvidia.*'
$ sudo apt-get purge nvidia-*
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
Synaptic
```
$ synaptic-pkexec
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
```
## Github
View log
```
$ git log --oneline
```
Rebase
```
https://www.internalpointers.com/post/squash-commits-into-one-git
$ git rebase --interactive 6394dc
Change pick to s, except the first one
$ git push origin HEAD -f
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
