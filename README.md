## Ubuntu
List package
```
$ dpkg -l | grep nvidia
```
Remove package
```
$ sudo apt-get purge 'nvidia.*'
```
Remove permission
```
$ sudo chmod o+rx <filename>
```
Increase permission of hard-drive
```
$ sudo chown -R username:username /media/username/nameofdrive
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
