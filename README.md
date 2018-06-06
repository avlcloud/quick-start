# AVL GPU CLOUD QUICK-START

Login with your 4 digits ID (6210 is an example)
https://cn.portal.availink.com:6210/vnc.html

### Copy example "models" from /home/public folder to local
Right click mouse to "Open Terminal"
```bash
$ mkdir -p mygit
$ cp -r /home/public/tensorflow/models mygit/.
```

### Start avlcloud/tf-horovod docker
```bash
$ docker run -it --network=host --pid=host \
-v /home/public/tensorflow/tf.record:/home/ubuntu/tf.record \
-v $HOME/mygit:/home/ubuntu/mygit \
--name my-tf-horovod --rm --privileged \
avlcloud/tf-horovod:latest
```
you can save above in a run.sh file and run ./run.sh next time
### Run inference demo
Inside docker run
```bash
$ cd mygit/models/research/ ; source manual_set.sh ; cd object_detection
$ python3 object_detection_demo_image.py
```
![Alt text](image0_result_faster_rcnn_nas_coco_2017_11_08.png?raw=true "result")

### Run training
```bash
$ cd mygit/models/research/ ; source manual_set.sh ; cd object_detection
$ ./ssd_mobilenet_v1_coco_train.sh
```
