## Ubuntu
```
$ dpkg -l | grep nvidia
$ sudo apt-get purge 'nvidia.*'
```

## Darknet
```
$ ./darknet detector train /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg ./darknet53.conv.74 -gpus 0,1 > /home/jeff/DARKNET/dataset/train.log
$ ./darknet detector test /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg /home/jeff/DARKNET/dataset/darknet-yolov3_1000.weights /home/jeff/DARKNET/dataset/001.png
$ ./darknet detector train /home/jeff/DARKNET/dataset/darknet.data /home/jeff/DARKNET/dataset/darknet-yolov3.cfg /home/jeff/DARKNET/dataset/darknet-yolov3.backup > /home/jeff/DARKNET/dataset/train.log
```
## Jupyter
```
$ sudo python3 -m pip install -U jupyter ipython
```
## Github
```
$ git log --oneline

https://www.internalpointers.com/post/squash-commits-into-one-git
$ git rebase --interactive 6394dc
Change pick to s, except the first one
$ git push origin HEAD -f
```
